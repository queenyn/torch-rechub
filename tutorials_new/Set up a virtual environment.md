# windows系统（建议用win10/win11）：
## 步骤1：安装Python（建议用Python 3.9+）：
1、访问 Python 官方 Windows 下载页 https://www.python.org/downloads/windows/ ，下滑找到 “Python 3.10.10”，点击 “Windows Installer (64-bit)” 下载；  
2、运行安装包，勾选以下选项：  
Add Python 3.10 to PATH（添加到系统环境变量）。  
3、等待安装完成后，用管理员模式运行powershell，输入：  
```
python --version
```
输出 Python 3.10.10 即安装成功。  
## 步骤2：创建虚拟环境（创建虚拟环境可使用 conda、uv 等工具进行管理（可以自行查询教程。）使用uv管理跳转到步骤4，不需要经过步骤2、3）：
1、此处假设项目文件夹的路径为C:\Users\你的用户名\Desktop\torch_rechub，实际操作中可自行设置路径。  
2、在powershell中输入：  
```
mkdir C:\Users\你的用户名\Desktop\torch_rechub
```
运行后，继续输入：  
```
cd C:\Users\你的用户名\Desktop\torch_rechub
```
这样就创建好了项目文件夹并且在powershell中进入了该文件夹。  
3、此处假设虚拟环境的名字为torch_rechub。在powershell中输入：  
```
python -m venv torch_rechub
```
运行后，继续输入：  
```
.\torch_rechub\Scripts\Activate.ps1
```
这样就完成了虚拟环境的创建与激活。  
在运行后，如果PowerShell 前缀出现 (torch_rechub)（如 (torch_rechub) PS C:\Users\...\torch_rechub>），即代表操作成功。  
## 步骤3：下载需要用到的包：  
1、下载pytorch。  
进入 https://pytorch.org/get-started/locally/ 网站，选择自己的型号后，复制生成的代码，在启动了虚拟环境的powershell中输入（前缀出现 (torch_rechub)时）并且运行，之后虚拟环境会开始下载pytorch。  
提示：如果是50系显卡，可能需要搜寻网上教程，自行下载可用的版本；如果下载速度慢，可以自行切换镜像源。  
下载完成后，在powershell中依次输入并运行：  
```
python
```
```
import torch
```
```
print(torch.__version__)
```
如果输出版本号，即证明下载成功。  
```
print(torch.cuda.is_available())
```
如果是gpu版本pytorch，这里应该输出True，如果是cpu版本pytorch，这里应该输出False。  
2、在powershell中输入并运行：  
```
pip install numpy pandas scipy scikit-learn
```
```
pip install torch-rechub
```
这样就下载好了。  
下载完成后，在powershell中依次输入并运行：  
```
import torch_rechub  
```
```
print(torch_rechub.__version__)  
```
如果输出版本号，即证明下载成功。  
## 步骤4：使用uv管理：  
打开powershell，依次输入并运行：  
```
pip install uv
```
```
git clone https://github.com/datawhalechina/torch-rechub.git
```
```
cd torch-rechub
```
```
uv sync
```
如果您想为 Torch-RecHub 做出贡献或使用源代码，需要额外运行以下代码，用于以开发模式安装包：  
```
uv pip install -e .
```
下载完成后，在powershell中依次输入并运行：  
```
import torch_rechub
```
```
print(torch_rechub.__version__)
```
如果输出版本号，即证明下载成功。  
