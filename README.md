# Album Collection Application - ICE Task 3

## 1. Introduction
The Album Collection application is a React Native mobile application built using Expo and TypeScript[cite: 1, 2]. It allows music enthusiasts to record, track, and manage their favorite albums by inputting key details such as title, artist, release year, genre, and a rating, while supporting validation rules and persistent list rendering[cite: 1, 2].

## 2. Development Environment
* **Framework:** React Native / Expo[cite: 1, 2]
* **Language:** TypeScript[cite: 1, 2]
* **Testing Emulator:** BlueStacks 5 (using Expo Go)[cite: 1, 2]
* **Development Tool:** Visual Studio Code[cite: 1, 2]

## 3. Error Log

| # | Location | Problem | Error Type | Description of your correction |
|---|---|---|---|---|
| 1 | `handleSave` | `setAlbums([temporaryAlbum])` overwrote the entire array instead of appending items. | Logic / State Management | Replaced it with spread syntax `[...currentAlbums, temporaryAlbum]` so that existing albums remain when a new one is added. |
| 2 | `handleDelete` | Filter condition `album.id === id` kept *only* the deleted item. | Logic / Array Filtering | Changed the condition to `album.id !== id` to correctly filter out the target album while keeping the rest of the collection. |
| 3 | `Picker` component | Picker was bound to `title` and item values were hardcoded to `{genre}`. | UI Binding | Updated `selectedValue` to `genre` and set item values to `{item}` to correctly capture user selections. |
| 4 | `FlatList` | `keyExtractor` used `item.title`, which causes key collisions if duplicate titles exist. | Performance / Rendering | Changed `keyExtractor` to target `item.id` to guarantee unique keys. |

## 4. Testing
The application was tested inside the BlueStacks 5 emulator using Expo Go[cite: 1, 2] with the following scenarios:
* **Initial Launch:** The application loaded successfully with no unexpected errors, presenting empty list messaging[cite: 1, 2].
* **Invalid Input Validation:** Attempting to submit blank fields or incorrect years/ratings triggered alert warnings and successfully prevented submission[cite: 1, 2].
* **Valid Album Submission:** Entering valid credentials added the album to the list cleanly[cite: 1, 2].
* **Multiple Albums:** Adding multiple distinct albums confirmed that state updates properly and all entries remain visible in the collection[cite: 1, 2].
* **Deletion:** Clicking the delete button on an album successfully removed that entry while leaving the rest of the collection fully functional[cite: 1, 2].

## 5. Screenshot
*(Include your emulator screenshot showing the completed Album Collection app running here)*[cite: 1, 2]

## 6. Conclusion
Investigating and debugging this React Native application highlighted the critical importance of careful state management, accurate array mutation handling, and precise data binding in TypeScript[cite: 1, 2]. Fixing these intentional errors ensured that form validations, list collection updates, and deletions execute reliably and provide a smooth user experience[cite: 1, 2].
