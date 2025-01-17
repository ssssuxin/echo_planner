# code_planner
The paper "CODE: Complete Coverage UAV Exploration Planner using Dual-Type Viewpoints for Multi-Layer Complex Environments" has been accepted by RA-L in December 12th, 2024.

## Expeiments Videos  
We have designed several experimental evironments to validate the capability of our method. Updates are ongoing.  
  
Experiment ① "Narrow Tunnel": https://youtu.be/jENgJ3dgBa0 or https://www.bilibili.com/video/BV1h18YejEWP/    
Experiment ② "Narrow Tunnel: DSVP VS CODE": https://www.youtube.com/watch?v=VOSmzPwXvmc or https://www.bilibili.com/video/BV1vMvKesEBz/  
Experiment ③ "Garage-D"       : https://www.youtube.com/watch?v=5gJdlG9kfTY or https://www.bilibili.com/video/BV14DeZe9Ev3/
## Comparison between 2D and 3D exploration tasks
https://youtu.be/98l-RHV5oCA
## Explorration in Garage-D with different robot-init-point
https://youtu.be/04E0oGMSxJ8
## Requirement
Ubuntu20.04  
Ros2 Foxy
## Simulation environment  
①Garage-D garage with part of it's driveway destoryed: https://github.com/ssssuxin/autonomous_navigation_environment_ego  
②narrow tunnel: https://github.com/ssssuxin/autonomous_navigation_environment_ros1  

## Usages  
Please follow step "Simulation environment" to install experimental environments first.
### Garage-D  
in env_ego (https://github.com/ssssuxin/autonomous_navigation_environment_ego)  

    ros2 launch ego_planner uav_new_garage.launch.py  
    ros2 launch visualization_tools visualization_tools.launch.py  

(If anything wrong with rendering simulation environment, please try copy directory "new_garage_v2"(in src/vehicle_simulator/mesh) to "~/.gazebo/models")    
in planner  

    ros2 launch uav_planner garage_D_uav.launch.py (Stable_version)
or

    ros2 launch uav_planner 5_21_new_garage_invalid.launch.py (Fast_version)
Performing Fast_version, please set "max_vel" and "max_acc" as 5.0 and 2.5 respectively in "single_run_in_sim.launch.py" of project env.
### Narrow Tunnel  
in env_ros1 (https://github.com/ssssuxin/autonomous_navigation_environment_ros1)    

    roslaunch vehicle_simulator narrow_tunnel.launch  
in env_ego (https://github.com/ssssuxin/autonomous_navigation_environment_ego)    

    ros2 launch visualization_tools visualization_tools_for_tunnel.launch.py   
in planner  

    ros2 launch uav_planner tunnel_guv.launch.py
in a new terminate  

    source /opt/ros/noetic/setup.bash
    source /opt/ros/foxy/setup.bash
    ros2 run ros1_bridge dynamic_bridge   
note: you cloud install ros1_bridge by apt-get or https://github.com/ros2/ros1_bridge

## Results of Tests
### Test 1
<div>
  <img src="test_results/garage_tra.png" height=200 >
</div>
Check https://youtu.be/cI60Tal7ov0 for tra comparison.

CODE                                                   TARE
<div>
  <img src="test_results/O_G.gif" width=400 >  <img src="test_results/T_G.gif" width=400 > 
</div>




<div>
  <img src="test_results/Timenewroma_garage_volumn.png" width=400><img src="test_results/Timenewroma_garage_runtime.png" width=400>
</div>

### Test 2
<div>
  <img src="test_results/tunnel_tra.png" height=200 >
</div>
<div>
  <img src="test_results/Timenewroma_tunnel_volumn.png" width=500><img src="test_results/Timenewroma_tunnel_runtime.png" width=500>
</div>

### Test 3
<div>
  <img src="test_results/REAL_ENV.png" height=200 >
</div>
Check https://youtu.be/bqUJAKtqXxA for tra comparison.

CODE                                                   TARE
<div>
  <img src="test_results/O_R.gif" width=400 >  <img src="test_results/T_R.gif" width=400 > 
</div>
<div>
  <img src="test_results/REAL_VOL.png" width=500><img src="test_results/REAL_RUNTIME.png" width=500>
</div>



<!---
<div>
  <img src="img/pic1.jpg" height=200 ><img src="img/pic2.jpg" height=200>
</div>
<div>
  <img src="img/1.jpg" height=200><img src="img/4.jpg" height=200>
</div>
<img src="img/res1.png" height=400>  
<div>
  <img src="img/map1.png" height=200" ><img src="img/map2.png" height=200><img src="img/map3.png" height=200>
</div>
<div>
  <img src="img/tra1.png" height=200 ><img src="img/tra2.png" height=200><img src="img/tra3.png" height=200>
</div>
--->



## DATA Rigor
Please check the data statistics for comparing experiments, including exploration volume, time cost, etc., in the directory "t_distribution_for_datarigor".
<div>
  <img src="/t_distribution_for_datarigor/garage/our/Volumn.png" height=200 >
</div>

