# Zelda TOTK Recall Mechanic

### Overview

Inspired by the Recall ability from The Legend of Zelda: Tears of the Kingdom, I developed a mechanic that allows for objects affected by physics to be reversed. This system tracks the movements of physics objects every frame and enables them to revert to their previous positions upon activation.

All objects tagged with a specific physics tag have their movements continuously tracked, and measures are in place to optimize memory usage to prevent excessive resource consumption. When activated, the scene transitions to greyscale, and a yellow highlight appears around the affected object. The object then begins to revert to its original position, and the ability deactivates once the object reaches its starting location, returning everything to normal.

### Development & Features

The project was developed on Roblox and their Luau programming language. Key milestones included:

- **Physics Tracking**: Tagged physics objects are tracked every frame, and their movement is recorded to enable the reverse mechanic.
- **Memory Optimization**: Implemented measures to ensure efficient use of memory, preventing excessive data storage and ensuring smooth gameplay.
- **Visual Effects**: The scene turns greyscale with a yellow highlight on the affected object to indicate the ability’s activation.
- **Object Reversal**: When the ability is activated, the object’s movement is reversed, and it returns to its original position.
- **Deactivation**: Once the object reaches its earliest position, the ability deactivates, and the scene returns to normal.

### Real-World Applications

This mechanic was developed as a side project to learn new techniques and approaches inspired by proven game mechanics. While it’s not currently being used in any of my projects, the Recall ability serves as a valuable learning experience for working with physics-based interactions and memory management.

### Demonstration

Recall ability on a single ball with only vertical movements.

![Recall-Demo-Ball](https://github.com/user-attachments/assets/5a026234-b36b-4a90-9897-be2ade5a7e14)

Recall ability on two varying object shapes falling down a slope.

![Recall-Demo-Slope](https://github.com/user-attachments/assets/6796a059-cc81-4a3b-a2b0-7dc41a95b618)

### Challenges & Learnings
The main challenge was finding a way to track each rewindable object efficiently. Naturally, this is very expensive on memory as new entires could be created after each frame. This was optimized through only keeping track of changes in rotation and speed. Another challenge was keeping track of the limited history. Since history would only be tracked for a couple of seconds, it was important to clean out frames that are considred expired. This was resolved through LinkedList, which made removing earlier entires take O(1) time.
