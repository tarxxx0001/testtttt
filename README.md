do local gui =  game:GetService("CoreGui").RobloxGui.Modules:FindFirstChild("X2ZLIB") if ui then ui:Destroy() end end


if _G.Color == nil then
    _G.Color = Color3.fromRGB(255,0,0)
end

if _G.Color2 == nil then
   _G.Color2 = Color3.fromRGB(51,255,0)  
end

local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")

local WindowFocusReleasedFunction = function()
	RunService:Set3dRenderingEnabled(false)
	setfpscap(30)
	return
end

local WindowFocusedFunction = function()
	RunService:Set3dRenderingEnabled(true)
	setfpscap(360)
	return
end

local Initialize = function()
	UserInputService.WindowFocusReleased:Connect(WindowFocusReleasedFunction)
	UserInputService.WindowFocused:Connect(WindowFocusedFunction)
	return
end
Initialize()

	repeat wait()
		if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Visible == true then
			if _G.TeamPirate then
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			elseif _G.TeamMarine then
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			else
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			end
		end     
	until game.Players.LocalPlayer.Team ~= nil and game:IsLoaded() 

local ts = game:GetService("TeleportService")
local p = game:GetService("Players").LocalPlayer

_G.AutoRejoin = true
	spawn(function()
	    while wait() do
	        if _G.AutoRejoin then
	                getgenv().rejoin = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(child)
                        if child.Name == 'ErrorPrompt' and child:FindFirstChild('MessageArea') and child.MessageArea:FindFirstChild("ErrorFrame") then
                            game:GetService("TeleportService"):Teleport(game.PlaceId)
                        end
                    end)
	            end
	        end
	end)

_G.AntiAFK = true
	local VirsssssUser = game:GetService("VirtualUser")
	game:GetService("Players").LocalPlayer.Idled:connect(function()
		if _G.AntiAFK then
			VirsssssUser:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
			wait(1)
			VirsssssUser:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
		end
	end)

_G.ActiveKen = true
_G.KENHIDE = true

    spawn(function()
        while wait() do
            if _G.ActiveKen then
                pcall(function()
                    game:GetService("ReplicatedStorage").Remotes.CommE:FireServer("Ken",true)
                end)
            end    
        end
    end)

	spawn(function()
		while wait() do wait(40)
			pcall(function()
				if _G.KENHIDE and not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
					ObservationVirtualUser:CaptureController()
					ObservationVirtualUser:SetKeyDown('0x65')
					wait(2)
					ObservationVirtualUser:SetKeyUp('0x65')
				end
			end)
		end
	end)

	if syn then
		setfflag("HumanoidParallelRemoveNoPhysics", "False")
		setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
		setfflag("DFStringCrashPadUploadToBacktraceToBacktraceBaseUrl", "")
		setfflag("DFIntCrashUploadToBacktracePercentage", "0")
		setfflag("DFStringCrashUploadToBacktraceBlackholeToken", "")
		setfflag("DFStringCrashUploadToBacktraceWindowsPlayerToken", "")
	end

spawn(function()
    game_pid = game.PlaceId
    asiufdl = 0
    repeat wait(1)
    game:GetService("StarterGui"):SetCore("SendNotification", {
        Title = "Rocket V 1.0.1",
        Text = "CHECKING GAME LOAD : "..tostring(asiufdl),
        Duration = 3
    })
        asiufdl = 1
    until asiufdl > 240 or game:IsLoaded()
    repeat wait()
        if not game:IsLoaded() then
            if game_pid == nil then
                game_pid = game.PlaceId
            end
            pcall(function()
                print("Found Error Function - [ 1 ] -")
                game:GetService('TeleportService'):TeleportToPlaceInstance(game_pid, game.JobId, game.Players.LocalPlayer)
                print("Rejoin : 1 Time")
            end)
            pcall(function()
                print("Found Error Function - [ 2 ] -")
                game:GetService('TeleportService'):Teleport(game_pid)
                print("Rejoin : 2 Time")
            end)
            wait(2)
        end
    until game:IsLoaded()
end)

joingame_timr = 0
repeat 
	wait(0.1)
    joingame_timr = 0.1
until game:IsLoaded()


spawn(function()
    while wait(1) do
        pcall(function()
            game_pid = game.PlaceId
            repeat wait() until game.CoreGui:FindFirstChild('RobloxPromptGui')
            local lp,po,ts = game:GetService('Players').LocalPlayer,game.CoreGui.RobloxPromptGui.promptOverlay,game:GetService('TeleportService')
            po.ChildAdded:connect(function(a)
                if a.Name == 'ErrorPrompt' then
                    gujaef = 0
                    repeat wait(1)

                            game:GetService("StarterGui"):SetCore("SendNotification", {
                            Title = "X2Z SV",
                            Text = "Waiting To Rejoin if  Found ErrorPrompt " ..tostring(gujaef),
                            Duration = 5
                           })
    
    
                        gujaef = 1
                    until gujaef > 40
                    if a.Name == 'ErrorPrompt' then
                        while wait() do
                            --ts:Teleport(game.PlaceId)
                            if game_pid == nil then
                                game_pid = game.PlaceId
                            end
            pcall(function()
                print("Found Error Function - [ 1 ] -")
                ts:Teleport(game.PlaceId, p)
                print("Rejoin : 1 Time")
            end)
            pcall(function()
                print("Found Error Function - [ 2 ] -")
                ts:Teleport(game.PlaceId, p)
                print("Rejoin : 2 Time")
            end)
                            wait(2)
                        end
                    end
                end
            end)
        end)
    end
end)

	xwd = game:GetService("MarketplaceService"):GetProductInfo(game.PlaceId)
		Gamename = xwd.Name
		local games = {
		[game.PlaceId] = {
			Title = "Blox Fruits",
			Icons = "rbxassetid://7607745682",
			Welcome = function()
					return tostring(
					" "
						..

								"[ ROCKET HUB ] BLOXFRUIT SCRIPT".."\nNEW UI AND NEW FUNCTION!"
					)
			end
		}
		}
		if games[game.PlaceId] then	
		if games[game.PlaceId].Title == "Blox Fruits" then
			local function notify(types, ...)
					if types == "Notify" then
					require(game.ReplicatedStorage.Notification).new(...):Display()
					end
			end
			notify("Notify", games[game.PlaceId].Welcome())
		end
	end
		

    if not game:IsLoaded() then repeat game.Loaded:Wait() until game:IsLoaded() end
    
    repeat wait() until game:GetService("Players")
    
    if not game:GetService("Players").LocalPlayer.Character:FindFirstChild("HumanoidRootPart") then repeat wait() until game:GetService("Players").LocalPlayer.Character:FindFirstChild("HumanoidRootPart") end
        
    wait(1)
    
local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")

local function MakeDraggable(topbarobject, object)
	local Dragging = nil
	local DragInput = nil
	local DragStart = nil
	local StartPosition = nil

	local function Update(input)
		local Delta = input.Position - DragStart
		local pos =
			UDim2.new(
				StartPosition.X.Scale,
				StartPosition.X.Offset + Delta.X,
				StartPosition.Y.Scale,
				StartPosition.Y.Offset + Delta.Y
			)
		local Tween = TweenService:Create(object, TweenInfo.new(0.2), {Position = pos})
		Tween:Play()
	end

	topbarobject.InputBegan:Connect(
		function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
				Dragging = true
				DragStart = input.Position
				StartPosition = object.Position

				input.Changed:Connect(
					function()
						if input.UserInputState == Enum.UserInputState.End then
							Dragging = false
						end
					end
				)
			end
		end
	)

	topbarobject.InputChanged:Connect(
		function(input)
			if
				input.UserInputType == Enum.UserInputType.MouseMovement or
				input.UserInputType == Enum.UserInputType.Touch
			then
				DragInput = input
			end
		end
	)

	UserInputService.InputChanged:Connect(
		function(input)
			if input == DragInput and Dragging then
				Update(input)
			end
		end
	)
end

local library = {}

function library:AddWindow(text,logo,keybind)
	local uihide = false
	local abc = false
	local logo = logo or 0
	local currentpage = ""
	local keybind = keybind or Enum.KeyCode.RightControl
	local yoo = string.gsub(tostring(keybind),"Enum.KeyCode.","")
	
	local X2ZLIB = Instance.new("ScreenGui")
	X2ZLIB.Name = "X2ZLIB"
	X2ZLIB.Parent = game:GetService("CoreGui").RobloxGui.Modules
	X2ZLIB.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

	local Main = Instance.new("Frame")
	Main.Name = "Main"
	Main.Parent = X2ZLIB
	Main.ClipsDescendants = true
	Main.AnchorPoint = Vector2.new(0.5,0.5)
	Main.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
	Main.Position = UDim2.new(0.5, 0, 0.5, 0)
	Main.Size = UDim2.new(0, 0, 0, 0)

	local Main2 = Instance.new("Frame")
	Main2.Name = "Main2"
	Main2.Parent = X2ZLIB
	Main2.ClipsDescendants = true
	Main2.AnchorPoint = Vector2.new(0.5,0.5)
	Main2.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
	Main2.Position = UDim2.new(0.18, 19, 0.5, 0)
	Main2.Size = UDim2.new(0, 0, 0, 0)


	local Main55 = Instance.new("UIStroke")
	Main55.Name = "Main55"
	Main55.Parent = Main2

	local Main5 = Instance.new("UICorner")
	Main5.Name = "Main5"
	Main5.Parent = Main2
	
	Main:TweenSize(UDim2.new(0, 656, 0, 400),"Out","Quad",0.4,true)
    
	local MCNR = Instance.new("UICorner")
	MCNR.Name = "MCNR"
	MCNR.Parent = Main

	local Top = Instance.new("Frame")
	Top.Name = "Top"
	Top.Parent = Main
	Top.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
	Top.Size = UDim2.new(0, 656, 0, 27)

	local TCNR = Instance.new("UICorner")
	TCNR.Name = "TCNR"
	TCNR.Parent = Top

	local Logo = Instance.new("ImageButton")
	Logo.Name = "Logo"
	Logo.Parent = Top
	Logo.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Logo.BackgroundTransparency = 1.000
	Logo.Position = UDim2.new(0, 10, 0, 1)
	Logo.Size = UDim2.new(0, 25, 0, 25)
	Logo.Image = "rbxassetid://"..tostring(logo)
    Logo.MouseButton1Click:Connect(function()
    game:GetService("StarterGui"):SetCore("SendNotification", {
        Title = "ROCKET SCRIPT",
        Text = "VERSION 1.2.0",
        Duration = 3
    })
    end)
    
	local Logo2 = Instance.new("ImageButton")
	Logo2.Name = "Logo2"
	Logo2.Parent = Top
	Logo2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Logo2.BackgroundTransparency = 1.000
	Logo2.Position = UDim2.new(0, 525, 0, 1)
	Logo2.Size = UDim2.new(0, 25, 0, 25)
	Logo2.Image = "rbxassetid://6026568198"

	local Logo3 = Instance.new("ImageButton")
	Logo3.Name = "Logo3"
	Logo3.Parent = Top
	Logo3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Logo3.BackgroundTransparency = 1.000
	Logo3.Position = UDim2.new(0, 500, 0, 1)
	Logo3.Size = UDim2.new(0, 25, 0, 25)
	Logo3.Image = "rbxassetid://6034509993"
	
ON = false

Logo2.MouseButton1Click:Connect(function()
    if ON == false then
        Main2:TweenSize(UDim2.new(0, 150, 0, 350),"Out","Quad",0.4,true)
    else
        Main2:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.4,true)
        Logo3.BackgroundTransparency = 0
    end
end)

OFF = false

Logo3.MouseButton1Click:Connect(function()
    if OFF == false then
        Main2:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.4,true)
    end
end)

--Main2

	local Name1 = Instance.new("TextLabel")
	Name1.Name = "Name1"
	Name1.Parent = Main2
	Name1.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Name1.BackgroundTransparency = 1.000
	Name1.Position = UDim2.new(0, 32, 0, 1)
	Name1.Size = UDim2.new(0, 61, 0, 27)
	Name1.Font = Enum.Font.GothamSemibold
	Name1.Text = " F O X Y - H U B"
	Name1.TextColor3 = Color3.fromRGB(225, 225, 225)
	Name1.TextSize = 17.000
	
	local Name1 = Instance.new("TextLabel")
	Name1.Name = "Name1"
	Name1.Parent = Main2
	Name1.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Name1.BackgroundTransparency = 1.000
	Name1.Position = UDim2.new(0, 32, 0, 20)
	Name1.Size = UDim2.new(0, 61, 0, 27)
	Name1.Font = Enum.Font.GothamSemibold
	Name1.Text = "BLOX FRUIT SCRIPT"
	Name1.TextColor3 = Color3.fromRGB(225, 225, 225)
	Name1.TextSize = 13.000

	local Name1 = Instance.new("TextLabel")
	Name1.Name = "Name1"
	Name1.Parent = Main2
	Name1.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Name1.BackgroundTransparency = 1.000
	Name1.Position = UDim2.new(0, 32, 0, 35)
	Name1.Size = UDim2.new(0, 61, 0, 27)
	Name1.Font = Enum.Font.GothamSemibold
	Name1.Text = "PREMIUM SCRIPT    "
	Name1.TextColor3 = Color3.fromRGB(225, 225, 225)
	Name1.TextSize = 13.000
	
	local Name = Instance.new("TextLabel")
	Name.Name = "Name"
	Name.Parent = Top
	Name.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Name.BackgroundTransparency = 1.000
	Name.Position = UDim2.new(0, 32, 0, 1)
	Name.Size = UDim2.new(0, 61, 0, 27)
	Name.Font = Enum.Font.GothamSemibold
	Name.Text = text
	Name.TextColor3 = Color3.fromRGB(225, 225, 225)
	Name.TextSize = 17.000

	local BTNMAIN2 = Instance.new("TextButton")
	BTNMAIN2.Name = "BTNMAIN2"
	BTNMAIN2.Parent = Main2
	BTNMAIN2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	BTNMAIN2.BackgroundTransparency = 1.000
	BTNMAIN2.Position = UDim2.new(0.26, 0, 0, 50)
	BTNMAIN2.Size = UDim2.new(0, 100, 0, 27)
	BTNMAIN2.Font = Enum.Font.GothamSemibold
	BTNMAIN2.Text = "JOIN DISCORD         "
	BTNMAIN2.TextColor3 = Color3.fromRGB(100, 100, 100)
	BTNMAIN2.TextSize = 11.000
	BTNMAIN2.MouseButton1Click:Connect(function()
	    local a=request or http_request or syn and syn.request;local b=game.HttpService;a({Url="http://127.0.0.1:6463/rpc?v=1",Method="POST",Headers={["Content-Type"]="application/json",["Origin"]="https://discord.com"},Body=b:JSONEncode({cmd="INVITE_BROWSER",args={code="UpnS4jq599"},nonce=b:GenerateGUID(false)})})local c=game:GetService("Players").LocalPlayer
	end)
	
	local BTNMAIN23 = Instance.new("TextButton")
	BTNMAIN23.Name = "BTNMAIN23"
	BTNMAIN23.Parent = Main2
	BTNMAIN23.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	BTNMAIN23.BackgroundTransparency = 1.000
	BTNMAIN23.Position = UDim2.new(0.26, 0, 0, 100)
	BTNMAIN23.Size = UDim2.new(0, 100, 0, 70)
	BTNMAIN23.Font = Enum.Font.GothamSemibold
	BTNMAIN23.Text = "COPY DISCORD LINK         "
	BTNMAIN23.TextColor3 = Color3.fromRGB(100, 100, 100)
	BTNMAIN23.TextSize = 11.000
	BTNMAIN23.MouseButton1Click:Connect(function()
	    setclipboard("https://discord.gg/UpnS4jq599")
	end)
	
	local BTNMAIN235 = Instance.new("TextButton")
	BTNMAIN235.Name = "BTNMAIN235"
	BTNMAIN235.Parent = Main2
	BTNMAIN235.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	BTNMAIN235.BackgroundTransparency = 1.000
	BTNMAIN235.Position = UDim2.new(0.26, 0, 0, 190)
	BTNMAIN235.Size = UDim2.new(0, 100, 0, 50)
	BTNMAIN235.Font = Enum.Font.GothamSemibold
	BTNMAIN235.Text = "COPY DISCORD IO LINK          "
	BTNMAIN235.TextColor3 = Color3.fromRGB(100, 100, 100)
	BTNMAIN235.TextSize = 11.000
	BTNMAIN235.MouseButton1Click:Connect(function()
	    setclipboard("https://discord")
	end)

	local Hub = Instance.new("TextLabel")
	Hub.Name = "Hub"
	Hub.Parent = Top
	Hub.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Hub.BackgroundTransparency = 1.000
	Hub.Position = UDim2.new(0, 85, 0, 1)
	Hub.Size = UDim2.new(0, 81, 0, 27)
	Hub.Font = Enum.Font.GothamSemibold
	Hub.Text = " HUB"
	Hub.TextColor3 = _G.Color
	Hub.TextSize = 17.000
	Hub.TextXAlignment = Enum.TextXAlignment.Left

	local Hubm = Instance.new("TextLabel")
	Hubm.Name = "Hubm"
	Hubm.Parent = Top
	Hubm.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Hubm.BackgroundTransparency = 1.000
	Hubm.Position = UDim2.new(0, 550, 0, 1)
	Hubm.Size = UDim2.new(0, 81, 0, 27)
	Hubm.Font = Enum.Font.GothamSemibold
	Hubm.Text = "Version 1.0.1"
	Hubm.TextColor3 = _G.Color2
	Hubm.TextSize = 17.000
	Hubm.TextXAlignment = Enum.TextXAlignment.Left
	
	local BindButton = Instance.new("TextButton")
	BindButton.Name = "BindButton"
	BindButton.Parent = Top
	BindButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	BindButton.BackgroundTransparency = 1.000
	BindButton.Position = UDim2.new(0.20, 0, 0, 0)
	BindButton.Size = UDim2.new(0, 100, 0, 27)
	BindButton.Font = Enum.Font.GothamSemibold
	BindButton.Text = "[ "..string.gsub(tostring(keybind),"Enum.KeyCode.","").." ]"
	BindButton.TextColor3 = Color3.fromRGB(100, 100, 100)
	BindButton.TextSize = 11.000
	
	BindButton.MouseButton1Click:Connect(function ()
		BindButton.Text = "[ ... ]"
		local inputwait = game:GetService("UserInputService").InputBegan:wait()
		local shiba = inputwait.KeyCode == Enum.KeyCode.Unknown and inputwait.UserInputType or inputwait.KeyCode

		if shiba.Name ~= "Focus" and shiba.Name ~= "MouseMovement" then
			BindButton.Text = "[ "..shiba.Name.." ]"
			yoo = shiba.Name
		end
	end)

	local Tab = Instance.new("Frame")
	Tab.Name = "Tab"
	Tab.Parent = Main
	Tab.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
	Tab.Position = UDim2.new(0, 5, 0, 30)
	Tab.Size = UDim2.new(0, 150, 0, 365)

	local TCNR = Instance.new("UICorner")
	TCNR.Name = "TCNR"
	TCNR.Parent = Tab

	local ScrollTab = Instance.new("ScrollingFrame")
	ScrollTab.Name = "ScrollTab"
	ScrollTab.Parent = Tab
	ScrollTab.Active = true
	ScrollTab.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ScrollTab.BackgroundTransparency = 1.000
	ScrollTab.Size = UDim2.new(0, 150, 0, 365)
	ScrollTab.CanvasSize = UDim2.new(0, 0, 0, 0)
	ScrollTab.ScrollBarThickness = 0

	local PLL = Instance.new("UIListLayout")
	PLL.Name = "PLL"
	PLL.Parent = ScrollTab
	PLL.SortOrder = Enum.SortOrder.LayoutOrder
	PLL.Padding = UDim.new(0, 15)

	local PPD = Instance.new("UIPadding")
	PPD.Name = "PPD"
	PPD.Parent = ScrollTab
	PPD.PaddingLeft = UDim.new(0, 10)
	PPD.PaddingTop = UDim.new(0, 10)

	local Page = Instance.new("Frame")
	Page.Name = "Page"
	Page.Parent = Main
	Page.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
	Page.Position = UDim2.new(0.245426834, 0, 0.075000003, 0)
	Page.Size = UDim2.new(0, 490, 0, 365)

	local PCNR = Instance.new("UICorner")
	PCNR.Name = "PCNR"
	PCNR.Parent = Page

	local MainPage = Instance.new("Frame")
	MainPage.Name = "MainPage"
	MainPage.Parent = Page
	MainPage.ClipsDescendants = true
	MainPage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	MainPage.BackgroundTransparency = 1.000
	MainPage.Size = UDim2.new(0, 490, 0, 365)

	local PageList = Instance.new("Folder")
	PageList.Name = "PageList"
	PageList.Parent = MainPage

	local UIPageLayout = Instance.new("UIPageLayout")

	UIPageLayout.Parent = PageList
	UIPageLayout.SortOrder = Enum.SortOrder.LayoutOrder
	UIPageLayout.EasingDirection = Enum.EasingDirection.InOut
	UIPageLayout.EasingStyle = Enum.EasingStyle.Quad
	UIPageLayout.FillDirection = Enum.FillDirection.Vertical
	UIPageLayout.Padding = UDim.new(0, 15)
	UIPageLayout.TweenTime = 0.400
	UIPageLayout.GamepadInputEnabled = false
	UIPageLayout.ScrollWheelInputEnabled = false
	UIPageLayout.TouchInputEnabled = false
	
	MakeDraggable(Top,Main,Main2)

	UserInputService.InputBegan:Connect(function(input)
		if input.KeyCode == Enum.KeyCode[yoo] then
			if uihide == false then
				uihide = true
				Main:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.4,true)
			else
				uihide = false
                --Main2:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.4,true)
				Main:TweenSize(UDim2.new(0, 656, 0, 400),"Out","Quad",0.4,true)
			end
		end
	end)

	local uitab = {}
	
	function uitab:AddTab(text)
		local TabButton = Instance.new("TextButton")
		
		TabButton.Parent = ScrollTab
		TabButton.Name = text.."Server"
		TabButton.Text = text
		TabButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		TabButton.BackgroundTransparency = 1.000
		TabButton.Size = UDim2.new(0, 130, 0, 23)
		TabButton.Font = Enum.Font.GothamSemibold
		TabButton.TextColor3 = Color3.fromRGB(225, 225, 225)
		TabButton.TextSize = 15.000
		TabButton.TextTransparency = 0.500
		

	        
		local MainFramePage = Instance.new("ScrollingFrame")
		MainFramePage.Name = text.."_Page"
		MainFramePage.Parent = PageList
		MainFramePage.Active = true
		MainFramePage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		MainFramePage.BackgroundTransparency = 1.000
		MainFramePage.BorderSizePixel = 0
		MainFramePage.Size = UDim2.new(0, 490, 0, 365)
		MainFramePage.CanvasSize = UDim2.new(0, 0, 0, 0)
		MainFramePage.ScrollBarThickness = 0
		
		local UIPadding = Instance.new("UIPadding")
		local UIListLayout = Instance.new("UIListLayout")
		
		UIPadding.Parent = MainFramePage
		UIPadding.PaddingLeft = UDim.new(0, 10)
		UIPadding.PaddingTop = UDim.new(0, 10)

		UIListLayout.Padding = UDim.new(0,15)
		UIListLayout.Parent = MainFramePage
		UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
		

		TabButton.MouseButton1Click:Connect(function()
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0.5}
					):Play()
				end
				TweenService:Create(
					TabButton,
					TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			for i,v in next, PageList:GetChildren() do
				currentpage = string.gsub(TabButton.Name,"Server","").."_Page"
				if v.Name == currentpage then
					UIPageLayout:JumpTo(v)
				end
			end
		end)

		if abc == false then
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0.5}
					):Play()
				end
				TweenService:Create(
					TabButton,
					TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			UIPageLayout:JumpToIndex(1)
			abc = true
		end
		
		game:GetService("RunService").Stepped:Connect(function()
			pcall(function()
				MainFramePage.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 20)
				ScrollTab.CanvasSize = UDim2.new(0,0,0,PLL.AbsoluteContentSize.Y + 20)
			end)
		end)
		

		local main = {}
		function main:AddButton(text,callback)
			local Button = Instance.new("Frame")
			local UICorner = Instance.new("UICorner")
			local TextBtn = Instance.new("TextButton")
			local UICorner_2 = Instance.new("UICorner")
			local Black = Instance.new("Frame")
			local UICorner_3 = Instance.new("UICorner")
			
			Button.Name = "Button"
			Button.Parent = MainFramePage
			Button.BackgroundColor3 = _G.Color
			Button.Size = UDim2.new(0, 470, 0, 37)
			
			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = Button
			
			TextBtn.Name = "TextBtn"
			TextBtn.Parent = Button
			TextBtn.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			TextBtn.Position = UDim2.new(0, 1, 0, 1)
			TextBtn.Size = UDim2.new(0, 468, 0, 35)
			TextBtn.AutoButtonColor = false
			TextBtn.Font = Enum.Font.GothamSemibold
			TextBtn.Text = text
			TextBtn.TextColor3 = Color3.fromRGB(225, 225, 225)
			TextBtn.TextSize = 15.000
	        
			UICorner_2.CornerRadius = UDim.new(0, 5)
			UICorner_2.Parent = TextBtn


			Black.Name = "Black"
			Black.Parent = Button
			Black.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
			Black.BackgroundTransparency = 1.000
			Black.BorderSizePixel = 0
			Black.Position = UDim2.new(0, 1, 0, 1)
			Black.Size = UDim2.new(0, 468, 0, 35)
			
			UICorner_3.CornerRadius = UDim.new(0, 5)
			UICorner_3.Parent = Black

			TextBtn.MouseEnter:Connect(function()
				TweenService:Create(
					Black,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{BackgroundTransparency = 0.7}
				):Play()
			end)
			TextBtn.MouseLeave:Connect(function()
				TweenService:Create(
					Black,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{BackgroundTransparency = 1}
				):Play()
			end)
			TextBtn.MouseButton1Click:Connect(function()
				TextBtn.TextSize = 0
				TweenService:Create(
					TextBtn,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextSize = 15}
				):Play()
				callback()
			end)
		end
		

		function main:AddToggle(text,config,callback)
			config = config or false
			local toggled = config
			local Toggle = Instance.new("Frame")
			local UICorner = Instance.new("UICorner")
			local Button = Instance.new("TextButton")
			local UICorner_2 = Instance.new("UICorner")
			local Label = Instance.new("TextLabel")
			local ToggleImage = Instance.new("Frame")
			local UICorner_3 = Instance.new("UICorner")
			local Circle = Instance.new("Frame")
		    local IMGTOG = Instance.new("ImageLabel")
			local UICorner_4 = Instance.new("UICorner")
   
			Toggle.Name = "Toggle"
			Toggle.Parent = MainFramePage
			Toggle.BackgroundColor3 = _G.Color
			Toggle.Size = UDim2.new(0, 470, 0, 37) --UDim2.new(0, 470, 0, 31)

			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = Toggle

			Button.Name = "Button"
			Button.Parent = Toggle
			Button.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			Button.Position = UDim2.new(0, 1, 0, 1)
			Button.Size = UDim2.new(0, 468, 0, 35)
			Button.AutoButtonColor = false
			Button.Font = Enum.Font.SourceSans
			Button.Text = ""
			Button.TextColor3 = Color3.fromRGB(0, 0, 0)
			Button.TextSize = 11.000

			UICorner_2.CornerRadius = UDim.new(0, 5)
			UICorner_2.Parent = Button

			Label.Name = "Label"
			Label.Parent = Toggle
			Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Label.BackgroundTransparency = 1.000
			Label.Position = UDim2.new(0, 1, 0, 1)
			Label.Size = UDim2.new(0, 468, 0, 34)
			Label.Font = Enum.Font.GothamSemibold
			Label.Text = text
			Label.TextColor3 = Color3.fromRGB(225, 225, 225)
			Label.TextSize = 15.000

			ToggleImage.Name = "ToggleImage"
			ToggleImage.Parent = Toggle
			ToggleImage.BackgroundColor3 = Color3.fromRGB(225, 225, 225)
			ToggleImage.Position = UDim2.new(0, 415, 0, 8)
			ToggleImage.Size = UDim2.new(0, 45, 0, 20)

			UICorner_3.CornerRadius = UDim.new(0, 10)
			UICorner_3.Parent = ToggleImage

			Circle.Name = "Circle"
			Circle.Parent = ToggleImage
			Circle.BackgroundColor3 = Color3.fromRGB(227, 60, 60)
			Circle.Position = UDim2.new(0, 2, 0, 2)
			Circle.Size = UDim2.new(0, 16, 0, 16)
			
	        IMGTOG.Name = "Logo"
	        IMGTOG.Parent = Toggle
	        IMGTOG.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	        IMGTOG.BackgroundTransparency = 1.000
         	IMGTOG.Position = UDim2.new(0, 10, 0, 5)
	        IMGTOG.Size = UDim2.new(0, 25, 0, 25)
	        IMGTOG.Image = "rbxassetid://6022668898"
	
			UICorner_4.CornerRadius = UDim.new(0, 10)
			UICorner_4.Parent = Circle

			local check = {toggled = false ; loacker = true ; togfunction = {

				};}
				
			Button.MouseButton1Click:Connect(function()
				if toggled == false then
					toggled = true
					Circle:TweenPosition(UDim2.new(0,27,0,2),"Out","Sine",0.2,true)
					TweenService:Create(
						Circle,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = _G.Color}
					):Play()
				else
					toggled = false
					Circle:TweenPosition(UDim2.new(0,2,0,2),"Out","Sine",0.2,true)
					TweenService:Create(
						Circle,
						TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(227, 60, 110)}
					):Play()
				end
				pcall(callback,toggled)
			end)
			
			Button.MouseButton1Click:Connect(function()
					if check.toggled == false and check.loacker == true  then
						TweenService:Create(
							TextButton_3_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(255, 23, 46)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							Toggle_2_Toggle_UIStroke,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Color =  Color3.fromRGB(255, 23, 46)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_2_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TextButton_3_Toggle:TweenSizeAndPosition(UDim2.new(0, 17, 0, 17), UDim2.new(0.76, 0, 0.5, 0), "Out", "Quad", 0.1, true)
					elseif  check.loacker ==  true then
						TweenService:Create(
							Toggle_2_Toggle_UIStroke,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{Color =  Color3.fromRGB(0, 0, 0)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_3_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(255, 46, 46)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TweenService:Create(
							TextButton_2_Toggle,
							TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
							{BackgroundColor3 =  Color3.fromRGB(255, 255, 255)} -- UDim2.new(0, 128, 0, 25)
						):Play()
						TextButton_3_Toggle:TweenSizeAndPosition(UDim2.new(0, 17, 0, 17), UDim2.new(0, 10, 0.5, 0), "Out", "Quad", 0.1, true)
					end
					if  check.loacker == true  then
						check.toggled = not check.toggled
						callback(check.toggled)
					end
				end)
			if config == true then
				toggled = true
				Circle:TweenPosition(UDim2.new(0,27,0,2),"Out","Sine",0.4,true)
				TweenService:Create(
					Circle,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{BackgroundColor3 = _G.Color}
				):Play()
				pcall(callback,toggled)
			end
				
				local lockerframe = Instance.new("Frame")

				lockerframe.Name = "lockerframe"
				lockerframe.Parent = Toggle
				lockerframe.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				lockerframe.BackgroundTransparency = 1
				lockerframe.BorderSizePixel = 0
				lockerframe.Size = UDim2.new(0, 468, 0, 35)
				lockerframe.Position = UDim2.new(0.50, 0, 0.5, 0)
				lockerframe.AnchorPoint = Vector2.new(0.5, 0.5)

				local LockerImageLabel = Instance.new("ImageLabel")
				LockerImageLabel.Parent = lockerframe
				LockerImageLabel.BackgroundTransparency = 1.000
				LockerImageLabel.BorderSizePixel = 0
				LockerImageLabel.Position = UDim2.new(0.45, 10, 0.5, 0)
				LockerImageLabel.AnchorPoint = Vector2.new(0.5, 0.5)
				LockerImageLabel.Size = UDim2.new(0, 0, 0, 0)
				LockerImageLabel.Image = "http://www.roblox.com/asset/?id=6031082533"

				function check.togfunction:lock()
					TweenService:Create(
						lockerframe,
						TweenInfo.new(.4, Enum.EasingStyle.Sine, Enum.EasingDirection.Out,0.1),
						{BackgroundTransparency = 0.7}
					):Play()
					wait(0.5)
					TweenService:Create(
						LockerImageLabel,
						TweenInfo.new(.2, Enum.EasingStyle.Bounce, Enum.EasingDirection.Out,0.1),
						{Size = UDim2.new(0, 25, 0, 25)}
					):Play()
                    IMGTOG.Image = "rbxassetid://6031082533"
					check.loacker  = false
				end
				function check.togfunction:unlock()
					TweenService:Create(
						lockerframe,
						TweenInfo.new(.4, Enum.EasingStyle.Sine, Enum.EasingDirection.Out,0.1),
						{BackgroundTransparency = 1}
					):Play()
					wait(0.5)
					TweenService:Create(
						LockerImageLabel,
						TweenInfo.new(.2, Enum.EasingStyle.Bounce, Enum.EasingDirection.Out,0.1),
						{Size = UDim2.new(0, 0, 0, 0)}
					):Play()
					IMGTOG.Image = "rbxassetid://6022668898"
					check.loacker  = true
				end
				return  check.togfunction
		end
		
		function main:AddDropdown(text,option,callback)
			local isdropping = false
			local Dropdown = Instance.new("Frame")
			local UICorner = Instance.new("UICorner")
			local DropTitle = Instance.new("TextLabel")
			local DropScroll = Instance.new("ScrollingFrame")
			local UIListLayout = Instance.new("UIListLayout")
			local UIPadding = Instance.new("UIPadding")
			local DropButton = Instance.new("TextButton")
			local DropImage = Instance.new("ImageLabel")
			
			Dropdown.Name = "Dropdown"
			Dropdown.Parent = MainFramePage
			Dropdown.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			Dropdown.ClipsDescendants = true
			Dropdown.Size = UDim2.new(0, 470, 0, 35)
			
			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = Dropdown
			
			DropTitle.Name = "DropTitle"
			DropTitle.Parent = Dropdown
			DropTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			DropTitle.BackgroundTransparency = 1.000
			DropTitle.Size = UDim2.new(0, 470, 0, 31)
			DropTitle.Font = Enum.Font.GothamSemibold
			DropTitle.Text = text.. " : "
			DropTitle.TextColor3 = Color3.fromRGB(225, 225, 225)
			DropTitle.TextSize = 15.000
			
			DropScroll.Name = "DropScroll"
			DropScroll.Parent = DropTitle
			DropScroll.Active = true
			DropScroll.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			DropScroll.BackgroundTransparency = 1.000
			DropScroll.BorderSizePixel = 0
			DropScroll.Position = UDim2.new(0, 0, 0, 31)
			DropScroll.Size = UDim2.new(0, 470, 0, 100)
			DropScroll.CanvasSize = UDim2.new(0, 0, 0, 0)
			DropScroll.ScrollBarThickness = 3
			
			UIListLayout.Parent = DropScroll
			UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
			UIListLayout.Padding = UDim.new(0, 5)
			
			UIPadding.Parent = DropScroll
			UIPadding.PaddingLeft = UDim.new(0, 5)
			UIPadding.PaddingTop = UDim.new(0, 5)
			
			DropImage.Name = "DropImage"
			DropImage.Parent = Dropdown
			DropImage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			DropImage.BackgroundTransparency = 1.000
			DropImage.Position = UDim2.new(0, 445, 0, 6)
			DropImage.Rotation = 180.000
			DropImage.Size = UDim2.new(0, 20, 0, 20)
			DropImage.Image = "rbxassetid://6031090990"
			
			DropButton.Name = "DropButton"
			DropButton.Parent = Dropdown
			DropButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			DropButton.BackgroundTransparency = 1.000
			DropButton.Size = UDim2.new(0, 470, 0, 31)
			DropButton.Font = Enum.Font.SourceSans
			DropButton.Text = ""
			DropButton.TextColor3 = Color3.fromRGB(0, 0, 0)
			DropButton.TextSize = 14.000

			for i,v in next,option do
				local Item = Instance.new("TextButton")
	            local IMGTOG2  = Instance.new("ImageLabel")
	    
				Item.Name = "Item"
				Item.Parent = DropScroll
				Item.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Item.BackgroundTransparency = 1.000
				Item.Size = UDim2.new(0, 460, 0, 26)
				Item.Font = Enum.Font.GothamSemibold
				Item.Text = tostring(v)
				Item.TextColor3 = Color3.fromRGB(225, 225, 225)
				Item.TextSize = 13.000
				Item.TextTransparency = 0.500

	        IMGTOG2.Name = "Logo2"
	        IMGTOG2.Parent = Item
	        IMGTOG2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	        IMGTOG2.BackgroundTransparency = 1
         	IMGTOG2.Position = UDim2.new(0, 10, 0, 3)
	        IMGTOG2.Size = UDim2.new(0,25,0,26)
	        IMGTOG2.Image = "rbxassetid://6022668898"
	        
				Item.MouseEnter:Connect(function()
					TweenService:Create(
						Item,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end)

				Item.MouseLeave:Connect(function()
					TweenService:Create(
						Item,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0.5}
					):Play()
				end)

				Item.MouseButton1Click:Connect(function()
					isdropping = false
					Dropdown:TweenSize(UDim2.new(0,470,0,31),"Out","Quad",0.3,true)
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Rotation = 180}
					):Play()
					callback(Item.Text)
					DropTitle.Text = text.." : "..Item.Text
				end)
			end

			DropScroll.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 10)

			DropButton.MouseButton1Click:Connect(function()
				if isdropping == false then
					isdropping = true
					Dropdown:TweenSize(UDim2.new(0,470,0,131),"Out","Quad",0.3,true)
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Rotation = 0}
					):Play()
				else
					isdropping = false
					Dropdown:TweenSize(UDim2.new(0, 470, 0, 35),"Out","Quad",0.3,true)
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Rotation = 180}
					):Play()
				end
			end)


			local dropfunc = {}
			function dropfunc:Add(t)
				local Item = Instance.new("TextButton")
				Item.Name = "Item"
				Item.Parent = DropScroll
				Item.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Item.BackgroundTransparency = 1.000
				Item.Size = UDim2.new(0, 470, 0, 26)
				Item.Font = Enum.Font.GothamSemibold
				Item.Text = tostring(t)
				Item.TextColor3 = Color3.fromRGB(225, 225, 225)
				Item.TextSize = 13.000
				Item.TextTransparency = 0.500
	        
				Item.MouseEnter:Connect(function()
					TweenService:Create(
						Item,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end)

				Item.MouseLeave:Connect(function()
					TweenService:Create(
						Item,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0.5}
					):Play()
				end)
				
				Item.MouseButton1Click:Connect(function()
					isdropping = false
					Dropdown:TweenSize(UDim2.new(0,470,0,31),"Out","Quad",0.3,true)
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Rotation = 180}
					):Play()
					callback(Item.Text)
					DropTitle.Text = text.." : "..Item.Text
				end)
			end
				
			function dropfunc:Clear()
				DropTitle.Text = tostring(text).." : "
				isdropping = false
				Dropdown:TweenSize(UDim2.new(0,470,0,31),"Out","Quad",0.3,true)
				TweenService:Create(
					DropImage,
					TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{Rotation = 180}
				):Play()
				for i,v in next, DropScroll:GetChildren() do
					if v:IsA("TextButton") then
						v:Destroy()
					end
				end
			end
			return dropfunc
		end

		function main:AddSlider(text,min,max,set,callback)
			local Slider = Instance.new("Frame")
			local slidercorner = Instance.new("UICorner")
			local sliderr = Instance.new("Frame")
			local sliderrcorner = Instance.new("UICorner")
			local SliderLabel = Instance.new("TextLabel")
			local HAHA = Instance.new("Frame")
			local AHEHE = Instance.new("TextButton")
			local bar = Instance.new("Frame")
			local bar1 = Instance.new("Frame")
			local bar1corner = Instance.new("UICorner")
			local barcorner = Instance.new("UICorner")
			local circlebar = Instance.new("Frame")
			local UICorner = Instance.new("UICorner")
			local slidervalue = Instance.new("Frame")
			local valuecorner = Instance.new("UICorner")
			local TextBox = Instance.new("TextBox")
			local UICorner_2 = Instance.new("UICorner")

			Slider.Name = "Slider"
			Slider.Parent = MainFramePage
			Slider.BackgroundColor3 = _G.Color
			Slider.BackgroundTransparency = 0
			Slider.Size = UDim2.new(0, 470, 0, 51)

			slidercorner.CornerRadius = UDim.new(0, 5)
			slidercorner.Name = "slidercorner"
			slidercorner.Parent = Slider

			sliderr.Name = "sliderr"
			sliderr.Parent = Slider
			sliderr.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			sliderr.Position = UDim2.new(0, 1, 0, 1)
			sliderr.Size = UDim2.new(0, 468, 0, 49)

			sliderrcorner.CornerRadius = UDim.new(0, 5)
			sliderrcorner.Name = "sliderrcorner"
			sliderrcorner.Parent = sliderr

			SliderLabel.Name = "SliderLabel"
			SliderLabel.Parent = sliderr
			SliderLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			SliderLabel.BackgroundTransparency = 1.000
			SliderLabel.Position = UDim2.new(0, 15, 0, 0)
			SliderLabel.Size = UDim2.new(0, 180, 0, 26)
			SliderLabel.Font = Enum.Font.GothamSemibold
			SliderLabel.Text = text
			SliderLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
			SliderLabel.TextSize = 16.000
			SliderLabel.TextTransparency = 0
			SliderLabel.TextXAlignment = Enum.TextXAlignment.Left

			HAHA.Name = "HAHA"
			HAHA.Parent = sliderr
			HAHA.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			HAHA.BackgroundTransparency = 1.000
			HAHA.Size = UDim2.new(0, 468, 0, 29)

			AHEHE.Name = "AHEHE"
			AHEHE.Parent = sliderr
			AHEHE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			AHEHE.BackgroundTransparency = 1.000
			AHEHE.Position = UDim2.new(0, 10, 0, 35)
			AHEHE.Size = UDim2.new(0, 448, 0, 5)
			AHEHE.Font = Enum.Font.SourceSans
			AHEHE.Text = ""
			AHEHE.TextColor3 = Color3.fromRGB(0, 0, 0)
			AHEHE.TextSize = 14.000

			bar.Name = "bar"
			bar.Parent = AHEHE
			bar.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
			bar.Size = UDim2.new(0, 448, 0, 5)

			bar1.Name = "bar1"
			bar1.Parent = bar
			bar1.BackgroundColor3 = _G.Color
			bar1.BackgroundTransparency = 0
			bar1.Size = UDim2.new(set/max, 0, 0, 5)

			bar1corner.CornerRadius = UDim.new(0, 5)
			bar1corner.Name = "bar1corner"
			bar1corner.Parent = bar1

			barcorner.CornerRadius = UDim.new(0, 5)
			barcorner.Name = "barcorner"
			barcorner.Parent = bar

			circlebar.Name = "circlebar"
			circlebar.Parent = bar1
			circlebar.BackgroundColor3 = Color3.fromRGB(225, 225, 225)
			circlebar.Position = UDim2.new(1, -2, 0, -3)
			circlebar.Size = UDim2.new(0, 10, 0, 10)

			UICorner.CornerRadius = UDim.new(0, 100)
			UICorner.Parent = circlebar

			slidervalue.Name = "slidervalue"
			slidervalue.Parent = sliderr
			slidervalue.BackgroundColor3 = _G.Color
			slidervalue.BackgroundTransparency = 0
			slidervalue.Position = UDim2.new(0, 395, 0, 5)
			slidervalue.Size = UDim2.new(0, 65, 0, 18)

			valuecorner.CornerRadius = UDim.new(0, 5)
			valuecorner.Name = "valuecorner"
			valuecorner.Parent = slidervalue

			TextBox.Parent = slidervalue
			TextBox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
			TextBox.Position = UDim2.new(0, 1, 0, 1)
			TextBox.Size = UDim2.new(0, 63, 0, 16)
			TextBox.Font = Enum.Font.GothamSemibold
			TextBox.TextColor3 = Color3.fromRGB(225, 225, 225)
			TextBox.TextSize = 9.000
			TextBox.Text = set
			TextBox.TextTransparency = 0

			UICorner_2.CornerRadius = UDim.new(0, 5)
			UICorner_2.Parent = TextBox

			local mouse = game.Players.LocalPlayer:GetMouse()
			local uis = game:GetService("UserInputService")

			if Value == nil then
				Value = set
				pcall(function()
					callback(Value)
				end)
			end
			
			AHEHE.MouseButton1Down:Connect(function()
				Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min)) or 0
				pcall(function()
					callback(Value)
				end)
				bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
				circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
				moveconnection = mouse.Move:Connect(function()
					TextBox.Text = Value
					Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min))
					pcall(function()
						callback(Value)
					end)
					bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
					circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
				end)
				releaseconnection = uis.InputEnded:Connect(function(Mouse)
					if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
						Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min))
						pcall(function()
							callback(Value)
						end)
						bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
						circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
						moveconnection:Disconnect()
						releaseconnection:Disconnect()
					end
				end)
			end)
			releaseconnection = uis.InputEnded:Connect(function(Mouse)
				if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
					Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min))
					TextBox.Text = Value
				end
			end)

			TextBox.FocusLost:Connect(function()
				if tonumber(TextBox.Text) > max then
					TextBox.Text  = max
				end
				bar1.Size = UDim2.new((TextBox.Text or 0) / max, 0, 0, 5)
				circlebar.Position = UDim2.new(1, -2, 0, -3)
				TextBox.Text = tostring(TextBox.Text and math.floor( (TextBox.Text / max) * (max - min) + min) )
				pcall(callback, TextBox.Text)
			end)
		end

		function main:AddTextbox(text,disappear,callback)
			local Textbox = Instance.new("Frame")
			local TextboxCorner = Instance.new("UICorner")
			local Textboxx = Instance.new("Frame")
			local TextboxxCorner = Instance.new("UICorner")
			local TextboxLabel = Instance.new("TextLabel")
			local txtbtn = Instance.new("TextButton")
			local RealTextbox = Instance.new("TextBox")
			local UICorner = Instance.new("UICorner")

			Textbox.Name = "Textbox"
			Textbox.Parent = MainFramePage
			Textbox.BackgroundColor3 = _G.Color
			Textbox.BackgroundTransparency = 0
			Textbox.Size = UDim2.new(0, 470, 0, 37)

			TextboxCorner.CornerRadius = UDim.new(0, 5)
			TextboxCorner.Name = "TextboxCorner"
			TextboxCorner.Parent = Textbox

			Textboxx.Name = "Textboxx"
			Textboxx.Parent = Textbox
			Textboxx.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			Textboxx.Position = UDim2.new(0, 1, 0, 1)
			Textboxx.Size = UDim2.new(0, 468, 0, 35)

			TextboxxCorner.CornerRadius = UDim.new(0, 5)
			TextboxxCorner.Name = "TextboxxCorner"
			TextboxxCorner.Parent = Textboxx

			TextboxLabel.Name = "TextboxLabel"
			TextboxLabel.Parent = Textbox
			TextboxLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			TextboxLabel.BackgroundTransparency = 1.000
			TextboxLabel.Position = UDim2.new(0, 15, 0, 1)
			TextboxLabel.Text = text
			TextboxLabel.Size = UDim2.new(0, 151, 0, 31)
			TextboxLabel.Font = Enum.Font.GothamSemibold
			TextboxLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
			TextboxLabel.TextSize = 16.000
			TextboxLabel.TextTransparency = 0
			TextboxLabel.TextXAlignment = Enum.TextXAlignment.Left

			txtbtn.Name = "txtbtn"
			txtbtn.Parent = Textbox
			txtbtn.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			txtbtn.BackgroundTransparency = 1.000
			txtbtn.Position = UDim2.new(0, 1, 0, 1)
			txtbtn.Size = UDim2.new(0, 468, 0, 29)
			txtbtn.Font = Enum.Font.SourceSans
			txtbtn.Text = ""
			txtbtn.TextColor3 = Color3.fromRGB(0, 0, 0)
			txtbtn.TextSize = 14.000

			RealTextbox.Name = "RealTextbox"
			RealTextbox.Parent = Textbox
			RealTextbox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
			RealTextbox.BackgroundTransparency = 0
			RealTextbox.Position = UDim2.new(0, 360, 0, 6)
			RealTextbox.Size = UDim2.new(0, 100, 0, 24)
			RealTextbox.Font = Enum.Font.GothamSemibold
			RealTextbox.Text = ""
			RealTextbox.TextColor3 = Color3.fromRGB(225, 225, 225)
			RealTextbox.TextSize = 11.000
			RealTextbox.TextTransparency = 0

			RealTextbox.FocusLost:Connect(function()
				callback(RealTextbox.Text)
				if disappear then
					RealTextbox.Text = ""
				end
			end)

			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = RealTextbox
		end
		function main:AddLabel(text)
			local Label = Instance.new("TextLabel")
			local PaddingLabel = Instance.new("UIPadding")
			local labell = {}
	
			Label.Name = "Label"
			Label.Parent = MainFramePage
			Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Label.BackgroundTransparency = 1.000
			Label.Size = UDim2.new(0, 470, 0, 20)
			Label.Font = Enum.Font.GothamSemibold
			Label.TextColor3 = Color3.fromRGB(225, 225, 225)
			Label.TextSize = 16.000
			Label.Text = text
			Label.TextXAlignment = Enum.TextXAlignment.Left

			PaddingLabel.PaddingLeft = UDim.new(0,15)
			PaddingLabel.Parent = Label
			PaddingLabel.Name = "PaddingLabel"
	
			function labell:Set(newtext)
				Label.Text = newtext
			end

			return labell
		end
		function main:AddSeperator(text)
			local Seperator = Instance.new("Frame")
			local Sep1 = Instance.new("Frame")
			local Sep2 = Instance.new("TextLabel")
			local Sep3 = Instance.new("Frame")
			
			Seperator.Name = "Seperator"
			Seperator.Parent = MainFramePage
			Seperator.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Seperator.BackgroundTransparency = 1.000
			Seperator.Size = UDim2.new(0, 470, 0, 20)
			
			Sep1.Name = "Sep1"
			Sep1.Parent = Seperator
			Sep1.BackgroundColor3 = _G.Color
			Sep1.BorderSizePixel = 0
			Sep1.Position = UDim2.new(0, 0, 0, 10)
			Sep1.Size = UDim2.new(0, 80, 0, 1)
			
			Sep2.Name = "Sep2"
			Sep2.Parent = Seperator
			Sep2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Sep2.BackgroundTransparency = 1.000
			Sep2.Position = UDim2.new(0, 185, 0, 0)
			Sep2.Size = UDim2.new(0, 100, 0, 20)
			Sep2.Font = Enum.Font.GothamSemibold
			Sep2.Text = text
			Sep2.TextColor3 = Color3.fromRGB(255, 255, 255)
			Sep2.TextSize = 14.000
			
			Sep3.Name = "Sep3"
			Sep3.Parent = Seperator
			Sep3.BackgroundColor3 = _G.Color
			Sep3.BorderSizePixel = 0
			Sep3.Position = UDim2.new(0, 390, 0, 10)
			Sep3.Size = UDim2.new(0, 80, 0, 1)
		end

		function main:AddLine()
			local Linee = Instance.new("Frame")
			local Line = Instance.new("Frame")
			
			Linee.Name = "Linee"
			Linee.Parent = MainFramePage
			Linee.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Linee.BackgroundTransparency = 1.000
			Linee.Position = UDim2.new(0, 0, 0.119999997, 0)
			Linee.Size = UDim2.new(0, 470, 0, 20)
			
			Line.Name = "Line"
			Line.Parent = Linee
			Line.BackgroundColor3 = Color3.fromRGB(225, 225, 225)
			Line.BorderSizePixel = 0
			Line.Position = UDim2.new(0, 0, 0, 10)
			Line.Size = UDim2.new(0, 470, 0, 1)
		end
		return main
	end
	return uitab
end

local win = library:AddWindow("Rocket","",Enum.KeyCode.RightControl)
Tab1 = win:AddTab("General")
Item = win:AddTab("Item")
Tab2 = win:AddTab("Combat")
Shop = win:AddTab("Shop")
Tab4 = win:AddTab("Teleport")
Tab5 = win:AddTab("Dungeon")
Tab6 = win:AddTab("Devil Fruits")
Tab7 = win:AddTab("Visual")
Settings = win:AddTab("Settings")

local placeId = game.PlaceId
				if placeId == 2753915549 then
					world1 = true
				elseif placeId == 4442272183 then
					world2 = true
					_G.EN = true
				elseif placeId == 7449423635 then
					world3 = true
					_G.EN = true
				else
					game.Players.LocalPlayer:Kick("LoL")
				end

Settings:AddSeperator("Farming Settings")
Tab1:AddSeperator("Auto Farm")

				Tab1:AddToggle("Auto Farm Level",false,function(value)
					_G.AutoFarm = value
					ps = value
				end)
				Tab1:AddButton("Redeem All Code",function(value)
					_G.RDAC = value
				end)
spawn(function()
if _G.RDAC == true then
	function UseCode(Text)
                     game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
                end
                UseCode("UPD16")
                UseCode("2BILLION")
                UseCode("UPD15")
                UseCode("FUDD10")
                UseCode("BIGNEWS")
                UseCode("THEGREATACE")
                UseCode("SUB2GAMERROBOT_EXP1")
                UseCode("StrawHatMaine")
                UseCode("Sub2OfficialNoobie")
                UseCode("SUB2NOOBMASTER123")
                UseCode("Sub2Daigrock")
                UseCode("Axiore")
                UseCode("TantaiGaming")
                UseCode("STRAWHATMAINE")
end
end)
				Settings:AddToggle("Auto Set Spawn Point",false,function(value)
				_G.AutoSetSpawn = value
				end)
local REJOIN = Settings:AddToggle("Auto Rejoin",true,function(vu)
   _G.AutoRejoin = vu
end)

	spawn(function()
	    while wait() do
	        if _G.AutoRejoin then
	                getgenv().rejoin = game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(child)
                        if child.Name == 'ErrorPrompt' and child:FindFirstChild('MessageArea') and child.MessageArea:FindFirstChild("ErrorFrame") then
                            game:GetService("TeleportService"):Teleport(game.PlaceId)
                        end
                    end)
	            end
	        end
	end)
				local LOCK = Tab1:AddToggle("Secret",true,function(value)
				ps = value
				end)


				spawn(function()
					pcall(function()
						while wait(3) do
							if _G.AutoSetSpawn then
							   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
							end
						end
					end)
				end)


				--[[Tab1:AddButton("Godmode ( Ban Risk )",function()
					if game.Players.LocalPlayer.Character.Humanoid.Health > 0 or game.Players.LocalPlayer.PlayerGui.Main.HP.TextLabel.Text == "Health 100/100" then
						_G.StartBypass = true
						game.Players.LocalPlayer.Character.Humanoid:SetStateEnabled(15,false);
						if world1 then           
							_G.Autohaki_autofarm = true
							for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
								if v.Name == "Galley Captain [Lv. 650]" then
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
						end
							end
						elseif world2 then
							_G.Autohaki_autofarm = true
							for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
								if v.Name == "Marine Captain [Lv. 900]" then
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
				end
							end
						elseif world3 then
							_G.Autohaki_autofarm = true
							for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
								if v.Name == "Giant Islander [Lv. 1650]" then
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
				end
							end
						end
					end
				end)]]--

				spawn(function()
					while wait(.1) do
						if _G.Autohaki_autofarm then 
							if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
							end
						end
						if _G.Legendary_Sworld then
							local args = {
								[1] = "LegendarySwordDealer",
								[2] = "2"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						end 
						if _G.AutoEnhancement then
							local args = {
								[1] = "ColorsDealer",
								[2] = "2"
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						end 
					end
				end)


				function Hop()
				local pages = ""
				local stopsearch = false
				function TPReturner()
					local Site;
					if pages == "" then
						Site = game:GetService("HttpService"):JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. game.PlaceId .. '/servers/Public?sortOrder=Asc&limit=100'))
					else
						Site = game:GetService("HttpService"):JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. game.PlaceId .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. pages))
					end
					if Site.nextPageCursor and Site.nextPageCursor ~= "null" then
						pages = Site.nextPageCursor
					end
					for i,v in pairs(Site["data"]) do
						if v.playing < v.maxPlayers and v.ping < 100 then
							stopsearch = true
							print(v.id)
							game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, v.id)
							break
						end
					end
				end

				function Teleport()
					while task.wait() do
						pcall(function()
							if not stopsearch then
								TPReturner()
								if pages ~= "" then
									TPReturner()
								end
							end
						end)
						if stopsearch then
							break
						end
					end
				end

				Teleport()
				end

				function hop1()
					local PlaceID = game.PlaceId
					local AllIDs = {}
					local foundAnything = ""
					local actualHour = os.date("!*t").hour
					local Deleted = false
					function TPReturner()
						local Site;
						if foundAnything == "" then
							Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
						else
							Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
						end
						local ID = ""
						if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
							foundAnything = Site.nextPageCursor
						end
						local num = 0;
						for i,v in pairs(Site.data) do
							local Possible = true
							ID = tostring(v.id)
							if tonumber(v.maxPlayers) > tonumber(v.playing) then
								for _,Existing in pairs(AllIDs) do
									if num ~= 0 then
										if ID == tostring(Existing) then
											Possible = false
										end
									else
										if tonumber(actualHour) ~= tonumber(Existing) then
											local delFile = pcall(function()
												-- delfile("NotSameServers.json")
												AllIDs = {}
												table.insert(AllIDs, actualHour)
											end)
										end
									end
									num = num + 1
								end
								if Possible == true then
									table.insert(AllIDs, ID)
									wait()
									pcall(function()
										-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
										wait()
										game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
									end)
									wait(.1)
								end
							end
						end
					end
					function Teleport() 
						while wait() do
							pcall(function()
								TPReturner()
								if foundAnything ~= "" then
									TPReturner()
								end
							end)
						end
					end
					Teleport()
				end

				spawn(function()
					while wait() do
						pcall(function()
							if _G.StartBypass then
								wait(6)
								if game.Players.LocalPlayer.Character.Humanoid.Health == game.Players.LocalPlayer.Character.Humanoid.MaxHealth then
									_G.Bypassed = false
								elseif game.Players.LocalPlayer.Character.Humanoid.Health <= 0 then
									_G.Bypassed = true
								end
							end
						end)
					end
				end)

				Wapon = {}
				for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
					if v:IsA("Tool") then
						table.insert(Wapon ,v.Name)
					end
				end
				for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
					if v:IsA("Tool") then
						table.insert(Wapon, v.Name)
					end
				end
				
Tab1:AddSeperator("Select Weapon")

				local SlcWP = Tab1:AddDropdown("Select Weapon",Wapon,function(t)
				_G.SelectToolWeapon = t
				end)

				Tab1:AddButton("Refresh Weapon",function()
				 SlcWP:Clear()
					wait()
					for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
						if v:IsA("Tool") then
							SlcWP:Add(v.Name)
						end
					end
				end)
				
Tab1:AddSeperator("Others")

				local FUNC2 = Tab1:AddToggle("Auto Random Surprise",false,function(value)
				_G.AutoRandomSurprise = value
				end)

				spawn(function()
					pcall(function()
						while wait() do
							if _G.AutoRandomSurprise then    
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
							end
						end
					end)
				end)


    local Client = game.Players.LocalPlayer
    local STOP = require(Client.PlayerScripts.CombatFramework.Particle)
    local STOPRL = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
                      
				local FUNC3 = Settings:AddToggle("No Animation Attack",false,function(value)
                      _G.A = value
                      spawn(function()
                        if not shared.orl then 
                            shared.orl = STOPRL.wrapAttackAnimationAsync 
                        end
                        if not shared.cpc then 
                            shared.cpc = STOP.play 
                        end
                        if _G.A then
                            STOPRL.wrapAttackAnimationAsync = function(a,b,c,d,func)
                                local Hits = STOPRL.getBladeHits(b,c,d)
                                if Hits then
                                    STOP.play = function()
                                end
                            a:Play(0.01,0.01,0.01)
                            func(Hits)
                            STOP.play = shared.cpc
                            wait(a.length * 0.5)
                            a:Stop()
                        end
                        end
                        end
                    end)
				end)


				local FUNC4 = Settings:AddToggle("Fast Attack",false,function(value)
				_G.FastAttack=value
				end)
				
				local up = getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework))

				function round(number, decimals)
				  local power = 10^decimals
				  return math.floor(number * power) / power
				end



				RigC = up[2]

				local mt = getrawmetatable(game)
				local old = mt.__namecall
				setreadonly(mt, false)
				mt.__namecall = newcclosure(function(...)
					local args = {...}
					if tostring(getnamecallmethod()) == "FireServer" then
						if tostring(args[1]) == "RigControllerEvent" and type(args[4]) == "number" then
							args[4] = #RigC.activeController.anims.basic
						end
						return old(unpack(args))
					end
					return old(...)
				end)
				
local CameraShaker = require(game.ReplicatedStorage.Util.CameraShaker)
local Attack = 0.1
for i,v in pairs(getreg()) do
    if typeof(v) == "function" and getfenv(v).script == game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework then
        for x,w in pairs(debug.getupvalues(v)) do
             if typeof(w) == "table" then
                spawn(function()
                    game:GetService("RunService").Heartbeat:Connect(function()
                        if _G.FastAttack then
                            pcall(function()
								if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") then
									w.activeController.timeToNextAttack = 3
								elseif game.Players.LocalPlayer.Character:FindFirstChild("Electro") then
									w.activeController.timeToNextAttack = 2
								else
									w.activeController.timeToNextAttack = 0
								end             
                                CameraShaker:Stop()
                                w.activeController.attacking = false
                                w.activeController.increment = 3
                                w.activeController.blocking = false                            
                                w.activeController.hitboxMagnitude = 100
    		                    w.activeController.humanoid.AutoRotate = true
    	                      	w.activeController.activeController.focusStart = 0
                                  round(w,0)
									round(w,0)
                                end)
                        end
                    end)
                end)
            end
        end
    end
end

spawn(function()
   pcall(function()
       while task.wait() do
           if _G.FastAttack then
           Click()
           end
        end
    end) 
end)




				function Click()
					game:GetService('VirtualUser'):CaptureController()
					game:GetService('VirtualUser'):ClickButton1(Vector2.new(1280, 672), game.Workspace.Camera.CFrame)
				end

				local FUNC5 = Tab1:AddToggle("Auto Select / Equiq Weapon",false,function(value)
				AutoEquip = value
					while AutoEquip do wait()
						pcall(function()
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") then
								EquipWeapon("Combat")
							_G.SelectToolWeapon = "Combat"
							
							elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") then
							EquipWeapon("Black Leg")
							_G.SelectToolWeapon = "Black Leg"
							
							elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") then
							EquipWeapon("Death Step")
							_G.SelectToolWeapon = "Death Step"
							
							elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") then
							EquipWeapon("Electro")
									_G.SelectToolWeapon = "Electro"
									
							elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman  Karate") then
							EquipWeapon("Fishman  Karate")
							_G.SelectToolWeapon = "Fishman  Karate"
							
							elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman  Karate") then
							EquipWeapon("Sharkman  Karate")
							_G.SelectToolWeapon = "Sharkman  Karate"
							
							elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") then
							EquipWeapon("Superhuman")
							_G.SelectToolWeapon = "Superhuman"
							
							elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Eletric Claw") then
							EquipWeapon("Eletric Claw")
							_G.SelectToolWeapon = "Eletric Claw"
							
							elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") then
							EquipWeapon("Dragon Claw")
							_G.SelectToolWeapon = "Dragon Claw"
							
							elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") then
							EquipWeapon("Dragon Talon")
							_G.SelectToolWeapon = "Dragon Talon"
									
									end
						end)
					end
				end)


				function EquipWeapon(ToolSe)
					if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
						Tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
						wait(.1)
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(Tool)
					end
				end
				function EquipTool(ToolSe)
					if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
						Tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
						wait(.1)
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(Tool)
					end
				end


Settings:AddSeperator("Level")
                Settings:AddSlider("Lock at Level",1,2300,500,function(value)
					LevelLock = value
				end)
				local FUNC6 = Settings:AddToggle("Lock Level",false,function(value)
				_G.StartLockLevel = value
					while _G.StartLockLevel do wait()
						pcall(function()
							if _G.StartLockLevel then
								if game.Players.LocalPlayer.Data.Level.Value == LevelLock then
									game.Players.LocalPlayer:Kick("FULLY LOCK LEVEL")
								end
							end
						end)
					end
				end)
				
Settings:AddButton("Lock Func : 1",function()
    FUNC2:lock()
    FUNC6:lock()
    FUNC3:lock()
    FUNC4:lock()
    FUNC5:lock()
    FUNC6:lock()
end)
Settings:AddButton("UnLock Func : 1",function()
    FUNC2:unlock()
    FUNC6:unlock()
    FUNC3:unlock()
    FUNC4:unlock()
    FUNC5:unlock()
    FUNC6:unlock()    
end)

				Item:AddToggle("Auto New World",false,function(value)
				_G.AutoNew_Ws= value
				_G.Autohaki_autofarm = value
				_G.Lock = value
							while wait() do
							local g1=game local p1=g1:GetService('Players') local l1=p1.LocalPlayer local c1=l1.Character local h1=c1:FindFirstChild('Humanoid') local h2=c1:FindFirstChild('HumanoidRootPart') local v0=true local v1='BodyVelocity'
							local x=function() while task.wait() do if _G.Lock then if h2 then if h2:FindFirstChild(v1) then return elseif not h2:FindFirstChild(v1) then local vc=Instance.new(v1, h2) vc.MaxForce=Vector3.new(1, 1, 1)*math.huge vc.Velocity=Vector3.new(0, 0, 0) end end else if h2 then if h2:FindFirstChild(v1) then local aa=h2:FindFirstChild(v1) aa:Destroy() end end end end end spawn(function() pcall(x) end)
				end
				end)

				 Item:AddToggle("Auto Bartlio Quest",false,function(value)
				_G.AutoQuestBartilo = value
				_G.Lock = value
							while wait() do
							local g1=game local p1=g1:GetService('Players') local l1=p1.LocalPlayer local c1=l1.Character local h1=c1:FindFirstChild('Humanoid') local h2=c1:FindFirstChild('HumanoidRootPart') local v0=true local v1='BodyVelocity'
							local x=function() while task.wait() do if _G.Lock then if h2 then if h2:FindFirstChild(v1) then return elseif not h2:FindFirstChild(v1) then local vc=Instance.new(v1, h2) vc.MaxForce=Vector3.new(1, 1, 1)*math.huge vc.Velocity=Vector3.new(0, 0, 0) end end else if h2 then if h2:FindFirstChild(v1) then local aa=h2:FindFirstChild(v1) aa:Destroy() end end end end end spawn(function() pcall(x) end)
				end
				end)

				 Item:AddToggle("Auto Rengoku",false,function(value)
				_G.AUTORENGOKU = value
				_G.Lock = value
							while wait() do
							local g1=game local p1=g1:GetService('Players') local l1=p1.LocalPlayer local c1=l1.Character local h1=c1:FindFirstChild('Humanoid') local h2=c1:FindFirstChild('HumanoidRootPart') local v0=true local v1='BodyVelocity'
							local x=function() while task.wait() do if _G.Lock then if h2 then if h2:FindFirstChild(v1) then return elseif not h2:FindFirstChild(v1) then local vc=Instance.new(v1, h2) vc.MaxForce=Vector3.new(1, 1, 1)*math.huge vc.Velocity=Vector3.new(0, 0, 0) end end else if h2 then if h2:FindFirstChild(v1) then local aa=h2:FindFirstChild(v1) aa:Destroy() end end end end end spawn(function() pcall(x) end)
				end
				end)
				 Item:AddToggle("AutoHolyTorch",false,function(value)
				if not world3 then
						game.Players.LocalPlayer:Kick('Go to Sea3')
					else
						_G.AutoHolyTorch = value
					end 
					_G.Autohaki_autofarm = value
				 end)
			
			
						    Item:AddToggle("Auto Evo Race",nil,function(value)
                   _G.AutoEvoRace = value
			    end)
             
             spawn(function()
        pcall(function()
            while wait(.1) do
                if _G.AutoEvoRace then
                    if not game:GetService("Players").LocalPlayer.Data.Race:FindFirstChild("Evolved") then
                        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 0 then
                            TP2FF(CFrame.new(-2779.83521, 72.9661407, -3574.02002, -0.730484903, 6.39014104e-08, -0.68292886, 3.59963224e-08, 1, 5.50667032e-08, 0.68292886, 1.56424669e-08, -0.730484903))
                            if (Vector3.new(-2779.83521, 72.9661407, -3574.02002) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 then
                                wait(1.3)
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","2")
                            end
                        elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 1 then
                            pcall(function()
                                if not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 1") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 1") then
                                    TP2FF(game:GetService("Workspace").Flower1.CFrame)
                                elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 2") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 2") then
                                    TP2FF(game:GetService("Workspace").Flower2.CFrame)
                                elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 3") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 3") then
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Zombie [Lv. 950]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Zombie [Lv. 950]" then
                                                repeat task.wait()
                                                    EquipWeapon(_G.SelectToolWeapon)
                                                    TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(5,10,7))
                                                    v.HumanoidRootPart.CanCollide = false
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    _G.FastAttack = true
                                                    PosMonEvo = v.HumanoidRootPart.CFrame
                                                    StartEvoMagnet = true
                                                until game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 3") or not v.Parent or v.Humanoid.Health <= 0 or _G.AutoEvoRace == false
                                                StartEvoMagnet = false
                                            end
                                        end
                                    else
                                        StartEvoMagnet = false
                                        TP2FF(CFrame.new(-5685.9233398438, 48.480125427246, -853.23724365234))
                                    end
                                end
                            end)
                        elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 2 then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","3")
                        end
                    end
                end
            end
        end)
    end)
			
                Item:AddToggle("Auto Musketeer Hat",false,function(value)
                         _G.AutoMusketeerHat = value
                end)
           
           Item:AddToggle("Auto Rainbow Haki",false,function(value)
                _G.AutorainbowHaki = value
           end)
             
             Item:AddToggle("Auto Farm Ectoplasm",false,function(value)
                  _G.AutoEctoplasm = value
                 end)
                 
                 spawn(function()
        pcall(function()
            while wait() do
                if _G.AutoEctoplasm then
                    if game:GetService("Workspace").Enemies:FindFirstChild("Ship Deckhand [Lv. 1250]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Steward [Lv. 1300]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Officer [Lv. 1325]") then
                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                            if string.find(v.Name, "Ship") then
                                repeat task.wait()
                                    EquipWeapon(_G.SelectToolWeapon)
                                    if string.find(v.Name,"Ship") then
                                        v.HumanoidRootPart.CanCollide = false
                                        v.Head.CanCollide = false
                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                        TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
                                        _G.FastAttack = true
                                        EctoplasmMon = v.HumanoidRootPart.CFrame
                                        StartEctoplasmMagnet = true
                                    else
                                        StartEctoplasmMagnet = false
                                        TP2FF(CFrame.new(911.35827636719, 125.95812988281, 33159.5390625))
                                    end
                                until _G.AutoEctoplasm == false or not v.Parent or v.Humanoid.Health <= 0
                            end
                        end
                    else
                        StartEctoplasmMagnet = false
                        local Distance = (Vector3.new(911.35827636719, 125.95812988281, 33159.5390625) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
                        if Distance > 18000 then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                        end
                        TP2FF(CFrame.new(911.35827636719, 125.95812988281, 33159.5390625))
                    end
                end
            end
        end)
                 end)

 spawn(function()
        while task.wait() do
            pcall(function()
                     for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                           if _G.AutoEctoplasm and StartEctoplasmMagnet then
                            if string.find(v.Name, "Ship") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - EctoplasmMon.Position).Magnitude <= 250 then
                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                v.HumanoidRootPart.CFrame = EctoplasmMon
                                v.Humanoid:ChangeState(14)
                                v.HumanoidRootPart.CanCollide = false
                                v.Head.CanCollide = false
                                if v.Humanoid:FindFirstChild("Animator") then
                                    v.Humanoid.Animator:Destroy()
                                end
                                sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
                            end
                       end
                    end
                 end)
              end
            end)
            
            spawn(function()
        while task.wait() do
            pcall(function()
                     for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                                       if _G.AutoMusketeerHat and StartMagnetMusketeerhat then
                            if v.Name == "Forest Pirate [Lv. 1825]" and (v.HumanoidRootPart.Position - MusketeerHatMon.Position).Magnitude <= 250 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                v.Humanoid:ChangeState(14)
                                v.HumanoidRootPart.CanCollide = false
                                v.Head.CanCollide = false
                                v.HumanoidRootPart.CFrame = MusketeerHatMon
                                if v.Humanoid:FindFirstChild("Animator") then
                                    v.Humanoid.Animator:Destroy()
                                end
                                sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
                            end
                             end
                       end
                     end)
                end
            end)

 spawn(function()
        while task.wait() do
            pcall(function()
                    if _G.AutoEvoRace and StartEvoMagnet then
                            if v.Name == "Zombie [Lv. 950]" and (v.HumanoidRootPart.Position - PosMonEvo.Position).Magnitude <= 250 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                v.Humanoid:ChangeState(14)
                                v.HumanoidRootPart.CanCollide = false
                                v.Head.CanCollide = false
                                v.HumanoidRootPart.CFrame = PosMonEvo
                                if v.Humanoid:FindFirstChild("Animator") then
                                    v.Humanoid.Animator:Destroy()
                                end
                                
                                sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRadius", math.huge)
                            end
                        end
                 end)
          end
    end)
            
             spawn(function()
        pcall(function()
            while wait(.1) do
                if _G.AutorainbowHaki then
                    if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                        TP2FF(CFrame.new(-11892.0703125, 930.57672119141, -8760.1591796875))
                        if (Vector3.new(-11892.0703125, 930.57672119141, -8760.1591796875) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 30 then
                            wait(1.5)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("HornedMan","Bet")
                        end
                    elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true and string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Stone") then
                        if game:GetService("Workspace").Enemies:FindFirstChild("Stone [Lv. 1550] [Boss]") then
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                if v.Name == "Stone [Lv. 1550] [Boss]" then
                                    OldCFrameRainbow = v.HumanoidRootPart.CFrame
                                    repeat task.wait()
                                        EquipWeapon(_G.SelectToolWeapon)
                                        TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(5,10,7))
                                        v.HumanoidRootPart.CanCollide = false
                                        v.HumanoidRootPart.CFrame = OldCFrameRainbow
                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                        _G.FastAttack = true
                                        sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                                    until _G.AutorainbowHaki == false or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                end
                            end
                        else
                            TP2FF(CFrame.new(-1086.11621, 38.8425903, 6768.71436, 0.0231462717, -0.592676699, 0.805107772, 2.03251839e-05, 0.805323839, 0.592835128, -0.999732077, -0.0137055516, 0.0186523199))
                        end
                    elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true and string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Island Empress") then
                        if game:GetService("Workspace").Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                if v.Name == "Island Empress [Lv. 1675] [Boss]" then
                                    OldCFrameRainbow = v.HumanoidRootPart.CFrame
                                    repeat task.wait()
                                        EquipWeapon(_G.SelectToolWeapon)
                                        topos(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
                                        v.HumanoidRootPart.CanCollide = false
                                        v.HumanoidRootPart.CFrame = OldCFrameRainbow
                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                        _G.FastAttack = true
                                        sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                                    until _G.AutorainbowHaki == false or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                end
                            end
                        else
                            TP2FF(CFrame.new(5713.98877, 601.922974, 202.751251, -0.101080291, -0, -0.994878292, -0, 1, -0, 0.994878292, 0, -0.101080291))
                        end
                    elseif string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Kilo Admiral") then
                        if game:GetService("Workspace").Enemies:FindFirstChild("Kilo Admiral [Lv. 1750] [Boss]") then
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                if v.Name == "Kilo Admiral [Lv. 1750] [Boss]" then
                                    OldCFrameRainbow = v.HumanoidRootPart.CFrame
                                    repeat task.wait()
                                        EquipWeapon(_G.SelectToolWeapon)
                                        TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(5,10,7))
                                        v.HumanoidRootPart.CanCollide = false
                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                        v.HumanoidRootPart.CFrame = OldCFrameRainbow
                                        _G.FastAttack = true
                                        sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                                    until _G.AutorainbowHaki == false or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                end
                            end
                        else
                            TP2FF(CFrame.new(2877.61743, 423.558685, -7207.31006, -0.989591599, -0, -0.143904909, -0, 1.00000012, -0, 0.143904924, 0, -0.989591479))
                        end
                    elseif string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Captain Elephant") then
                        if game:GetService("Workspace").Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                if v.Name == "Captain Elephant [Lv. 1875] [Boss]" then
                                    OldCFrameRainbow = v.HumanoidRootPart.CFrame
                                    repeat task.wait()
                                        EquipWeapon(_G.SelectToolWeapon)
                                        topos(v.HumanoidRootPart.CFrame * CFrame.new(5,10,7))
                                        v.HumanoidRootPart.CanCollide = false
                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                        v.HumanoidRootPart.CFrame = OldCFrameRainbow
                                        _G.FastAttack = true
                                        
                                        sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                                    until _G.AutorainbowHaki == false or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                end
                            end
                        else
                            TP2FF(CFrame.new(-13485.0283, 331.709259, -8012.4873, 0.714521289, 7.98849911e-08, 0.69961375, -1.02065748e-07, 1, -9.94383065e-09, -0.69961375, -6.43015241e-08, 0.714521289))
                        end
                    elseif string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Beautiful Pirate") then
                        if game:GetService("Workspace").Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                if v.Name == "Beautiful Pirate [Lv. 1950] [Boss]" then
                                    OldCFrameRainbow = v.HumanoidRootPart.CFrame
                                    repeat task.wait()
                                        EquipWeapon(_G.SelectToolWeapon)
                                        TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
                                        v.HumanoidRootPart.CanCollide = false
                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                        v.HumanoidRootPart.CFrame = OldCFrameRainbow
                                      _G.FastAttack = true
                                        sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                                    until _G.AutorainbowHaki == false or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                end
                            end
                        else
                            TP2FF(CFrame.new(5312.3598632813, 20.141201019287, -10.158538818359))
                        end
                    else
                        TP2FF(CFrame.new(-11892.0703125, 930.57672119141, -8760.1591796875))
                        if (Vector3.new(-11892.0703125, 930.57672119141, -8760.1591796875) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 30 then
                            wait(1.5)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("HornedMan","Bet")
                        end
                    end
                end
            end
        end)
    end)
               
               spawn(function()
        pcall(function()
            while wait(.1) do
                if _G.AutoMusketeerHat then
                    if game:GetService("Players").LocalPlayer.Data.Level.Value >= 1800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress").KilledBandits == false then
                        if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Forest Pirate") and string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                            if game:GetService("Workspace").Enemies:FindFirstChild("Forest Pirate [Lv. 1825]") then
                                for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                    if v.Name == "Forest Pirate [Lv. 1825]" then
                                        repeat task.wait()
                                            pcall(function()
                                                EquipWeapon(_G.SelectToolWeapon)
                                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
                                                v.HumanoidRootPart.CanCollide = false
                                                _G.FastAttack = true
                                                MusketeerHatMon = v.HumanoidRootPart.CFrame
                                                StartMagnetMusketeerhat = true
                                            end)
                                        until _G.AutoMusketeerHat == false or not v.Parent or v.Humanoid.Health <= 0 or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                        StartMagnetMusketeerhat = false
                                    end
                                end
                            else
                                StartMagnetMusketeerhat = false
                                TP2FF(CFrame.new(-13206.452148438, 425.89199829102, -7964.5537109375))
                            end
                        else
                            TP2FF(CFrame.new(-12443.8671875, 332.40396118164, -7675.4892578125))
                            if (Vector3.new(-12443.8671875, 332.40396118164, -7675.4892578125) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 30 then
                                wait(1.5)
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest","CitizenQuest",1)
                            end
                        end
                    elseif game:GetService("Players").LocalPlayer.Data.Level.Value >= 1800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress").KilledBoss == false then
                        if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible and string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Captain Elephant") and game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                            if game:GetService("Workspace").Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
                                for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                    if v.Name == "Captain Elephant [Lv. 1875] [Boss]" then
                                        OldCFrameElephant = v.HumanoidRootPart.CFrame
                                        repeat task.wait()
                                            pcall(function()
                                                EquipWeapon(_G.SelectToolWeapon)
                                                AutoHaki()
                                                v.HumanoidRootPart.CanCollide = false
                                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
                                                v.HumanoidRootPart.CanCollide = false
                                                v.HumanoidRootPart.CFrame = OldCFrameElephant
                                               _G.FastAttack = true
                                                sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                                            end)
                                        until _G.AutoMusketeerHat == false or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                    end
                                end
                            else
                                TP2FF(CFrame.new(-13374.889648438, 421.27752685547, -8225.208984375))
                            end
                        else
                            TP2FF(CFrame.new(-12443.8671875, 332.40396118164, -7675.4892578125))
                            if (CFrame.new(-12443.8671875, 332.40396118164, -7675.4892578125).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 then
                                wait(1.5)
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen")
                            end
                        end
                    elseif game:GetService("Players").LocalPlayer.Data.Level.Value >= 1800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen") == 2 then
                        TP2FF(CFrame.new(-12512.138671875, 340.39279174805, -9872.8203125))
                    end
                end
            end
        end)
    end)




				spawn(function()
					while wait(.1) do
						if _G.AutoNew_Ws == true then
							if game.Players.localPlayer.Data.Level.Value >= 700 and world1 then
								_G.AutoFarm = false
								if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("DressrosaQuestProgress", "Dressrosa") ~= 0 then
									if Workspace.Map.Ice.Door.Transparency == 1 then
										if (CFrame.new(1347.7124, 37.3751602, -1325.6488).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 250 then
											if game.Players.LocalPlayer.Backpack:FindFirstChild("Key") then
												local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Key")
												wait(.4)
												EquipTool(tool)
												game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
											end
											DoorNewWorldTween = toTarget(CFrame.new(1347.7124, 37.3751602, -1325.6488).Position,CFrame.new(1347.7124, 37.3751602, -1325.6488))
											if (CFrame.new(1347.7124, 37.3751602, -1325.6488).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
												if DoorNewWorldTween then
													DoorNewWorldTween:Stop()
												end
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1347.7124, 37.3751602, -1325.6488)
											end
										elseif game.Workspace.Enemies:FindFirstChild("Ice Admiral [Lv. 700] [Boss]") and game.Workspace.Map.Ice.Door.CanCollide == false and game.Workspace.Map.Ice.Door.Transparency == 1 and (CFrame.new(1347.7124, 37.3751602, -1325.6488).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
											if DoorNewWorldTween then
												DoorNewWorldTween:Stop()
											end
											for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
												if _G.AutoNew_Ws and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and v.Name == "Ice Admiral [Lv. 700] [Boss]" then
													repeat wait()
														if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
															Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
														elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
															if Farmtween then
																Farmtween:Stop()
															end
															if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
																local args = {
																	[1] = "Buso"
																}
																game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
															end
															game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
															_G.FastAttack = true
															_G.FastAttack1 = true
														end 
													until not _G.AutoNew_Ws or not v.Parent or v.Humanoid.Health <= 0
													_G.FastAttack = false
													_G.FastAttack1 = false
												end
											end
										end 
									else
										if game.Players.LocalPlayer.Backpack:FindFirstChild("Key") or game.Players.LocalPlayer.Character:FindFirstChild("Key") then
											DoorNewWorldTween = toTarget(CFrame.new(1347.7124, 37.3751602, -1325.6488).Position,CFrame.new(1347.7124, 37.3751602, -1325.6488))
											if (CFrame.new(1347.7124, 37.3751602, -1325.6488).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
												if DoorNewWorldTween then
												   DoorNewWorldTween:Stop()
												end
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1347.7124, 37.3751602, -1325.6488)
												local args = {
													[1] = "DressrosaQuestProgress",
													[2] = "Detective"
												}
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
												wait(0.5)
												if game.Players.LocalPlayer.Backpack:FindFirstChild("Key") then
													local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Key")
													wait(.4)
													game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
												end
											end
										else
											AutoNewWorldTween = toTarget(CFrame.new(4849.29883, 5.65138149, 719.611877).Position,CFrame.new(4849.29883, 5.65138149, 719.611877))
											if (CFrame.new(4849.29883, 5.65138149, 719.611877).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
												if AutoNewWorldTween then
													AutoNewWorldTween:Stop()
												end
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(4849.29883, 5.65138149, 719.611877)
												local args = {
													[1] = "DressrosaQuestProgress",
													[2] = "Detective"
												}
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
												wait(0.5)
												if game.Players.LocalPlayer.Backpack:FindFirstChild("Key") then
													local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Key")
													wait(.4)
													game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
												end
											end
										end
									end
								else
									local args = {
										[1] = "TravelDressrosa"
									}
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
								end
							end
						end
					end
				end)

				Item:AddToggle("Auto Third World",false,function(value)
				_G.AutoThirdSea = value
				_G.Autohaki_autofarm = value
				_G.Lock = value
							while wait() do
							local g1=game local p1=g1:GetService('Players') local l1=p1.LocalPlayer local c1=l1.Character local h1=c1:FindFirstChild('Humanoid') local h2=c1:FindFirstChild('HumanoidRootPart') local v0=true local v1='BodyVelocity'
							local x=function() while task.wait() do if _G.Lock then if h2 then if h2:FindFirstChild(v1) then return elseif not h2:FindFirstChild(v1) then local vc=Instance.new(v1, h2) vc.MaxForce=Vector3.new(1, 1, 1)*math.huge vc.Velocity=Vector3.new(0, 0, 0) end end else if h2 then if h2:FindFirstChild(v1) then local aa=h2:FindFirstChild(v1) aa:Destroy() end end end end end spawn(function() pcall(x) end)
				end
				end)

				Item:AddToggle("Auto Factory Farm",false,function(value)
				_G.Factory = value
						if not _G.Factory then
							_G.FactoryCore = false
						end
						_G.Autohaki_autofarm = value
					end)
					
				Item:AddToggle("Auto Farm Bones",false,function(value)
				_G.AutoFarmBone = value 
					MagnetBone = false
							_G.Autohaki_autofarm = value
				end)


				Item:AddToggle("Auto Farm Katakuri",false,function(value)
				_G.AutoKatakuri = value
				end)

				Item:AddToggle("Auto Farm Katakuri+Hop",false,function(value)
				_G.AutoKatakuri_Hop = value
				end)


				spawn(function()
					while wait() do 
						pcall(function()
						if _G.AutoKatakuri then
								if game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name == "Cake Prince [Lv. 2300] [Raid Boss]" then
										repeat game:GetService("RunService").Heartbeat:wait()
											EquipWeapon(_G.SelectToolWeapon)
											StatrMagnetPosmonKatakuri = false
											PosmonKatakuri = v.HumanoidRootPart.CFrame
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
											_G.FastAttack1 = true
											_G.FastAttack  = true
											TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,60,0))
											StatrMagnetPosmonKatakuri = true
										until _G.AutoKatakuri == false or not v.Parent or v.Humanoid.Health <= 0
											StatrMagnetPosmonKatakuri = false
										else
										 if _G.AutoKatakuri_Hop then
											 Hop()
										end
									end
								end
							end
						end
					end)
				end
				end)
				


				spawn(function()
					for i = 1,math.huge do game:GetService("RunService").RenderStepped:Wait()
						if _G.AutoKatakuri and StatrMagnetPosmonKatakuri then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if StatrMagnetPosmonKatakuri and _G.AutoKatakuri and v.Name == "Cake Prince [Lv. 2300] [Raid Boss]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									v.HumanoidRootPart.CFrame = PosmonKatakuri
												v.Humanoid.JumpPower = 0
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.Size = Vector3.new(150,150,150)
												v.HumanoidRootPart.CanCollide = false
												if v.Humanoid:FindFirstChild("Animator") then
													v.Humanoid.Animator:Destroy()
												end
												sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
												v.Humanoid:ChangeState(14)
								end 
							end
						end
					end
				end)


				Item:AddToggle("Auto Farm Cake Prince",false,function(value)
				_G.AutoCakePrince = value
				end)

				Item:AddToggle("Auto Farm Cake Prince+Hop",false,function(value)
				_G.AutoCakePrince_Hop = value

				end)
				spawn(function()
				    pcall(function()
						if _G.AutoCakePrince_Hop then
							Hop()
						end
					end)
				end)


				spawn(function()
					while wait() do
						pcall(function()
							if _G.AutoCakePrince then
								if game:GetService("ReplicatedStorage"):FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
									CAKEMAGNET = false
									TP2FF(CFrame.new(-2009.2802734375, 4532.97216796875, -14937.3076171875))    
								elseif game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do 
										if v.Name == "Cake Prince [Lv. 2300] [Raid Boss]" then
											repeat game:GetService("RunService").Heartbeat:wait()
												EquipWeapon(_G.SelectToolWeapon)
												v.HumanoidRootPart.CanCollide = false
												TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,30,15))
											until _G.AutoCakePrince == false or not v.Parent or v.Humanoid.Health <= 0
										end    
									end    
								else	
									local args = {
										[1] = "CakePrinceSpawner",
										[2] = true
									}
									
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))                    
									local args = {
										[1] = "CakePrinceSpawner"
									}
									
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
									if game.Workspace.Enemies:FindFirstChild("Baking Staff [Lv. 2250]") or game.Workspace.Enemies:FindFirstChild("Head Baker [Lv. 2275]") or game.Workspace.Enemies:FindFirstChild("Cake Guard [Lv. 2225]") or game.Workspace.Enemies:FindFirstChild("Cookie Crafter [Lv. 2200]")  then
										for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do  
											if (v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Cookie Crafter [Lv. 2200]") and v.Humanoid.Health > 0 then
												repeat game:GetService("RunService").Heartbeat:wait()
													EquipWeapon(_G.SelectToolWeapon)
													Posmoncake = v.HumanoidRootPart.CFrame
													TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
													_G.FastAttack = true
													_G.FastAttack1 = true
													CAKEMAGNET = true
												until _G.AutoCakePrince == false or game:GetService("ReplicatedStorage"):FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or not v.Parent or v.Humanoid.Health <= 0
											end
										end
									else
										CAKEMAGNET = false
										TP2FF(CFrame.new(-2189.00341796875, 409.69915771484375, -12512.63671875))
									end
								end
							end
						end)
					end
				end)

				spawn(function()
					while task.wait() do
						if _G.AutoCakePrince and CAKEMAGNET then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if CAKEMAGNET and _G.AutoCakePrince and (v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Cookie Crafter [Lv. 2200]") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.HumanoidRootPart.CFrame = Posmoncake
									v.HumanoidRootPart.CanCollide = false
									if v.Humanoid:FindFirstChild("Animator") then
										v.Humanoid.Animator:Destroy()
									end
									sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
								end
							end
						end
					end
				end)




				Item:AddToggle("Auto Farm Observation",false,function(value)
					_G.AutoObservation = value
							_G.Autohaki_autofarm = value
				end)

				spawn(function()
					while wait() do
						pcall(function()
							if _G.AutoObservation then
								if not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
									repeat wait()                        
										game:GetService("VirtualInputManager"):SendKeyEvent(true,"E",false,game)
										wait(1)
										game:GetService("VirtualInputManager"):SendKeyEvent(false,"E",false,game)
									until game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") or not _G.AutoObservation
								end
							end
						end)
					end
				end)
				Item:AddToggle("Auto Farm Observation+Hop",false,function(value)
				_G.AutoObservation_Hop = value
						_G.Autohaki_autofarm = value
				end)



				Item:AddSeperator("Boss")

				BossList = {}
				for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
					if string.find(v.Name, "Boss") then
						table.insert(BossList, v.Name)
					end
				end

				local SlcBoss = Item:AddDropdown("Select Boss",BossList, function(value)
				_G.SelectBoss = value
				end)

				Item:AddButton("Refresh Boss", function()
				SlcBoss:Clear()
					wait(.1)
					for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
						if string.find(v.Name,"Boss") then
							SlcBoss:Add(v.Name) 
						end
					end
				end)

				Item:AddToggle("Auto Farm Boss",false,function(value)
				 _G.AutoFarmBoss = value
				end)

				Item:AddToggle("Auto Farm All Boss",false,function(value)
					_G.AutoFarmAllBoss = value
					end)
				Item:AddToggle("Auto Farm All Boss + Hop",false,function(value)
                    _G.AutoFarmAllBoss_Hop = value
                end)

				spawn(function()
					while wait() do
						if _G.AutoFarmBoss then
							pcall(function()
								if game:GetService("Workspace").Enemies:FindFirstChild(_G.SelectBoss) then
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name == _G.SelectBoss then
											if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
												repeat task.wait()
													EquipWeapon(_G.SelectToolWeapon)
													v.HumanoidRootPart.CanCollide = false
													v.Humanoid.WalkSpeed = 0
													v.HumanoidRootPart.Size = Vector3.new(80,80,80)                             
													TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
													_G.FastAttack = true
													sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
												until not _G.AutoFarmBoss or not v.Parent or v.Humanoid.Health <= 0
											end
										end
									end
								else
									if game:GetService("ReplicatedStorage"):FindFirstChild(_G.SelectBoss) then
										TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild(_G.SelectBoss).HumanoidRootPart.CFrame * CFrame.new(0,50,0))
									end
								end
							end)
						end
					end
				end)
			spawn(function()
					while wait() do
						if _G.AutoFarmAllBoss then
							pcall(function()
								for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
									if string.find(v.Name,"Boss") then
										if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 17000 then
											repeat task.wait()
												EquipWeapon(_G.SelectToolWeapon)
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.CanCollide = false
												v.Head.CanCollide = false
												v.HumanoidRootPart.Size = Vector3.new(80,80,80)
												topos(v.HumanoidRootPart.CFrame*CFrame.new(0,50,0))
												_G.FastAttack = true
												sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",math.huge)
											until v.Humanoid.Health <= 0 or _G.AutoFarmAllBoss == false or not v.Parent
										end
									else
										if _G.AutoFarmAllBoss_Hop then
											Hop()
										end
									end
								end
							end)
						end
					end
				end)


				Item:AddSeperator("Mastery")
				Item:AddToggle("Auto Farm Mastery Gun",false,function(value)
				_G.AutoFarmMasteryGun = value
					MagnetGun = false
					USEGUN = false
				end)


				function QuestVis()
					return game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible 
				end

				function QuestVis()
					return game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible 
				end

				Item:AddToggle("Auto Farm Mastery Fruits",false,function(value)
				_G.AutoFarmMasteryFruit = value
					MagnetFruit = false
					USEBF = false
				_G.Lock = value
						while wait() do
						local g1=game local p1=g1:GetService('Players') local l1=p1.LocalPlayer local c1=l1.Character local h1=c1:FindFirstChild('Humanoid') local h2=c1:FindFirstChild('HumanoidRootPart') local v0=true local v1='BodyVelocity'
						local x=function() while task.wait() do if _G.Lock then if h2 then if h2:FindFirstChild(v1) then return elseif not h2:FindFirstChild(v1) then local vc=Instance.new(v1, h2) vc.MaxForce=Vector3.new(1, 1, 1)*math.huge vc.Velocity=Vector3.new(0, 0, 0) end end else if h2 then if h2:FindFirstChild(v1) then local aa=h2:FindFirstChild(v1) aa:Destroy() end end end end end spawn(function() pcall(x) end)
					end
				end)

                local sldr = Item:AddSlider("Use Skill Kill At:", 0, 100, 20, function(t)
				_G.KillAt = t
				end)

				Item:AddToggle("Auto Skill Z",false,function(value)
				_G.SkillZ = value 
				end)

				Item:AddToggle("Auto Skill X",false,function(value)
				_G.SkillX = value 
				end)
				Item:AddToggle("Auto Skill C",false,function(value)
				_G.SkillC = value
				end)
				Item:AddToggle("Auto Skill V",false,function(value)
				  _G.SkillV = value
				end)



				Item:AddSeperator("Fighting Styles")
				Item:AddToggle("Auto Superhuman",false,function(value)
				_G.AutoSuperhuman = value
				_G.Autohaki_autofarm = value
				end)
				Item:AddToggle("Auto Superhuman Full",false,function(value)
				_G.AutoSuperhumanFull = value
				_G.Autohaki_autofarm = value
				end)

				Item:AddToggle("Auto DeathStep",false,function(value)
				_G.AutoDeathStep = value
					if value then
						local args = {
							[1] = "BuyBlackLeg"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
				_G.Autohaki_autofarm = value
				end)
				Item:AddToggle("Auto Dragon Talon",false,function(value)
				_G.AutoDargonTalon = value
					if value then
						local args = {
							[1] = "BlackbeardReward",
							[2] = "DragonClaw",
							[3] = "2"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					_G.Autohaki_autofarm = value
				end)
				Item:AddToggle("Auto Electric Clow",false,function(value)
				_G.AutoElectricclow = value
					if vu then
						local args = {
							[1] = "BuyElectro"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
					_G.Autohaki_autofarm = value
				end)
				Item:AddToggle("Auto Sharkman Karate",false,function(value)
				_G.AutoSharkmanKarate = value
				end)



				Item:AddSeperator("Elite Hunter")
				Item:AddToggle("Auto Elite Hunter",false,function(value)
				_G.AutoEliteHunter = value
				end)
				Item:AddToggle("Auto Elite Hunter+Hop",false,function(value)
				_G.AutoEliteHunterHop = value
				end)
                Item:AddSlider("Lock Elite Hunter",1,100,1,function(value)
					_G.SelectLockElite = value
				end)
				Item:AddToggle("Lock Elite Hunter",false,function(value)
				_G.LockElite = value
				end)



				Item:AddSeperator("Yama")
				Item:AddToggle("Auto Yama",false,function(value)
				if not world3 then
						game.Players.LocalPlayer:Kick('ไป Sea3 ดิ ต้องให้พูดกี่รอบวะ')
					else
						_G.AutoYama = value
						_G.TeleportYama = value
						_G.MagnetYama = value
					end 
				end)
				Item:AddToggle("Auto Yama+Hop",false,function(value)
				if not world3 then
						game.Players.LocalPlayer:Kick('ไป Sea3 ดิ ต้องให้พูดกี่รอบวะ')
					else
						_G.AutoYama = value
						_G.AutoYama_HOP = value
						_G.TeleportYama = value
						_G.MagnetYama = value
					end 
				end)


				Item:AddSeperator("Buddy Sword")
				Item:AddToggle("Auto Buddy Sworld",false,function(value)
				if not world3 then
						game.Players.LocalPlayer:Kick('Go To Sea3 ควยสัส กูบอกกี่รอบเเล้ว')
					else
						_G.AutoBuddySword = value
					end 
					_G.Autohaki_autofarm = value
				end)
				Item:AddToggle("Auto Buddy Sworld+Hop",false,function(value)
				if not world3 then
						game.Players.LocalPlayer:Kick('Go To Sea3 ควยสัส กูบอกกี่รอบเเล้ว')
					else
						_G.AutoBuddySword = value
						_G.AutoBuddySwords_HOP = value
					end 
				_G.Autohaki_autofarm = value
				end)



				Item:AddSeperator("Pole")
				Item:AddToggle("Auto Pole",false,function(value)
				_G.AutoPole = value
				end)
				Item:AddToggle("Auto Pole+Hop",false,function(value)
				_G.AutoPoleHop = value
				end)
				spawn(function()
					while wait() do
						if _G.AutoPole and world1 then
							pcall(function()
								if game:GetService("Workspace").Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name == "Thunder God [Lv. 575] [Boss]" then
											if v.Humanoid.Health > 0 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
												repeat task.wait()
													EquipWeapon(_G.SelectToolWeapon)
													v.HumanoidRootPart.CanCollide = false
													v.Humanoid.WalkSpeed = 0
													if not v.HumanoidRootPart:FindFirstChild("BodyVelocity") then
														local bv = Instance.new("BodyVelocity")
													end
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
				_G.FastAttack = true
													_G.FastAttack1 = true
												until _G.AutoPole == false or v.Humanoid.Health <= 0 or not v.Parent
											end
										end
									end
								elseif game:GetService("ReplicatedStorage"):FindFirstChild("Thunder God [Lv. 575] [Boss]") then
									TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Thunder God [Lv. 575] [Boss]").HumanoidRootPart.CFrame)
								else
									if _G.AutoPoleHop then
										Hop()
									end
								end
							end)
						end
					end
				end)



				Item:AddSeperator("Canvender")
				Item:AddToggle("Auto Canvender",false,function(value)
					_G.AutoCanvender = value
					end)
				Item:AddToggle("Auto Canvender+Hop",false,function(value)
					_G.AutoCanvenderHop = value
					end)

				Item:AddSeperator("Dark Dagger")
				Item:AddToggle("Auto Dark Dagger",false,function(value)
				 _G.AutoDarkDagger = value
				 end)
				 Item:AddToggle("Auto Dark Dagger+Hop",false,function(value)
				_G.AutoDaggerHop = value
				end)



				Item:AddSeperator("Serpent Bow")
				 Item:AddToggle("Auto Serpent Bow",false,function(value)
				_G.AutoSerpentbow = value
				_G.Lock = value
						while wait() do
						local g1=game local p1=g1:GetService('Players') local l1=p1.LocalPlayer local c1=l1.Character local h1=c1:FindFirstChild('Humanoid') local h2=c1:FindFirstChild('HumanoidRootPart') local v0=true local v1='BodyVelocity'
						local x=function() while task.wait() do if _G.Lock then if h2 then if h2:FindFirstChild(v1) then return elseif not h2:FindFirstChild(v1) then local vc=Instance.new(v1, h2) vc.MaxForce=Vector3.new(1, 1, 1)*math.huge vc.Velocity=Vector3.new(0, 0, 0) end end else if h2 then if h2:FindFirstChild(v1) then local aa=h2:FindFirstChild(v1) aa:Destroy() end end end end end spawn(function() pcall(x) end)
					end
				end)
				 Item:AddToggle("Auto Serpent Bow+Hop",false,function(value)
				_G.AutoSerpentbow_Hop = value
				_G.Lock = value
						while wait() do
						local g1=game local p1=g1:GetService('Players') local l1=p1.LocalPlayer local c1=l1.Character local h1=c1:FindFirstChild('Humanoid') local h2=c1:FindFirstChild('HumanoidRootPart') local v0=true local v1='BodyVelocity'
						local x=function() while task.wait() do if _G.Lock then if h2 then if h2:FindFirstChild(v1) then return elseif not h2:FindFirstChild(v1) then local vc=Instance.new(v1, h2) vc.MaxForce=Vector3.new(1, 1, 1)*math.huge vc.Velocity=Vector3.new(0, 0, 0) end end else if h2 then if h2:FindFirstChild(v1) then local aa=h2:FindFirstChild(v1) aa:Destroy() end end end end end spawn(function() pcall(x) end)
					end
				end)



				Item:AddSeperator("Saber")
				 Item:AddToggle("Auto Saber",false,function(value)
				_G.AutoSaber = value
				_G.Lock = value
						while wait() do
						local g1=game local p1=g1:GetService('Players') local l1=p1.LocalPlayer local c1=l1.Character local h1=c1:FindFirstChild('Humanoid') local h2=c1:FindFirstChild('HumanoidRootPart') local v0=true local v1='BodyVelocity'
						local x=function() while task.wait() do if _G.Lock then if h2 then if h2:FindFirstChild(v1) then return elseif not h2:FindFirstChild(v1) then local vc=Instance.new(v1, h2) vc.MaxForce=Vector3.new(1, 1, 1)*math.huge vc.Velocity=Vector3.new(0, 0, 0) end end else if h2 then if h2:FindFirstChild(v1) then local aa=h2:FindFirstChild(v1) aa:Destroy() end end end end end spawn(function() pcall(x) end)
					end
				end)

				Item:AddToggle("Auto Saber+Hop",false,function(value)
				_G.AutoSaberHop = value
				end)

				Item:AddSeperator("Legendary Sword")

				 Item:AddToggle("Auto Buy Legendary Sword",false,function(value)
				_G.AutoLegendarySword = value
				end)
				 Item:AddToggle("Auto Buy Legendary Sword+Hop",false,function(value)
				_G.AutoLegendarySwordHop = value
				end)

				spawn(function()
					pcall(function()
						while _G.AutoLegendarySword do wait()
							if _G.AutoLegendarySword then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LegendarySwordDealer","2")
							end 
						end
					end)
				end)

				Item:AddSeperator("Enhancement Haki")
				 Item:AddToggle("Auto Buy Enhancement Colors",false,function(value)
				 _G.AutoEnhancement = value
				end)
				 Item:AddToggle("Auto Buy Enhancement Colors+Hop",false,function(value)
				_G.AutoEnhancementHop = value
				end)

				spawn(function()
					pcall(function()
						while _G.AutoEnhance_ment do wait()
							if _G.AutoEnhance_ment then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ColorsDealer", "2")
							end 
						end
					end)
				end)

				spawn(function()
					pcall(function()
						while wait() do
							if _G.AutoEnhancementHop or _G.AutoLegendaryHop then
								wait(5)
								Hop()
							end
						end
					end)
				end)





				spawn(function()
					while wait() do
						if _G.AUTORENGOKU and world2 then
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or game.Players.LocalPlayer.Character:FindFirstChild("Hidden Key") then
								EquipWeapon("Hidden Key")
								if (CFrame.new(6571.81885, 296.689758, -6966.76514).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									Farmtween = toTarget(CFrame.new(6571.81885, 296.689758, -6966.76514).Position,CFrame.new(6571.81885, 296.689758, -6966.76514))
								elseif (CFrame.new(6571.81885, 296.689758, -6966.76514).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if Farmtween then
										Farmtween:Stop()
									end
									TP2FF(CFrame.new(6571.81885, 296.689758, -6966.76514, 0.825126112, 8.412257e-10, 0.564948559, -2.42370835e-08, 1, 3.39100339e-08, -0.564948559, -4.16727595e-08, 0.825126112))
								end 
							elseif game.Workspace.Enemies:FindFirstChild("Snow Lurker [Lv. 1375]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if _G.AUTORENGOKU and v.Name == "Snow Lurker [Lv. 1375]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
										repeat wait()
											if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
												Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												StatrMagnetRengoku = false
											elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
												if Farmtween then
													Farmtween:Stop()
												end
												PosMonRengoku = v.HumanoidRootPart.CFrame
												EquipWeapon(_G.SelectToolWeapon)
												_G.FastAttack = true
												_G.FastAttack1 = true
												StatrMagnetRengoku = true
												if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
													local args = {
														[1] = "Buso"
													}
													game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
												end
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 10, 10)
																				game:GetService'VirtualUser':CaptureController()
												game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
											end 
										until game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or _G.AutoRengoku == false or not v.Parent or v.Humanoid.Health <= 0
										StatrMagnetRengoku = false
										_G.FastAttack = false
										_G.FastAttack1 = false
										if (CFrame.new(5518.00684, 60.5559731, -6828.80518).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											Farmtween = toTarget(CFrame.new(5518.00684, 60.5559731, -6828.80518).Position,CFrame.new(5518.00684, 60.5559731, -6828.80518))
										elseif (CFrame.new(5518.00684, 60.5559731, -6828.80518).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Farmtween then
												Farmtween:Stop()
											end
											TP2FF(CFrame.new(5518.00684, 60.5559731, -6828.80518, 0.825126112, 8.412257e-10, 0.564948559, -2.42370835e-08, 1, 3.39100339e-08, -0.564948559, -4.16727595e-08, 0.825126112))
										end 
									end
								end
							else
								StatrMagnetRengoku = false
								if (CFrame.new(5518.00684, 60.5559731, -6828.80518).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									Farmtween = toTarget(CFrame.new(5518.00684, 60.5559731, -6828.80518).Position,CFrame.new(5518.00684, 60.5559731, -6828.80518))
								elseif (CFrame.new(5518.00684, 60.5559731, -6828.80518).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if Farmtween then
										Farmtween:Stop()
									end
									TP2FF(CFrame.new(5518.00684, 60.5559731, -6828.80518, -0.650781393, -3.64292951e-08, 0.759265184, -4.07668654e-09, 1, 4.44854642e-08, -0.759265184, 2.58550248e-08, -0.650781393))
								end 
							end
						end
					end
				end)
				spawn(function()
					for i = 1,math.huge do game:GetService("RunService").RenderStepped:Wait()
						if _G.AUTORENGOKU and StatrMagnetRengoku then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if StatrMagnetRengoku and _G.AUTORENGOKU and v.Name == Ms and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 270 then
									v.HumanoidRootPart.CFrame = PosMonRengoku
												v.Humanoid.JumpPower = 0
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.Size = Vector3.new(150,150,150)
												v.HumanoidRootPart.CanCollide = false
												if v.Humanoid:FindFirstChild("Animator") then
													v.Humanoid.Animator:Destroy()
												end
												sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
												v.Humanoid:ChangeState(14)
								end 
							end
						end
					end
				end)
				spawn(function()
					while wait() do
						if _G.AutoHolyTorch and world3 then
							if game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") and game:GetService("Workspace").Map.Turtle.TushitaGate.TushitaGate.Transparency == 1 then
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Holy Torch") then
									EquipWeapon("Holy Torch")
								elseif game.Players.LocalPlayer.Character:FindFirstChild("Holy Torch") then
									if game:GetService("Workspace").Map.Turtle.QuestTorches.Torch1.Particles.Main.Enabled ~= true then
										if (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											HolyTorchFarmtween = toTarget(game:GetService("Workspace").Map.Turtle.QuestTorches.Torch1.Position,game:GetService("Workspace").Map.Turtle.QuestTorches.Torch1.CFrame)
										elseif (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if HolyTorchFarmtween then
												HolyTorchFarmtween:Stop()
											end
											game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Turtle.QuestTorches.Torch1.CFrame
										end
									elseif game:GetService("Workspace").Map.Turtle.QuestTorches.Torch2.Particles.Main.Enabled ~= true then
										if (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch2.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											HolyTorchFarmtween = toTarget(game:GetService("Workspace").Map.Turtle.QuestTorches.Torch2.Position,game:GetService("Workspace").Map.Turtle.QuestTorches.Torch2.CFrame)
										elseif (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch2.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if HolyTorchFarmtween then
												HolyTorchFarmtween:Stop()
											end
											game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Turtle.QuestTorches.Torch2.CFrame
										end
									elseif game:GetService("Workspace").Map.Turtle.QuestTorches.Torch3.Particles.Main.Enabled ~= true then
										if (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch3.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											HolyTorchFarmtween = toTarget(game:GetService("Workspace").Map.Turtle.QuestTorches.Torch3.Position,game:GetService("Workspace").Map.Turtle.QuestTorches.Torch3.CFrame)
										elseif (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch3.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if HolyTorchFarmtween then
												HolyTorchFarmtween:Stop()
											end
											game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Turtle.QuestTorches.Torch3.CFrame
										end
									elseif game:GetService("Workspace").Map.Turtle.QuestTorches.Torch4.Particles.Main.Enabled ~= true then
										if (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch4.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											HolyTorchFarmtween = toTarget(game:GetService("Workspace").Map.Turtle.QuestTorches.Torch4.Position,game:GetService("Workspace").Map.Turtle.QuestTorches.Torch4.CFrame)
										elseif (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch4.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if HolyTorchFarmtween then
												HolyTorchFarmtween:Stop()
											end
											game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Turtle.QuestTorches.Torch4.CFrame
										end
									elseif game:GetService("Workspace").Map.Turtle.QuestTorches.Torch5.Particles.Main.Enabled ~= true then
										if (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch5.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											HolyTorchFarmtween = toTarget(game:GetService("Workspace").Map.Turtle.QuestTorches.Torch5.Position,game:GetService("Workspace").Map.Turtle.QuestTorches.Torch5.CFrame)
										elseif (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch5.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if HolyTorchFarmtween then
												HolyTorchFarmtween:Stop()
											end
											game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Turtle.QuestTorches.Torch5.CFrame
										end
									end
								else
									game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Waterfall.SecretRoom.Room.Door.Door.Hitbox.CFrame
								end
							end
						end
					end
				end)

Tab2:AddSeperator("Auto Stats")
				 Tab2:AddToggle("Stats Kaitan",false,function(value)
				_G.Kaitanstat = value
				end)

				 Tab2:AddToggle("Melee",false,function(value)
				_G.Melee = value 
				end)

				 Tab2:AddToggle("Defense",false,function(value)
				_G.Defense = value   
				end)

				 Tab2:AddToggle("Sword",false,function(value)
				_G.Sword = value
				end)

				 Tab2:AddToggle("Gun",false,function(value)
				_G.Gun = value
				end)
				 Tab2:AddToggle("Fruit",false,function(value)
				_G.Fruit = value
				end)

Tab2:AddSeperator("Auto Other Stats")

				 Tab2:AddToggle("MaxPoint",false,function(value)
				_G.MaxPoint = value
				end)
				 Tab2:AddToggle("Stats Kaitan",false,function(value)
				_G.Kaitanstat = value
				 end)
			
Tab2:AddSeperator("Select Add Point")

                Tab2:AddSlider("Points", 0, 100, 5, function(value)
				PointStats = value
				end)

Tab2:AddSeperator("Players")

				PlayerList = {}
				for i,v in pairs(game.Players:GetPlayers()) do  
					table.insert(PlayerList ,v.Name)
				end
				local Plr = Tab2:AddDropdown("Select Players",PlayerList, function(value)
					_G.SelectedPlayer = value
				end)

				Tab2:AddButton("Refresh Players", function()
				Plr:Clear()
					wait(.1)
					for i,v in pairs(game.Players:GetPlayers()) do
						Plr:Add(v.Name)
					end
				end)

				 Tab2:AddToggle("Spectate Player",false,function(value)
				Spectate = value
					local plr1 = game.Players.LocalPlayer.Character.Humanoid
					local plr2 = game.Players:FindFirstChild(_G.SelectWeaponP)
					repeat wait()
					game:GetService("Workspace").Camera.CameraSubject = plr2.Character.Humanoid
					until Spectate == false 
					game:GetService("Workspace").Camera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
				end)


				Tab2:AddToggle("Teleport To Player",false,function(value)
				_G.TeleportPlayer = value
				ps=value
					pcall(function()
						if _G.TeleportPlayer then
							repeat TP2FF(game.Players:FindFirstChild(_G.SelectedPlayer).Character.HumanoidRootPart.CFrame) wait() until _G.TeleportPlayer == false
						end
					end)
				end)

				 Tab2:AddToggle("Auto Kill Player Melee",false,function(value)
				_G.AutoKillPlayersMelee = value
				ps=value
				end)
				spawn(function()
					while wait() do
						if _G.AutoKillPlayersMelee then
							pcall(function()
								for i,v in pairs(game.Players:GetChildren()) do
									if v.Name == _G.SelectedPlayer then
										repeat task.wait()
											EquipWeapon(_G.SelectWeaponP)
											v.Character.HumanoidRootPart.Size = Vector3.new(60,60,60)
											TP2FF(v.Character.HumanoidRootPart.CFrame * CFrame.new(0,-6.2,0))
											_G.FastAttack = true
											_G.FastAttack1 = true
										until v.Character.Humanoid.Helth <= 0 or _G.AutoKillPlayersMelee == false
									end
								end
							end)
						end
					end
				end)

				 Tab2:AddToggle("Auto Kill Player Gun",false,function(value)
				_G.AutoKillGUN = value
				ps=value
				end)

				spawn(function()
					while wait() do
						if _G.AutoKillGUN then
							pcall(function()
								for i,v in pairs(game.Players:GetChildren()) do
									if v.Name == _G.PLAYERSELECTED then
										repeat task.wait()
											EquipWeapon(SelectWeaponGun)
											v.Character.HumanoidRootPart.Size = Vector3.new(60,60,60)
											TP2FF(v.Character.HumanoidRootPart.CFrame * CFrame.new(0,50,-15))
										until v.Character.Humanoid.Helth <= 0 or _G.AutoKillGUN == false
									end
								end
							end)
						end
					end
				end)
				local Plr = game:GetService('Players').LocalPlayer
				local Mouse = Plr:GetMouse()
				Mouse.Button1Down:Connect(function()
					if _G.AutoKillGun and game.Players.LocalPlayer.Character:FindFirstChild(SelectWeaponGun) then
						local args = {
						[1] = game.Players:FindFirstChild(_G.SelectedPlayer).Character.HumanoidRootPart.Position,
						[2] = game.Players:FindFirstChild(_G.SelectedPlayer).Character.HumanoidRootPart
						}
						game:GetService("Players").LocalPlayer.Character[SelectWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
					end
				end)

				 Tab2:AddToggle("Auto Enabled PVP",false,function(value)
				_G.PVP = value
				end)

				spawn(function()
					pcall(function()
						while wait() do
							if _G.PVP then
								if game:GetService("Players").LocalPlayer.PlayerGui.Main.PvpDisabled.Visible == true then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")
								end
							end
						end
					end)
				end)

				WeaponListPlayer = {}
				for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v:IsA("Tool") then
						table.insert(WeaponListPlayer, v.Name)
					end
				end

				spawn(function()
					pcall(function()
						while wait() do
							for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
								if v:IsA("Tool") then
									if v:FindFirstChild("RemoteFunctionShoot") then 
										SelectWeaponGun = v.Name
									end
								end
							end
						end
					end)
				end)

				local PlrWS = Tab2:AddDropdown("Select Weapon Kill Player",WeaponListPlayer, function(value)
				_G.SelectWeaponP = value
				end)

				Tab2:AddButton("Refresh Weapon", function()
				PlrWS:Clear()
					wait(.1)
					for i,v in pairs(game.Players:GetPlayers()) do
						PlrWS:Add(v.Name)
					end
				end)
				
				Tab2:AddToggle("Auto Safe Mode",false,function(value)
					_G.SafeMode = value
				end)

				spawn(function()
					pcall(function()
						while wait() do
							if _G.SafeMode then
								if game.Players.LocalPlayer.Character.Humanoid.Health <= game.Players.LocalPlayer.Character.Humanoid.Health * _G.SafeAt/100 then
									repeat TP2FF(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,1000000,0)) wait() until _G.SafeMode == false
								end
							end
						end
					end)
				end)

                Tab2:AddSlider("Safe Mode At:", 0, 100, 20, function(t)
					_G.SafeAt = value
				end)

Tab2:AddSeperator("Aimbot")

				 Tab2:AddToggle("Aimbot Gun",false,function(value)
				_G.Aimbot = value
				end)

				local lp = game:GetService('Players').LocalPlayer
				local mouse = lp:GetMouse()
				mouse.Button1Down:Connect(function()
					if _G.Aimbot and game.Players.LocalPlayer.Character:FindFirstChild(SelectWeaponGun) then
						local args = {
						[1] = game.Players:FindFirstChild(_G.SelectedPlayer).Character.HumanoidRootPart.Position,
						[2] = game.Players:FindFirstChild(_G.SelectedPlayer).Character.HumanoidRootPart
						}
						game:GetService("Players").LocalPlayer.Character[SelectWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
					end
				end)

				spawn(function()
					pcall(function()
						while wait() do
							if _G.Aimbot then
								game:GetService("VirtualUser"):CaptureController()
								game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672),workspace.CurrentCamera.CFrame)
							end
						end
					end)
				end)
				 Tab2:AddToggle("Aimbot Skill",false,function(value)
				_G.AimBotSkill = value
				end)

				spawn(function()
					pcall(function()
					local gg = getrawmetatable(game)
					local old = gg.namecall
					setreadonly(gg,false)
					gg.namecall = newcclosure(function(...)
						local method = getnamecallmethod()
						local args = {...}
						if tostring(method) == "FireServer" then
							if tostring(args[1]) == "RemoteEvent" then
								if tostring(args[2]) ~= "true" and tostring(args[2]) ~= "false" then
										args[2] = PlayersPosition
										return old(unpack(args))
									end
								end
							end
							return old(...)
						end)
					end)
				end) 

				spawn(function()
					while wait() do
						if _G.AimBotSkill and game.Players:FindFirstChild(SelectedPlayer) and game.Players:FindFirstChild(SelectedPlayer).Character:FindFirstChild("HumanoidRootPart") then
							PlayersPosition = game.Players:FindFirstChild(SelectedPlayer).Character:FindFirstChild("HumanoidRootPart").Position
						end
					end
				end)

Tab2:AddSeperator("Other / Boats")

					BoatEZ = {}
					for i,v in pairs(game:GetService("Workspace").Boats:GetChildren()) do  
					table.insert(BoatEZ ,v.Name)
					end

				local Boats  = Tab2:AddDropdown("Select Boat ",BoatEZ, function(value)
				SelectBoats = value
				end)

				Tab2:AddButton("Refresh Boath", function()
				BoatEZ = {}
					Boats:Clear()
					for i,v in pairs(game:GetService("Workspace").Boats:GetChildren()) do  
						Boats:Add(v.Name)
					end
				end)

				Tab2:AddButton("Bring Boath", function()
				game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Boats[SelectBoats].Seat.CFrame
				end)

Tab4:AddSeperator("Islands")

				local IslandList 
				if world1 then
					IslandList = {
						"Start Island",
						"Marine Start",
						"Middle Town",
						"Jungle",
						"Pirate Village",
						"Desert",
						"Frozen Village",
						"Marine Ford",
						"Colosseum",
						"Sky 1st Floor",
						"Sky 2nd Floor",
						"Skr 3rd Floor",
						"Prison",
						"Magma Village",
						"Underwater City",
						"Fountain City",
						"House Cyborg's",
						"Shank's Room",
						"Mob Island"
					}
				elseif world2 then
					IslandList = {
						"First Spot",
						"Kingdom of Rose",
						"Swan Mansion",
						"Swan Room",
						"Green Zone",
						"Cafe",
						"Factory",
						"Colosseum",
						"Graveyard Island",
						"Snow Mountain",
						"Cold Island",
						"Hot Island",
						"Cursed Ship",
						"Ice Castle",
						"Forgotten Island",
						"Usoapp Island",
						"Minisky Island"
					}
				elseif world3 then
					IslandList = {
						"Port Town",
						"Hydra Island" ,
						"Great Tree",
						"Castle on the Sea",
						"Floating Turtle",
						"Mansion",
						"Secret Temple",
						"Friendly Arena",
						"Beautiful Pirate Domain",
						"Haunted Castle",
						"Ice Cream Island",
						"Peanut Island",
						"Cake Island"
					}
				end


				local IS = Tab4:AddDropdown("Selected Island",IslandList, function(value)
				ISLAND = value
				end)

				 Tab4:AddToggle("Teleport",false,function(value)
				_G.Teleport = value
				end)

				spawn(function()
					while wait() do 
						if _G.Teleport then
							pcall(function()
								repeat wait()
									if world1 then
										if ISLAND == "Start Island" then
											TP2FF(CFrame.new(1071.2832, 16.3085976, 1426.86792))
										elseif ISLAND == "Marine Start" then
											TP2FF(CFrame.new(-2573.3374, 6.88881969, 2046.99817))
										elseif ISLAND == "Middle Town" then
											TP2FF(CFrame.new(-655.824158, 7.88708115, 1436.67908))
										elseif ISLAND == "Jungle" then
											TP2FF(CFrame.new(-1249.77222, 11.8870859, 341.356476))
										elseif ISLAND == "Pirate Village" then
											TP2FF(CFrame.new(-1122.34998, 4.78708982, 3855.91992))
										elseif ISLAND == "Desert" then
											TP2FF(CFrame.new(1094.14587, 6.47350502, 4192.88721))
										elseif ISLAND == "Frozen Village" then
											TP2FF(CFrame.new(1198.00928, 27.0074959, -1211.73376))
										elseif ISLAND == "Marine Ford" then
											TP2FF(CFrame.new(-4505.375, 20.687294, 4260.55908))
										elseif ISLAND == "Colosseum" then
											TP2FF(CFrame.new(-1428.35474, 7.38933945, -3014.37305))
										elseif ISLAND == "Sky 1st Floor" then
											TP2FF(CFrame.new(-4970.21875, 717.707275, -2622.35449))
										elseif ISLAND == "Sky 2nd Floor" then
											TP2FF(CFrame.new(-4813.0249, 903.708557, -1912.69055))
										elseif ISLAND == "Skr 3rd Floor" then
											TP2FF(CFrame.new(-7952.31006, 5545.52832, -320.704956))
										elseif ISLAND == "Prison" then
											TP2FF(CFrame.new(4854.16455, 5.68742752, 740.194641))
										elseif ISLAND == "Magma Village" then
											TP2FF(CFrame.new(-5231.75879, 8.61593437, 8467.87695))
										elseif ISLAND == "Underwater City" then
											TP2FF(CFrame.new(61163.8516, 11.7796879, 1819.78418))
										elseif ISLAND == "Fountain City" then
											TP2FF(CFrame.new(5132.7124, 4.53632832, 4037.8562))
										elseif ISLAND == "House Cyborg's" then
											TP2FF(CFrame.new(6262.72559, 71.3003616, 3998.23047))
										elseif ISLAND == "Shank's Room" then
											TP2FF(CFrame.new(-1442.16553, 29.8788261, -28.3547478))
										elseif ISLAND == "Mob Island" then
											TP2FF(CFrame.new(-2850.20068, 7.39224768, 5354.99268))
										end
									end
									if world2 then
										if ISLAND == "First Spot" then
											TP2FF(CFrame.new(82.9490662, 18.0710983, 2834.98779))
										elseif ISLAND == "Kingdom of Rose" then
											TP2FF(CFrame.new(-394.983521, 118.503128, 1245.8446))
										elseif ISLAND == "Swan Mansion" then
											TP2FF(CFrame.new(-390.096313, 331.886475, 673.464966))
										elseif ISLAND == "Swan Room" then
											TP2FF(CFrame.new(2302.19019, 15.1778421, 663.811035))
										elseif ISLAND == "Green Zone" then
											TP2FF(CFrame.new(-2372.14697, 72.9919434, -3166.51416))
										elseif ISLAND == "Cafe" then
											TP2FF(CFrame.new(-385.250916, 73.0458984, 297.388397))
										elseif ISLAND == "Factory" then
											TP2FF(CFrame.new(430.42569, 210.019623, -432.504791))
										elseif ISLAND == "Colosseum" then
											TP2FF(CFrame.new(-1836.58191, 44.5890656, 1360.30652))
										elseif ISLAND == "Graveyard Island" then
											TP2FF(CFrame.new(-5411.47607, 48.8234024, -721.272522))
										elseif ISLAND == "Snow Mountain" then
											TP2FF(CFrame.new(511.825226, 401.765198, -5380.396))
										elseif ISLAND == "Cold Island" then
											TP2FF(CFrame.new(-6026.96484, 14.7461271, -5071.96338))
										elseif ISLAND == "Hot Island" then
											TP2FF(CFrame.new(-5478.39209, 15.9775667, -5246.9126))
										elseif ISLAND == "Cursed Ship" then
											TP2FF(CFrame.new(902.059143, 124.752518, 33071.8125))
										elseif ISLAND == "Ice Castle" then
											TP2FF(CFrame.new(5400.40381, 28.21698, -6236.99219))
										elseif ISLAND == "Forgotten Island" then
											TP2FF(CFrame.new(-3043.31543, 238.881271, -10191.5791))
										elseif ISLAND == "Usoapp Island" then
											TP2FF(CFrame.new(4748.78857, 8.35370827, 2849.57959))
										elseif ISLAND == "Minisky Island" then
											TP2FF(CFrame.new(-260.358917, 49325.7031, -35259.3008))
										end
									end
									if world3 then
										if ISLAND == "Port Town" then
											TP2FF(CFrame.new(-236.423828, 6.72993994, 5362.34961))
										elseif ISLAND == "Hydra Island" then
											TP2FF(CFrame.new(5229.99561, 603.916565, 345.154022))
										elseif ISLAND == "Great Tree" then
											TP2FF(CFrame.new(2174.94873, 28.7312393, -6728.83154))
										elseif ISLAND == "Castle on the Sea" then
											TP2FF(CFrame.new(-5060.248046875, 314.51547241211, -2986.3635253906))
										elseif ISLAND == "Floating Turtle" then
											TP2FF(CFrame.new(-10919.2998, 331.788452, -8637.57227))
										elseif ISLAND == "Mansion" then
											TP2FF(CFrame.new(-12553.19140625, 337.16827392578, -7457.8315429688))
										elseif ISLAND == "Secret Temple" then
											TP2FF(CFrame.new(5217.35693, 6.56511116, 1100.88159, 0.00408430398))
										elseif ISLAND == "Friendly Arena" then
											TP2FF(CFrame.new(5220.28955, 72.8193436, -1450.86304))
										elseif ISLAND == "Beautiful Pirate Domain" then
											TP2FF(CFrame.new(5310.8095703125, 21.594484329224, 129.39053344727))
										elseif ISLAND == "Haunted Castle" then
											TP2FF(CFrame.new(-9506.1064453125, 142.13989257813, 5526.0405273438))
										elseif ISLAND == "Ice Cream Island" then
											TP2FF(CFrame.new(-871.98492431641, 65.819549560547, -10919.76953125))
										elseif ISLAND == "Peanut Island" then
											TP2FF(CFrame.new(-2018.2635498047, 38.103397369385, -10333.181640625))
									   elseif ISLAND == "Cake Island" then
											TP2FF(CFrame.new(-1927.2838134765625, 37.82392883300781, -12843.5244140625))
										end
									end
								until _G.Teleport == false
							end)
						end
					end
				end)

				function topos(Para1)
					if _G.Bypassed == true then
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Para1
					else
						Distance = (Para1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
						Speed = 300
						pcall(function() 
							tween = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart,TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),{CFrame = Para1})
							tween:Play()
							_G.Clip = true
							if Distance <= 300 then
								tween:Cancel()
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Para1
								_G.Clip = false
							end
							if _G.StopTween == true then
								tween:Cancel()
								_G.Clip = false
							end
						end)
					end
				end

				Tab4:AddSeperator("World")
				Tab4:AddButton("Teleport To Old World", function()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
				end)
				Tab4:AddButton("Teleport To Second Sea", function()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
				end)
				Tab4:AddButton("Teleport To Third Sea", function()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
				end)

				local Mouse = Plr:GetMouse()
				Mouse.Button1Down:Connect(
					function()
						if not game:GetService("UserInputService"):IsKeyDown(Enum.KeyCode.LeftControl) then
							return
						end
						if not Mouse.Target then
							return
						end
						if CTRL then
							Plr.Character:MoveTo(Mouse.Hit.p)
						elseif CTRL1 then
							topos(CFrame.new(Mouse.Hit.p) * CFrame.new(0,2.5,0))
						end
					end
				)

				spawn(function()
					while wait(.1) do
						pcall(function()
							if _G.Kaitanstat then
								PointStats = game:GetService("Players").LocalPlayer.Data.Points.Value
								if world1 then
									_G.Melee = true
								else
									_G.Defense = false
								end
							end
							if _G.MaxPoint then
								PointStats = game:GetService("Players").LocalPlayer.Data.Points.Value
							end
							if _G.Melee then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Melee", PointStats)
							end
							if _G.Defense then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Defense", PointStats)
							end
							if _G.Gun then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Gun", PointStats)
							end
							if _G.Sword then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Sword", PointStats)
							end
							if _G.Fruit then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Demon Fruit", PointStats)
							end
						end)
					end
				end)


			
Tab5:AddSeperator("Raid / Dungeon")

				Tab5:AddDropdown("Selected Chips",{"Flame","Ice","Quake","Light","Dark","String","Rumble","Magma","Human: Buddha","Sand","Bird-Bird: Phoenix"}, function(value)
				_G.SelectChip = value
				end)

				 Tab5:AddToggle("Auto Buy Chips",false,function(value)
				_G.AutoBuyChip = value
					while _G.AutoBuyChip do wait()
						pcall(function()
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc","Select",_G.SelectChip)
						end)
					end
				end)
				 Tab5:AddToggle("Auto Start Raid",false,function(value)
				_G.AutoStartRaid = value
				end)

				spawn(function()
					while wait() do
						if _G.AutoStartRaid then
							if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
								if not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") and game.Players.LocalPlayer.Backpack:FindFirstChild("Special Microchip") or game.Players.LocalPlayer.Character:FindFirstChild("Special Microchip") then
									if world2 then
										fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
									elseif world3 then
										fireclickdetector(game:GetService("Workspace").Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector)
									end
								end
							end
						end
					end
				end)

				 Tab5:AddToggle("Auto Raid",false,function(value)
				_G.AutoRaids = value
				 ps=value

				 end)
			
			spawn(function()
            pcall(function() 
                while wait() do
                    if _G.AutoRaids then
                        if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetDescendants()) do
                                if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                                    pcall(function()
                                        repeat wait()
                                            sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                                            v.Humanoid.Health = 0
                                            v.HumanoidRootPart.CanCollide = false
                                        until not _G.AutoRaids or not v.Parent or v.Humanoid.Health <= 0
                                    end)
                                end
                            end
                        end
                    end
                end
            end)
        end)
        
        spawn(function() 
            pcall(function()
                while wait() do
                    if _G.AutoRaids then
                        if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
                            if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
                                TP2FF(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame*CFrame.new(0,80,100))
                            elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
                                TP2FF(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame*CFrame.new(0,80,100))
                            elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
                                TP2FF(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame*CFrame.new(0,80,100))
                            elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
                                TP2FF(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame*CFrame.new(0,80,100))
                            elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
                                TP2FF(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame*CFrame.new(0,80,100))
                            end
                        end
                    end
                end
            end)
        end)

				 Tab5:AddToggle("Auto Awake",false,function(value)
				_G.AutoAwake = value
				end)

				spawn(function()
					while wait() do
						if _G.AutoAwake then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Check")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Awaken")
						end
					end
				end)

Tab5:AddSeperator("Others Dungeon")

				if world2 then
					Tab5:AddToggle("Teleport to Lab",TPLAB,function(value)
						TPLAB = value
						while TPLAB do wait()
							TP2FF(CFrame.new(-6438.73535, 250.645355, -4501.50684))
						end
					end)
				end

				if world3 then
					Tab5:AddToggle("Teleport to Lab",TPLAB,function(value)
						TPLAB = value
						while TPLAB do wait()
							TP2FF(CFrame.new(-5017.40869, 314.844055, -2823.0127))
						end
					end)
				end

Tab5:AddSeperator("Awaken Room Teleport")

				if world2 then
					Tab5:AddToggle("Awakening Room",TPAWAKE,function(value)
						TPAWAKE = value
						while TPAWAKE do wait()
							TP2FF(CFrame.new(266.227783, 1.39509034, 1857.00732))
						end
					end)
				elseif world3 then
					Tab5:AddToggle("Awakening Room",TPAWAKE,function(value)
						TPAWAKE = value
						while TPAWAKE do wait()
							TP2FF(CFrame.new(-11571.440429688, 49.172668457031, -7574.7368164062))
						end
					end)
				end

				local l__Remotes__11 = game.ReplicatedStorage:WaitForChild("Remotes");
				u45 = l__Remotes__11.CommF_:InvokeServer("GetFruits");
				DevilFruitList = {}
				for i,v in next,u45 do
					table.insert(DevilFruitList,v.Name)
				end
				Tab6:AddDropdown("Selected Fruits",DevilFruitList, function(value)
				SelectFruitSinper = value
				end)

				Tab6:AddToggle("Buy Fruits Sniper",false,function(value)
				_G.BuyFruitSinPer = value
				end)

				spawn(function()
					while wait(.1) do
						if _G.BuyFruitSinPer then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PurchaseRawFruit",SelectFruitSinper)
						end 
					end
				end)

Tab6:AddSeperator("Others Fruits")

				Tab6:AddToggle("Bring Fruits",false,function(value)
				_G.BRINGSFRUITS = value
				end)
				Tab6:AddToggle("Keep Fruit To Inventory",false,function(value)
				_G.SaveFruits_Inventory = value
				end)
				Tab6:AddToggle("Auto DropFruits",false,function(value)
				_G.AutoDropfruits = value
				end)

				Tab6:AddToggle("Auto Random Fruits",false,function(value)
				_G.Autorandomfruits = value
				end)

				spawn(function()
					while wait(0.5) do
						if _G.Autorandomfruits then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
						end
					end
				end) 

				spawn(function()
					while wait() do
						if _G.SaveFruits_Inventory then wait()
							for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
								if string.find(v.Name,"Fruit") then
									local FruitName = RemoveSpaces(v.Name)
									if v.Name == "Bird: Falcon Fruit" then
										NameFruit = "Bird-Bird: Falcon"
									elseif v.Name == "Bird: Phoenix Fruit" then
										NameFruit = "Bird-Bird: Phoenix"
									elseif v.Name == "Human: Buddha Fruit" then
										NameFruit = "Human-Human: Buddha"
									else
										NameFruit = FruitName.."-"..FruitName
									end

									local string_1 = "getInventoryFruits";
									local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
									for i1,v1 in pairs(Target:InvokeServer(string_1)) do
										if v1.Name == NameFruit then
											HaveFruitInStore = true
										end
									end
									if not Have then
										local string_1 = "StoreFruit";
										local string_2 = NameFruit;
										local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
										Target:InvokeServer(string_1, string_2);
									end
									HaveFruitInStore = false
								end
							end
						end
					end
				end)

				spawn(function()
					while wait() do
						if _G.AutoDropfruits then
							pcall(function()
								for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
									if string.find(v.Name, "Fruit") then
										EquipWeapon(v.Name)
										SelectfruitDrop = v.Name
										wait(.1)
										if game:GetService("Players").LocalPlayer.PlayerGui.Main.Dialogue.Visible == true then
											game:GetService("Players").LocalPlayer.PlayerGui.Main.Dialogue.Visible = false
										end
										EquipWeapon(v.Name)
										game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectfruitDrop).EatRemote:InvokeServer("Drop")
									end
								end
								for i,v in pairs(game:GetService("Players").LocalPlayer.Character:GetChildren()) do
									if string.find(v.Name, "Fruit") then
										EquipWeapon(v.Name)
										SelectfruitDrop = v.Name
										wait(0.5)
										if game:GetService("Players").LocalPlayer.PlayerGui.Main.Dialogue.Visible == true then
											game:GetService("Players").LocalPlayer.PlayerGui.Main.Dialogue.Visible = false
										end
										EquipWeapon(v.Name)
										game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectfruitDrop).EatRemote:InvokeServer("Drop")
									end
								end
							end)
						end
					end
				end)

				spawn(function()
					while wait() do
						if _G.BRINGSFRUITS then
							pcall(function()
								if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
									for i,v in pairs(game.Workspace:GetChildren()) do
										if v:IsA("Tool") then
											if (v.Handle.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 20000 then
												v.Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
											else 
												TP2FF(v.Handle.CFrame)
											end
										end
									end
								end
							end)
						end
					end
				end)

				Shop:AddSeperator("Ablilities")
				Shop:AddButton("Geppo",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Geppo")
				end)
				Shop:AddButton("Buso Haki",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Buso")
				end)
				Shop:AddButton("Soru",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Soru")
				end)
				Shop:AddButton("Observation Haki", function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk","Buy")
				end)
				Shop:AddSeperator("Fighting Styles")
				Shop:AddButton("Black Leg",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
				end)
				Shop:AddButton("Electro",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
				end)
				Shop:AddButton("Fishman Karate",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
				end)
				Shop:AddButton("Dragon Claw",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","1")
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2")
				end)
				Shop:AddButton("Superhuman",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman")
				end)
				Shop:AddButton("Death Step",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
				end)
				Shop:AddButton("Sharkman Karate",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true)
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
				end)
				Shop:AddButton("Electric Claw",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
				end)
				Shop:AddButton("Dragon Talon",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
				end)
				Shop:AddSeperator("Accessory")
				Shop:AddButton("Tomoe Ring",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Tomoe Ring")
				end)

				Shop:AddButton("Black Cape",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Black Cape")
				end)

				Shop:AddButton("Swordsman Hat",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Swordsman Hat")
				end)
				Shop:AddSeperator("Sword")
				Shop:AddButton("Cutlass",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cutlass")
				end)

				Shop:AddButton("Katana",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Katana")
				end)

				Shop:AddButton("Iron Mace",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Iron Mace")
				end)

				Shop:AddButton("Duel Katana",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Duel Katana")
				end)

				Shop:AddButton("Triple Katana", function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Triple Katana")
				end)

				Shop:AddButton("Pipe",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Pipe")
				end)

				Shop:AddButton("Dual Headed Blade",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Dual-Headed Blade")
				end)

				Shop:AddButton("Bisento",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Bisento")
				end)

				Shop:AddButton("Soul Cane",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Soul Cane")
				end)

				Shop:AddSeperator("Gun")

				Shop:AddButton("Slingshot",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Slingshot")
				end)

				Shop:AddButton("Musket",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Musket")
				end)

				Shop:AddButton("Flintlock",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Flintlock")
				end)

				Shop:AddButton("Refined Flintlock",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Refined Flintlock")
				end)

				Shop:AddButton("Cannon",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cannon")
				end)

				Shop:AddButton("Kabucha",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","1")
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","2")
				end)


				Tab7:AddSeperator("Haki")


				Tab7:AddButton("Stage 0", function()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",0)
				end)
				Tab7:AddButton("Stage 1", function()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",1)
				end)
				Tab7:AddButton("Stage 2", function()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",2)
				end)
				Tab7:AddButton("Stage 3", function()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",3)
				end)
				Tab7:AddButton("Stage 4", function()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",4)
				end)
				Tab7:AddButton("Stage 5", function()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ChangeBusoStage",5)
				end)



				Tab7:AddSeperator("ESP")
				function isnil(thing)
					return (thing == nil)
				end
				local function round(n)
					return math.floor(tonumber(n) + 0.5)
				end
				Number = math.random(1,1000000)

				Tab7:AddToggle("ESP PLAYERS",false,function(value)
				ESPPlayer = value
				end)
				spawn(function()
					while wait() do
						pcall(function()
							if ESPPlayer then
								for i,v in pairs(game.Players:GetPlayers()) do
									if not isnil(v.Character) then
										if not v.Character.Head:FindFirstChild('NameEsp'..v.Name) then
											local BillboardGui = Instance.new("BillboardGui")
											local ESP = Instance.new("TextLabel")
											local HealthESP = Instance.new("TextLabel")
											BillboardGui.Parent = v.Character.Head
											BillboardGui.Name = 'NameEsp'..v.Name
											BillboardGui.ExtentsOffset = Vector3.new(0, 1, 0)
											BillboardGui.Size = UDim2.new(1,200,1,30)
											BillboardGui.Adornee = v.Character.Head
											BillboardGui.AlwaysOnTop = true
											ESP.Name = "ESP"
											ESP.Parent = BillboardGui
											ESP.TextTransparency = 0
											ESP.BackgroundTransparency = 1
											ESP.Size = UDim2.new(0, 200, 0, 30)
											ESP.Position = UDim2.new(0,25,0,0)
											ESP.Font = Enum.Font.Gotham
											ESP.Text = (v.Name ..' '..round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
											ESP.TextColor3 = Color3.fromRGB(245, 80, 245)
											ESP.TextSize = 14
											ESP.TextStrokeTransparency = 0.500
											ESP.TextWrapped = true
											HealthESP.Name = "HealthESP"
											HealthESP.Parent = ESP
											HealthESP.TextTransparency = 0
											HealthESP.BackgroundTransparency = 1
											HealthESP.Position = ESP.Position + UDim2.new(0, -25, 0, 15)
											HealthESP.Size = UDim2.new(0, 200, 0, 30)
											HealthESP.Font = Enum.Font.Gotham
											HealthESP.TextColor3 = Color3.fromRGB(255, 255, 255)
											HealthESP.TextSize = 14
											HealthESP.TextStrokeTransparency = 0.500
											HealthESP.TextWrapped = true
											HealthESP.Text = "Health "..math.floor(v.Character.Humanoid.Health).."/"..math.floor(v.Character.Humanoid.MaxHealth)
										else
											v.Character.Head['NameEsp'..v.Name].ESP.Text = (v.Name ..' '..round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
											v.Character.Head['NameEsp'..v.Name].ESP.HealthESP.Text = "Health "..math.floor(v.Character.Humanoid.Health).."/"..math.floor(v.Character.Humanoid.MaxHealth)
											v.Character.Head:FindFirstChild('NameEsp'..v.Name).ESP.TextTransparency = 0
											v.Character.Head:FindFirstChild('NameEsp'..v.Name).ESP.HealthESP.TextTransparency = 0
										end
									end
								end
							else
								for i,v in pairs(game.Players:GetPlayers()) do
									if v.Character.Head:FindFirstChild('NameEsp'..v.Name) then
										v.Character.Head:FindFirstChild('NameEsp'..v.Name).ESP.TextTransparency = 1
										v.Character.Head:FindFirstChild('NameEsp'..v.Name).ESP.HealthESP.TextTransparency = 1
									end
								end
							end              
						end)
					end
				end)

				Tab7:AddToggle("ESP Chest",false,function(value)
				ESPChest = value
				end)

				spawn(function()
					while wait() do
						pcall(function()
							if ESPChest then
								for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
									if string.find(v.Name,"Chest") then
										if not v:FindFirstChild('ChestESP'..Number) then
											local bill = Instance.new('BillboardGui',v)
											bill.Name = 'ChestESP'..Number
											bill.ExtentsOffset = Vector3.new(0, 1, 0)
											bill.Size = UDim2.new(1,200,1,30)
											bill.Adornee = v
											bill.AlwaysOnTop = true
											local name = Instance.new('TextLabel',bill)
											name.Font = Enum.Font.Gotham
											name.TextSize = 14
											name.TextWrapped = true
											name.Size = UDim2.new(1,0,1,0)
											name.TextYAlignment = 'Top'
											name.BackgroundTransparency = 1
											name.TextTransparency = 0
											name.TextStrokeTransparency = 0.5
											if v.Name == "Chest1" then
												name.TextColor3 = Color3.fromRGB(200,200,200)
												name.Text = ("Chest 1" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
											end
											if v.Name == "Chest2" then
												name.TextColor3 = Color3.fromRGB(245, 245, 80)
												name.Text = ("Chest 2" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
											end
											if v.Name == "Chest3" then
												name.TextColor3 = Color3.fromRGB(80, 245, 245)
												name.Text = ("Chest 3" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
											end
										else
											v:FindFirstChild('ChestESP'..Number).TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
										end
									end
								end
							else
								if v:FindFirstChild('ChestESP'..Number) then
									v:FindFirstChild('ChestESP'..Number).TextLabel.TextTransparency = 1
								end
							end
						end)
					end
				end)

				Tab7:AddToggle("ESP Fruit",false,function(value)
				 ESPFruit = value
				end)

				spawn(function()
					while wait() do 
						pcall(function()
							for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
								if ESPFruit then
									if string.find(v.Name, "Fruit") then   
										if not v.Handle:FindFirstChild('FruitESP'..Number) then
											local bill = Instance.new('BillboardGui',v.Handle)
											bill.Name = 'FruitESP'..Number
											bill.ExtentsOffset = Vector3.new(0, 1, 0)
											bill.Size = UDim2.new(1,200,1,30)
											bill.Adornee = v.Handle
											bill.AlwaysOnTop = true
											local name = Instance.new('TextLabel',bill)
											name.Font = Enum.Font.Gotham
											name.TextSize = 14
											name.TextWrapped = true
											name.Size = UDim2.new(1,0,1,0)
											name.TextYAlignment = 'Top'
											name.BackgroundTransparency = 1
											name.TextTransparency = 0
											name.TextStrokeTransparency = 0.5
											name.TextColor3 = Color3.fromRGB(245, 80, 80)
											name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
										else
											v.Handle['FruitESP'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
										end
									end
								else
									if v.Handle:FindFirstChild('FruitESP'..Number) then
										v.Handle:FindFirstChild('FruitESP'..Number).TextLabel.TextTransparency = 1
									end
								end
							end
						end)
					end
				end)

				Tab7:AddToggle("ESP Flower",false,function(value)
				ESPFlower = value
				end)

				spawn(function()
					while wait() do
						pcall(function()
							if ESPFlower then 
								for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
									if v.Name == "Flower2" or v.Name == "Flower1" then
										if not v:FindFirstChild('FlowerESP'..Number) then
											local bill = Instance.new('BillboardGui',v)
											bill.Name = 'FlowerESP'..Number
											bill.ExtentsOffset = Vector3.new(0, 1, 0)
											bill.Size = UDim2.new(1,200,1,30)
											bill.Adornee = v
											bill.AlwaysOnTop = true
											local name = Instance.new('TextLabel',bill)
											name.Font = Enum.Font.Gotham
											name.FontSize = "Size14"
											name.TextWrapped = true
											name.Size = UDim2.new(1,0,1,0)
											name.TextYAlignment = 'Top'
											name.BackgroundTransparency = 1
											name.TextTransparency = 0
											name.TextStrokeTransparency = 0.5
											name.TextColor3 = Color3.fromRGB(255, 0, 0)
											if v.Name == "Flower1" then 
												name.Text = ("Blue Flower" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
												name.TextColor3 = Color3.fromRGB(0, 0, 255)
											end
											if v.Name == "Flower2" then
												name.Text = ("Red Flower" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
												name.TextColor3 = Color3.fromRGB(255, 0, 0)
											end
										else
											v:FindFirstChild('FlowerESP'..Number).TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
										end
									end   
								end
							else
								if v:FindFirstChild('FlowerESP'..Number) then
									v:FindFirstChild('FlowerESP'..Number).TextLabel.TextTransparency = 1
								end
							end
						end)
					end
				end)

				Tab7:AddSeperator("Server")
				Tab7:AddButton("Server Hop",function()
				Hop()
				end)

				Tab7:AddButton("Rejoin Server",function()
				game:GetService("TeleportService"):Teleport(game.PlaceId, game:GetService("Players").LocalPlayer)
				end)

				Tab7:AddButton("Hop To Lower Player",function()
				getgenv().AutoTeleport = true
					getgenv().DontTeleportTheSameNumber = true 
					getgenv().CopytoClipboard = false
					if not game:IsLoaded() then
						repeat wait() until game:IsLoaded()
					end
					local maxplayers = math.huge
					local serversmaxplayer;
					local goodserver;
					local gamelink = "https://games.roblox.com/v1/games/" .. game.PlaceId .. "/servers/Public?sortOrder=Asc&limit=100" 
					function serversearch()
						for _, v in pairs(game:GetService("HttpService"):JSONDecode(game:HttpGetAsync(gamelink)).data) do
							if type(v) == "table" and v.playing ~= nil and maxplayers > v.playing then
								serversmaxplayer = v.maxPlayers
								maxplayers = v.playing
								goodserver = v.id
							end
						end
					end
					function getservers()
						serversearch()
						for i,v in pairs(game:GetService("HttpService"):JSONDecode(game:HttpGetAsync(gamelink))) do
							if i == "nextPageCursor" then
								if gamelink:find("&cursor=") then
									local a = gamelink:find("&cursor=")
									local b = gamelink:sub(a)
									gamelink = gamelink:gsub(b, "")
								end
								gamelink = gamelink .. "&cursor=" ..v
								getservers()
							end
						end
					end 
					getservers()
					if CopytoClipboard then
					end
					if AutoTeleport then
					if DontTeleportTheSameNumber then 
					if #game:GetService("Players"):GetPlayers() - 4  == maxplayers then
					elseif goodserver == game.JobId then
					end
					end
					game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, goodserver)
					end
				end)

				Tab7:AddButton("Remove Fog",function()
					spawn(function()
						pcall(function()
							game.Lighting.FogEnd = math.huge
							game:GetService("Lighting").FantasySky:Destroy()
						end)
					end)
				end)

				Tab7:AddButton("Fps Boost",function()
				local decalsyeeted = true -- Leaving this on makes games look shitty but the fps goes up by at least 20.
						local g = game
						local w = g.Workspace
						local l = g.Lighting
						local t = w.Terrain
						t.WaterWaveSize = 0
						t.WaterWaveSpeed = 0
						t.WaterReflectance = 0
						t.WaterTransparency = 0
						l.GlobalShadows = false
						l.FogEnd = 9e9
						l.Brightness = 0
						settings().Rendering.QualityLevel = "Level01"
						for i, v in pairs(g:GetDescendants()) do
							if v:IsA("Part") or v:IsA("Union") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then 
								v.Material = "Plastic"
								v.Reflectance = 0
							elseif v:IsA("Decal") or v:IsA("Texture") and decalsyeeted then
								v.Transparency = 1
							elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
								v.Lifetime = NumberRange.new(0)
							elseif v:IsA("Explosion") then
								v.BlastPressure = 1
								v.BlastRadius = 1
							elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
								v.Enabled = false
							elseif v:IsA("MeshPart") then
								v.Material = "Plastic"
								v.Reflectance = 0
								v.TextureID = 10385902758728957
							end
						end
						for i, e in pairs(l:GetChildren()) do
							if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
								e.Enabled = false
							end
						end
						end)

				Tab7:AddSeperator("UI")



				Tab7:AddButton("Open Devil Shop",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
					game.Players.LocalPlayer.PlayerGui.Main.FruitShop.Visible = true
				end)

				Tab7:AddButton("Open Inventory",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryWeapons")
					wait(.3)
					game.Players.LocalPlayer.PlayerGui.Main.Inventory.Visible = true
				end)

				Tab7:AddButton("Open Inventory Fruit",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryFruits")
					game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Visible = true
				end)

                Tab7:AddSeperator("Team")
                
				Tab7:AddButton("Join Pirates Team",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetTeam","Pirates") 
				end)

				Tab7:AddButton("Join Marines Team",function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetTeam","Marines") 
				end)

				Tab7:AddSeperator("Ablility")


				Tab7:AddToggle("Dodge NoCooldown", false, function(value)
				_G.DodgeNoCooldown = value
				DodgeNoCooldown()
				end)

				Tab7:AddToggle("Soru No Cooldown", false, function(value)
				_G.SoruNoCooldown = value
				SoruNoCooldown()
				end)

				Tab7:AddToggle("Infinits Geppo", false, function(value)
				_G.InfinitsGeppo = value
				NoGeppoCool()
				end)

				Tab7:AddToggle("Infinits Energy", false, function(value)
				_G.InfinitsEnergy = value
				INGENG()
				end)

				Tab7:AddToggle("Infinite Agility", false, function(value)
				InfiniteAbility = value
				end)






				spawn(function()
					while wait() do
						if InfiniteAbility then
							InfAb()
						end
					end
				end)

				function InfAb()
					if InfiniteAbility then
						if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility") then
							local inf = Instance.new("ParticleEmitter")
							inf.Acceleration = Vector3.new(0,0,0)
							inf.Archivable = true
							inf.Drag = 20
							inf.EmissionDirection = Enum.NormalId.Top
							inf.Enabled = true
							inf.Lifetime = NumberRange.new(0.2,0.2)
							inf.LightInfluence = 0
							inf.LockedToPart = true
							inf.Name = "Agility"
							inf.Rate = 500
							local numberKeypoints2 = {
								NumberSequenceKeypoint.new(0, 0); 
								NumberSequenceKeypoint.new(1, 4); 
							}

							inf.Size = NumberSequence.new(numberKeypoints2)
							inf.RotSpeed = NumberRange.new(999, 9999)
							inf.Rotation = NumberRange.new(0, 0)
							inf.Speed = NumberRange.new(30, 30)
							inf.SpreadAngle = Vector2.new(360,360)
							inf.Texture = "rbxassetid://243098098"
							inf.VelocityInheritance = 0
							inf.ZOffset = 2
							inf.Transparency = NumberSequence.new(0)
							inf.Color = ColorSequence.new(Color3.fromRGB(0, 255, 255),Color3.fromRGB(0, 255, 255))
							inf.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
						end
					else
						repeat wait()
							game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility"):Destroy()
						until not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility")
					end
				end

				nododgecool = false
				function DodgeNoCooldown()
					if _G.DodgeNoCooldown then
						for i,v in next, getgc() do
							if game.Players.LocalPlayer.Character.Dodge then
								if typeof(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character.Dodge then
									for i2,v2 in next, getupvalues(v) do
										if tostring(v2) == "0.4" then
											repeat wait(.1)
												setupvalue(v,i2,0)
											until not _G.DodgeNoCooldown
										end
									end
								end
							end
						end
					end
				end
				function InfinitsGeppo()
					if _G.InfinitsGeppo then
						for i,v in next, getgc() do
							if game.Players.LocalPlayer.Character.Geppo then
								if typeof(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character.Geppo then
									for i2,v2 in next, getupvalues(v) do
										if tostring(v2) == "0" then
											repeat wait(.1)
												setupvalue(v,i2,0)
											until not _G.InfinitsGeppo
										end
									end
								end
							end
						end
					end
				end
				function SoruNoCooldown()
					for i, v in pairs(getgc()) do
						if type(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character:WaitForChild("Soru") then
							for i2,v2 in pairs(debug.getupvalues(v)) do
								if type(v2) == 'table' then
									if v2.LastUse then
										repeat wait()
											setupvalue(v, i2, {LastAfter = 0,LastUse = 0})
										until not _G.SoruNoCooldown
									end
								end
							end
						end
					end
				end
				local LocalPlayer = game:GetService'Players'.LocalPlayer
				local originalstam = LocalPlayer.Character.Energy.Value
				function INGENG()
					game:GetService'Players'.LocalPlayer.Character.Energy.Changed:connect(function()
						if _G.InfinitsEnergy then
							LocalPlayer.Character.Energy.Value = originalstam
						end 
					end)
				end

				spawn(function()
					for i = 1,math.huge do game:GetService("RunService").RenderStepped:Wait()
						if _G.AutoBartilo and MagnetBartlio then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Swan Pirate [Lv. 775]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 400 then    v.HumanoidRootPart.CanCollide = false
									v.HumanoidRootPart.CFrame = PosMonBartlio
												v.Humanoid.JumpPower = 0
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.Size = Vector3.new(150,150,150)
												v.HumanoidRootPart.CanCollide = false
												if v.Humanoid:FindFirstChild("Animator") then
													v.Humanoid.Animator:Destroy()
												end
												sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
												v.Humanoid:ChangeState(14)
								end 
							end
						end
					end
				end)

				spawn(function()
					while wait() do
						if _G.AutoQuestBartilo and world2 then
							pcall(function()
								local QuestTitle = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
								if game.Players.LocalPlayer.Data.Level.Value >= 850 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 0 then
									if QuestVis() then 
										if string.find(QuestTitle, "Swan Pirates") and string.find(QuestTitle, "50") then
											if game:GetService("Workspace").Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
												for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
													if v.Name == "Swan Pirate [Lv. 775]" then
														repeat task.wait()
															EquipWeapon(_G.SelectToolWeapon)
															v.Humanoid.WalkSpeed = 0
															v.HumanoidRootPart.CanCollide = false
															v.Head.CanCollide = false
															PosMonBartlio =  v.HumanoidRootPart.CFrame
															MagnetBartlio = true
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
															_G.FastAttack = true
															_G.FastAttack1 = true
														until not v.Parent or v.Humanoid.Health <= 0 or _G.AutoBartilo == false or not QuestVis()
													end
												end
											else
												MagnetBartlio = false
												if game:GetService("ReplicatedStorage"):FindFirstChild("Swan Pirate [Lv. 775]") then
													TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Swan Pirate [Lv. 775]").HumanoidRootPart.CFrame * CFrame.new(0,25,5))
												end
											end
										else
											MagnetBartlio = false
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
										end
									elseif not QuestVis() then
										repeat 
											TP2FF(CFrame.new(-456.28952, 73.0200958, 299.895966)) 
											wait() 
										until not _G.AutoBartilo or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-456.28952, 73.0200958, 299.895966)).Magnitude <= 3
										wait(1.1)
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest","BartiloQuest",1)
										wait(.5)
									end 
								elseif game.Players.LocalPlayer.Data.Level.Value >= 850 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 1 then
									if QuestVis() then
										if game:GetService("Workspace").Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
											for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
												if v.Name == "Jeremy [Lv. 850] [Boss]" then
													if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
														repeat task.wait()
															EquipWeapon(_G.SelectToolWeapon)
															v.Humanoid.WalkSpeed = 0
															v.HumanoidRootPart.CanCollide = false                                        
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
															_G.FastAttack = true
															_G.FastAttack1 = true
														until not v.Parent or v.Humanoid.Health <= 0 or _G.AutoBartilo == false
													end
												end
											end
										elseif game:GetService("ReplicatedStorage"):FindFirstChild("Jeremy [Lv. 850] [Boss]") then
											TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Jeremy [Lv. 850] [Boss]").HumanoidRootPart.CFrame * CFrame.new(0,25,5))
										end
									elseif not QuestVis() then
										repeat 
											TP2FF(CFrame.new(-456.28952, 73.0200958, 299.895966)) 
											wait() 
										until not _G.AutoBartilo or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-456.28952, 73.0200958, 299.895966)).Magnitude <= 10
										wait(1.1)
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo")
										wait(.5)
									end
								elseif game.Players.LocalPlayer.Data.Level.Value >= 850 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 2 then
									repeat
										TP2FF(CFrame.new(-1850.49329, 13.1789551, 1750.89685)) 
										wait() 
									until not _G.AutoBartilo or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1850.49329, 13.1789551, 1750.89685)).Magnitude <= 3
									wait(.3)
									repeat
										TP2FF(CFrame.new(-1858.87305, 19.3777466, 1712.01807)) 
										wait() 
									until not _G.AutoBartilo or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1858.87305, 19.3777466, 1712.01807)).Magnitude <= 3
									wait(.3)
									repeat
										TP2FF(CFrame.new(-1803.94324, 16.5789185, 1750.89685)) 
										wait() 
									until not _G.AutoBartilo or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1803.94324, 16.5789185, 1750.89685)).Magnitude <= 3
									wait(.3)
									repeat
										TP2FF(CFrame.new(-1858.55835, 16.8604317, 1724.79541)) 
										wait() 
									until not _G.AutoBartilo or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1858.55835, 16.8604317, 1724.79541)).Magnitude <= 3
									wait(.3)
									repeat
										TP2FF(CFrame.new(-1869.54224, 15.987854, 1681.00659)) 
										wait() 
									until not _G.AutoBartilo or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1869.54224, 15.987854, 1681.00659)).Magnitude <= 3
									wait(.3)
									repeat
										TP2FF(CFrame.new(-1800.0979, 16.4978027, 1684.52368))
										wait() 
									until not _G.AutoBartilo or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1800.0979, 16.4978027, 1684.52368)).Magnitude <= 3
									wait(.3)
									repeat
										TP2FF(CFrame.new(-1819.26343, 14.795166, 1717.90625)) 
										wait() 
									until not _G.AutoBartilo or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1819.26343, 14.795166, 1717.90625)).Magnitude <= 3
									wait(.3)
									repeat
										TP2FF(CFrame.new(-1813.51843, 14.8604736, 1724.79541)) 
										wait() 
									until not _G.AutoBartilo or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1813.51843, 14.8604736, 1724.79541)).Magnitude <= 3
								end
							end)
						end 
					end
				end)

				spawn(function()
					while wait() do
						if _G.AutoSaber and world1 then
							pcall(function()
								local MyLevel = game.Players.LocalPlayer.Data.Level.Value 
								local Part = game:GetService("Workspace").Map.Jungle.Final:FindFirstChild("Part")
								if MyLevel >= 200 and Part.CanCollide == true and Part.Transparency == 0 then
									repeat                
										wait(.1)
										if not game.Players.LocalPlayer.Backpack:FindFirstChild("Torch") then
											repeat 
												TP2FF(CFrame.new(-1421.87024, 55.4666862, 21.7750397)) 
												wait() 
											until not _G.AutoSaber or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1421.87024, 55.4666862, 21.7750397)).Magnitude <= 3
											wait(.1)
											repeat 
												TP2FF(CFrame.new(-1647.19556, 29.1544189, 438.299408)) 
												wait() 
											until not _G.AutoSaber or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1647.19556, 29.1544189, 438.299408)).Magnitude <= 3
											wait(.1)
											repeat 
												TP2FF(CFrame.new(-1324.10144, 31.4560413, -461.404114)) 
												wait() 
											until not _G.AutoSaber or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1324.10144, 31.4560413, -461.404114)).Magnitude <= 3
											wait(.1)
											repeat 
												TP2FF(CFrame.new(-1152.38464, 9.74718285, -700.309875)) 
												wait() 
											until not _G.AutoSaber or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1152.38464, 9.74718285, -700.309875)).Magnitude <= 3
											wait(.1)
											repeat 
												TP2FF(CFrame.new(-1180.89563, 21.0007095, 187.861374)) 
												wait() 
											until not _G.AutoSaber or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1180.89563, 21.0007095, 187.861374)).Magnitude <= 3
											wait(.1)
											repeat 
												TP2FF(CFrame.new(-1610.00757, 11.5049858, 164.001587)) 
												wait() 
											until not _G.AutoSaber or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-1610.00757, 11.5049858, 164.001587)).Magnitude <= 3
											wait(.1)             
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","GetTorch")
										else
											EquipWeapon("Torch")
											if not game.Players.LocalPlayer.Backpack:FindFirstChild("Cup") then
												repeat 
													TP2FF(CFrame.new(1114.55762, 4.9214654, 4349.2334)) 
													wait() 
												until not _G.AutoSaber or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(1114.55762, 4.9214654, 4349.2334)).Magnitude <= 3
												wait(3)
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","DestroyTorch")
												repeat 
													TP2FF(CFrame.new(1114.26721, 4.16943789, 4366.15332)) 
													wait() 
												until not _G.AutoSaber or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(1114.26721, 4.16943789, 4366.15332)).Magnitude <= 3
												wait(.3)
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress")
												wait(.3)
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","GetCup")
											else
												EquipWeapon("Cup")
												repeat 
													TP2FF(CFrame.new(1397.0614, 37.3480072, -1321.03955)) 
													wait() 
												until not _G.AutoSaber or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(1397.0614, 37.3480072, -1321.03955)).Magnitude <= 3
												wait(1.1)            
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","FillCup",game:GetService("Players").LocalPlayer.Character:FindFirstChild("Cup"))
												repeat 
													TP2FF(CFrame.new(1457.87976, 88.2521744, -1390.39575)) 
													wait() 
												until not _G.AutoSaber or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(1457.87976, 88.2521744, -1390.39575)).Magnitude <= 3
												wait(1.1)
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan")
												repeat 
													TP2FF(CFrame.new(-908.365845, 13.7778397, 4077.84668, -0.0465272143, 3.05009067e-08, -0.998917043, -2.55670285e-09, 1, 3.06530588e-08, 0.998917043, 3.98013533e-09, -0.0465272143)) 
													wait() 
												until (Vector3.new(-908.365845, 13.7778397, 4077.84668)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or _G.AutoSaber == false
												wait(1.1)            
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
												wait(.3)
												repeat TP2FF(CFrame.new(-2850.20068, 7.39224768, 5354.99268)) 
													wait() 
												until (Vector3.new(-2850.20068, 7.39224768, 5354.99268)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3
												wait(.3)
											end
										end
										if game:GetService("Workspace").Enemies:FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
											for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
												if v.Name == "Mob Leader [Lv. 120] [Boss]" then
													if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
														repeat task.wait()    
															EquipWeapon(_G.SelectToolWeapon) 
															v.HumanoidRootPart.Size = Vector3.new(50,50,50)
															v.HumanoidRootPart.CanCollide = false
															v.Humanoid.WalkSpeed = 0
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
															_G.FastAttack = true 
															_G.FastAttack1 = true
														until v.Humanoid.Health <= 0 or not v.Parent or not _G.AutoSaber
														repeat 
															TP2FF(CFrame.new(-908.365845, 13.7778397, 4077.84668, -0.0465272143, 3.05009067e-08, -0.998917043, -2.55670285e-09, 1, 3.06530588e-08, 0.998917043, 3.98013533e-09, -0.0465272143)) 
															wait() 
														until (Vector3.new(-908.365845, 13.7778397, 4077.84668)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or _G.AutoSaber == false
														wait(1.1)
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress")
														wait(.3)
														EquipWeapon("Relic")
														repeat 
															TP2FF(CFrame.new(-1405.45728, 29.8778057, 4.69083405, 0.87234509, 1.10293916e-08, 0.488890588, -2.06415529e-09, 1, -1.88768947e-08, -0.488890588, 1.54580206e-08, 0.87234509)) 
															wait() 
														until (Vector3.new(-1405.45728, 29.8778057, 4.69083405)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or _G.AutoSaber == false
														wait(.3)
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","PlaceRelic")
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress")
														wait(.3)
													end
												end
											end
										elseif game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
											TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]") * CFrame.new(0,25,5))
										end
									until Part.CanCollide == false and Part.Transparency == 1 or not _G.AutoSaber
								elseif MyLevel >= 200 and Part.CanCollide == false and Part.Transparency == 1 then
									if game:GetService("Workspace").Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
										for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
											if v.Name == "Saber Expert [Lv. 200] [Boss]" then 
												if v.Humanoid.Health > 0 and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
													repeat task.wait()
														EquipWeapon(_G.SelectWeapon)
														v.Humanoid.WalkSpeed = 0
														v.HumanoidRootPart.CanCollide = false
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
														_G.FastAttack = true 
															_G.FastAttack1 = true
													until _G.AutoSaber == true or v.Humanoid.Health <= 0
												end
											end
										end 
									elseif game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
										TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]").HumanoidRootPart.CFrame * CFrame.new(0,25,5))
									else
										if _G.AutoSaberHop then 
											Hop()
										end
									end
								end
							end)
						end
					end
				end)

				spawn(function()
					while wait() do
						if _G.AutoSerpentbow and world3 then
							pcall(function()
								if game:GetService("Workspace").Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name == "Island Empress [Lv. 1675] [Boss]" then
											if v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
												repeat task.wait()
													EquipWeapon(_G.SelectToolWeapon)
													v.HumanoidRootPart.CanCollide = false
													v.Humanoid.WalkSpeed = 0
													topos(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
													_G.FastAttack = true
													_G.FastAttack1 = true
												until _G.AutoSerpentbow == false or v.Humanoid.Health <= 0
											end                           
										end
									end
								elseif game:GetService("ReplicatedStorage"):FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
									TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Island Empress [Lv. 1675] [Boss]").HumanoidRootPart.CFrame * CFrame.new(0,25,5))
								else
									if _G.AutoSerpentbow_Hop then
										Hop()
									end
								end
							end)
						end
					end
				end)
				 
				 
				 spawn(function()
					while wait() do
						if _G.AutoDarkDagger and world3 then
							pcall(function()
								if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 5000] [Raid Boss]") then
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if (v.Name == "rip_indra True Form [Lv. 5000] [Raid Boss]" or v.Name == "rip_indra [Lv. 5000] [Raid Boss]") then
											if v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
												repeat task.wait()
													EquipWeapon(_G.SelectToolWeapon)
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
													v.Humanoid.WalkSpeed = 0
													v.HumanoidRootPart.CanCollide = false
													_G.FastAttack = true
													_G.FastAttack1 = true
												until _G.AutoDarkDagger == false or v.Humanoid.Health <= 0 or not v.Parent
											end
										end
									end
								elseif game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra [Lv. 5000] [Raid Boss]") then
									if game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
										TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]").HumanoidRootPart.CFrame * CFrame.new(0,25,5))
									elseif game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra [Lv. 5000] [Raid Boss]") then
										TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra [Lv. 5000] [Raid Boss]").HumanoidRootPart.CFrame * CFrame.new(0,25,5))
									end
								else
									if _G.AutoDaggerHop then 
										Hop()
									end
								end
							end)
						end
					end
				end)
					
				spawn(function()
					while wait() do
						if _G.AutoCanvender and world3 then
							pcall(function()
								if game:GetService("Workspace").Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name =="Beautiful Pirate [Lv. 1950] [Boss]" then
											if v.Humanoid.Health > 0 and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") then
												repeat task.wait()
													EquipWeapon(_G.SelectToolWeaponWeapon)
													v.HumanoidRootPart.CanCollide = false
													v.Humanoid.WalkSpeed = 0
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
													_G.FastAttack = true
													_G.FastAttack1 = true
												until _G.AutoCanvender == false or v.Humanoid.Health <= 0
											end                           
										end
									end
								elseif game:GetService("ReplicatedStorage"):FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
									TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]").HumanoidRootPart.CFrame * CFrame.new(0,50,0))
								else
									if _G.AutoCanvenderHop then
										Hop()
									end
								end
							end)
						end
					end
				end)

				spawn(function()
					while wait() do
						if _G.AutoBuddySword and world3 then
							if game.ReplicatedStorage:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") or game.Workspace.Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
								if game.Workspace.Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
									for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
										if _G.AutoBuddySword and v.Name == "Cake Queen [Lv. 2175] [Boss]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
											Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
											if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
												if Farmtween then
													Farmtween:Stop()
												end
												EquipWeapon(_G.SelectToolWeapon)
												_G.FastAttack = true
												_G.FastAttack1 = true
												if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
													local args = {
														[1] = "Buso"
													}
													game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
												end
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
											end 
										end
									end
								else
									BuddySwordsTween = toTarget(CFrame.new(-821, 66, -10965).Position,CFrame.new(-821, 66, -10965))
									if (CFrame.new(-821, 66, -10965).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
										if BuddySwordsTween then
											BuddySwordsTween:Stop()
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-821, 66, -10965)
									end
								end
							elseif _G.AutoBuddySwords_HOP then
								local PlaceID = game.PlaceId
								local AllIDs = {}
								local foundAnything = ""
								local actualHour = os.date("!*t").hour
								local Deleted = false
								function TPReturner()
									local Site;
									if foundAnything == "" then
										Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
									else
										Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
									end
									local ID = ""
									if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
										foundAnything = Site.nextPageCursor
									end
									local num = 0;
									for i,v in pairs(Site.data) do
										local Possible = true
										ID = tostring(v.id)
										if tonumber(v.maxPlayers) > tonumber(v.playing) then
											for _,Existing in pairs(AllIDs) do
												if num ~= 0 then
													if ID == tostring(Existing) then
														Possible = false
													end
												else
													if tonumber(actualHour) ~= tonumber(Existing) then
														local delFile = pcall(function()
															-- delfile("NotSameServers.json")
															AllIDs = {}
															table.insert(AllIDs, actualHour)
														end)
													end
												end
												num = num + 1
											end
											if Possible == true then
												table.insert(AllIDs, ID)
												wait()
												pcall(function()
													-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
													wait()
													game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
												end)
												wait(1)
											end
										end
									end
								end
								function Teleport() 
									while wait() do
										pcall(function()
											TPReturner()
											if foundAnything ~= "" then
												TPReturner()
											end
										end)
									end
								end
								Teleport()
							end
						end
					end
				end)

				spawn(function()
					while wait() do
						if _G.AutoYama and world3 then
							if game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("EliteHunter", "Progress") < 30 then
								if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
									if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Diablo") or string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Urban") or string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Deandre") then
										for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
											if string.find(v.Name,"Diablo") then
												YamaTween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
													if YamaTween then
														YamaTween:Stop()
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
												end
											end	
											if string.find(v.Name,"Urban") then
												YamaTween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
													if YamaTween then
														YamaTween:Stop()
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
												end
											end	
											if string.find(v.Name,"Deandre") then
												YamaTween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
													if YamaTween then
														YamaTween:Stop()
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
												end
											end	
										end
										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
											if _G.AutoYama and string.find(v.Name,"Diablo") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
												repeat wait()
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
													if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
														if Farmtween then
															Farmtween:Stop()
														end
														EquipWeapon(_G.SelectToolWeapon)
														_G.FastAttack = true
														_G.FastAttack1 = true
														if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
															local args = {
																[1] = "Buso"
															}
															game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
														end
														game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
														game:GetService'VirtualUser':CaptureController()
														game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
													end 
												until not _G.AutoYama or not v.Parent or v.Humanoid.Health <= 0
												_G.FastAttack = false
												_G.FastAttack1 = false
											end
											if _G.AutoYama and string.find(v.Name,"Urban") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
												repeat wait()
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
													if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
														if Farmtween then
															Farmtween:Stop()
														end
														EquipWeapon(_G.SelectToolWeapon)
														_G.FastAttack = true
														_G.FastAttack1 = true
														if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
															local args = {
																[1] = "Buso"
															}
															game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
														end
														game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
													end 
												until not _G.AutoYama or not v.Parent or v.Humanoid.Health <= 0
												_G.FastAttack = false
												_G.FastAttack1 = false
											end
											if _G.AutoYama and string.find(v.Name,"Deandre") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
												repeat wait()
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
													if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
														if Farmtween then
															Farmtween:Stop()
														end
														EquipWeapon(_G.SelectToolWeapon)
														_G.FastAttack = true
														_G.FastAttack1 = true
														if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
															local args = {
																[1] = "Buso"
															}
															game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
														end
														game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
																						game:GetService'VirtualUser':CaptureController()
												game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
													end 
												until not _G.AutoYama or not v.Parent or v.Humanoid.Health <= 0
												_G.FastAttack = false
												_G.FastAttack1 = false
											end
										end
									else
										local string_1 = "EliteHunter";
										local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
										Target:InvokeServer(string_1);
									end
								else
									if _G.AutoYama_HOP and game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("EliteHunter") == "I don't have anything for you right now. Come back later." then
										local PlaceID = game.PlaceId
										local AllIDs = {}
										local foundAnything = ""
										local actualHour = os.date("!*t").hour
										local Deleted = false
										function TPReturner()
											local Site;
											if foundAnything == "" then
												Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
											else
												Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
											end
											local ID = ""
											if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
												foundAnything = Site.nextPageCursor
											end
											local num = 0;
											for i,v in pairs(Site.data) do
												local Possible = true
												ID = tostring(v.id)
												if tonumber(v.maxPlayers) > tonumber(v.playing) then
													for _,Existing in pairs(AllIDs) do
														if num ~= 0 then
															if ID == tostring(Existing) then
																Possible = false
															end
														else
															if tonumber(actualHour) ~= tonumber(Existing) then
																local delFile = pcall(function()
																	-- delfile("NotSameServers.json")
																	AllIDs = {}
																	table.insert(AllIDs, actualHour)
																end)
															end
														end
														num = num + 1
													end
													if Possible == true then
														table.insert(AllIDs, ID)
														wait()
														pcall(function()
															-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
															wait()
															game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
														end)
														wait(1)
													end
												end
											end
										end
										function Teleport() 
											while wait() do
												pcall(function()
													TPReturner()
													if foundAnything ~= "" then
														TPReturner()
													end
												end)
											end
										end
										Teleport()
									else
										local string_1 = "EliteHunter";
										local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
										Target:InvokeServer(string_1);
									end
								end
							else
								TweenYema = toTarget(game.Workspace.Map.Waterfall.SealedKatana.Handle.Position,game.Workspace.Map.Waterfall.SealedKatana.Handle.CFrame)
								if (game.Workspace.Map.Waterfall.SealedKatana.Handle.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if TweenYema then
										TweenYema:Stop()
									end
									if game.Workspace.Enemies:FindFirstChild("Ghost [Lv. 1500]") then
										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
											if _G.AutoYama and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and v.Name == "Ghost [Lv. 1500]" then
												repeat wait()
													if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
														Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
													elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
														if Farmtween then
															Farmtween:Stop()
														end
														EquipWeapon(_G.SelectToolWeapon)
														_G.FastAttack = true
														_G.FastAttack1 = true
														if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
															local args = {
																[1] = "Buso"
															}
															game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
														end
														game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
													end 
												until not _G.AutoYama or not v.Parent or v.Humanoid.Health <= 0
												_G.FastAttack = false
												_G.FastAttack1 = false
											end
										end
									else
										if TweenYema then
											TweenYema:Stop()
										end
										fireclickdetector(game.Workspace.Map.Waterfall.SealedKatana.Handle.ClickDetector)
									end
								end
							end
						end
					end
				end)

				function eltiepg()
					return game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter","Progress")
				end

				spawn(function()
					while wait() do 
						if _G.LockElite then
							if elitepg() >= _G.SelectLockElite then
								game.Players.LocalPlayer:Kick("Gang Gang : LockElite Hunter")
							end
						end
					end
				end)

				spawn(function()
					while wait() do
						if  _G.AutoElitehunter and world3 then
							pcall(function()
								local QuestTitle = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
								if not QuestVis() then
									repeat  wait()
										TP2FF(CFrame.new(-5418.892578125, 313.74130249023, -2826.2260742188)) 
									until not _G.AutoElitehunter or (Vector3.new(-5418.892578125, 313.74130249023, -2826.2260742188)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3
									if (Vector3.new(-5418.892578125, 313.74130249023, -2826.2260742188)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
										wait(1.1)
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
										wait(0.5)
									end
								elseif QuestVis() then
									if string.find(QuestTitle,"Diablo") or string.find(QuestTitle,"Deandre") or string.find(QuestTitle,"Urban") then
										if game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
											for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
												if v.Name == "Diablo [Lv. 1750]" or v.Name == "Deandre [Lv. 1750]" or v.Name == "Urban [Lv. 1750]" then
													if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
														repeat task.wait()
															EquipWeapon(_G.SelectToolWeapon)
															v.HumanoidRootPart.CanCollide = false
															v.Humanoid.WalkSpeed = 0
															  _G.FastAttack = true 
															  _G.FastAttack1 = true
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
														until _G.AutoEliteHunter == false or v.Humanoid.Health <= 0 or not v.Parent
													end
												end
											end
										else
											if game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") then
												TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame * CFrame.new(0,25,5))
											elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") then
												TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame * CFrame.new(0,25,5))
											elseif game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") then
												TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame * CFrame.new(0,25,5))
											else
												if _G.AutoEliteHunterHop then
													Hop()
												end
											end
										end                    
									end
								end
							end)
						end
					end
				end)

				spawn(function()
					while wait(.5) do
						if _G.AutoSuperhuman and game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Combat") then
								local args = {
									[1] = "BuyBlackLeg"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end   
							if game.Players.LocalPlayer.Character:FindFirstChild("Superhuman") or game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								_G.SelectToolWeapon = "Superhuman"
							end  
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 299 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								_G.SelectToolWeapon = "Black Leg"
							end
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 299 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								_G.SelectToolWeapon = "Electro"
							end
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 299 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								_G.SelectToolWeapon = "Fishman Karate"
							end
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 299 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								_G.SelectToolWeapon = "Dragon Claw"
							end
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								local args = {
									[1] = "BuyElectro"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
							if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								local args = {
									[1] = "BuyElectro"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
							
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								local args = {
									[1] = "BuyFishmanKarate"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
							if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								local args = {
									[1] = "BuyFishmanKarate"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								local args = {
									[1] = "BlackbeardReward",
									[2] = "DragonClaw",
									[3] = "2"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
							if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								local args = {
									[1] = "BlackbeardReward",
									[2] = "DragonClaw",
									[3] = "2"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								local args = {
									[1] = "BuySuperhuman"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
							if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								local args = {
									[1] = "BuySuperhuman"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end 
						end
						if _G.AutoDeathStep  and game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 400 then
								local args = {
									[1] = "BuyDeathStep"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
								_G.SelectToolWeapon = "Death Step"
							end  
							if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 400 then
								local args = {
									[1] = "BuyDeathStep"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
								
								_G.SelectToolWeapon = "Death Step"
							end  
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value < 400 then
								_G.SelectToolWeapon = "Black Leg"
							end 
						end
						if _G.AutoDargonTalon and game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 399 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								_G.SelectToolWeapon = "Dragon Claw"
							end
							if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value <= 399 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								_G.SelectToolWeapon = "Dragon Claw"
							end

							if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
								_G.SelectToolWeapon = "Dragon Claw"
								if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
									local string_1 = "Bones";
									local string_2 = "Buy";
									local number_1 = 1;
									local number_2 = 1;
									local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
									Target:InvokeServer(string_1, string_2, number_1, number_2);

									local string_1 = "BuyDragonTalon";
									local bool_1 = true;
									local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
									Target:InvokeServer(string_1, bool_1);
									
								elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
								else
									local string_1 = "BuyDragonTalon";
									local bool_1 = true;
									local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
									Target:InvokeServer(string_1, bool_1);
									local string_1 = "BuyDragonTalon";
									local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
									Target:InvokeServer(string_1);
								end 
							end
						end
						if _G.AutoElectricclow and game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value < 400 then
								_G.SelectToolWeapon = "Electro"
							end  
							if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value < 400 then
								_G.SelectToolWeapon = "Electro"
							end  
							if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 then
								local v175 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true);
								if v175 == 4 then
									local v176 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start");
									if v176 == nil then
										game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-12548, 337, -7481)
									end
								else
									local string_1 = "BuyElectricClaw";
									local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
									Target:InvokeServer(string_1);
									
								end
							end
							if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 then
								local v175 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true);
								if v175 == 4 then
									local v176 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start");
									if v176 == nil then
										game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-12548, 337, -7481)
									end
								else
									local string_1 = "BuyElectricClaw";
									local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
									Target:InvokeServer(string_1);
									
								end
							end
						end
					end
				end)

				spawn(function()
					while wait() do
						if _G.AutoSharkmanKarate then
							pcall(function()
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
								if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then  
									if game.Players.LocalPlayer.Character:FindFirstChild("Water Key") or game.Players.LocalPlayer.Backpack:FindFirstChild("Water Key") then
										TP2FF(CFrame.new(-2604.6958, 239.432526, -10315.1982, 0.0425701365, 0, -0.999093413, 0, 1, 0, 0.999093413, 0, 0.0425701365))
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
									else 
										if game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then   
											for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
												if v.Name == "Tide Keeper [Lv. 1475] [Boss]" then    
													repeat task.wait()
														EquipWeapon(_G.SelectToolWeapon)
														v.HumanoidRootPart.CanCollide = false
														v.Humanoid.WalkSpeed = 0

				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
														_G.FastAttack = true
														_G.FastAttack1 = true
													until not v.Parent or v.Humanoid.Health <= 0 or _G.AutoSharkmanKarate == false or game.Players.LocalPlayer.Character:FindFirstChild("Water Key") or game.Players.LocalPlayer.Backpack:FindFirstChild("Water Key")                                            
												end
											end
										else
											if game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
												TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]").HumanoidRootPart.CFrame)
											end
										end
									end
								else 
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
									_G.FastAttack = false
									_G.FastAttack1 = false
								end
							end)
						end
					end
				end)

				spawn(function()
					while wait() do
						if _G.AutoFarmMasteryGun then
							pcall(function()
								cq()
								local QuestTitle = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
								if not string.find(QuestTitle,NameMon) then
									MagnetGun = false
									USEGUN = false
								end
								if not QuestVis() then
									MagnetGun = false
									USEGUN = false
									repeat wait()
										TP2FF(CFrameQuest)
									until (CFrameQuest.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3
									if (CFrameQuest.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
										wait(1.1)
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NameQuest,LevelQuest)
										wait(.5)
									end
								elseif QuestVis() then
									if game:GetService("Workspace").Enemies:FindFirstChild(Mon) then 
										for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
											cq()
											if v.Name == Mon then
												if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
													if string.find(QuestTitle, NameMon) then
														repeat task.wait()
															HealthMin = v.Humanoid.MaxHealth * _G.KillAt/100
															if v.Humanoid.Health <= HealthMin then
																EquipWeapon(SelectWeaponGun)
																v.HumanoidRootPart.CanCollide = false
																v.Head.CanCollide = false
																v.Humanoid.WalkSpeed = 0
																_G.FastAttack = true
																_G.FastAttack1 = true
																MagnetGun = true
																USEGUN = true
																PosMonGun = v.HumanoidRootPart.CFrame
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
																local args = {
																	[1] = v.HumanoidRootPart.Position,
																	[2] = v.HumanoidRootPart
																}
																game:GetService("Players").LocalPlayer.Character[SelectWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
															else
															  EquipWeapon(_G.SelectToolWeapon)
																v.HumanoidRootPart.CanCollide = false
																v.Head.CanCollide = false
																MagnetGun = true
																USEGUN = false
																PosMonGun = v.HumanoidRootPart.CFrame
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
															end
														until not v.Parent or v.Humanoid.Health <= 0 or not _G.AutoMasteryGun or not QuestVis()
													else      
														MagnetGun = false
														USEGUN = false   
													   _G.FastAttack = false
													  _G.FastAttack1 = false									   
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
													end
												end
											end
										end
									else
										USEGUN = false
										MagnetGun = false                        
										if game:GetService("ReplicatedStorage"):FindFirstChild(Mon) then
											TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild(Mon).HumanoidRootPart.CFrame * CFrame.new(0,25,5))
										end
									end
								end
							end)
						end
					end
				end)
				spawn(function()
					for i = 1,math.huge do game:GetService("RunService").RenderStepped:Wait()
						if _G.AutoFarmMasteryGun and MagnetGun then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if MagnetGun and _G.AutoFarmMasteryGun and v.Name == Ms and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 270 then
									v.HumanoidRootPart.CFrame = PosMonGun
												v.Humanoid.JumpPower = 0
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.Size = Vector3.new(150,150,150)
												v.HumanoidRootPart.CanCollide = false
												if v.Humanoid:FindFirstChild("Animator") then
													v.Humanoid.Animator:Destroy()
												end
												sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
												v.Humanoid:ChangeState(14)
								end 
							end
						end
					end
				end)

				spawn(function()
					while wait() do
						if USEGUN then
							pcall(function()
								if _G.SkillZ then
									local args = {
										[1] = PosMonGun.Position
									}
									game:GetService("Players").LocalPlayer.Character[SelectWeaponGun].RemoteEvent:FireServer(unpack(args))
									game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
									game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
								end
								if _G.SkillX then
									local args = {
										[1] = PosMonGun.Position
									}
									game:GetService("Players").LocalPlayer.Character[SelectWeaponGun].RemoteEvent:FireServer(unpack(args))
									game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
									game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
								end
							end)
						end
					end
				end)

				spawn(function()
					while task.wait() do
						pcall(function()
							if USEGUN and PosMonGun ~= nil then
								local args = {
									[1] = PosMonGun.Position
								}
								game:GetService("Players").LocalPlayer.Character[SelectWeaponGun].RemoteEvent:FireServer(unpack(args))
							end
						end)
					end
				end)


				spawn(function()
					while wait() do
						if _G.AutoFarmMasteryFruit then
							cq()
							local QuestTitle = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
							if not string.find(QuestTitle, NameMon) then
								MagnetFruit = false    
								USEBF = false                                    
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
							end
							if not QuestVis() then
								USEBF = false
								MagnetFruit = false
								repeat wait()
									TP2FF(CFrameQuest) 
								until (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3
								if (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
									wait(1.1)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, LevelQuest)
									wait(0.5)
								end
							elseif QuestVis() then
								if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
									pcall(function()
									cq()
										for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
											if v.Name == Ms then
												if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
													if string.find(QuestTitle, NameMon) then    
														repeat task.wait()
															HealthMon = v.Humanoid.MaxHealth * _G.KillAt/100
															if v.Humanoid.Health <= HealthMon then
																EquipWeapon(game.Players.LocalPlayer.Data.DevilFruit.Value)
																v.Head.CanCollide = false
																v.HumanoidRootPart.CanCollide = false
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
																USEBF = true
																MagnetFruit = true
																PosMonFruit = v.HumanoidRootPart.CFrame
															else
																USEBF = false
																EquipWeapon(_G.SelectToolWeapon)
																v.Head.CanCollide = false
																v.HumanoidRootPart.CanCollide = false
				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
				MagnetFruit = true
																PosMonFruit = v.HumanoidRootPart.CFrame
																_G.FastAttack = true
																_G.FastAttack1 = true
															end
														until v.Humanoid.Health <= 0 or _G.AutoMasteryFruit == false or not v.Parent or not QuestVis()
													else
														USEBF = false
														MagnetFruit = false
													   _G.FastAttack = false
													   _G.FastAttack1 = false
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
													end
												end
											end
										end
									end)
								else
									USEBF = false
									MagnetFruit = false    
									_G.FastAttack = false   
								   _G.FastAttack1 = false					
									if game:GetService("ReplicatedStorage"):FindFirstChild(Ms) then
										TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild(Ms).HumanoidRootPart.CFrame * CFrame.new(0,30,0))
									end
								end 
							end
						end
					end
				end)
				spawn(function()
					for i = 1,math.huge do game:GetService("RunService").RenderStepped:Wait()
						if _G.AutoFarmMasteryFruit and MagnetFruit then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if MagnetFruit and _G.AutoFarmMasteryFruit and v.Name == Ms and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 270 then
									v.HumanoidRootPart.CFrame = PosMonFruit
												v.Humanoid.JumpPower = 0
												v.Humanoid.WalkSpeed = 0
												v.HumanoidRootPart.Size = Vector3.new(150,150,150)
												v.HumanoidRootPart.CanCollide = false
												if v.Humanoid:FindFirstChild("Animator") then
													v.Humanoid.Animator:Destroy()
												end
												sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
												v.Humanoid:ChangeState(14)
								end 
							end
						end
					end
				end)

				spawn(function()
					while wait() do
						if USEBF then
							pcall(function()
								cq()
								if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha") then
									if _G.SkillZ and game.Players.LocalPlayer.Character.HumanoidRootPart.Size == Vector3.new(2, 2.0199999809265, 1) then
										local args = {
											[1] = PosMonFruit.Position
										}
										game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
										game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
										wait(.3)
										game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
									end
									if _G.SkillX then
										local args = {
											[1] = PosMonFruit.Position
										}
										game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
										game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
										game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
									end
									if _G.SkillC then
										local args = {
											[1] = PosMonFruit.Position
										}
										game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
										game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
										game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
									end
									if _G.SkillV then
										local args = {
											[1] = PosMonFruit.Position
										}
										game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
										game:GetService("VirtualInputManager"):SendKeyEvent(true,"V",false,game)
										game:GetService("VirtualInputManager"):SendKeyEvent(false,"V",false,game)
									end
								elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild(game.Players.LocalPlayer.Data.DevilFruit.Value) then
									if _G.SkillZ then
										local args = {
											[1] = PosMonFruit.Position
										}
										game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
										game:GetService("VirtualInputManager"):SendKeyEvent(true,"Z",false,game)
										game:GetService("VirtualInputManager"):SendKeyEvent(false,"Z",false,game)
									end
									if _G.SkillX then
										local args = {
											[1] = PosMonFruit.Position
										}
										game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
										game:GetService("VirtualInputManager"):SendKeyEvent(true,"X",false,game)
										game:GetService("VirtualInputManager"):SendKeyEvent(false,"X",false,game)
									end
									if _G.SkillC then
										local args = {
											[1] = PosMonFruit.Position
										}
										game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
										game:GetService("VirtualInputManager"):SendKeyEvent(true,"C",false,game)
										game:GetService("VirtualInputManager"):SendKeyEvent(false,"C",false,game)
									end
									if _G.SkillV then
										local args = {
											[1] = PosMonFruit.Position
										}
										game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name].RemoteEvent:FireServer(unpack(args))
										game:GetService("VirtualInputManager"):SendKeyEvent(true,"V",false,game)
										game:GetService("VirtualInputManager"):SendKeyEvent(false,"V",false,game)
									end
								end
							end)
						end
					end
				end)


				spawn(function()
					pcall(function()
						while task.wait() do
							if USEBF and PosMonFruit ~= nil then
								local args = {
									[1] = PosMonFruit.Position
								}
								game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Data.DevilFruit.Value].RemoteEvent:FireServer(unpack(args))
							end
						end
					end)
				end)



				spawn(function()
					pcall(function()
						while wait() do
							if _G.AutoObservation then
								if game.Players.LocalPlayer.VisionRadius.Value == 3000 then
									ui:Notification("Observation","You have max points.",2.5,nil)
								else
									if world2 then
										if game:GetService("Workspace").Enemies:FindFirstChild("Lava Pirate [Lv. 1200]") then
											if game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
												repeat wait()
													TP2FF(game:GetService("Workspace").Enemies:FindFirstChild("Lava Pirate [Lv. 1200]").HumanoidRootPart.CFrame * CFrame.new(3,0,0))
												until _G.AutoObservation == false or not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
											else
												repeat wait()
													TP2FF(game:GetService("Workspace").Enemies:FindFirstChild("Lava Pirate [Lv. 1200]").HumanoidRootPart.CFrame * CFrame.new(0,50,0))
													wait(1)
													if not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") and _G.AutoObservation_Hop == true then
														game:GetService("TeleportService"):Teleport(game.PlaceId,game:GetService("Players").LocalPlayer)
													end
												until _G.AutoObservation == false or game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
											end
										else
											if game:GetService("ReplicatedStorage"):FindFirstChild("Lava Pirate [Lv. 1200]") then
												TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Lava Pirate [Lv. 1200]").HumanoidRootPart.CFrame * CFrame.new(3,0,0))
											end
										end
									elseif world1 then
										if game:GetService("Workspace").Enemies:FindFirstChild("Galley Captain [Lv. 650]") then
											if game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
												repeat wait()
													TP2FF(game:GetService("Workspace").Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.CFrame * CFrame.new(3,0,0))
												until _G.AutoObservation == false or not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
											else
												repeat wait()
													TP2FF(game:GetService("Workspace").Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.CFrame * CFrame.new(0,50,0))
													wait(1)
													if not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") and _G.AutoObservation_Hop == true then
														game:GetService("TeleportService"):Teleport(game.PlaceId,game:GetService("Players").LocalPlayer)
													end
												until _G.AutoObservation == false or game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
											end
										else
											if game:GetService("ReplicatedStorage"):FindFirstChild("Galley Captain [Lv. 650]") then
												TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.CFrame * CFrame.new(3,0,0))
											end
										end
									elseif world3 then
										if game:GetService("Workspace").Enemies:FindFirstChild("Giant Islander [Lv. 1650]") then
											if game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
												repeat wait()
													TP2FF(game:GetService("Workspace").Enemies:FindFirstChild("Giant Islander [Lv. 1650]").HumanoidRootPart.CFrame * CFrame.new(3,0,0))
												until _G.AutoObservation == false or not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
											else
												repeat wait()
													TP2FF(game:GetService("Workspace").Enemies:FindFirstChild("Giant Islander [Lv. 1650]").HumanoidRootPart.CFrame * CFrame.new(0,50,0))
													wait(1)
													if not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") and _G.AutoObservation_Hop == true then
														game:GetService("TeleportService"):Teleport(game.PlaceId,game:GetService("Players").LocalPlayer)
													end
												until _G.AutoObservation == false or game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
											end
										else
											if game:GetService("ReplicatedStorage"):FindFirstChild("Giant Islander [Lv. 1650]") then
												TP2FF(game:GetService("ReplicatedStorage"):FindFirstChild("Giant Islander [Lv. 1650]").HumanoidRootPart.CFrame * CFrame.new(3,0,0))
											end
										end
									end
								end
							end
						end
					end)
				end)

				spawn(function()
					while wait() do 
						if _G.AutoFarmBone then
							pcall(function()
								if game:GetService("Workspace").Enemies:FindFirstChild("Reborn Skeleton [Lv. 1975]") or game:GetService("Workspace").Enemies:FindFirstChild("Living Zombie [Lv. 2000]") or game:GetService("Workspace").Enemies:FindFirstChild("Demonic Soul [Lv. 2025]") or game:GetService("Workspace").Enemies:FindFirstChild("Posessed Mummy [Lv. 2050]") then
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]" then
											if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
												repeat task.wait()
													Buso()
													EquipWeapon(_G.SelectToolWeapon)
													v.HumanoidRootPart.CanCollide = false
													v.Humanoid.WalkSpeed = 0
													v.Head.CanCollide = false 
													MagnetBone = true
													PosMonBone = v.HumanoidRootPart.CFrame
													TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(0,30,0))
													_G.FastAttack = true
													_G.FastAttack1 = true
												until not _G.AutoFarmBone or not v.Parent or v.Humanoid.Health <= 0
											end
										end
									end
								else
									MagnetBone = false
									for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
										if v.Name == "Reborn Skeleton [Lv. 1975]" then
											TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(0,30,0))
										elseif v.Name == "Living Zombie [Lv. 2000]" then
											TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(0,30,0))
										elseif v.Name == "Demonic Soul [Lv. 2025]" then
											TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(0,30,0))
										elseif v.Name == "Posessed Mummy [Lv. 2050]" then
											TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(0,30,0))
										end
									end
								end
							end)
						end
					end
				end)

				spawn(function()
						  while task.wait() do
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]" then
											if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 400 then
								  v.HumanoidRootPart.CFrame = PosMonBone
								  v.HumanoidRootPart.Size = Vector3.new(10,10,10)
										v.HumanoidRootPart.Transparency = 1
								  v.HumanoidRootPart.CanCollide = false
							  v.Humanoid:ChangeState(11)
							   v.Head.CanCollide = false
								  sethiddenproperty(game.Players.LocalPlayer, "MaximumSimulationRadius",  math.huge)
								sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  9e20)
								end
							  end
						   end
						end
				end)
					
				spawn(function()
						while wait() do
							if _G.Factory then
								if game.Workspace.Enemies:FindFirstChild("Core") then
									_G.FactoryCore = true
									_G.AutoFarm = false
									for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
										if _G.FactoryCore and v.Name == "Core" and v.Humanoid.Health > 0 then
											repeat wait(.1)
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
													if Farmtween then
														Farmtween:Stop()
													end
													EquipWeapon(_G.SelectToolWeapon)
													_G.FastAttack = true
													_G.FastAttack1 = true
													if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
														local args = {
															[1] = "Buso"
														}
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 10, 10)
												end
											until not _G.FactoryCore or v.Humanoid.Health <= 0 or _G.Factory == false
											_G.FastAttack = false
											_G.FastAttack1 = false
										end
									end
								elseif game.ReplicatedStorage:FindFirstChild("Core") and game.ReplicatedStorage:FindFirstChild("Core"):FindFirstChild("Humanoid") then
									_G.FactoryCore = true
									_G.AutoFarm = false
									GOtween = toTarget(CFrame.new(448.46756, 199.356781, -441.389252).Position,CFrame.new(448.46756, 199.356781, -441.389252).CFrame)
									if (CFrame.new(448.46756, 199.356781, -441.389252).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
										if Farmtween then
											GOtween:Stop()
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(448.46756, 199.356781, -441.389252)
									end
								elseif _G.AutoFarm then
									_G.FactoryCore = false
									_G.AutoFarm = true
								end
							end
						end
					end)

				spawn(function()
					pcall(function()
						while wait() do
							if _G.AutoThirdSea then
								if game:GetService("Players").LocalPlayer.Data.Level.Value >= 1500 and world2 then
									_G.AutoFarm = false
									if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress").KilledIndraBoss == false then
										if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 then
											if game:GetService("Players").LocalPlayer.Data.SpawnPoint.Value == "Bar" then
												if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
													if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") == 0 then
														if (CFrame.new(-1926.3221435547, 12.819851875305, 1738.3092041016).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10 then
															wait(1.1)
															_G.FastAttack= false
															_G.FastAttack1 = false
															game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Begin")
														else
															_G.FastAttack = false
															_G.FastAttack1 = false
															TPFF(CFrame.new(-1926.3221435547, 12.819851875305, 1738.3092041016))
														end
														if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") then
															for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
																if v.Name == "rip_indra [Lv. 1500] [Boss]" then
																	repeat game:GetService("RunService").Heartbeat:wait()
																		_G.FastAttack = true
																		_G.FastAttack1 = true
																		pcall(function()
																			EquipWeapon(_G.SelectToolWeapon)
																			TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,25,25))
																			require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework).activeController.hitboxMagnitude = 1000
																			game:GetService'VirtualUser':CaptureController()
																			game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
																			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
																			sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
																		end)
																	until _G.AutoThirdSea == false or v.Humanoid.Health <= 0 or not v.Parent
																	_G.FastAttack = false
																	_G.FastAttack1 = false
																end
															end
														elseif not game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") and (CFrame.new(-26880.93359375, 22.848554611206, 473.18951416016).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
															TP2FF(CFrame.new(-26880.93359375, 22.848554611206, 473.18951416016))
															_G.FastAttack = false
															_G.FastAttack1 = false
														end
													elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") ~= 0 then
														if game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
															if game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
																for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
																	if v.Name == "Don Swan [Lv. 1000] [Boss]" then
																		repeat game:GetService("RunService").Heartbeat:wait()
																			pcall(function()
																				_G.FastAttack = true
																				_G.FastAttack1 = true
																				EquipWeapon(_G.SelectToolWeapon)
																				TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,25,25))
																				require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework).activeController.hitboxMagnitude = 1000
																				game:GetService'VirtualUser':CaptureController()
																				game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
																				sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
																			end)
																		until _G.AutoThirdSea == false or v.Humanoid.Health <= 0 or not v.Parent
																		_G.FastAttack = false
																		_G.FastAttack1 = false
																	end
																end
															else
																if (CFrame.new(2284.912109375, 15.537666320801, 905.48291015625).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1000 then
																	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(2284.912109375, 15.537666320801, 905.48291015625))
																	wait()
																end
																_G.FastAttack = false
																_G.FastAttack1 = false
																TPFF(CFrame.new(2284.912109375, 15.537666320801, 905.48291015625))
															end
														elseif _G.AutoThirdSea and not game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
															Hop()
														elseif not _G.AutoThirdSea and not game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
															if (CFrame.new(2284.912109375, 15.537666320801, 905.48291015625).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1000 then
																game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(2284.912109375, 15.537666320801, 905.48291015625))
																wait()
															end
															_G.FastAttack = false
															_G.FastAttack1 = false
															TPFF(CFrame.new(2284.912109375, 15.537666320801, 905.48291015625))
														end
													end
												elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") ~= 0 then
													for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
														if string.find(v.Name, "Fruit") then
															if v:IsA("Tool") then
																if (v.Handle.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 20000 then
																	v.Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
																end
															end
														end
													end
													if game.Players.LocalPlayer.Backpack:FindFirstChild("Quake Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Human: Buddha Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("String Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Bird: Phoenix Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Rumble Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Paw Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Gravity Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Dough Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Shadow Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Venom Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Control Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Quake Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Human: Buddha Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("String Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Bird: Phoenix Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Rumble Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Paw Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Gravity Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Dough Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Shadow Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Venom Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Control Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Dragon Fruit") then
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1")
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","2")
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","3")
													end
												end
											else
												TP2FF(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
											end
										else
											if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 0 then
												if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Swan Pirates") and string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
													if game.Workspace.Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
														for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
															if v.Name == "Swan Pirate [Lv. 775]" then
																PosMonBarto =  v.HumanoidRootPart.CFrame
																pcall(function()
																	repeat wait()
																		for k,x in pairs(game.Workspace.Enemies:GetChildren()) do
																			if x.Name ==  "Swan Pirate [Lv. 775]"  then
																				x.HumanoidRootPart.Size = Vector3.new(5,5,5)
																				x.HumanoidRootPart.Transparency = 1
																				x.HumanoidRootPart.CanCollide = false
																				x.HumanoidRootPart.CFrame = PosMonBarto
																				sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
																			end
																		end
																		_G.FastAttack = true
																		_G.FastAttack1 = true
																		EquipWeapon(_G.SelectToolWeapon)
																		v.HumanoidRootPart.CanCollide = false
																		v.HumanoidRootPart.Size = Vector3.new(5, 5, 5)
																		TP2FF( v.HumanoidRootPart.CFrame * CFrame.new(0,15,0))
																		game:GetService'VirtualUser':CaptureController()
																		game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))                           
																	until not v.Parent or v.Humanoid.Health <= 0 or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
																	_G.FastAttack = false
																	_G.FastAttack1 = false
																end)
															end
														end
													else
														_G.FastAttack = false
														_G.FastAttack1 = false
														TP2FF(CFrame.new(1057.92761, 137.614319, 1242.08069))
													end
												else
													_G.FastAttack = false
													_G.FastAttack1 = false
													TP2FF(CFrame.new(-456.28952, 73.0200958, 299.895966))
													wait(1.1)
													game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest","BartiloQuest",1)
												end
											elseif game.Players.LocalPlayer.Data.Level.Value >= 800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 1 then
												if game.Workspace.Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
													Ms = "Jeremy [Lv. 850] [Boss]"
													for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
														if v.Name == Ms then
															repeat wait()
																_G.FastAttack = true
																_G.FastAttack1 = true
																EquipWeapon(_G.SelectToolWeapon)
																v.HumanoidRootPart.CanCollide = false
																v.HumanoidRootPart.Size = Vector3.new(35, 35, 35)
																TP2FF(v.HumanoidRootPart.CFrame * CFrame.new(0,15,0))
																game:GetService'VirtualUser':CaptureController()
																game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
															until not v.Parent or v.Humanoid.Health <= 0
															_G.FastAttack = false
															_G.FastAttack1 = false
														end
													end
												elseif game.ReplicatedStorage:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
													_G.FastAttack = false
													_G.FastAttack1 = false
													TP2FF(CFrame.new(-456.28952, 73.0200958, 299.895966))
													wait(1.1)
													game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo")
													wait(1)
													TP2FF(CFrame.new(2099.88159, 448.931, 648.997375))
													wait(2)
												else
													TP2FF(CFrame.new(2099.88159, 448.931, 648.997375))
												end
												wait(15)
												if not game.Workspace.Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
													Hop()
												end
											elseif game.Players.LocalPlayer.Data.Level.Value >= 800 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 2 then
												TP2FF(CFrame.new(-1850.49329, 13.1789551, 1750.89685))
												_G.FastAttack = false
												_G.FastAttack1 = false
												wait(1.5)
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.87305, 19.3777466, 1712.01807)
												wait(1.5)
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1803.94324, 16.5789185, 1750.89685)
												wait(1.5)
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.55835, 16.8604317, 1724.79541)
												wait(1.5)
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1869.54224, 15.987854, 1681.00659)
												wait(1.5)                                                                  
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1800.0979, 16.4978027, 1684.52368) 
												wait(1.5)
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1819.26343, 15.795166, 1717.90625)
												wait(1.5)
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1813.51843, 15.8604736, 1724.79541)
												wait(1.5)
											end
										end
									else
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
									end
								end
							end
						end
					end)
				end)
				spawn(function()
					pcall(function()
						while wait(.1) do wait(5)
							if _G.AutoThirdSea and world2 and game:GetService("Players").LocalPlayer.Data.Level.Value >= 1500 then
								if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 then
									if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") ~= 0 then
										if not game.Players.LocalPlayer.Backpack:FindFirstChild("Quake Fruit") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Human: Buddha Fruit") and not game.Players.LocalPlayer.Backpack:FindFirstChild("String Fruit") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Bird: Phoenix Fruit") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Rumble Fruit") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Paw Fruit") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Gravity Fruit") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Dough Fruit") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Shadow Fruit") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Venom Fruit") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Control Fruit") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("Quake Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("Human: Buddha Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("String Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("Bird: Phoenix Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("Rumble Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("Paw Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("Gravity Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("Dough Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("Shadow Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("Venom Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("Control Fruit") and not game.Players.LocalPlayer.Character:FindFirstChild("Dragon Fruit") then
											Hop()
										end
									end
								end
							end
						end
					end)
				end)

                   spawn(function()
                       while wait() do
                           if _G.AutoFarm then
                           pcall(function()
            					if _G.AutoFarm and game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
            						cq()
            						kkii = require(game.ReplicatedStorage.Util.CameraShaker)
            						kkii:Stop()
            						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
            							cq()
            							_G.FastAttack = false
            							_G.FastAttack1 = false
            							StartMagnetAutoFarm = false
            								TP2FF(CFrameQuest)
            								wait(1)
            								local args = {
            											[1] = "StartQuest",
            											[2] = NameQuest,
            											[3] = LevelQuest
            										   }
            									game:GetService("ReplicatedStorage").Remotes.CommF_	:InvokeServer(unpack(args))
            									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
            						elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
            							cq()
            							if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
            								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
            									if _G.AutoFarm and v.Name == Ms and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
            										if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
            											repeat wait()
            													StartMagnetAutoFarm = false
            													_G.FastAttack = true
            													_G.FastAttack1 = true
            													PosMonAutoFarm = v.HumanoidRootPart.CFrame * CFrame.new(0,0,0)
            													if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
            														local args = {
            															[1] = "Buso"
            														}
            														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            													end
            													TPFF(v.HumanoidRootPart.CFrame * CFrame.new(0,30,0))
            													EquipWeapon(_G.SelectToolWeapon)
            													StartMagnetAutoFarm = true
            											until not _G.AutoFarm or not v.Parent or v.Humanoid.Health <= 0 or not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
            											if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
            												local args = {
            											[1] = "AbandonQuest"
            												}
            												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            											end
            											StartMagnetAutoFarm = false
            											_G.FastAttack = false
            											_G.FastAttack1 = false
            
            										else
            											local args = {
            											[1] = "AbandonQuest"
            												}
            												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            										end 
            									end
            								end
            							else
            								if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
            									local args = {
            								[1] = "AbandonQuest"
            									}
            								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            								end
            								StartMagnetAutoFarm = false
            								_G.FastAttack = false
            								_G.FastAttack1 = false
            							end
            							
            						end 
            					end
                           end)
                       end
			        end
				end)



				spawn(function()
					game:GetService("RunService").Heartbeat:Connect(function()
						pcall(function()
							local MyLevel = game.Players.LocalPlayer.Data.Level.Value
							if StartMagnetAutoFarm then
								if (CFrameMon.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1000 then
									for y,x in pairs(game.Workspace.Enemies:GetChildren()) do
											if not string.find(x.Name,"Boss") and(x.HumanoidRootPart.Position-PosMonAutoFarm.Position).Magnitude <= 300 then
												x.HumanoidRootPart.CFrame = PosMonAutoFarm
												x.Humanoid.JumpPower = 0
												x.Humanoid.WalkSpeed = 0
												x.HumanoidRootPart.Size = Vector3.new(150,150,150)
												x.HumanoidRootPart.CanCollide = false
												x.Head.CanCollide = false
												x.Head.Transparency = 0.7
												x.UpperTorso.Transparency = 0.7
												if x.Humanoid:FindFirstChild("Animator") then
													x.Humanoid.Animator:Destroy()
												end
												sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
												x.Humanoid:ChangeState(14)
											end
									end
								end
							end
						end)
					end)
				end)





				function toTarget(targetPos, targetCFrame)
					local tweenfunc = {}
					local tween_s = game:service"TweenService"
					local info = TweenInfo.new((targetPos - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).Magnitude/300, Enum.EasingStyle.Linear)
					local tween = tween_s:Create(game:GetService("Players").LocalPlayer.Character["HumanoidRootPart"], info, {CFrame = targetCFrame * CFrame.fromAxisAngle(Vector3.new(1,0,0), math.rad(0))})
					tween:Play()

					function tweenfunc:Stop()
						tween:Cancel()
						return tween
					end

					if not tween then return tween end
					return tweenfunc
				end


				function TPFF(P)
					Distance = (P.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
					if Distance < 10 then
						Speed = 1000
					elseif Distance < 170 then
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = P
						Speed = 350
					elseif Distance < 1000 then
						Speed = 350
					elseif Distance >= 1000 then
						Speed = 250
					end
					game:GetService("TweenService"):Create(
						game.Players.LocalPlayer.Character.HumanoidRootPart,
						TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
						{CFrame = P}
					):Play()
				end


				function TP2FF(P1)
					Distance = (P1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
					if Distance < 1000 then
						Speed = 350
					elseif Distance >= 1000 then
						Speed = 250
					elseif Distance < 200 then
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = P1
					end
					game:GetService("TweenService"):Create(
						game.Players.LocalPlayer.Character.HumanoidRootPart,
						TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
						{CFrame = P1}
					):Play()
					wait(Distance/Speed)
				end



				function to(a)
					pos = (a.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position)
					speed = pos.Magnitude/15

					incrementX = pos.X/speed
					incrementY = pos.Y/speed
					incrementZ = pos.Z/speed

					game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = a-pos+Vector3.new(incrementX, incrementY, incrementZ)

					if(distance(a.Position)<=100)then
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = a
					end
				end

				function distance(a)
					return(game.Players.LocalPlayer:DistanceFromCharacter(a))
				end

				function doingquest()
					return(game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible)
				end


		spawn(function()
			game:GetService("RunService").Stepped:Connect(function()
				if ps then
					if syn and game.Players.LocalPlayer.Character:FindFirstChild("Humanoid") then
						setfflag("HumanoidParallelRemoveNoPhysics", "False")
						setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
						game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
					else
						if not game:GetService("Workspace"):FindFirstChild("LOL") then
							local LOL = Instance.new("Part")
							LOL.Name = "LOL"
							LOL.Parent = game.Workspace
							LOL.Anchored = true
							LOL.Transparency = 0.8
							LOL.Size = Vector3.new(50,0.5,50)
						elseif game:GetService("Workspace"):FindFirstChild("LOL") then
							game.Workspace["LOL"].CFrame = CFrame.new(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.X,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Y - 3.8,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Z)
						end
					end
					for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
						if v:IsA("BasePart") then
							v.CanCollide = false
						end
					end
				end
			end)
		end)
		

			
			
function cq()
    if world1 then
        local MyLevel = game.Players.LocalPlayer.Data.Level.Value
		if MyLevel == 1 or MyLevel <= 9 or SelectMonster == "Bandit [Lv. 5]" then -- Bandit
			Ms = "Bandit [Lv. 5]"
			NameQuest = "BanditQuest1"
			LevelQuest = 1
			NameMon = "Bandit"
			CFrameQuest = CFrame.new(1061.66699, 16.5166187, 1544.52905, -0.942978859, -3.33851502e-09, 0.332852632, 7.04340497e-09, 1, 2.99841325e-08, -0.332852632, 3.06188177e-08, -0.942978859)
			CFrameMon = CFrame.new(1199.31287, 52.2717781, 1536.91516, -0.929782331, 6.60215846e-08, -0.368109822, 3.9077392e-08, 1, 8.06501603e-08, 0.368109822, 6.06023249e-08, -0.929782331)
		elseif MyLevel == 10 or MyLevel <= 14 or SelectMonster == "Monkey [Lv. 14]" then -- Monkey
			Ms = "Monkey [Lv. 14]"
			NameQuest = "JungleQuest"
			LevelQuest = 1
			NameMon = "Monkey"
			CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
			CFrameMon = CFrame.new(-1502.74609, 98.5633316, 90.6417007, 0.836947978, 0, 0.547282517, -0, 1, -0, -0.547282517, 0, 0.836947978)
		elseif MyLevel == 15 or MyLevel <= 29 or SelectMonster == "Gorilla [Lv. 20]" then -- Gorilla
			Ms = "Gorilla [Lv. 20]"
			NameQuest = "JungleQuest"
			LevelQuest = 2
			NameMon = "Gorilla"
			CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
			CFrameMon = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
		elseif MyLevel == 30 or MyLevel <= 39 or SelectMonster == "Pirate [Lv. 35]" then -- Pirate
			Ms = "Pirate [Lv. 35]"
			NameQuest = "BuggyQuest1"
			LevelQuest = 1
			NameMon = "Pirate"
			CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
			CFrameMon = CFrame.new(-1219.32324, 4.75205183, 3915.63452, -0.966492832, -6.91238853e-08, 0.25669381, -5.21195496e-08, 1, 7.3047012e-08, -0.25669381, 5.72206496e-08, -0.966492832)
		elseif MyLevel == 40 or MyLevel <= 59 or SelectMonster == "Brute [Lv. 45]" then -- Brute
			Ms = "Brute [Lv. 45]"
			NameQuest = "BuggyQuest1"
			LevelQuest = 2
			NameMon = "Brute"
			CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
			CFrameMon = CFrame.new(-1146.49646, 96.0936813, 4312.1333, -0.978175163, -1.53222057e-08, 0.207781896, -3.33316912e-08, 1, -8.31738873e-08, -0.207781896, -8.82843523e-08, -0.978175163)
		elseif MyLevel == 60 or MyLevel <= 74 or SelectMonster == "Desert Bandit [Lv. 60]" then -- Desert Bandit
			Ms = "Desert Bandit [Lv. 60]"
			NameQuest = "DesertQuest"
			LevelQuest = 1
			NameMon = "Desert Bandit"
			CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.97168, -0.804044724, 3.68233266e-08, 0.594568789, 6.97835176e-08, 1, 3.24365246e-08, -0.594568789, 6.75715199e-08, -0.804044724)
			CFrameMon = CFrame.new(932.788818, 6.4503746, 4488.24609, -0.998625934, 3.08948351e-08, 0.0524050146, 2.79967303e-08, 1, -5.60361286e-08, -0.0524050146, -5.44919629e-08, -0.998625934)
		elseif MyLevel == 75 or MyLevel <= 89 or SelectMonster == "Desert Officer [Lv. 70]" then -- Desert Officre
			Ms = "Desert Officer [Lv. 70]"
			NameQuest = "DesertQuest"
			LevelQuest = 2
			NameMon = "Desert Officer"
			CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.97168, -0.804044724, 3.68233266e-08, 0.594568789, 6.97835176e-08, 1, 3.24365246e-08, -0.594568789, 6.75715199e-08, -0.804044724)
			CFrameMon = CFrame.new(1580.03198, 4.61375761, 4366.86426, 0.135744005, -6.44280718e-08, -0.990743816, 4.35738308e-08, 1, -5.90598574e-08, 0.990743816, -3.51534837e-08, 0.135744005)
		elseif MyLevel == 90 or MyLevel <= 99 or SelectMonster == "Snow Bandit [Lv. 90]" then -- Snow Bandits
			Ms = "Snow Bandit [Lv. 90]"
			NameQuest = "SnowQuest"
			LevelQuest = 1
			NameMon = "Snow Bandits"
			CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482, 0.348555952, -2.53947841e-09, -0.937287986, 1.49860568e-08, 1, 2.86358204e-09, 0.937287986, -1.50443711e-08, 0.348555952)
			CFrameMon = CFrame.new(1370.24316, 102.403511, -1411.52905, 0.980274439, -1.12995728e-08, 0.197641045, -9.57343449e-09, 1, 1.04655214e-07, -0.197641045, -1.04482936e-07, 0.980274439)
		elseif MyLevel == 100 or MyLevel <= 119 or SelectMonster == "Snowman [Lv. 100]"  then -- Snowman
			Ms = "Snowman [Lv. 100]"
			NameQuest = "SnowQuest"
			LevelQuest = 2
			NameMon = "Snowman"
			CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482, 0.348555952, -2.53947841e-09, -0.937287986, 1.49860568e-08, 1, 2.86358204e-09, 0.937287986, -1.50443711e-08, 0.348555952)
			CFrameMon = CFrame.new(1370.24316, 102.403511, -1411.52905, 0.980274439, -1.12995728e-08, 0.197641045, -9.57343449e-09, 1, 1.04655214e-07, -0.197641045, -1.04482936e-07, 0.980274439)
		elseif MyLevel == 120 or MyLevel <= 149 or SelectMonster == "Chief Petty Officer [Lv. 120]" then -- Chief Petty Officer
			Ms = "Chief Petty Officer [Lv. 120]"
			NameQuest = "MarineQuest2"
			LevelQuest = 1
			NameMon = "Chief Petty Officer"
			CFrameQuest = CFrame.new(-5035.0835, 28.6520386, 4325.29443, 0.0243340395, -7.08064647e-08, 0.999703884, -6.36926814e-08, 1, 7.23777944e-08, -0.999703884, -6.54350671e-08, 0.0243340395)
			CFrameMon = CFrame.new(-4882.8623, 22.6520386, 4255.53516, 0.273695946, -5.40380647e-08, -0.96181643, 4.37720793e-08, 1, -4.37274998e-08, 0.96181643, -3.01326679e-08, 0.273695946)
		elseif MyLevel == 150 or MyLevel <= 174 or SelectMonster == "Sky Bandit [Lv. 150]" then -- Sky Bandit
			Ms = "Sky Bandit [Lv. 150]"
			NameQuest = "SkyQuest"
			LevelQuest = 1
			NameMon = "Sky Bandit"
			CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436, -0.875942111, 5.59710216e-08, -0.482416272, 3.04023082e-08, 1, 6.08195947e-08, 0.482416272, 3.86078725e-08, -0.875942111)
			CFrameMon = CFrame.new(-4970.74219, 294.544342, -2890.11353, -0.994874597, -8.61311236e-08, -0.101116329, -9.10836206e-08, 1, 4.43614923e-08, 0.101116329, 5.33441664e-08, -0.994874597)
		elseif MyLevel == 175 or MyLevel <= 189 or SelectMonster == "Dark Master [Lv. 175]" then -- Dark Master
			Ms = "Dark Master [Lv. 175]"
			NameQuest = "SkyQuest"
			LevelQuest = 2
			NameMon = "Dark Master"
			CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436, -0.875942111, 5.59710216e-08, -0.482416272, 3.04023082e-08, 1, 6.08195947e-08, 0.482416272, 3.86078725e-08, -0.875942111)
			CFrameMon = CFrame.new(-5220.58594, 430.693298, -2278.17456, -0.925375521, 1.12086873e-08, 0.379051805, -1.05115507e-08, 1, -5.52320891e-08, -0.379051805, -5.50948407e-08, -0.925375521)
		elseif MyLevel == 190 or MyLevel <= 209 or SelectMonster == "Prisoner [Lv. 190]" then
			Ms = "Prisoner [Lv. 190]"
			NameQuest = "PrisonerQuest"
			LevelQuest = 1
			NameMon = "Prisoner"
			CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
			CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
		elseif MyLevel == 210 or MyLevel <= 249 or SelectMonster == "Dangerous Prisoner [Lv. 210]" then
			Ms = "Dangerous Prisoner [Lv. 210]"
			NameQuest = "PrisonerQuest"
			LevelQuest = 2
			NameMon = "Dangerous Prisoner"
			CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
			CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
		elseif MyLevel == 250 or MyLevel <= 274 or SelectMonster == "Toga Warrior [Lv. 225]" then -- Toga Warrior
			Ms = "Toga Warrior [Lv. 250]"
			NameQuest = "ColosseumQuest"
			LevelQuest = 1
			NameMon = "Toga Warrior"
			CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
			CFrameMon = CFrame.new(-1779.97583, 44.6077499, -2736.35474, 0.984437346, 4.10396339e-08, 0.175734788, -3.62286876e-08, 1, -3.05844168e-08, -0.175734788, 2.3741821e-08, 0.984437346)
		elseif MyLevel == 275 or MyLevel <= 299 or SelectMonster == "Gladiator [Lv. 275]" then -- Gladiato
			Ms = "Gladiator [Lv. 275]"
			NameQuest = "ColosseumQuest"
			LevelQuest = 2
			NameMon = "Gladiato"
			CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
			CFrameMon = CFrame.new(-1274.75903, 58.1895943, -3188.16309, 0.464524001, 6.21005611e-08, 0.885560572, -4.80449414e-09, 1, -6.76054768e-08, -0.885560572, 2.71497012e-08, 0.464524001)
		elseif MyLevel == 300 or MyLevel <= 324 or SelectMonster == "Military Soldier [Lv. 300]" then -- Military Soldier
			Ms = "Military Soldier [Lv. 300]"
			NameQuest = "MagmaQuest"
			LevelQuest = 1
			NameMon = "Military Soldier"
			CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
			CFrameMon = CFrame.new(-5363.01123, 41.5056877, 8548.47266, -0.578253984, -3.29503091e-10, 0.815856814, 9.11209668e-08, 1, 6.498761e-08, -0.815856814, 1.11920997e-07, -0.578253984)
		elseif MyLevel == 325 or MyLevel <= 374 or SelectMonster == "Military Spy [Lv. 330]" then -- Military Spy
			Ms = "Military Spy [Lv. 325]"
			NameQuest = "MagmaQuest"
			LevelQuest = 2
			NameMon = "Military Spy"
			CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
			CFrameMon = CFrame.new(-5787.99023, 120.864456, 8762.25293, -0.188358366, -1.84706277e-08, 0.982100308, -1.23782129e-07, 1, -4.93306951e-09, -0.982100308, -1.22495649e-07, -0.188358366)
		elseif MyLevel == 375 or MyLevel <= 399 or SelectMonster == "Fishman Warrior [Lv. 375]" then -- Fishman Warrior
            FM = true
			Ms = "Fishman Warrior [Lv. 375]"
			NameQuest = "FishmanQuest"
			LevelQuest = 1
			NameMon = "Fishman Warrior"
			CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
			CFrameMon = CFrame.new(60946.6094, 48.6735229, 1525.91687, -0.0817126185, 8.90751153e-08, 0.996655822, 2.00889794e-08, 1, -8.77269599e-08, -0.996655822, 1.28533992e-08, -0.0817126185)
            if _G.AutoFarm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
			end
        elseif MyLevel == 400 or MyLevel <= 449 or SelectMonster == "Fishman Commando [Lv. 400]" then -- Fishman Commando
            FM = true
			Ms = "Fishman Commando [Lv. 400]"
			NameQuest = "FishmanQuest"
			LevelQuest = 2
			NameMon = "Fishman Commando"
			CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
			CFrameMon = CFrame.new(61885.5039, 18.4828243, 1504.17896, 0.577502489, 0, -0.816389024, -0, 1.00000012, -0, 0.816389024, 0, 0.577502489)
            if _G.AutoFarm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
			end
        elseif MyLevel == 450 or MyLevel <= 474 or SelectMonster == "God's Guard [Lv. 450]" then -- God's Guards
            FM = false
			Ms = "God's Guard [Lv. 450]"
			NameQuest = "SkyExp1Quest"
			LevelQuest = 1
			NameMon = "God's Guards"
			CFrameQuest = CFrame.new(-4721.71436, 845.277161, -1954.20105, -0.999277651, -5.56969759e-09, 0.0380011722, -4.14751478e-09, 1, 3.75035256e-08, -0.0380011722, 3.73188307e-08, -0.999277651)
			CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.92542, -0.93441087, -6.77488776e-09, -0.356197298, 1.12145182e-08, 1, -4.84390199e-08, 0.356197298, -4.92565206e-08, -0.93441087)
            if _G.AutoFarm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
			end
        elseif MyLevel == 475 or MyLevel <= 524 or SelectMonster == "Shanda [Lv. 475]" then -- Shandas
            sky = false
			Ms = "Shanda [Lv. 475]"
			NameQuest = "SkyExp1Quest"
			LevelQuest = 2
			NameMon = "Shandas"
			CFrameQuest = CFrame.new(-7863.63672, 5545.49316, -379.826324, 0.362120807, -1.98046344e-08, -0.93213129, 4.05822291e-08, 1, -5.48095125e-09, 0.93213129, -3.58431969e-08, 0.362120807)
			CFrameMon = CFrame.new(-7685.12354, 5601.05127, -443.171509, 0.150056243, 1.79768236e-08, -0.988677442, 6.67798661e-09, 1, 1.91962481e-08, 0.988677442, -9.48289181e-09, 0.150056243)
            if _G.AutoFarm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
			end
        elseif MyLevel == 525 or MyLevel <= 549 or SelectMonster == "Royal Squad [Lv. 525]" then -- Royal Squad
            sky = true
			Ms = "Royal Squad [Lv. 525]"
			NameQuest = "SkyExp2Quest"
			LevelQuest = 1
			NameMon = "Royal Squad"
			CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802, 0.0504222959, 2.5710392e-08, 0.998727977, 1.12541557e-07, 1, -3.14249675e-08, -0.998727977, 1.13982921e-07, 0.0504222959)
			CFrameMon = CFrame.new(-7685.02051, 5606.87842, -1442.729, 0.561947823, 7.69527464e-09, -0.827172697, -4.24974544e-09, 1, 6.41599973e-09, 0.827172697, -9.01838604e-11, 0.561947823)
		elseif MyLevel == 550 or MyLevel <= 624 or SelectMonster == "Royal Soldier [Lv. 550]" then -- Royal Soldier
            Dis = 240
            sky = true
			Ms = "Royal Soldier [Lv. 550]"
			NameQuest = "SkyExp2Quest"
			LevelQuest = 2
			NameMon = "Royal Soldier"
			CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802, 0.0504222959, 2.5710392e-08, 0.998727977, 1.12541557e-07, 1, -3.14249675e-08, -0.998727977, 1.13982921e-07, 0.0504222959)
			CFrameMon = CFrame.new(-7864.44775, 5661.94092, -1708.22351, 0.998389959, 2.28686137e-09, -0.0567218624, 1.99431383e-09, 1, 7.54200258e-08, 0.0567218624, -7.54117195e-08, 0.998389959)
		elseif MyLevel == 625 or MyLevel <= 649 or SelectMonster == "Galley Pirate [Lv. 625]" then -- Galley Pirate
            Dis = 240
            sky = false
			Ms = "Galley Pirate [Lv. 625]"
			NameQuest = "FountainQuest"
			LevelQuest = 1
			NameMon = "Galley Pirate"
			CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678, -0.0504891425, -3.62066501e-08, -0.998724639, -9.87921389e-09, 1, -3.57534553e-08, 0.998724639, 8.06145284e-09, -0.0504891425)
			CFrameMon = CFrame.new(5595.06982, 41.5013695, 3961.47095, -0.992138803, -2.11610267e-08, -0.125142589, -1.34249509e-08, 1, -6.26613996e-08, 0.125142589, -6.04887518e-08, -0.992138803)
		elseif MyLevel >= 650 or SelectMonster == "Galley Captain [Lv. 650]" then -- Galley Captain
            Dis = 240
			Ms = "Galley Captain [Lv. 650]"
			NameQuest = "FountainQuest"
			LevelQuest = 2
			NameMon = "Galley Captain"
			CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678, -0.0504891425, -3.62066501e-08, -0.998724639, -9.87921389e-09, 1, -3.57534553e-08, 0.998724639, 8.06145284e-09, -0.0504891425)
			CFrameMon = CFrame.new(5658.5752, 38.5361786, 4928.93506, -0.996873081, 2.12391046e-06, -0.0790185928, 2.16989656e-06, 1, -4.96097414e-07, 0.0790185928, -6.66008248e-07, -0.996873081)
		end
    elseif world2 then
        local MyLevel = game.Players.LocalPlayer.Data.Level.Value
		Dis = 240
		if MyLevel == 700 or MyLevel <= 724 or SelectMonster == "Raider [Lv. 700]" then -- Raider [Lv. 700]
			Ms = "Raider [Lv. 700]"
			NameQuest = "Area1Quest"
			LevelQuest = 1
			NameMon = "Raider"
			CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
			CFrameMon = CFrame.new(-737.026123, 39.1748352, 2392.57959, 0.272128761, 0, -0.962260842, -0, 1, -0, 0.962260842, 0, 0.272128761)
		elseif MyLevel == 725 or MyLevel <= 774 or SelectMonster == "Mercenary [Lv. 725]" then -- Mercenary [Lv. 725]
			Ms = "Mercenary [Lv. 725]"
			NameQuest = "Area1Quest"
			LevelQuest = 2
			NameMon = "Mercenary"
			CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
			CFrameMon = CFrame.new(-973.731995, 95.8733215, 1836.46936, 0.999135971, 2.02326991e-08, -0.0415605344, -1.90767793e-08, 1, 2.82094952e-08, 0.0415605344, -2.73922804e-08, 0.999135971)
		elseif MyLevel == 775 or MyLevel <= 799 or SelectMonster == "Swan Pirate [Lv. 775]" then -- Swan Pirate [Lv. 775]
			Ms = "Swan Pirate [Lv. 775]"
			NameQuest = "Area2Quest"
			LevelQuest = 1
			NameMon = "Swan Pirate"
			CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
			CFrameMon = CFrame.new(970.369446, 142.653198, 1217.3667, 0.162079468, -4.85452638e-08, -0.986777723, 1.03357589e-08, 1, -4.74980872e-08, 0.986777723, -2.50063148e-09, 0.162079468)
		elseif MyLevel == 800 or MyLevel <= 874 or SelectMonster == "Factory Staff [Lv. 800]" then -- Factory Staff [Lv. 800]
			Ms = "Factory Staff [Lv. 800]"
			NameQuest = "Area2Quest"
			LevelQuest = 2
			NameMon = "Factory Staff"
			CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
			CFrameMon = CFrame.new(296.786499, 72.9948196, -57.1298141, -0.876037002, -5.32364979e-08, 0.482243896, -3.87658332e-08, 1, 3.99718729e-08, -0.482243896, 1.63222538e-08, -0.876037002)
		elseif MyLevel == 875 or MyLevel <= 899 or SelectMonster == "Marine Lieutenant [Lv. 875]" then -- Marine Lieutenant [Lv. 875]
			Ms = "Marine Lieutenant [Lv. 875]"
			NameQuest = "MarineQuest3"
			LevelQuest = 1
			NameMon = "Marine Lieutenant"
			CFrameQuest = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
			CFrameMon = CFrame.new(-2913.26367, 73.0011826, -2971.64282, 0.910507619, 0, 0.413492233, 0, 1.00000012, 0, -0.413492233, 0, 0.910507619)
		elseif MyLevel == 900 or MyLevel <= 949 or SelectMonster == "Marine Captain [Lv. 900]" then -- Marine Captain [Lv. 900]
			Ms = "Marine Captain [Lv. 900]"
			NameQuest = "MarineQuest3"
			LevelQuest = 2
			NameMon = "Marine Captain"
			CFrameQuest = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
			CFrameMon = CFrame.new(-1868.67688, 73.0011826, -3321.66333, -0.971402287, 1.06502087e-08, 0.237439692, 3.68856199e-08, 1, 1.06050372e-07, -0.237439692, 1.11775684e-07, -0.971402287)
		elseif MyLevel == 950 or MyLevel <= 974 or SelectMonster == "Zombie [Lv. 950]" then -- Zombie [Lv. 950]
			Ms = "Zombie [Lv. 950]"
			NameQuest = "ZombieQuest"
			LevelQuest = 1
			NameMon = "Zombie"
			CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742, 4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
			CFrameMon = CFrame.new(-5634.83838, 126.067039, -697.665039, -0.992770672, 6.77618939e-09, 0.120025545, 1.65461245e-08, 1, 8.04023372e-08, -0.120025545, 8.18070234e-08, -0.992770672)
		elseif MyLevel == 975 or MyLevel <= 999 or SelectMonster == "Vampire [Lv. 975]" then -- Vampire [Lv. 975]
			Ms = "Vampire [Lv. 975]"
			NameQuest = "ZombieQuest"
			LevelQuest = 2
			NameMon = "Vampire"
			CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742, 4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
			CFrameMon = CFrame.new(-6030.32031, 6.4377408, -1313.5564, -0.856965423, 3.9138893e-08, -0.515373945, -1.12178942e-08, 1, 9.45958547e-08, 0.515373945, 8.68467822e-08, -0.856965423)
		elseif MyLevel == 1000 or MyLevel <= 1049 or SelectMonster == "Snow Trooper [Lv. 1000]" then -- Snow Trooper [Lv. 1000] **
			Ms = "Snow Trooper [Lv. 1000]"
			NameQuest = "SnowMountainQuest"
			LevelQuest = 1
			NameMon = "Snow Trooper"
			CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287, 0.353063971, 1.89520435e-08, -0.935599446, -5.81846002e-08, 1, -1.70033754e-09, 0.935599446, 5.50377841e-08, 0.353063971)
			CFrameMon = CFrame.new(535.893433, 401.457062, -5329.6958, -0.999524176, 0, 0.0308452044, 0, 1, -0, -0.0308452044, 0, -0.999524176)
		elseif MyLevel == 1050 or MyLevel <= 1099 or SelectMonster == "Winter Warrior [Lv. 1050]" then -- Winter Warrior [Lv. 1050]
			Ms = "Winter Warrior [Lv. 1050]"
			NameQuest = "SnowMountainQuest"
			LevelQuest = 2
			NameMon = "Winter Warrior"
			CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287, 0.353063971, 1.89520435e-08, -0.935599446, -5.81846002e-08, 1, -1.70033754e-09, 0.935599446, 5.50377841e-08, 0.353063971)
			CFrameMon = CFrame.new(1223.7417, 454.575226, -5170.02148, 0.473996818, 2.56845354e-08, 0.880526543, -5.62456428e-08, 1, 1.10811016e-09, -0.880526543, -5.00510211e-08, 0.473996818)
		elseif MyLevel == 1100 or MyLevel <= 1124 or SelectMonster == "Lab Subordinate [Lv. 1100]" then -- Lab Subordinate [Lv. 1100]
			Ms = "Lab Subordinate [Lv. 1100]"
			NameQuest = "IceSideQuest"
			LevelQuest = 1
			NameMon = "Lab Subordinate"
			CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528, 1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
			CFrameMon = CFrame.new(-5769.2041, 37.9288292, -4468.38721, -0.569419742, -2.49055017e-08, 0.822046936, -6.96206541e-08, 1, -1.79282633e-08, -0.822046936, -6.74401548e-08, -0.569419742)
		elseif MyLevel == 1125 or MyLevel <= 1174 or SelectMonster == "Horned Warrior [Lv. 1125]" then -- Horned Warrior [Lv. 1125]
			Ms = "Horned Warrior [Lv. 1125]"
			NameQuest = "IceSideQuest"
			LevelQuest = 2
			NameMon = "Horned Warrior"
			CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528, 1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
			CFrameMon = CFrame.new(-6400.85889, 24.7645149, -5818.63574, -0.964845479, 8.65926566e-08, -0.262817472, 3.98261392e-07, 1, -1.13260398e-06, 0.262817472, -1.19745812e-06, -0.964845479)
		elseif MyLevel == 1175 or MyLevel <= 1199 or SelectMonster == "Magma Ninja [Lv. 1175]" then -- Magma Ninja [Lv. 1175]
			Ms = "Magma Ninja [Lv. 1175]"
			NameQuest = "FireSideQuest"
			LevelQuest = 1
			NameMon = "Magma Ninja"
			CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
			CFrameMon = CFrame.new(-5496.65576, 58.6890411, -5929.76855, -0.885073781, 0, -0.465450764, 0, 1.00000012, -0, 0.465450764, 0, -0.885073781)
		elseif MyLevel == 1200 or MyLevel <= 1249 or SelectMonster == "Lava Pirate [Lv. 1200]" then -- Lava Pirate [Lv. 1200]
			Ms = "Lava Pirate [Lv. 1200]"
			NameQuest = "FireSideQuest"
			LevelQuest = 2
			NameMon = "Lava Pirate"
			CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
			CFrameMon = CFrame.new(-5169.71729, 34.1234779, -4669.73633, -0.196780294, 0, 0.98044765, 0, 1.00000012, -0, -0.98044765, 0, -0.196780294)
		elseif MyLevel == 1250 or MyLevel <= 1274 or SelectMonster == "Ship Deckhand [Lv. 1250]" then -- Ship Deckhand [Lv. 1250]
			Ms = "Ship Deckhand [Lv. 1250]"
			NameQuest = "ShipQuest1"
			LevelQuest = 1
			NameMon = "Ship Deckhand"
			CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
			CFrameMon = CFrame.new(1163.80872, 138.288452, 33058.4258, -0.998580813, 5.49076979e-08, -0.0532564968, 5.57436763e-08, 1, -1.42118655e-08, 0.0532564968, -1.71604082e-08, -0.998580813)
            if _G.AutoFarm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
			end 
        elseif MyLevel == 1275 or MyLevel <= 1299 or SelectMonster == "Ship Engineer [Lv. 1275]"  then -- Ship Engineer [Lv. 1275]
			Ms = "Ship Engineer [Lv. 1275]"
			NameQuest = "ShipQuest1"
			LevelQuest = 2
			NameMon = "Ship Engineer"
			CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
			CFrameMon = CFrame.new(916.666504, 44.0920448, 32917.207, -0.99746871, -4.85034697e-08, -0.0711069331, -4.8925461e-08, 1, 4.19294288e-09, 0.0711069331, 7.66126895e-09, -0.99746871)
            if _G.AutoFarm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
			end
        elseif MyLevel == 1300 or MyLevel <= 1324 or SelectMonster == "Ship Steward [Lv. 1300]" then -- Ship Steward [Lv. 1300]
			Ms = "Ship Steward [Lv. 1300]"
			NameQuest = "ShipQuest2"
			LevelQuest = 1
			NameMon = "Ship Steward"
			CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
			CFrameMon = CFrame.new(918.743286, 129.591064, 33443.4609, -0.999792814, -1.7070947e-07, -0.020350717, -1.72559169e-07, 1, 8.91351277e-08, 0.020350717, 9.2628369e-08, -0.999792814)
            if _G.AutoFarm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
			end
        elseif MyLevel == 1325 or MyLevel <= 1349 or SelectMonster == "Ship Officer [Lv. 1325]" then -- Ship Officer [Lv. 1325]
			Ms = "Ship Officer [Lv. 1325]"
			NameQuest = "ShipQuest2"
			LevelQuest = 2
			NameMon = "Ship Officer"
			CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
			CFrameMon = CFrame.new(786.051941, 181.474106, 33303.2969, 0.999285698, -5.32193063e-08, 0.0377905183, 5.68968588e-08, 1, -9.62386864e-08, -0.0377905183, 9.83201005e-08, 0.999285698)
            if _G.AutoFarm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
			end
        elseif MyLevel == 1350 or MyLevel <= 1374 or SelectMonster == "Arctic Warrior [Lv. 1350]" then -- Arctic Warrior [Lv. 1350]
			Ms = "Arctic Warrior [Lv. 1350]"
			NameQuest = "FrostQuest"
			LevelQuest = 1
			NameMon = "Arctic Warrior"
			CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226, -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
			CFrameMon = CFrame.new(5995.07471, 57.3188477, -6183.47314, 0.702747107, -1.53454167e-07, -0.711440146, -1.08168464e-07, 1, -3.22542007e-07, 0.711440146, 3.03620908e-07, 0.702747107)
            if _G.AutoFarm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
			end
        elseif MyLevel == 1375 or MyLevel <= 1424 or SelectMonster == "Snow Lurker [Lv. 1375]" then -- Snow Lurker [Lv. 1375]
			Ms = "Snow Lurker [Lv. 1375]"
			NameQuest = "FrostQuest"
			LevelQuest = 2
			NameMon = "Snow Lurker"
			CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226, -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
			CFrameMon = CFrame.new(5518.00684, 60.5559731, -6828.80518, -0.650781393, -3.64292951e-08, 0.759265184, -4.07668654e-09, 1, 4.44854642e-08, -0.759265184, 2.58550248e-08, -0.650781393)
		elseif MyLevel == 1425 or MyLevel <= 1449 or SelectMonster == "Sea Soldier [Lv. 1425]" then -- Sea Soldier [Lv. 1425]
			Ms = "Sea Soldier [Lv. 1425]"
			NameQuest = "ForgottenQuest"
			LevelQuest = 1
			NameMon = "Sea Soldier"
			CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943, -0.997911751, 4.42321983e-08, 0.064591676, 4.90968759e-08, 1, 7.37270085e-08, -0.064591676, 7.67442998e-08, -0.997911751)
			CFrameMon = CFrame.new(-3029.78467, 66.944252, -9777.38184, -0.998552859, 1.09555076e-08, 0.0537791774, 7.79564235e-09, 1, -5.89660658e-08, -0.0537791774, -5.84614881e-08, -0.998552859)
		elseif MyLevel >= 1450 or SelectMonster == "Water Fighter [Lv. 1450]" then -- Water Fighter [Lv. 1450]
			Ms = "Water Fighter [Lv. 1450]"
			NameQuest = "ForgottenQuest"
			LevelQuest = 2
			NameMon = "Water Fighter"
			CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943, -0.997911751, 4.42321983e-08, 0.064591676, 4.90968759e-08, 1, 7.37270085e-08, -0.064591676, 7.67442998e-08, -0.997911751)
			CFrameMon = CFrame.new(-3262.00098, 298.699615, -10553.6943, -0.233570755, -4.57538185e-08, 0.972339869, -5.80986068e-08, 1, 3.30992194e-08, -0.972339869, -4.87605725e-08, -0.233570755)
		end
    else 
        local MyLevel =  game.Players.LocalPlayer.Data.Level.Value
		Dis = 240
		if MyLevel == 1500 or MyLevel <= 1524 or SelectMonster == "Pirate Millionaire [Lv. 1500]" then
			Ms = "Pirate Millionaire [Lv. 1500]"
			NameQuest = "PiratePortQuest"
			LevelQuest = 1
			NameMon = "Pirate Millionaire"
			CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
			CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
		elseif MyLevel == 1525 or MyLevel <= 1574 or SelectMonster == "Pistol Billionaire [Lv. 1525]" then
			Ms = "Pistol Billionaire [Lv. 1525]"
			NameQuest = "PiratePortQuest"
			LevelQuest = 2
			NameMon = "Pistol Billionaire"
			CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
			CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
		elseif MyLevel == 1575 or MyLevel <= 1599 or SelectMonster == "Dragon Crew Warrior [Lv. 1575]" then
			Ms = "Dragon Crew Warrior [Lv. 1575]"
			NameQuest = "AmazonQuest"
			LevelQuest = 1
			NameMon = "Dragon Crew Warrior"
			CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
			CFrameMon = CFrame.new(6241.9951171875, 51.522083282471, -1243.9771728516)
		elseif MyLevel == 1600 or MyLevel <= 1624 or SelectMonster == "Dragon Crew Archer [Lv. 1600]" then
			Ms = "Dragon Crew Archer [Lv. 1600]"
			NameQuest = "AmazonQuest"
			LevelQuest = 2
			NameMon = "Dragon Crew Archer"
			CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
			CFrameMon = CFrame.new(6488.9155273438, 383.38375854492, -110.66246032715)
		elseif MyLevel == 1625 or MyLevel <= 1649 or SelectMonster == "Female Islander [Lv. 1625]" then
			Ms = "Female Islander [Lv. 1625]"
			NameQuest = "AmazonQuest2"
			LevelQuest = 1
			NameMon = "Female Islander"
			CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(4770.4990234375, 758.95520019531, 1069.8680419922)
		elseif MyLevel == 1650 or MyLevel <= 1699 or SelectMonster == "Giant Islander [Lv. 1650]" then
			Ms = "Giant Islander [Lv. 1650]"
			NameQuest = "AmazonQuest2"
			LevelQuest = 2
			NameMon = "Giant Islander"
			CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(4530.3540039063, 656.75695800781, -131.60952758789)
		elseif MyLevel == 1700 or MyLevel <= 1724 or SelectMonster == "Marine Commodore [Lv. 1700]" then
			Ms = "Marine Commodore [Lv. 1700]"
			NameQuest = "MarineTreeIsland"
			LevelQuest = 1
			NameMon = "Marine Commodore"
			CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
			CFrameMon = CFrame.new(2490.0844726563, 190.4232635498, -7160.0502929688)
		elseif MyLevel == 1725 or MyLevel <= 1774 or SelectMonster == "Marine Rear Admiral [Lv. 1725]" then
			Ms = "Marine Rear Admiral [Lv. 1725]"
			NameQuest = "MarineTreeIsland"
			LevelQuest = 2
			NameMon = "Marine Rear Admiral"
			CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
			CFrameMon = CFrame.new(3951.3903808594, 229.11549377441, -6912.81640625)
		elseif MyLevel == 1775 or MyLevel <= 1799 or SelectMonster == "Fishman Raider [Lv. 1775]" then
			Ms = "Fishman Raider [Lv. 1775]"
			NameQuest = "DeepForestIsland3"
			LevelQuest = 1
			NameMon = "Fishman Raider"
			CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
			CFrameMon = CFrame.new(-10322.400390625, 390.94473266602, -8580.0908203125)
		elseif MyLevel == 1800 or MyLevel <= 1824 or SelectMonster == "Fishman Captain [Lv. 1800]" then
			Ms = "Fishman Captain [Lv. 1800]"
			NameQuest = "DeepForestIsland3"
			LevelQuest = 2
			NameMon = "Fishman Captain"
			CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
			CFrameMon = CFrame.new(-11194.541992188, 442.02795410156, -8608.806640625)
		elseif MyLevel == 1825 or MyLevel <= 1849 or SelectMonster == "Forest Pirate [Lv. 1825]" then
			Ms = "Forest Pirate [Lv. 1825]"
			NameQuest = "DeepForestIsland"
			LevelQuest = 1
			NameMon = "Forest Pirate"
			CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
			CFrameMon = CFrame.new(-13225.809570313, 428.19387817383, -7753.1245117188)
		elseif MyLevel == 1850 or MyLevel <= 1899 or SelectMonster == "Mythological Pirate [Lv. 1850]" then
			Ms = "Mythological Pirate [Lv. 1850]"
			NameQuest = "DeepForestIsland"
			LevelQuest = 2
			NameMon = "Mythological Pirate"
			CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
			CFrameMon = CFrame.new(-13869.172851563, 564.95251464844, -7084.4135742188)
		elseif MyLevel == 1900 or MyLevel <= 1924 or SelectMonster == "Jungle Pirate [Lv. 1900]" then
			Ms = "Jungle Pirate [Lv. 1900]"
			NameQuest = "DeepForestIsland2"
			LevelQuest = 1
			NameMon = "Jungle Pirate"
			CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
			CFrameMon = CFrame.new(-11982.221679688, 376.32522583008, -10451.415039063)
		elseif MyLevel == 1925 or MyLevel <= 1974 or SelectMonster == "Musketeer Pirate [Lv. 1925]" then
			Ms = "Musketeer Pirate [Lv. 1925]"
			NameQuest = "DeepForestIsland2"
			LevelQuest = 2
			NameMon = "Musketeer Pirate"
			CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
			CFrameMon = CFrame.new(-13282.3046875, 496.23684692383, -9565.150390625)
        elseif MyLevel == 1975 or MyLevel <= 1999 or SelectMonster == "Reborn Skeleton [Lv. 1975]" then
			Ms = "Reborn Skeleton [Lv. 1975]"
			NameQuest = "HauntedQuest1"
			LevelQuest = 1
			NameMon = "Reborn Skeleton"
			CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(-8761.3154296875, 164.85829162598, 6161.1567382813)
        elseif MyLevel == 2000 or MyLevel <= 2024 or SelectMonster == "Living Zombie [Lv. 2000]" then
			Ms = "Living Zombie [Lv. 2000]"
			NameQuest = "HauntedQuest1"
			LevelQuest = 2
			NameMon = "Living Zombie"
			CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
			CFrameMon = CFrame.new(-10093.930664063, 237.38233947754, 6180.5654296875)
		elseif MyLevel == 2025 or MyLevel <= 2049 or SelectMonster == "Demonic Soul [Lv. 2025]" then
			Ms = "Demonic Soul [Lv. 2025]"
			NameQuest = "HauntedQuest2"
			LevelQuest = 1
			NameMon = "Demonic Soul"
			CFrameQuest = CFrame.new(-9514.78027, 171.162918, 6078.82373, 0.301918149, 7.4535027e-09, 0.953333855, -3.22802141e-09, 1, -6.79604995e-09, -0.953333855, -1.02553133e-09, 0.301918149)
			CFrameMon = CFrame.new(-9466.72949, 171.162918, 6132.01514)
		elseif MyLevel == 2050 or MyLevel <= 2074 or SelectMonster == "Posessed Mummy [Lv. 2050]" then
			Ms = "Posessed Mummy [Lv. 2050]" 
			NameQuest = "HauntedQuest2"
			LevelQuest = 2
			NameMon = "Posessed Mummy"
			CFrameQuest = CFrame.new(-9514.78027, 171.162918, 6078.82373, 0.301918149, 7.4535027e-09, 0.953333855, -3.22802141e-09, 1, -6.79604995e-09, -0.953333855, -1.02553133e-09, 0.301918149)
			CFrameMon = CFrame.new(-9589.93848, 4.85058546, 6190.27197)
        elseif MyLevel == 2075 or MyLevel <= 2099 or SelectMonster == "Peanut Scout [Lv. 2075]" then
            Ms = "Peanut Scout [Lv. 2075]"
            NameQuest = "NutsIslandQuest"
            LevelQuest = 1
            NameMon = "Peanut Scout"
            CFrameQuest = CFrame.new(-2103.9375, 38.139019012451, -10192.702148438)
            CFrameMon = CFrame.new(-2150.587890625, 122.49767303467, -10358.994140625)
		elseif MyLevel == 2100 or MyLevel <= 2124 or SelectMonster == "Peanut President [Lv. 2100]" then
            Ms = "Peanut President [Lv. 2100]"
            NameQuest = "NutsIslandQuest"
            LevelQuest = 2
            NameMon = "Peanut President"
            CFrameQuest = CFrame.new(-2103.9375, 38.139019012451, -10192.702148438)
            CFrameMon = CFrame.new(-2150.587890625, 122.49767303467, -10358.994140625)
        elseif MyLevel == 2125 or MyLevel <= 2149 or SelectMonster == "Ice Cream Chef [Lv. 2125]" then
            Ms = "Ice Cream Chef [Lv. 2125]"
            NameQuest = "IceCreamIslandQuest"
            LevelQuest = 1
            NameMon = "Ice Cream Chef"
            CFrameQuest = CFrame.new(-819.84533691406, 65.845329284668, -10965.487304688)
            CFrameMon = CFrame.new(-890.55895996094, 186.34135437012, -11127.306640625)
        elseif MyLevel == 2150 or MyLevel <= 2199 or SelectMonster == "Ice Cream Commander [Lv. 2150]" then
            Ms = "Ice Cream Commander [Lv. 2150]"
            NameQuest = "IceCreamIslandQuest"
            LevelQuest = 2
            NameMon = "Ice Cream Commander"
            CFrameQuest = CFrame.new(-819.84533691406, 65.845329284668, -10965.487304688)
            CFrameMon = CFrame.new(-890.55895996094, 186.34135437012, -11127.306640625)
		elseif MyLevel == 2200 or MyLevel <= 2224 or SelectMonster == "Cookie Crafter [Lv. 2200]" then
            Ms = "Cookie Crafter [Lv. 2200]"
            NameQuest = "CakeQuest1"
            LevelQuest = 1
            NameMon = "Cookie Crafter"
            CFrameQuest = CFrame.new(-2021.5509033203125, 37.798221588134766, -12028.103515625)
            CFrameMon = CFrame.new(-2273.00244140625, 90.22590637207031, -12151.62109375)
		elseif MyLevel == 2225 or MyLevel <= 2249 or SelectMonster == "Cake Guard [Lv. 2225]" then
            Ms = "Cake Guard [Lv. 2225]"
            NameQuest = "CakeQuest1"
            LevelQuest = 2
            NameMon = "Cake Guard"
            CFrameQuest = CFrame.new(-2021.5509033203125, 37.798221588134766, -12028.103515625)
            CFrameMon = CFrame.new(-1442.373046875, 158.14111328125, -12277.37109375)
		elseif MyLevel == 2250 or MyLevel <= 2274 or SelectMonster == "Baking Staff [Lv. 2250]" then
            Ms = "Baking Staff [Lv. 2250]"
            NameQuest = "CakeQuest2"
            LevelQuest = 1
            NameMon = "Baking Staff"
            CFrameQuest = CFrame.new(-1927.9107666015625, 37.79813003540039, -12843.78515625)
            CFrameMon = CFrame.new(-1837.2803955078125, 129.0594482421875, -12934.5498046875)
		elseif MyLevel >= 2275 or SelectMonster == "Head Baker [Lv. 2275]" then
            Ms = "Head Baker [Lv. 2275]"
            NameQuest = "CakeQuest2"
            LevelQuest = 2
            NameMon = "Head Baker"
            CFrameQuest = CFrame.new(-1927.9107666015625, 37.79813003540039, -12843.78515625)
            CFrameMon = CFrame.new(-2203.302490234375, 109.90937042236328, -12788.7333984375)
        end
    end
end

-------------------------------------Confige kaitan-------------------------------------
spawn(function()
	if _G.ScriptMode == "kaitan" then
	    _G.Team = "Pirate" -- Marine
        _G.FpsBoost = true
        _G.AutoSetSpawn = true
        _G.FastAttack = true
        _G.SelectToolWeapon = "Combat"
        _G.Kaitanstat =  true
        ps = true



    SelectFruitSinper = "Dark" -- ชื่อ Fruits : Name Fruits
        _G.BuyFruitSinPer = true
        _G.BRINGSFRUITS = true
        _G.Autorandomfruits = true

    if game.PlaceId == 2753915549 then -- Sea 1
        _G.AutoFarm = true 
        _G.AutoNew_Ws = true -- Auto New World
        _G.AutoSaber = true
        _G.AutoSuperhuman = true
        _G.BuyKaitun = true
        AutoEquip = true
    elseif game.PlaceId == 4442272183 then -- Sea 2
        _G.AutoFarm = true 
        _G.AutoLegendarySword = true
        _G.AutoThirdSea = true
        _G.AutoQuestBartilo = true
        _G.BuyKaitun = false
        _G.AutoNew_Ws = false -- Auto New World
        AutoEquip = true
    elseif game.PlaceId == 7449423635 then -- Sea 3
        _G.AutoFarm = true 
        _G.AutoThirdSea = false
        _G.AutoNew_Ws = false
        _G.AutoBuddySword = true
        _G.AutoKatakuri = true
        _G.AutoEliteHunter = true
        AutoEquip = true
    elseif _G.Masterymode then -- Mastery Mode
        _G.AutoFarm = false 
        _G.AutoFarmMasteryFruit = true
        _G.KillAt = 20
        _G.AutoCakePrince = false
        _G.AutoBuddySword = false
        _G.AutoKatakuri = false
        _G.AutoEliteHunter = false
     elseif _G.Raidmode then  -- Raid Mode
        _G.SelectChip = "fruits"-- "Flame","Ice","Quake","Light","Dark","String","Rumble","Magma","Human: Buddha","Sand","Bird-Bird: Phoenix"
        _G.AutoBuyChip = true
        _G.AutoStartRaid = true
        _G.AutoRaids = true
        ps = true
        _G.AutoCakePrince = false
        _G.AutoBuddySword = false
        _G.AutoKatakuri = false
        _G.AutoEliteHunter = false
   end

_G.HideUi = true


if _G.HideUi then
		wait(1)
		game:GetService("VirtualInputManager"):SendKeyEvent(true,305,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
		game:GetService("VirtualInputManager"):SendKeyEvent(false,305,false,game.Players.LocalPlayer.Character.HumanoidRootPart)
end
end
end)

spawn(function()
if _G.Script_Mode == "kaitun" then

local gui = game:GetService("CoreGui").RobloxGui.Modules:FindFirstChild("X2ZLIB")
    gui:Destroy()

do
	local ui = game.CoreGui:FindFirstChild("ABc")
	if ui then
		ui:Destroy()
	end
end

local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")
local RunService = game:GetService("RunService")
local LocalPlayer = game:GetService("Players").LocalPlayer
local Mouse = LocalPlayer:GetMouse()
local tween = game:GetService("TweenService")
local Red = {RainbowColorValue = 0, HueSelectionPosition = 0}


local function MakeDraggable(topbarobject, object)
	local Dragging = nil
	local DragInput = nil
	local DragStart = nil
	local StartPosition = nil

	local function Update(input)
		local Delta = input.Position - DragStart
		local pos =
			UDim2.new(
				StartPosition.X.Scale,
				StartPosition.X.Offset + Delta.X,
				StartPosition.Y.Scale,
				StartPosition.Y.Offset + Delta.Y
			)
		local Tween = TweenService:Create(object, TweenInfo.new(0.2), {Position = pos})
		Tween:Play()
	end

	topbarobject.InputBegan:Connect(
		function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
				Dragging = true
				DragStart = input.Position
				StartPosition = object.Position

				input.Changed:Connect(
					function()
						if input.UserInputState == Enum.UserInputState.End then
							Dragging = false
						end
					end
				)
			end
		end
	)

	topbarobject.InputChanged:Connect(
		function(input)
			if
				input.UserInputType == Enum.UserInputType.MouseMovement or
				input.UserInputType == Enum.UserInputType.Touch
			then
				DragInput = input
			end
		end
	)

	UserInputService.InputChanged:Connect(
		function(input)
			if input == DragInput and Dragging then
				Update(input)
			end
		end
	)
end

local function Tween(instance, properties,style,wa)
	if style == nil or "" then
		return Back
	end
	tween:Create(instance,TweenInfo.new(wa,Enum.EasingStyle[style]),{properties}):Play()
end

local ActualTypes = {
	RoundFrame = "ImageLabel",
	Shadow = "ImageLabel",
	Circle = "ImageLabel",
	CircleButton = "ImageButton",
	Frame = "Frame",
	Label = "TextLabel",
	Button = "TextButton",
	SmoothButton = "ImageButton",
	Box = "TextBox",
	ScrollingFrame = "ScrollingFrame",
	Menu = "ImageButton",
	NavBar = "ImageButton"
}

local Properties = {
	RoundFrame = {
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554237731",
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(3,3,297,297)
	},
	SmoothButton = {
		AutoButtonColor = false,
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554237731",
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(3,3,297,297)
	},
	Shadow = {
		Name = "Shadow",
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554236805",
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(23,23,277,277),
		Size = UDim2.fromScale(1,1) + UDim2.fromOffset(30,30),
		Position = UDim2.fromOffset(-15,-15)
	},
	Circle = {
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554831670"
	},
	CircleButton = {
		BackgroundTransparency = 1,
		AutoButtonColor = false,
		Image = "http://www.roblox.com/asset/?id=5554831670"
	},
	Frame = {
		BackgroundTransparency = 1,
		BorderSizePixel = 0,
		Size = UDim2.fromScale(1,1)
	},
	Label = {
		BackgroundTransparency = 1,
		Position = UDim2.fromOffset(5,0),
		Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
		TextSize = 14,
		TextXAlignment = Enum.TextXAlignment.Left
	},
	Button = {
		BackgroundTransparency = 1,
		Position = UDim2.fromOffset(5,0),
		Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
		TextSize = 14,
		TextXAlignment = Enum.TextXAlignment.Left
	},
	Box = {
		BackgroundTransparency = 1,
		Position = UDim2.fromOffset(5,0),
		Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
		TextSize = 14,
		TextXAlignment = Enum.TextXAlignment.Left
	},
	ScrollingFrame = {
		BackgroundTransparency = 1,
		ScrollBarThickness = 0,
		CanvasSize = UDim2.fromScale(0,0),
		Size = UDim2.fromScale(1,1)
	},
	Menu = {
		Name = "More",
		AutoButtonColor = false,
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5555108481",
		Size = UDim2.fromOffset(20,20),
		Position = UDim2.fromScale(1,0.5) - UDim2.fromOffset(25,10)
	},
	NavBar = {
		Name = "SheetToggle",
		Image = "http://www.roblox.com/asset/?id=5576439039",
		BackgroundTransparency = 1,
		Size = UDim2.fromOffset(20,20),
		Position = UDim2.fromOffset(5,5),
		AutoButtonColor = false
	}
}

local Types = {
	"RoundFrame",
	"Shadow",
	"Circle",
	"CircleButton",
	"Frame",
	"Label",
	"Button",
	"SmoothButton",
	"Box",
	"ScrollingFrame",
	"Menu",
	"NavBar"
}

function FindType(String)
	for _, Type in next, Types do
		if Type:sub(1, #String):lower() == String:lower() then
			return Type
		end
	end
	return false
end

local Objects = {}

function Objects.new(Type)
	local TargetType = FindType(Type)
	if TargetType then
		local NewImage = Instance.new(ActualTypes[TargetType])
		if Properties[TargetType] then
			for Property, Value in next, Properties[TargetType] do
				NewImage[Property] = Value
			end
		end
		return NewImage
	else
		return Instance.new(Type)
	end
end

local function GetXY(GuiObject)
	local Max, May = GuiObject.AbsoluteSize.X, GuiObject.AbsoluteSize.Y
	local Px, Py = math.clamp(Mouse.X - GuiObject.AbsolutePosition.X, 0, Max), math.clamp(Mouse.Y - GuiObject.AbsolutePosition.Y, 0, May)
	return Px/Max, Py/May
end

local function CircleAnim(GuiObject, EndColour, StartColour)
	local PX, PY = GetXY(GuiObject)
	local Circle = Objects.new("Circle")
	Circle.Size = UDim2.fromScale(0,0)
	Circle.Position = UDim2.fromScale(PX,PY)
	Circle.ImageColor3 = StartColour or GuiObject.ImageColor3
	Circle.ZIndex = 200
	Circle.Parent = GuiObject
	local Size = GuiObject.AbsoluteSize.X
	TweenService:Create(Circle, TweenInfo.new(0.5), {Position = UDim2.fromScale(PX,PY) - UDim2.fromOffset(Size/2,Size/2), ImageTransparency = 1, ImageColor3 = EndColour, Size = UDim2.fromOffset(Size,Size)}):Play()
	spawn(function()
		wait(0.5)
		Circle:Destroy()
	end)
end
local library = {}

function library:Window(text,logo,keybind)
	local uihide = false
	local abc = false
	local logo = logo or 0
	local currentpage = ""
	local keybind = keybind or Enum.KeyCode.RightControl
	local yoo = string.gsub(tostring(keybind),"Enum.KeyCode.","")

	local ABc = Instance.new("ScreenGui")
	ABc.Name = "ABc"
	ABc.Parent = game.CoreGui
	ABc.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

	local Main = Instance.new("Frame")
	Main.Name = "Main"
	Main.Parent = ABc
	Main.ClipsDescendants = false
	Main.AnchorPoint = Vector2.new(0.5,0.5)
	Main.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
	Main.Position = UDim2.new(0.5, 0, 0.5, 0)
	Main.Size = UDim2.new(0, 0, 0, 0)

	Main:TweenSize(UDim2.new(0, 656, 0, 400),"Out","Quad",0.4,true)
	wait(0.45)
	Main.ClipsDescendants = false

	local Glow = Instance.new("ImageLabel")

	Glow.Name = "Glow"
	Glow.Parent = Main
	Glow.Active = true
	Glow.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Glow.BackgroundTransparency = 1.000
	Glow.Position = UDim2.new(-0.0563295893, 0, -0.059, 0)
	Glow.Size = UDim2.new(0, 731, 0, 447)
	Glow.Image = "rbxassetid://5028857084"
	Glow.ImageColor3 = Color3.fromRGB(255, 37, 40)

	local MCNR = Instance.new("UICorner")
	MCNR.Name = "MCNR"
	MCNR.Parent = Main

	local Top = Instance.new("Frame")
	Top.Name = "Top"
	Top.Parent = Main
	Top.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
	Top.Size = UDim2.new(0, 656, 0, 27)

	local TCNR = Instance.new("UICorner")
	TCNR.Name = "TCNR"
	TCNR.Parent = Top

	local Logo = Instance.new("ImageLabel")
	Logo.Name = "Logo"
	Logo.Parent = Top
	Logo.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Logo.BackgroundTransparency = 1.000
	Logo.Position = UDim2.new(0, 10, 0, 1)
	Logo.Size = UDim2.new(0, 40, 0, 25)
	Logo.Image = "rbxassetid://"..tostring(logo)

	local Name = Instance.new("TextLabel")
	Name.Name = "Name"
	Name.Parent = Top
	Name.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Name.BackgroundTransparency = 1.000
	Name.Position = UDim2.new(0.0609756112, 0, 0, 0)
	Name.Size = UDim2.new(0, 61, 0, 27)
	Name.Font = Enum.Font.GothamSemibold
	Name.Text = text
	Name.TextColor3 = Color3.fromRGB(225, 225, 225)
	Name.TextSize = 17.000

	local Hub = Instance.new("TextLabel")
	Hub.Name = "Hub"
	Hub.Parent = Top
	Hub.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Hub.BackgroundTransparency = 1.000
	Hub.Position = UDim2.new(0, 110, 0, 0)
	Hub.Size = UDim2.new(0, 81, 0, 27)
	Hub.Font = Enum.Font.GothamSemibold
	Hub.Text = "HUB"
	Hub.TextColor3 = Color3.fromRGB(249, 44, 79)
	Hub.TextSize = 17.000
	Hub.TextXAlignment = Enum.TextXAlignment.Left

	local VER = Instance.new("TextLabel")
	VER.Name = "VERSION"
	VER.Parent = Top
	VER.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	VER.BackgroundTransparency = 1.000
	VER.Position = UDim2.new(0.847561002, 0, 0)
	VER.Size = UDim2.new(0, 81, 0, 27)
	VER.Font = Enum.Font.GothamSemibold
	VER.Text = "Version 1.0.1"
	VER.TextColor3 = Color3.fromRGB(249, 44, 79)
	VER.TextSize = 17.000
	VER.TextXAlignment = Enum.TextXAlignment.Right

	local BindButton = Instance.new("TextButton")
	BindButton.Name = "BindButton"
	BindButton.Parent = Top
	BindButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	BindButton.BackgroundTransparency = 1.000
	BindButton.Position = UDim2.new(0.267561002, 0, 0, 0)
	BindButton.Size = UDim2.new(0, 100, 0, 27)
	BindButton.Font = Enum.Font.GothamSemibold
	BindButton.Text = "[ "..string.gsub(tostring(keybind),"Enum.KeyCode.","").." ]"
	BindButton.TextColor3 = Color3.fromRGB(100, 100, 100)
	BindButton.TextSize = 11.000

	BindButton.MouseButton1Click:Connect(function ()
		BindButton.Text = "[ ... ]"
		local inputwait = game:GetService("UserInputService").InputBegan:wait()
		local shiba = inputwait.KeyCode == Enum.KeyCode.Unknown and inputwait.UserInputType or inputwait.KeyCode

		if shiba.Name ~= "Focus" and shiba.Name ~= "MouseMovement" then
			BindButton.Text = "[ "..shiba.Name.." ]"
			yoo = shiba.Name
		end
	end)

	local Tab = Instance.new("Frame")
	Tab.Name = "Tab"
	Tab.Parent = Main
	Tab.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
	Tab.Position = UDim2.new(0, 5, 0, 30)
	Tab.Size = UDim2.new(0, 150, 0, 365)

	local TCNR = Instance.new("UICorner")
	TCNR.Name = "TCNR"
	TCNR.Parent = Tab

	local ScrollTab = Instance.new("ScrollingFrame")
	ScrollTab.Name = "ScrollTab"
	ScrollTab.Parent = Tab
	ScrollTab.Active = true
	ScrollTab.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ScrollTab.BackgroundTransparency = 1.000
	ScrollTab.Size = UDim2.new(0, 150, 0, 365)
	ScrollTab.CanvasSize = UDim2.new(0, 0, 0, 0)
	ScrollTab.ScrollBarThickness = 0

	local PLL = Instance.new("UIListLayout")
	PLL.Name = "PLL"
	PLL.Parent = ScrollTab
	PLL.SortOrder = Enum.SortOrder.LayoutOrder
	PLL.Padding = UDim.new(0, 15)

	local PPD = Instance.new("UIPadding")
	PPD.Name = "PPD"
	PPD.Parent = ScrollTab
	PPD.PaddingLeft = UDim.new(0, 10)
	PPD.PaddingTop = UDim.new(0, 10)

	local Page = Instance.new("Frame")
	Page.Name = "Page"
	Page.Parent = Main
	Page.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
	Page.Position = UDim2.new(0.245426834, 0, 0.075000003, 0)
	Page.Size = UDim2.new(0, 490, 0, 365)

	local PCNR = Instance.new("UICorner")
	PCNR.Name = "PCNR"
	PCNR.Parent = Page

	local MainPage = Instance.new("Frame")
	MainPage.Name = "MainPage"
	MainPage.Parent = Page
	MainPage.ClipsDescendants = true
	MainPage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	MainPage.BackgroundTransparency = 1.000
	MainPage.Size = UDim2.new(0, 490, 0, 365)

	local PageList = Instance.new("Folder")
	PageList.Name = "PageList"
	PageList.Parent = MainPage

	local UIPageLayout = Instance.new("UIPageLayout")

	UIPageLayout.Parent = PageList
	UIPageLayout.SortOrder = Enum.SortOrder.LayoutOrder
	UIPageLayout.EasingDirection = Enum.EasingDirection.InOut
	UIPageLayout.EasingStyle = Enum.EasingStyle.Quad
	UIPageLayout.FillDirection = Enum.FillDirection.Vertical
	UIPageLayout.Padding = UDim.new(0, 15)
	UIPageLayout.TweenTime = 0.400
	UIPageLayout.GamepadInputEnabled = false
	UIPageLayout.ScrollWheelInputEnabled = false
	UIPageLayout.TouchInputEnabled = false

	MakeDraggable(Top,Main)

	do  local ui =  game:GetService("CoreGui"):FindFirstChild("Luna")  if ui then ui:Destroy() end end


	local Luna = Instance.new("ScreenGui")
	local ToggleFrameUi = Instance.new("Frame")
	local UICorner = Instance.new("UICorner")
	local ToggleImgUi = Instance.new("ImageLabel")
	local Uitoggle = Instance.new("TextLabel")
	local Yedhee = Instance.new("TextLabel")
	local SearchStroke = Instance.new("UIStroke")


	Luna.Name = "Luna"
	Luna.Parent = game.CoreGui
	Luna.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

	ToggleFrameUi.Name = "ToggleFrameUi"
	ToggleFrameUi.Parent = Luna
	ToggleFrameUi.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
	ToggleFrameUi.Position = UDim2.new(0.883, 0,0.282, 0)
	ToggleFrameUi.Size = UDim2.new(0, 198, 0, 48)

	SearchStroke.Thickness = 1
	SearchStroke.Name = ""
	SearchStroke.Parent = ToggleFrameUi
	SearchStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
	SearchStroke.LineJoinMode = Enum.LineJoinMode.Round
	SearchStroke.Color = Color3.fromRGB(249, 44, 79)
	SearchStroke.Transparency = 0

	UICorner.CornerRadius = UDim.new(0, 4)
	UICorner.Parent = ToggleFrameUi

	ToggleImgUi.Name = "ToggleImgUi"
	ToggleImgUi.Parent = ToggleFrameUi
	ToggleImgUi.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ToggleImgUi.BackgroundTransparency = 1.000
	ToggleImgUi.Position = UDim2.new(0.0454545468, 0, 0.125000313, 0)
	ToggleImgUi.Size = UDim2.new(0, 40, 0, 35)
	ToggleImgUi.Image = "rbxassetid://"

	local Glow = Instance.new("ImageLabel")

	Glow.Name = "Glow"
	Glow.Parent = ToggleFrameUi
	Glow.Active = true
	Glow.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Glow.BackgroundTransparency = 1.000
	Glow.Position = UDim2.new(-0.0714811087, 0, -0.125, 0)
	Glow.Size = UDim2.new(0, 0, 0, 0)
	Glow.Image = "rbxassetid://5028857084"
	Glow.ImageColor3 = Color3.fromRGB(255, 37, 40)

	Uitoggle.Name = "Uitoggle"
	Uitoggle.Parent = ToggleFrameUi
	Uitoggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Uitoggle.BackgroundTransparency = 1.000
	Uitoggle.Position = UDim2.new(0.25757575, 0, 0, 0)
	Uitoggle.Size = UDim2.new(0, 137, 0, 25)
	Uitoggle.Font = Enum.Font.GothamSemibold
	Uitoggle.Text = "UI Toggle :"
	Uitoggle.TextColor3 = Color3.fromRGB(255, 255, 255)
	Uitoggle.TextSize = 12.000

	Yedhee.Name = "Yedhee"
	Yedhee.Parent = ToggleFrameUi
	Yedhee.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Yedhee.BackgroundTransparency = 1.000
	Yedhee.Position = UDim2.new(0.25757575, 0, 0.479166657, 0)
	Yedhee.Size = UDim2.new(0, 137, 0, 25)
	Yedhee.Font = Enum.Font.GothamSemibold
	Yedhee.Text = "Lable"
	Yedhee.TextColor3 = Color3.fromRGB(255, 255, 255)
	Yedhee.TextSize = 12.000
	spawn(function()
		while wait() do
			Yedhee.Text = '['..yoo..']'
		end
	end)


	Yedhee.TextTransparency = 1
	Uitoggle.TextTransparency = 1
	ToggleImgUi.ImageTransparency = 1
	ToggleFrameUi.BackgroundTransparency = 1.000
	SearchStroke.Transparency = 1

	UserInputService.InputBegan:Connect(function(input)
		if input.KeyCode == Enum.KeyCode[yoo] then
			if uihide == false then
				game:GetService("TweenService"):Create(
				ToggleFrameUi,
				TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
				{Size = UDim2.new(0, 198, 0, 48)}
				):Play()
				game:GetService("TweenService"):Create(
				Glow,
				TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
				{Size = UDim2.new(0, 226, 0, 60)}
				):Play()
				game:GetService("TweenService"):Create(
				ToggleFrameUi,
				TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
				{BackgroundTransparency = 0}
				):Play()
				Main.ClipsDescendants = true
				Yedhee.TextTransparency = 0
				Uitoggle.TextTransparency = 0
				ToggleImgUi.ImageTransparency = 0
				SearchStroke.Transparency = 0
				wait(.2)
				uihide = true
				Main:TweenSize(UDim2.new(0, 0, 0, 0),"In","Quad",0.4,true)
			else
				game:GetService("TweenService"):Create(
				ToggleFrameUi,
				TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
				{Size = UDim2.new(0, 0, 0, 0)}
				):Play()
				game:GetService("TweenService"):Create(
				Glow,
				TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
				{Size = UDim2.new(0, 0, 0, 0)}
				):Play()
				game:GetService("TweenService"):Create(
				ToggleFrameUi,
				TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
				{BackgroundTransparency = 1}
				):Play()
				Yedhee.TextTransparency = 1
				Uitoggle.TextTransparency = 1
				ToggleImgUi.ImageTransparency = 1
				SearchStroke.Transparency = 1
				wait(.2)
				uihide = false
				Main:TweenSize(UDim2.new(0, 656, 0, 400),"Out","Quad",0.4,true)
				wait(0.45)
				Main.ClipsDescendants = false
			end
		end
	end)
	MakeDraggable(ToggleFrameUi,ToggleFrameUi)

	-- 	pcall(function()
	-- 		game:GetService("UserInputService").InputBegan:Connect(function(io, p)
	-- 			if io.KeyCode == Enum.KeyCode[yoo] then
	-- 				if uitoggled == false then


	-- 					game:GetService("TweenService"):Create(
	-- 						ToggleFrameUi,
	-- 						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
	-- 						{Size = UDim2.new(0, 0, 0, 0)}
	-- 					):Play()
	-- 					game:GetService("TweenService"):Create(
	-- 						ToggleFrameUi,
	-- 						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
	-- 						{BackgroundTransparency = 1}
	-- 					):Play()
	-- 					Yedhee.TextTransparency = 1
	-- 					Uitoggle.TextTransparency = 1
	-- 					ToggleImgUi.ImageTransparency = 1
	-- 					wait(.2)
	-- 					uitoggled = false
	-- 				else
	-- 					game:GetService("TweenService"):Create(
	-- 						ToggleFrameUi,
	-- 						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
	-- 						{Size = UDim2.new(0, 198, 0, 48)}
	-- 					):Play()
	-- 					game:GetService("TweenService"):Create(
	-- 						ToggleFrameUi,
	-- 						TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
	-- 						{BackgroundTransparency = 0}
	-- 					):Play()
	-- 					Yedhee.TextTransparency = 0
	-- 					Uitoggle.TextTransparency = 0
	-- 					ToggleImgUi.ImageTransparency = 0
	-- 					wait(.2)
	-- 					uitoggled = true
	-- 				end
	-- 			end
	-- 		end)
	-- 	end)

	local uitab = {}

	function uitab:Tab(text,Image)
		local Image = Image or 0
		local TabButton = Instance.new("TextButton")
		TabButton.Parent = ScrollTab
		TabButton.Name = text.."Server"
		TabButton.Text = text
		TabButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		TabButton.BackgroundTransparency = 1.000
		TabButton.Size = UDim2.new(0, 130, 0, 23)
		TabButton.Font = Enum.Font.GothamSemibold
		TabButton.TextColor3 = Color3.fromRGB(225, 225, 225)
		TabButton.TextSize = 15.000
		TabButton.TextTransparency = 0.500

		local MainFramePage = Instance.new("ScrollingFrame")
		MainFramePage.Name = text.."_Page"
		MainFramePage.Parent = PageList
		MainFramePage.Active = true
		MainFramePage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		MainFramePage.BackgroundTransparency = 1.000
		MainFramePage.BorderSizePixel = 0
		MainFramePage.Size = UDim2.new(0, 490, 0, 365)
		MainFramePage.CanvasSize = UDim2.new(0, 0, 0, 0)
		MainFramePage.ScrollBarThickness = 0

		local ImageTab = Instance.new("ImageLabel") --http://www.roblox.com/asset/?id=
		ImageTab.Name = "Icon"
		ImageTab.Parent = TabButton
		ImageTab.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ImageTab.BackgroundTransparency = 1.000
		ImageTab.Position = UDim2.new(0, 0, 0, 3)
		ImageTab.Size = UDim2.new(0, 20, 0, 20)
		ImageTab.Image = "rbxassetid://"..tostring(Image)

		local UIPadding = Instance.new("UIPadding")
		local UIListLayout = Instance.new("UIListLayout")

		UIPadding.Parent = MainFramePage
		UIPadding.PaddingLeft = UDim.new(0, 10)
		UIPadding.PaddingTop = UDim.new(0, 10)

		UIListLayout.Padding = UDim.new(0,15)
		UIListLayout.Parent = MainFramePage
		UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder

		TabButton.MouseButton1Click:Connect(function()
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0.5}
					):Play()
				end
				TweenService:Create(
					TabButton,
					TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			for i,v in next, PageList:GetChildren() do
				currentpage = string.gsub(TabButton.Name,"Server","").."_Page"
				if v.Name == currentpage then
					UIPageLayout:JumpTo(v)
				end
			end
		end)

		if abc == false then
			for i,v in next, ScrollTab:GetChildren() do
				if v:IsA("TextButton") then
					TweenService:Create(
						v,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0.5}
					):Play()
				end
				TweenService:Create(
					TabButton,
					TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end
			UIPageLayout:JumpToIndex(1)
			abc = true
		end

		game:GetService("RunService").Stepped:Connect(function()
			pcall(function()
				MainFramePage.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 20)
				ScrollTab.CanvasSize = UDim2.new(0,0,0,PLL.AbsoluteContentSize.Y + 20)
			end)
		end)

		local main = {}
		function main:Button(text,callback)
			local Button = Instance.new("Frame")
			local UICorner = Instance.new("UICorner")
			local TextBtn = Instance.new("TextButton")
			local UICorner_2 = Instance.new("UICorner")
			local Black = Instance.new("Frame")
			local UICorner_3 = Instance.new("UICorner")

			Button.Name = "Button"
			Button.Parent = MainFramePage
			Button.BackgroundColor3 = Color3.fromRGB(249, 44, 79)
			Button.BackgroundTransparency = 0.75
			Button.Size = UDim2.new(0, 470, 0, 39)

			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = Button

			TextBtn.Name = "TextBtn"
			TextBtn.Parent = Button
			TextBtn.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			TextBtn.Position = UDim2.new(0, 1, 0, 1)
			TextBtn.Size = UDim2.new(0, 468, 0, 37)
			TextBtn.AutoButtonColor = false
			TextBtn.Font = Enum.Font.GothamSemibold
			TextBtn.Text = text
			TextBtn.TextColor3 = Color3.fromRGB(225, 225, 225)
			TextBtn.TextSize = 15.000
			TextBtn.ClipsDescendants = true

			UICorner_2.CornerRadius = UDim.new(0, 5)
			UICorner_2.Parent = TextBtn

			Black.Name = "Black"
			Black.Parent = Button
			Black.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
			Black.BackgroundTransparency = 1.000
			Black.BorderSizePixel = 0
			Black.Position = UDim2.new(0, 1, 0, 1)
			Black.Size = UDim2.new(0, 468, 0, 37)

			UICorner_3.CornerRadius = UDim.new(0, 5)
			UICorner_3.Parent = Black

			TextBtn.MouseEnter:Connect(function()
				TweenService:Create(
					Black,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{BackgroundTransparency = 0.75}
				):Play()
			end)
			TextBtn.MouseLeave:Connect(function()
				TweenService:Create(
					Black,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{BackgroundTransparency = 1}
				):Play()
			end)
			TextBtn.MouseButton1Click:Connect(function()
				CircleAnim(TextBtn, Color3.fromRGB(255,255,255), Color3.fromRGB(255,255,255))
				TextBtn.TextSize = 0
				TweenService:Create(
					TextBtn,
					TweenInfo.new(0.4,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{TextSize = 15}
				):Play()
				callback()
			end)

			---------------------------------------------------------------------------
			TextBtn.MouseEnter:Connect(function()
				TweenService:Create(
					Button,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{BackgroundTransparency = 0}
				):Play()
				TweenService:Create(
					TextBtn,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
				TweenService:Create(
					TextBtn,
					TweenInfo.new(0, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end)
			TextBtn.MouseLeave:Connect(function()
				TweenService:Create(
					Button,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{BackgroundTransparency = 0.75}
				):Play()
				TweenService:Create(
					TextBtn,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
			end)
		end
		function main:Toggle(text,config,Imgidicon,callback)
			local Imgidicon = Imgidicon or 6022668898 or nil == 6022668898
			config = config or false
			local toggled = config
			local Toggle = Instance.new("Frame")
			local UICorner = Instance.new("UICorner")
			local Button = Instance.new("TextButton")
			local UICorner_2 = Instance.new("UICorner")
			local Label = Instance.new("TextLabel")
			local ToggleImage = Instance.new("Frame")
			local UICorner_3 = Instance.new("UICorner")
			local Circle = Instance.new("Frame")
			local UICorner_4 = Instance.new("UICorner")
			local imgLabelIcon = Instance.new("ImageLabel") --http://www.roblox.com/asset/?id=
			local Circle1 = Instance.new("Frame")

			Toggle.Name = "Toggle"
			Toggle.Parent = MainFramePage
			Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Toggle.Size = UDim2.new(0, 470, 0, 42)
			Toggle.BackgroundTransparency = 0.75

			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = Toggle

			Button.Name = "Button"
			Button.Parent = Toggle
			Button.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			Button.Position = UDim2.new(0, 1, 0, 1)
			Button.Size = UDim2.new(0, 468, 0, 40)
			Button.AutoButtonColor = false
			Button.Font = Enum.Font.SourceSans
			Button.Text = ""
			Button.TextColor3 = Color3.fromRGB(0, 0, 0)
			Button.TextSize = 11.000

			UICorner_2.CornerRadius = UDim.new(0, 5)
			UICorner_2.Parent = Button

			Label.Name = "Label"
			Label.Parent = Toggle
			Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Label.BackgroundTransparency = 1.000
			Label.Position = UDim2.new(0, 1, 0, 2.5)
			Label.Size = UDim2.new(0, 468, 0, 37)
			Label.Font = Enum.Font.GothamSemibold
			Label.Text = text
			Label.TextColor3 = Color3.fromRGB(225, 225, 225)
			Label.TextSize = 15.000

			ToggleImage.Name = "ToggleImage"
			ToggleImage.Parent = Toggle
			ToggleImage.BackgroundColor3 = Color3.fromRGB(200, 200, 200)
			ToggleImage.Position = UDim2.new(0, 410, 0, 9)
			ToggleImage.Size = UDim2.new(0, 45, 0, 22.5)

			UICorner_3.CornerRadius = UDim.new(0, 10)
			UICorner_3.Parent = ToggleImage

			Circle.Name = "Circle"
			Circle.Parent = ToggleImage
			Circle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Circle.Position = UDim2.new(0, 3, 0, 2)
			Circle.Size = UDim2.new(0, 18, 0, 18)

			-- 			Circle1.Name = "Circle"
			-- 			Circle1.Parent = Toggle
			-- 			Circle1.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			-- 			Circle1.Position = UDim2.new(0, 10, 0, 9)
			-- 			Circle1.Size = UDim2.new(0, 20, 0, 20)

			imgLabelIcon.Name = "Icon"
			imgLabelIcon.Parent = Toggle
			imgLabelIcon.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			imgLabelIcon.BackgroundTransparency = 1.000
			imgLabelIcon.Position = UDim2.new(0, 10, 0, 9)
			imgLabelIcon.Size = UDim2.new(0, 24, 0, 24)
			imgLabelIcon.Image = "rbxassetid://"..tostring(Imgidicon)

			UICorner_4.CornerRadius = UDim.new(0, 10)
			UICorner_4.Parent = Circle

			Button.MouseButton1Click:Connect(function()
				if toggled == false then
					Circle:TweenPosition(UDim2.new(0,18.5,0,2),"Out","Sine",0.25,true)
					TweenService:Create(
						Toggle,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(249, 44, 79)}
					):Play()
					TweenService:Create(
						Circle,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(249, 44, 79)}
					):Play()
					TweenService:Create(
						Circle,
						TweenInfo.new(0.2,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 26, 0, 18)}
					):Play()
					repeat wait(0.01) until Circle.Size == UDim2.new(0, 26, 0, 18)
					Circle:TweenPosition(UDim2.new(0,25.5,0,2),"Out","Sine",0.1,true)
					TweenService:Create(
						Circle,
						TweenInfo.new(0.1,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 18, 0, 18)}
					):Play()
				else
					Circle:TweenPosition(UDim2.new(0,3,0,2),"Out","Sine",0.25,true)
					TweenService:Create(
						Toggle,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(255, 255, 255)}
					):Play()
					TweenService:Create(
						Circle,
						TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(255, 255, 255)}
					):Play()
					TweenService:Create(
						Circle,
						TweenInfo.new(0.2,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 26, 0, 18)}
					):Play()
					repeat wait(0.01) until Circle.Size == UDim2.new(0, 26, 0, 18)
					TweenService:Create(
						Circle,
						TweenInfo.new(0.1,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Size = UDim2.new(0, 18, 0, 18)}
					):Play()
				end 
				toggled = not toggled
				pcall(callback,toggled)
			end)

			if config == true then
				Circle:TweenPosition(UDim2.new(0,18.5,0,2),"Out","Sine",0.25,true)
				TweenService:Create(
					Toggle,
					TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{BackgroundColor3 = Color3.fromRGB(249, 44, 79)}
				):Play()
				TweenService:Create(
					Circle,
					TweenInfo.new(0.3,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{BackgroundColor3 = Color3.fromRGB(249, 44, 79)}
				):Play()
				TweenService:Create(
					Circle,
					TweenInfo.new(0.2,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{Size = UDim2.new(0, 26, 0, 18)}
				):Play()
				repeat wait(0.01) until Circle.Size == UDim2.new(0, 26, 0, 18)
				Circle:TweenPosition(UDim2.new(0,25.5,0,2),"Out","Sine",0.1,true)
				TweenService:Create(
					Circle,
					TweenInfo.new(0.1,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{Size = UDim2.new(0, 18, 0, 18)}
				):Play()
				toggled = not toggled
				pcall(callback,toggled)
			end
			---------------------------------------------------------------------------
			Button.MouseEnter:Connect(function()
				TweenService:Create(
					Toggle,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{BackgroundTransparency = 0}
				):Play()
				TweenService:Create(
					Toggle,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
				TweenService:Create(
					Toggle,
					TweenInfo.new(0, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end)
			Button.MouseLeave:Connect(function()
				TweenService:Create(
					Toggle,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{BackgroundTransparency = 0.75}
				):Play()
				TweenService:Create(
					Toggle,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
			end)

		end
		function main:Dropdown(text,option,callback)
			local isdropping = false
			local Dropdown = Instance.new("Frame")
			local UICorner = Instance.new("UICorner")
			local DropTitle = Instance.new("TextLabel")
			local DropScroll = Instance.new("ScrollingFrame")
			local UIListLayout = Instance.new("UIListLayout")
			local UIPadding = Instance.new("UIPadding")
			local DropButton = Instance.new("TextButton")
			local DropImage = Instance.new("ImageLabel")

			Dropdown.Name = "Dropdown"
			Dropdown.Parent = MainFramePage
			Dropdown.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			Dropdown.ClipsDescendants = true
			Dropdown.Size = UDim2.new(0, 470, 0, 39)

			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = Dropdown

			DropTitle.Name = "DropTitle"
			DropTitle.Parent = Dropdown
			DropTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			DropTitle.BackgroundTransparency = 1.000
			DropTitle.Size = UDim2.new(0, 470, 0, 37)
			DropTitle.Font = Enum.Font.GothamSemibold
			DropTitle.Text = text.. " : "
			DropTitle.TextColor3 = Color3.fromRGB(225, 225, 225)
			DropTitle.TextSize = 15.000

			DropScroll.Name = "DropScroll"
			DropScroll.Parent = DropTitle
			DropScroll.Active = true
			DropScroll.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			DropScroll.BackgroundTransparency = 1.000
			DropScroll.BorderSizePixel = 0
			DropScroll.Position = UDim2.new(0, 0, 0, 37)
			DropScroll.Size = UDim2.new(0, 470, 0, 100)
			DropScroll.CanvasSize = UDim2.new(0, 0, 0, 0)
			DropScroll.ScrollBarThickness = 3

			UIListLayout.Parent = DropScroll
			UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
			UIListLayout.Padding = UDim.new(0, 5)

			UIPadding.Parent = DropScroll
			UIPadding.PaddingLeft = UDim.new(0, 5)
			UIPadding.PaddingTop = UDim.new(0, 5)

			DropImage.Name = "DropImage"
			DropImage.Parent = Dropdown
			DropImage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			DropImage.BackgroundTransparency = 1.000
			DropImage.Position = UDim2.new(0, 430, 0, 5.25)
			DropImage.Rotation = 360.000
			DropImage.Size = UDim2.new(0, 30, 0, 30)
			DropImage.Image = "rbxassetid://4370337241"

			DropButton.Name = "DropButton"
			DropButton.Parent = Dropdown
			DropButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			DropButton.BackgroundTransparency = 1.000
			DropButton.Size = UDim2.new(0, 470, 0, 37)
			DropButton.Font = Enum.Font.SourceSans
			DropButton.Text = ""
			DropButton.TextColor3 = Color3.fromRGB(0, 0, 0)
			DropButton.TextSize = 14.000

			for i,v in next,option do
				local Item = Instance.new("TextButton")

				Item.Name = "Item"
				Item.Parent = DropScroll
				Item.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Item.BackgroundTransparency = 1.000
				Item.Size = UDim2.new(0, 460, 0, 26)
				Item.Font = Enum.Font.GothamSemibold
				Item.Text = tostring(v)
				Item.TextColor3 = Color3.fromRGB(225, 225, 225)
				Item.TextSize = 13.000
				Item.TextTransparency = 0.500

				Item.MouseEnter:Connect(function()
					TweenService:Create(
						Item,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end)

				Item.MouseLeave:Connect(function()
					TweenService:Create(
						Item,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0.5}
					):Play()
				end)

				Item.MouseButton1Click:Connect(function()
					isdropping = false
					Dropdown:TweenSize(UDim2.new(0,470,0,37),"Out","Quad",0.5,true)
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Rotation = 360}
					):Play()
					callback(Item.Text)
					DropTitle.Text = text.." : "..Item.Text
				end)
			end

			DropScroll.CanvasSize = UDim2.new(0,0,0,UIListLayout.AbsoluteContentSize.Y + 10)

			DropButton.MouseButton1Click:Connect(function()
				if isdropping == false then
					isdropping = true
					Dropdown:TweenSize(UDim2.new(0,470,0,131),"Out","Quad",0.5,true)
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Rotation = 540}
					):Play()
				else
					isdropping = false
					Dropdown:TweenSize(UDim2.new(0,470,0,37),"Out","Quad",0.5,true)
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Rotation = 360}
					):Play()
				end
			end)

			local dropfunc = {}
			function dropfunc:Add(t)
				local Item = Instance.new("TextButton")
				Item.Name = "Item"
				Item.Parent = DropScroll
				Item.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Item.BackgroundTransparency = 1.000
				Item.Size = UDim2.new(0, 470, 0, 26)
				Item.Font = Enum.Font.GothamSemibold
				Item.Text = tostring(t)
				Item.TextColor3 = Color3.fromRGB(225, 225, 225)
				Item.TextSize = 13.000
				Item.TextTransparency = 0.500

				Item.MouseEnter:Connect(function()
					TweenService:Create(
						Item,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0}
					):Play()
				end)

				Item.MouseLeave:Connect(function()
					TweenService:Create(
						Item,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{TextTransparency = 0.5}
					):Play()
				end)

				Item.MouseButton1Click:Connect(function()
					isdropping = false
					Dropdown:TweenSize(UDim2.new(0,470,0,37),"Out","Quad",0.5,true)
					TweenService:Create(
						DropImage,
						TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
						{Rotation = 360}
					):Play()
					callback(Item.Text)
					DropTitle.Text = text.." : "..Item.Text
				end)
			end
			function dropfunc:Clear()
				DropTitle.Text = tostring(text).." : "
				isdropping = false
				Dropdown:TweenSize(UDim2.new(0,470,0,37),"Out","Quad",0.5,true)
				TweenService:Create(
					DropImage,
					TweenInfo.new(0.5,Enum.EasingStyle.Quad,Enum.EasingDirection.Out),
					{Rotation = 360}
				):Play()
				for i,v in next, DropScroll:GetChildren() do
					if v:IsA("TextButton") then
						v:Destroy()
					end
				end
			end
			return dropfunc
		end

		function main:Slider(text,min,max,set,callback)
			local Slider = Instance.new("Frame")
			local slidercorner = Instance.new("UICorner")
			local sliderr = Instance.new("Frame")
			local sliderrcorner = Instance.new("UICorner")
			local SliderLabel = Instance.new("TextLabel")
			local HAHA = Instance.new("Frame")
			local AHEHE = Instance.new("TextButton")
			local bar = Instance.new("Frame")
			local bar1 = Instance.new("Frame")
			local bar1corner = Instance.new("UICorner")
			local barcorner = Instance.new("UICorner")
			local circlebar = Instance.new("Frame")
			local UICorner = Instance.new("UICorner")
			local slidervalue = Instance.new("Frame")
			local valuecorner = Instance.new("UICorner")
			local TextBox = Instance.new("TextBox")
			local UICorner_2 = Instance.new("UICorner")

			Slider.Name = "Slider"
			Slider.Parent = MainFramePage
			Slider.BackgroundColor3 = Color3.fromRGB(249, 44, 79)
			Slider.BackgroundTransparency = 0.75
			Slider.Size = UDim2.new(0, 470, 0, 72)

			slidercorner.CornerRadius = UDim.new(0, 5)
			slidercorner.Name = "slidercorner"
			slidercorner.Parent = Slider

			sliderr.Name = "sliderr"
			sliderr.Parent = Slider
			sliderr.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			sliderr.Position = UDim2.new(0, 1, 0, 1)
			sliderr.Size = UDim2.new(0, 468, 0, 70)

			sliderrcorner.CornerRadius = UDim.new(0, 5)
			sliderrcorner.Name = "sliderrcorner"
			sliderrcorner.Parent = sliderr

			SliderLabel.Name = "SliderLabel"
			SliderLabel.Parent = sliderr
			SliderLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			SliderLabel.BackgroundTransparency = 1.000
			SliderLabel.Position = UDim2.new(0, 15, 0, 3)
			SliderLabel.Size = UDim2.new(0, 360, 0, 26)
			SliderLabel.Font = Enum.Font.GothamSemibold
			SliderLabel.Text = text
			SliderLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
			SliderLabel.TextSize = 16.000
			SliderLabel.TextTransparency = 0
			SliderLabel.TextXAlignment = Enum.TextXAlignment.Left

			HAHA.Name = "HAHA"
			HAHA.Parent = sliderr
			HAHA.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			HAHA.BackgroundTransparency = 1.000
			HAHA.Size = UDim2.new(0, 468, 0, 29)

			AHEHE.Name = "AHEHE"
			AHEHE.Parent = sliderr
			AHEHE.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			AHEHE.BackgroundTransparency = 1.000
			AHEHE.Position = UDim2.new(0, 10, 0, 50)
			AHEHE.Size = UDim2.new(0, 448, 0, 5)
			AHEHE.Font = Enum.Font.SourceSans
			AHEHE.Text = ""
			AHEHE.TextColor3 = Color3.fromRGB(0, 0, 0)
			AHEHE.TextSize = 14.000

			bar.Name = "bar"
			bar.Parent = AHEHE
			bar.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
			bar.Size = UDim2.new(0, 448, 0, 5)

			bar1.Name = "bar1"
			bar1.Parent = bar
			bar1.BackgroundColor3 = Color3.fromRGB(249, 44, 79)
			bar1.BackgroundTransparency = 0.75
			bar1.Size = UDim2.new(set/max, 0, 0, 5)

			bar1corner.CornerRadius = UDim.new(0, 5)
			bar1corner.Name = "bar1corner"
			bar1corner.Parent = bar1

			barcorner.CornerRadius = UDim.new(0, 5)
			barcorner.Name = "barcorner"
			barcorner.Parent = bar

			circlebar.Name = "circlebar"
			circlebar.Parent = bar1
			circlebar.BackgroundColor3 = Color3.fromRGB(225, 225, 225)
			circlebar.Position = UDim2.new(1, -2, 0, -3)
			circlebar.Size = UDim2.new(0, 10, 0, 10)

			UICorner.CornerRadius = UDim.new(0, 100)
			UICorner.Parent = circlebar

			slidervalue.Name = "slidervalue"
			slidervalue.Parent = sliderr
			slidervalue.BackgroundColor3 = Color3.fromRGB(249, 44, 79)
			slidervalue.BackgroundTransparency = 0.75
			slidervalue.Position = UDim2.new(0, 395, 0, 7)
			slidervalue.Size = UDim2.new(0, 65, 0, 22)

			valuecorner.CornerRadius = UDim.new(0, 5)
			valuecorner.Name = "valuecorner"
			valuecorner.Parent = slidervalue

			TextBox.Parent = slidervalue
			TextBox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
			TextBox.Position = UDim2.new(0, 1, 0, 1)
			TextBox.Size = UDim2.new(0, 63, 0, 20)
			TextBox.Font = Enum.Font.GothamSemibold
			TextBox.TextColor3 = Color3.fromRGB(225, 225, 225)
			TextBox.TextSize = 9.000
			TextBox.Text = set
			TextBox.TextTransparency = 0

			UICorner_2.CornerRadius = UDim.new(0, 5)
			UICorner_2.Parent = TextBox

			local mouse = game.Players.LocalPlayer:GetMouse()
			local uis = game:GetService("UserInputService")

			if Value == nil then
				Value = set
				pcall(function()
					callback(Value)
				end)
			end

			AHEHE.MouseButton1Down:Connect(function()
				Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min)) or 0
				pcall(function()
					callback(Value)
				end)
				bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
				circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
				moveconnection = mouse.Move:Connect(function()
					TextBox.Text = Value
					Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min))
					pcall(function()
						callback(Value)
					end)
					bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
					circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
				end)
				releaseconnection = uis.InputEnded:Connect(function(Mouse)
					if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
						Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min))
						pcall(function()
							callback(Value)
						end)
						bar1.Size = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X, 0, 448), 0, 5)
						circlebar.Position = UDim2.new(0, math.clamp(mouse.X - bar1.AbsolutePosition.X - 2, 0, 438), 0, -3)
						moveconnection:Disconnect()
						releaseconnection:Disconnect()
					end
				end)
			end)
			releaseconnection = uis.InputEnded:Connect(function(Mouse)
				if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
					Value = math.floor((((tonumber(max) - tonumber(min)) / 448) * bar1.AbsoluteSize.X) + tonumber(min))
					TextBox.Text = Value
				end
			end)

			TextBox.FocusLost:Connect(function()
				if tonumber(TextBox.Text) > max then
					TextBox.Text  = max
				end
				bar1.Size = UDim2.new((TextBox.Text or 0) / max, 0, 0, 5)
				circlebar.Position = UDim2.new(1, -2, 0, -3)
				TextBox.Text = tostring(TextBox.Text and math.floor( (TextBox.Text / max) * (max - min) + min) )
				pcall(callback, TextBox.Text)
			end)

			---------------------------------------------------------------------------
			sliderr.MouseEnter:Connect(function()
				TweenService:Create(
					Slider,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{BackgroundTransparency = 0}
				):Play()
				TweenService:Create(
					Slider,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
				TweenService:Create(
					Slider,
					TweenInfo.new(0, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end)
			sliderr.MouseLeave:Connect(function()
				TweenService:Create(
					Slider,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{BackgroundTransparency = 0.75}
				):Play()
				TweenService:Create(
					Slider,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
			end)

			---------------------------------------------------------------------------

			sliderr.MouseEnter:Connect(function()
				TweenService:Create(
					slidervalue,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{BackgroundTransparency = 0}
				):Play()
				TweenService:Create(
					slidervalue,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
				TweenService:Create(
					slidervalue,
					TweenInfo.new(0, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end)
			sliderr.MouseLeave:Connect(function()
				TweenService:Create(
					slidervalue,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{BackgroundTransparency = 0.75}
				):Play()
				TweenService:Create(
					slidervalue,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
			end)

			---------------------------------------------------------------------------

			sliderr.MouseEnter:Connect(function()
				TweenService:Create(
					bar1,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{BackgroundTransparency = 0}
				):Play()
				TweenService:Create(
					bar1,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
				TweenService:Create(
					bar1,
					TweenInfo.new(0, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextTransparency = 0}
				):Play()
			end)
			sliderr.MouseLeave:Connect(function()
				TweenService:Create(
					bar1,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{BackgroundTransparency = 0.75}
				):Play()
				TweenService:Create(
					bar1,
					TweenInfo.new(0.2, Enum.EasingStyle.Linear, Enum.EasingDirection.Out),
					{TextColor3 = Color3.fromRGB(225, 225, 225)}
				):Play()
			end)

		end

		function main:Textbox(text,disappear,callback)
			local Textbox = Instance.new("Frame")
			local TextboxCorner = Instance.new("UICorner")
			local Textboxx = Instance.new("Frame")
			local TextboxxCorner = Instance.new("UICorner")
			local TextboxLabel = Instance.new("TextLabel")
			local txtbtn = Instance.new("TextButton")
			local RealTextbox = Instance.new("TextBox")
			local UICorner = Instance.new("UICorner")

			Textbox.Name = "Textbox"
			Textbox.Parent = MainFramePage
			Textbox.BackgroundColor3 = Color3.fromRGB(249, 44, 79)
			Textbox.BackgroundTransparency = 0
			Textbox.Size = UDim2.new(0, 470, 0, 39)

			TextboxCorner.CornerRadius = UDim.new(0, 5)
			TextboxCorner.Name = "TextboxCorner"
			TextboxCorner.Parent = Textbox

			Textboxx.Name = "Textboxx"
			Textboxx.Parent = Textbox
			Textboxx.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
			Textboxx.Position = UDim2.new(0, 1, 0, 1)
			Textboxx.Size = UDim2.new(0, 468, 0, 37)

			TextboxxCorner.CornerRadius = UDim.new(0, 5)
			TextboxxCorner.Name = "TextboxxCorner"
			TextboxxCorner.Parent = Textboxx

			TextboxLabel.Name = "TextboxLabel"
			TextboxLabel.Parent = Textbox
			TextboxLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			TextboxLabel.BackgroundTransparency = 1.000
			TextboxLabel.Position = UDim2.new(0, 15, 0, 3)
			TextboxLabel.Text = text
			TextboxLabel.Size = UDim2.new(0, 145, 0, 31)
			TextboxLabel.Font = Enum.Font.GothamSemibold
			TextboxLabel.TextColor3 = Color3.fromRGB(225, 225, 225)
			TextboxLabel.TextSize = 16.000
			TextboxLabel.TextTransparency = 0
			TextboxLabel.TextXAlignment = Enum.TextXAlignment.Left

			txtbtn.Name = "txtbtn"
			txtbtn.Parent = Textbox
			txtbtn.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			txtbtn.BackgroundTransparency = 1.000
			txtbtn.Position = UDim2.new(0, 1, 0, 1)
			txtbtn.Size = UDim2.new(0, 468, 0, 29)
			txtbtn.Font = Enum.Font.SourceSans
			txtbtn.Text = ""
			txtbtn.TextColor3 = Color3.fromRGB(0, 0, 0)
			txtbtn.TextSize = 14.000

			RealTextbox.Name = "RealTextbox"
			RealTextbox.Parent = Textbox
			RealTextbox.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
			RealTextbox.BackgroundTransparency = 0
			RealTextbox.Position = UDim2.new(0, 360, 0, 7)
			RealTextbox.Size = UDim2.new(0, 100, 0, 24)
			RealTextbox.Font = Enum.Font.GothamSemibold
			RealTextbox.Text = ""
			RealTextbox.TextColor3 = Color3.fromRGB(225, 225, 225)
			RealTextbox.TextSize = 11.000
			RealTextbox.TextTransparency = 0

			RealTextbox.FocusLost:Connect(function()
				callback(RealTextbox.Text)
				if disappear then
					RealTextbox.Text = ""
				end
			end)

			UICorner.CornerRadius = UDim.new(0, 5)
			UICorner.Parent = RealTextbox
		end
		function main:Label(text)
			local Label = Instance.new("TextLabel")
			local PaddingLabel = Instance.new("UIPadding")
			local labell = {}

			Label.Name = "Label"
			Label.Parent = MainFramePage
			Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Label.BackgroundTransparency = 1.000
			Label.Size = UDim2.new(0, 470, 0, 20)
			Label.Font = Enum.Font.GothamSemibold
			Label.TextColor3 = Color3.fromRGB(225, 225, 225)
			Label.TextSize = 16.000
			Label.Text = text
			Label.TextXAlignment = Enum.TextXAlignment.Left

			PaddingLabel.PaddingLeft = UDim.new(0,15)
			PaddingLabel.Parent = Label
			PaddingLabel.Name = "PaddingLabel"

			function labell:Set(newtext)
				Label.Text = newtext
			end

			return labell
		end
		function main:Seperator(text)
			local Seperator = Instance.new("Frame")
			local Sep1 = Instance.new("Frame")
			local Sep2 = Instance.new("TextLabel")
			local Sep3 = Instance.new("Frame")

			Seperator.Name = "Seperator"
			Seperator.Parent = MainFramePage
			Seperator.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Seperator.BackgroundTransparency = 1.000
			Seperator.Size = UDim2.new(0, 470, 0, 20)

			Sep1.Name = "Sep1"
			Sep1.Parent = Seperator
			Sep1.BackgroundColor3 = Color3.fromRGB(249, 44, 79)
			Sep1.BorderSizePixel = 0
			Sep1.Position = UDim2.new(0, 0, 0, 10)
			Sep1.Size = UDim2.new(0, 80, 0, 1)

			Sep2.Name = "Sep2"
			Sep2.Parent = Seperator
			Sep2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Sep2.BackgroundTransparency = 1.000
			Sep2.Position = UDim2.new(0, 185, 0, 0)
			Sep2.Size = UDim2.new(0, 100, 0, 20)
			Sep2.Font = Enum.Font.GothamSemibold
			Sep2.Text = text
			Sep2.TextColor3 = Color3.fromRGB(255, 255, 255)
			Sep2.TextSize = 14.000

			Sep3.Name = "Sep3"
			Sep3.Parent = Seperator
			Sep3.BackgroundColor3 = Color3.fromRGB(249, 44, 79)
			Sep3.BorderSizePixel = 0
			Sep3.Position = UDim2.new(0, 390, 0, 10)
			Sep3.Size = UDim2.new(0, 80, 0, 1)
		end

		function main:Line()
			local LineFrame = Instance.new("Frame")
			local Line = Instance.new("Frame")
			local UIGradient = Instance.new("UIGradient")

			LineFrame.Name = "LineFrame"
			LineFrame.Parent = MainFramePage
			LineFrame.AnchorPoint = Vector2.new(0.5, 0.5)
			LineFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			LineFrame.BackgroundTransparency = 1.000
			LineFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
			LineFrame.Size = UDim2.new(0, 470, 0, 20)

			Line.Name = "Line"
			Line.Parent = LineFrame
			Line.Active = true
			Line.AnchorPoint = Vector2.new(0.5, 0.5)
			Line.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Line.BorderSizePixel = 0
			Line.Position = UDim2.new(0.5, 0, 0.5, 0)
			Line.Size = UDim2.new(0, 470, 0, 2)

			UIGradient.Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, Color3.fromRGB(35, 35, 35)), ColorSequenceKeypoint.new(0.17, Color3.fromRGB(51, 35, 36)), ColorSequenceKeypoint.new(0.51, Color3.fromRGB(255, 46, 56)), ColorSequenceKeypoint.new(0.78, Color3.fromRGB(100, 38, 41)), ColorSequenceKeypoint.new(1.00, Color3.fromRGB(35, 35, 35))}
			UIGradient.Parent = Line
		end
		return main
	end
	return uitab
end

local win = library:Window(" Rocket","",Enum.KeyCode.RightControl)

local AutoFarmTab = win:Tab("Kaitun Mode",nil)

AutoFarmTab:Line()

AutoFarmTab:Label("                                 One Click Kaitun")

AutoFarmTab:Line()

AutoFarmTab:Toggle("Start Kaitun",true,nil,function(a)
    _G.Script_Mode = a
    _G.FastAttack1 = a
end)

spawn(function()
	if _G.FastAttack1 then
local SuperFastMode = true

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
    local AC = CbFw2.activeController
    for i = 1, 1 do 
        local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
            plr.Character,
            {plr.Character.HumanoidRootPart},
            60
        )
        local cac = {}
        local hash = {}
        for k, v in pairs(bladehit) do
            if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                table.insert(cac, v.Parent.HumanoidRootPart)
                hash[v.Parent] = true
            end
        end
        bladehit = cac
        if #bladehit > 0 then
            local u8 = debug.getupvalue(AC.attack, 5)
            local u9 = debug.getupvalue(AC.attack, 6)
            local u7 = debug.getupvalue(AC.attack, 4)
            local u10 = debug.getupvalue(AC.attack, 7)
            local u12 = (u8 * 798405 + u7 * 727595) % u9
            local u13 = u7 * 798405
            (function()
                u12 = (u12 * u9 + u13) % 1099511627776
                u8 = math.floor(u12 / u9)
                u7 = u12 - u8 * u9
            end)()
            u10 = u10 + 1
            debug.setupvalue(AC.attack, 5, u8)
            debug.setupvalue(AC.attack, 6, u9)
            debug.setupvalue(AC.attack, 4, u7)
            debug.setupvalue(AC.attack, 7, u10)
            pcall(function()
                for k, v in pairs(AC.animator.anims.basic) do
                    v:Play()
                end                  
            end)
            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
            end
        end
    end
end
local cac
if SuperFastMode then 
	cac=task.wait
else
	cac=wait
end
while cac() do 
	AttackNoCD()
end

end

end)


AutoFarmTab:Button("Redeem All Code",function(a)
    _G.RDAC = a
end)

spawn(function()
if _G.RDAC == true then
	function UseCode(Text)
                     game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
                end
                UseCode("UPD16")
                UseCode("2BILLION")
                UseCode("UPD15")
                UseCode("FUDD10")
                UseCode("BIGNEWS")
                UseCode("THEGREATACE")
                UseCode("SUB2GAMERROBOT_EXP1")
                UseCode("StrawHatMaine")
                UseCode("Sub2OfficialNoobie")
                UseCode("SUB2NOOBMASTER123")
                UseCode("Sub2Daigrock")
                UseCode("Axiore")
                UseCode("TantaiGaming")
                UseCode("STRAWHATMAINE")
end
end)

				Wapon = {}
				for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
					if v:IsA("Tool") then
						table.insert(Wapon ,v.Name)
					end
				end
				for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
					if v:IsA("Tool") then
						table.insert(Wapon, v.Name)
					end
				end
				
				local SlcWP = AutoFarmTab:Dropdown("Select Weapon",Wapon,function(t)
				_G.SelectToolWeapon = t
				end)

				AutoFarmTab:Button("Refresh Weapon",function()
				 SlcWP:Clear()
					wait()
					for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
						if v:IsA("Tool") then
							SlcWP:Add(v.Name)
						end
					end
				end)

AutoFarmTab:Line()
end
end)

spawn(function()
	if _G.Script_Mode == "kaitun" then
	    _G.Team = "Marine" -- Marine Pirate
        _G.FpsBoost = true
        _G.AutoSetSpawn = true
        _G.FastAttack = true
        
_G.FastAttack1 = true
        _G.SelectToolWeapon = "Combat"
        _G.Kaitanstat =  true
        ps = true

    SelectFruitSinper = "Dark" -- ชื่อ Fruits : Name Fruits
        _G.BuyFruitSinPer = true
        _G.BRINGSFRUITS = true
        _G.Autorandomfruits = true

    if game.PlaceId == 2753915549 then -- Sea 1
        _G.AutoFarm = true 
        _G.AutoNew_Ws = true -- Auto New World
        _G.AutoSaber = true
        _G.AutoSuperhuman = true
        _G.BuyKaitun = true
        AutoEquip = true
    elseif game.PlaceId == 4442272183 then -- Sea 2
        _G.AutoFarm = true 
        _G.AutoLegendarySword = true
        _G.AutoThirdSea = true
        _G.AutoQuestBartilo = true
        _G.BuyKaitun = false
        _G.AutoNew_Ws = false -- Auto New World
        AutoEquip = true
    elseif game.PlaceId == 7449423635 then -- Sea 3
        _G.AutoFarm = true 
        _G.AutoThirdSea = false
        _G.AutoNew_Ws = false
        _G.AutoBuddySword = true
        _G.AutoKatakuri = true
        _G.AutoEliteHunter = true
        AutoEquip = true
    elseif _G.Masterymode then -- Mastery Mode
        _G.AutoFarm = false 
        _G.AutoFarmMasteryFruit = true
        _G.KillAt = 20
        _G.AutoCakePrince = false
        _G.AutoBuddySword = false
        _G.AutoKatakuri = false
        _G.AutoEliteHunter = false
     elseif _G.Raidmode then  -- Raid Mode
        _G.SelectChip = "fruits"-- "Flame","Ice","Quake","Light","Dark","String","Rumble","Magma","Human: Buddha","Sand","Bird-Bird: Phoenix"
        _G.AutoBuyChip = true
        _G.AutoStartRaid = true
        _G.AutoRaids = true
        ps = true
        _G.AutoCakePrince = false
        _G.AutoBuddySword = false
        _G.AutoKatakuri = false
        _G.AutoEliteHunter = false
     end
end
end)
