-- Variables

local code = require(game.ReplicatedStorage.DataSource.EnumType).clientRemoteEvent.DamageMonster

local unit = (function()

    for i,v in pairs(workspace.PlaceHero:GetChildren()) do

        if v.Name:find(game.Players.LocalPlayer.Name) and not v.Name:find("Doctor") then

            return v.Name

        end

    end

end)()

 

-- Yes

while true do

    for i,v in pairs(workspace.Monsters:GetChildren()) do

        game.ReplicatedStorage.RemoteEvent["RemoteEvent_Notice"]:FireServer(code, {unit,{v}})

    end

    wait()

end
