# 🔌 RemoteConnect Launcher

This is a simple and aesthetic batch script that helps you quickly connect to a remote machine using Remote Desktop (MSTSC).

## ⚙️ Features

- ✅ Clean UI with a retro terminal design
- 📶 Checks if the IP is reachable before trying to connect
- 🌀 Animated loading sequence
- ❌ Shows an error if the IP is unreachable

## 📸 Preview

![preview gif or screenshot here if you want]

## 🛠️ How to Use

1. Download or clone this repo.
2. Run the `wincon.exe` file.
3. Enter the IP address of the remote machine.
4. The script will:
   - Check if the IP is alive
   - Show a cool "Loading..." animation
   - Launch Remote Desktop

## 📄 Example

```bash
Enter the IP address of the remote machine: 192.168.1.10
Connecting to 192.168.1.10...
Loading...
Launching MSTSC...
```
the bat script 
::
::YAwzoRdxOk+EWAnk
::fBw5plQjdG8=
::YAwzuBVtJxjWCl3EqQJgSA==
::ZR4luwNxJguZRRnk
::Yhs/ulQjdF+5
::cxAkpRVqdFKZSDk=
::cBs/ulQjdF+5
::ZR41oxFsdFKZSDk=
::eBoioBt6dFKZSDk=
::cRo6pxp7LAbNWATEpCI=
::egkzugNsPRvcWATEpCI=
::dAsiuh18IRvcCxnZtBJQ
::cRYluBh/LU+EWAnk
::YxY4rhs+aU+JeA==
::cxY6rQJ7JhzQF1fEqQJQ
::ZQ05rAF9IBncCkqN+0xwdVs0
::ZQ05rAF9IAHYFVzEqQJQ
::eg0/rx1wNQPfEVWB+kM9LVsJDGQ=
::fBEirQZwNQPfEVWB+kM9LVsJDGQ=
::cRolqwZ3JBvQF1fEqQJQ
::dhA7uBVwLU+EWDk=
::YQ03rBFzNR3SWATElA==
::dhAmsQZ3MwfNWATElA==
::ZQ0/vhVqMQ3MEVWAtB9wSA==
::Zg8zqx1/OA3MEVWAtB9wSA==
::dhA7pRFwIByZRRnk
::Zh4grVQjdCyDJGyX8VAjFB5AVQWMAE+1EbsQ5+n//NaQq0MeW+xxfZfeug==
::YB416Ek+ZG8=
::
::
::978f952a14a936cc963da21a135fa983
@echo off
:: Clear screen
cls

:: Display the big title
echo.
echo  ░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░▒▓███████▓▒░ ░▒▓██████▓▒░ ░▒▓██████▓▒░░▒▓███████▓▒░  
echo  ░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░ 
echo  ░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░      ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░ 
echo  ░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░      ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░ 
echo  ░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░      ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░ 
echo  ░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░ 
echo   ░▒▓█████████████▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░░▒▓██████▓▒░ ░▒▓██████▓▒░░▒▓█▓▒░░▒▓█▓▒░ 
echo.                                                                            
echo.                                                                            

:: Prompt for IP address
set /p ip="Enter the IP address of the victim: "

:: Check if IP is reachable
ping -n 1 %ip% >nul 2>&1
if errorlevel 1 (
    echo.
    echo ❌ The IP address "%ip%" is not working or unreachable.
    pause
    exit /b
)

:: Animated loading
echo.
setlocal enabledelayedexpansion
for %%L in (1 2 3) do (
    cls
    echo Connecting to %ip%...
    set dots=
    for /L %%D in (1,1,%%L) do set dots=!dots!.
    echo Loading!dots!
    timeout /t 1 >nul
)
victim
:: Launch MSTSC
mstsc /v:%ip%
