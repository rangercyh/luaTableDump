Description
=====
using pure lua to print lua table. not support for nested loop table.
Using
=====
``` lua
local tableDump = require "printTable"
--[[string or number test]]
local num = 1
local str = "asdf"
local _nil = nil
print(tableDump(num))
print(tableDump(str))
print(_nil)

--[[table test]]
function tt() end
local t1 = {}
local t2 = {1,2,3}
local t3 = {"asdf","cccc"}
local t4 = {123,23,"sdf",}
local t5 = {[123]=1,["123"]=3,["asdf"]=nil,["aa"]="asdf"}
local t6 = {t1,t2}
local t7 = {["asdf"]=t6,[t3]=t4}
local t8 = {[tt]=tt,[t1]=t2}
print(tableDump(t1))
print(tableDump(t2))
print(tableDump(t3))
print(tableDump(t4))
print(tableDump(t5))
print(tableDump(t6))
print(tableDump(t7))
print(tableDump(t8))
```

if the table has some nested table in it. you can pass 'true' to the second args to let it fold the nested table.
``` lua
--[[nested table test]]
local t9 = {
    [t1] = t1,
    [t2] = {
        [t2] = t2,
        [t3] = t2,
    },
}
t9[3] = t9
print(tableDump(t9, true))
```
Licence
=====

[WTFPL](http://en.wikipedia.org/wiki/WTFPL) 
