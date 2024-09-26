```sh
python --version
# Python 3.10.12

sysctl -n machdep.cpu.brand_string
# Apple M2

sw_vers
# ProductName:            macOS
# ProductVersion:         15.0
# BuildVersion:           24A335

system_profiler SPHardwareDataType
# Hardware:

#     Hardware Overview:

#       Model Name: MacBook Air
#       Model Identifier: Mac14,2
#       Model Number: Z15Y0003MCH/A
#       Chip: Apple M2
#       Total Number of Cores: 8 (4 performance and 4 efficiency)
#       Memory: 16 GB
#       ...

uname -p
# arm
```

安装日志：
```sh
git clone https://github.com/exo-explore/exo.git
cd exo
pip install .
# alternatively, with venv （用的这个）
source install.sh
# 报错了，尝试更新到最新的pip

pip install --upgrade pip
pip install .

# 发现在Mac上安装需要额外的东西：If running on Mac, MLX has an install guide with troubleshooting steps. - https://ml-explore.github.io/mlx/build/html/install.html
# 简介：MLX is a NumPy-like array framework designed for efficient and flexible machine learning on Apple silicon, brought to you by Apple machine learning research.
pip install mlx
# 有点慢，可能要网络加速
# MLX is only available on devices running macOS >= 13.5 It is highly recommended to use macOS 14 (Sonoma)

# Run ./configure_mlx.sh. This runs commands to optimize GPU memory allocation on Apple Silicon Macs.
./configure_mlx.sh

source install.sh
# 有点慢，可能网络加速后会快点
# 提示有的依赖需要python11，回去看了要求，需要Python>=3.12.0

# 系统打开命令行用brew安装新版的python
brew install python

# 再次执行安装命令
source install.sh
# 成功，没报错


python main.py
# 进入网页，输入回车后一直转圈圈；看看generating的地方是个什么逻辑
```


```sh
# 定期从原项目拉取更新，以保持你的fork与原项目同步。
git pull upstream main
```