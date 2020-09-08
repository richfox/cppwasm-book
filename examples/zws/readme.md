# windows下安装emsdk
fork https://github.com/emscripten-core/emsdk.git

# Get the emsdk repo
git clone https://github.com/.../emsdk.git
# Enter that directory
cd emsdk

# Fetch the latest version of the emsdk (not needed the first time you clone)
git pull

# Download and install the latest SDK tools.
python emsdk.py install latest

# Make the "latest" SDK "active" for the current user. (writes .emscripten file)
python emsdk.py activate latest

# 不需要设置环境变量
emsdk_env.bat

# VS Code设置
# python debug
"configurations": [
        {
            "name": "Python: Aktuelle Datei",
            "type": "python",
            "request": "launch",
            "program": "${workspaceRoot}/upstream/emscripten/tests/runner.py",
            "console": "integratedTerminal",
            "args": ["other.*embind*"]
        }
    ]

# Javascript debug
http://localhost/wasm/examples/zws/logis*.html
按键F12

# 运行 emcc
cd emsdk
emcmdprompt.bat
emcc cppwasm-book\examples\zws\logis*.cpp -o temp\logis*.js --bind