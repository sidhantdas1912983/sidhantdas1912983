Open a conda terminal in the current directory.
For information on installing conda and opening a terminal see https://docs.anaconda.com/anaconda/user-guide/getting-started/

Perform the following steps to set up the dependencies within the environment:
1. Install gym-pybullet-drones - Run the following commands:

conda install git --y
conda install pip --y
conda install tensorboard --y
git clone https://github.com/utiasDSL/gym-pybullet-drones.git
cd gym-pybullet-drones
pip install -e .

2. Extract Team2_Final_Code.zip folder and replace the following files to their counterparts in the gym-pybullet-drones directories:

A. The "Team2_Final_Code/HoverAviary.py" has been modified by our team and it is therefore necessary to replace the file in the stock installation of the gym-pybullet-drones directory:

Replace "/gym-pybullet-drones/gym-pybullet-drones/envs/single_agent_rl/HoverAviary.py" with the file provided "Team2_Final_Code/HoverAviary.py"

B. The "Team2_Final_Code/singleagent.py" has been modified by our team and it is therefore necessary to replace the file in the stock installation of the gym-pybullet-drones directory:

Replace "/gym-pybullet-drones/experiments/learning/singleagent.py" with the file provided "Team2_Final_Code/singleagent.py"

C. The "Team2_Final_Code/test_singleagent.py" has been modified by our team and it is therefore necessary to replace the file in the stock installation of the gym-pybullet-drones directory:

Replace "/gym-pybullet-drones/experiments/learning/test_singleagent.py" with the file provided "Team2_Final_Code/test_singleagent.py"

3. Our pretrained models are provided within the Team2_Final_Code.zip folder. Copy the following folders to the "/gym-pybullet-drones/experiments/learning/results/" folder:

A. save-hover-ppo-kin-dyn-11.14.2021_20.15.51_works
B. save-hover-ddpg-kin-dyn-11.14.2021_23.37.49_works
C. save-hover-a2c-kin-dyn-11.15.2021_10.51.34_works

4. Inference is performed on the pretrained models by running the "test_singleagent.py" script. Navigate to the "/gym-pybullet-drones/experiments/learning/" directory and run the following scripts: 

A. For PPO, run:
python test_singleagent.py --exp ./results/save-hover-ppo-kin-dyn-11.14.2021_20.15.51_works

B. For DDPG, run:
python test_singleagent.py --exp ./results/save-hover-ddpg-kin-dyn-11.14.2021_23.37.49_works

C. For A2C, run:
python test_singleagent.py --exp ./result/save-hover-a2c-kin-dyn-11.15.2021_10.51.34_works

D. For other trained models, run:
python test_singleagent.py --exp ./result/<name of directory of trained model>

5. Training is performed by running the "singleagent.py" script. Navigate to the "/gym-pybullet-drones/experiments/learning/" directory and run the following scripts:

A. For PPO, run:
python singleagent.py --env hover --algo ppo --obs kin --act dyn --cpu 1

B. For DDPG, run:
python singleagent.py --env hover --algo ddpg --obs kin --act dyn --cpu 1

C. For A2C, run:
python singleagent.py --env hover --algo a2c --obs kin --act dyn --cpu 1

6. To change the goal state of the drone, perform the followin actions:
A. Open HoverAviary.py with an editor
B. Navigate to lines 77 through 79 (Function titled "_computeReward")
C. Change the values of "goal_state_x","goal_state_y", and "goal_state_z" variables in order to modify the goal state of the quadcopter.
D. Hyperparameters may also be changed near this section.