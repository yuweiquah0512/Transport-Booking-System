# Transport Booking System

This is a Java AWT/Applet project for a simple transport booking system. It lets users register, log in, create transport bookings, pay for bookings, view saved bookings, and manage basic profile details such as username, password, and phone numbers.

## Project Features

- User registration and login
- Booking for Bus, Train, and Ferry transport
- Destination selection with fixed prices
- Date and time validation
- Payment method selection
- Saved booking history
- User profile management
- Phone number add/delete support

## Project Files

| File | Purpose |
| --- | --- |
| `TransportBookingSystem.java` | Main applet class. Builds the user interface and controls the booking flow. |
| `Booking.java` | Booking data model. Stores booking details and payment status. |
| `UserManager.java` | Handles registration, login, and user lookup. |
| `UserProfileManager.java` | Handles profile updates such as username, password, and phone numbers. |
| `view.html` | Applet launcher page used by `appletviewer`. |
| `java.policy` | Java security policy for allowing local file access. |

## Requirements

This project uses Java Applet technology, which is no longer supported by modern web browsers and is not included with many newer JDK tools.

Recommended setup:

- JDK 8
- `appletviewer`, which is included with older JDK versions such as JDK 8

Modern JDKs can still compile the code in some environments, but they may not include a way to run the applet.

## How to Compile

Open a terminal or command prompt in this folder and run:

```bash
javac *.java
```

This creates `.class` files for the Java source files.

## How to Run

If you have JDK 8 or another JDK that includes `appletviewer`, run:

```bash
appletviewer -J-Djava.security.policy=java.policy view.html
```

The applet window should open with the login screen.

## How to Use the System

1. Start the applet.
2. Enter a username and password.
3. Click `Register` if this is a new account.
4. Click `Login` after registering or if the account already exists.
5. Choose a transport mode, destination, date, and time.
6. Click `Proceed`.
7. Review the booking details.
8. Choose a payment method and enter payment details.
9. Click `Confirm and Pay`.
10. Use `View Bookings` to see saved bookings.
11. Use `User Profile` to change username/password or manage phone numbers.

## Data Files Created at Runtime

The application creates and updates these files in the same folder:

| File | Purpose |
| --- | --- |
| `users.txt` | Stores registered usernames, passwords, and phone numbers. |
| `bookings.dat` | Stores booking records. |

These files are generated automatically when the program runs. If you delete them, the application will start with no saved users or bookings.

## Input Formats

- Date must use `YYYY-MM-DD`, for example `2026-10-04`.
- Time must use `HH:MM`, for example `14:30`.
- Phone numbers must contain digits only and must be 11 digits or fewer.

## Troubleshooting

### `appletviewer` is not recognized

Your installed JDK probably does not include Applet tools. Install and use JDK 8, then make sure its `bin` folder is added to your system `PATH`.

### Browser does not open the applet

Modern browsers no longer support Java Applets. Use `appletviewer` instead of opening `view.html` directly in a browser.

### User or booking data is not saved

Make sure the folder is writable and run the applet with the included `java.policy` file.

### Compilation shows an Applet warning

This is expected on newer Java versions because Applet support is deprecated or removed. The project was written for older Java Applet environments.

## Notes for Developers

- The main entry point is `TransportBookingSystem`.
- Destination prices are defined in `initializePrices()` inside `TransportBookingSystem.java`.
- Bookings are serialized using Java object serialization in `bookings.dat`.
- User details are stored as comma-separated text in `users.txt`.
- Passwords are stored as plain text because this is a learning project. Do not use this storage approach in a real production system.
