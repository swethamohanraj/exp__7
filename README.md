# EXP 07 - AI CHASING AI PLAYER

## AIM:
To implement-chasing when AI see the player.

## ALGORITHM: 

#### STEP 1: Set up the AI character Blueprint:

* Create an AI character Blueprint (if you haven't already) following the steps
mentioned earlier.
* Add a Sphere Collision component to the AI character Blueprint.
* Position and scale the Sphere Collision component to represent the AI's
detection range.
* Set the Sphere Collision component's collision settings to overlap with the player
character.

#### STEP 2: Create a new AI controller Blueprint:

* In the Content Browser, right-click in the desired folder.
* Select Create Basic Asset > Blueprint Class.
* Choose the AIController as the parent class.
* Name the Blueprint (e.g., "AIController_Chase") and click Create.

#### STEP 3: Open the AIController Blueprint:

* In the Blueprint editor, locate the Event Begin Play event.
* Drag off the execution line and search for "Set Sight Radius".
* Set the Sight Radius value to the desired range for the AI's vision.
* Drag off the execution line again and search for "Set Peripheral Vision Angle".
* Set the Peripheral Vision Angle value to the desired field of view for the AI's
vision.

#### STEP 4: Implement perception for the AI:

* Drag off the execution line in the Begin Play event and search for "Create and
Configure AI Perception Component".
* Connect the output of the AI Perception Component node to the AI Controller's
AI Perception property.
* In the AI Perception Component node, configure the settings for sight and sight
sense.
* Drag off the AI Perception Component node and search for "Update Perception".
* Connect the output of the Update Perception node to the Event Tick event.
* In the Update Perception node, select "Sight" as the stimulus to update.
* Connect the output of the AI Perception Component to a "For Each Loop" node
to iterate through all perceived stimuli.

#### STEP 5: Implement the chase behavior:

* Inside the For Each Loop, check if the perceived stimulus is the player character.
* If the stimulus is the player character, drag off the execution line and search for
"Move To Actor".
* Set the Move To Actor node's target to the player character.
* Connect the output of the Move To Actor node to the AI Controller's Move To
Location input.

#### STEP 6: Create blackboard keys for the AI

* Open the AIController Blueprint.
* In the Blueprint editor, locate the Event Begin Play event.
* Drag off the execution line and search for "Create Blackboard".
* Create a new blackboard object and assign it to the AIController's Blackboard
property.
* Drag off the execution line again and search for "Create Blackboard Key".
* Create a new key for the blackboard, such as "PlayerLocation".
* Connect the output of the Create Blackboard Key node to the AIController's
Blackboard property

#### STEP 7: Update blackboard values:

* In the AIController Blueprint, find the Event Tick event.
* Drag off the execution line and search for "Get Player Character".
* Drag off the player character reference and search for "Get Actor Location".
* Connect the output of the Get Actor Location node to the AIController's Set
Blackboard Value As Vector input.
* Set the Blackboard Key to the "PlayerLocation" key you created earlier

#### STEP 8: Set up the Behavior Tree:

* Create a Behavior Tree asset following the steps mentioned earlier.
* Open the Behavior Tree asset in the Behavior Tree editor.
* Drag and drop a "Blackboard Key Selector" node onto the graph.
* Configure the Blackboard Key Selector node to use the "PlayerLocation" key

## OUTPUT:

### Blackboard Key Creation:
![image](https://github.com/Aashima02/AI-Chasing/assets/93427086/7c19ba1d-5b1c-44b0-a44f-272094eb64cc)

### Behaviour Tree:
![image](https://github.com/Aashima02/AI-Chasing/assets/93427086/6799604b-7362-4af0-adc9-f85ccb060f75)

### Setting Player Key Sequence Node:
![image](https://github.com/Aashima02/AI-Chasing/assets/93427086/98db37df-d330-4f0c-9f5f-24e6d00075eb)

### Setting Player Key to Move Node:
![image](https://github.com/Aashima02/AI-Chasing/assets/93427086/12fbf454-8053-4a20-96f3-f13e08352267)

### Setting Player Ley to BB Rotate Node:
![image](https://github.com/Aashima02/AI-Chasing/assets/93427086/03d05274-01f7-43a7-bfb0-29f3f6328894)

### Adding AI Perception Node:
![image](https://github.com/Aashima02/AI-Chasing/assets/93427086/00c816c9-3908-4cb6-a4a2-db95c495ba2a)

### AI Controller Graph:
![image](https://github.com/Aashima02/AI-Chasing/assets/93427086/5739e717-0306-4f75-8b80-9608b04b14c6)

### AI Controller Class Selection:
![image](https://github.com/Aashima02/AI-Chasing/assets/93427086/2580ab17-3562-4fba-a0bb-59309f9dcc85)

### AI Sense Configuration:
![image](https://github.com/Aashima02/AI-Chasing/assets/93427086/8eecc9da-2e7f-42e9-b13c-9bdf3b70f5ef)


### Game Mode:
![244051776-eb54159c-074e-4c0b-b987-164275fdea43](https://github.com/Aashima02/AI-Chasing/assets/93427086/ca34b75b-f144-445a-a689-8475ce1e0756)

## RESULT:

Thus, the AI concept to the actor for chasing when AI sees the player.
