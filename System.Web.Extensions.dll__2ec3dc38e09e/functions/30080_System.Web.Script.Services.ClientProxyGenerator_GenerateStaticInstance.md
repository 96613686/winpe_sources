# System.Web.Script.Services.ClientProxyGenerator::GenerateStaticInstance

- ea: `0x30080`
- end: `0x306d3`
- name: `System.Web.Script.Services.ClientProxyGenerator::GenerateStaticInstance`
- size: `1619`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2fcc0`

## callees

- `0x30050`
- `0x30060`
- `0x30070`
- `0x30080`
- `0x30ca0`
- `0x31cb0`

## string_xrefs

- `0x300c6`: `.set_path = function(value) {\n`
- `0x300dd`: `._staticInstance.set_path(value); }\n`
- `0x30366`: `._staticInstance.set_path(value); }\n`
- `0x300f4`: `.get_path = function() { \n/// <value type="String" mayBeNull="true">The service url.</value>\nreturn `
- `0x3010b`: `._staticInstance.get_path();}\n`
- `0x30150`: `.get_timeout = function() { \n/// <value type="Number">The service timeout.</value>\nreturn `
- `0x301ac`: `.get_defaultUserContext = function() { \n/// <value mayBeNull="true">The service default user context.</value>\nreturn `
- `0x30208`: `.get_defaultSucceededCallback = function() { \n/// <value type="Function" mayBeNull="true">The service default succeeded callback.</value>\nreturn `
- `0x30264`: `.get_defaultFailedCallback = function() { \n/// <value type="Function" mayBeNull="true">The service default failed callback.</value>\nreturn `
- `0x30292`: `.set_enableJsonp = function(value) { `
- `0x3051b`: `.set_enableJsonp = function(value) { `
- `0x302a9`: `._staticInstance.set_enableJsonp(value); }\n`
- `0x30532`: `._staticInstance.set_enableJsonp(value); }\n`
- `0x302c0`: `.get_enableJsonp = function() { \n/// <value type="Boolean">Specifies whether the service supports JSONP for cross domain calling.</value>\nreturn `
- `0x302d7`: `._staticInstance.get_enableJsonp(); }\n`
- `0x30560`: `._staticInstance.get_enableJsonp(); }\n`
- `0x302ee`: `.set_jsonpCallbackParameter = function(value) { `
- `0x30577`: `.set_jsonpCallbackParameter = function(value) { `
- `0x30305`: `._staticInstance.set_jsonpCallbackParameter(value); }\n`
- `0x3058e`: `._staticInstance.set_jsonpCallbackParameter(value); }\n`
- `0x3031c`: `.get_jsonpCallbackParameter = function() { \n/// <value type="String">Specifies the parameter name that contains the callback function name for a JSONP request.</value>\nreturn `
- `0x30333`: `._staticInstance.get_jsonpCallbackParameter(); }\n`
- `0x305bc`: `._staticInstance.get_jsonpCallbackParameter(); }\n`
- `0x3034f`: `.set_path = function(value) { `
- `0x3037d`: `.get_path = function() { return `
- `0x30394`: `._staticInstance.get_path(); }\n`
- `0x30549`: `.get_enableJsonp = function() { return `
- `0x305a5`: `.get_jsonpCallbackParameter = function() { return `
- `0x3064b`: `.set_path("`
- `0x3067a`: `.set_enableJsonp(true);\n`
- `0x306b1`: `.set_jsonpCallbackParameter(`

## pseudocode

```c

```

## disassembly

```asm
0x30080  ldarg.0
0x30081  ldarg.1
0x30082  callvirt instance string System.Web.Script.Services.ClientProxyGenerator::GetProxyTypeName(class System.Web.Script.Services.WebServiceData data)
0x30087  stloc.0
0x30088  ldarg.0
0x30089  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x3008e  ldloc.0
0x3008f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30094  ldstr    aStaticinstance_1// "._staticInstance = new "
0x30099  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3009e  ldloc.0
0x3009f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x300a4  ldstr    asc_4B004// "();\r\n"
0x300a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x300ae  pop
0x300af  ldarg.0
0x300b0  ldfld    bool System.Web.Script.Services.ClientProxyGenerator::_debugMode
0x300b5  brfalse  loc_30343
0x300ba  ldarg.0
0x300bb  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x300c0  ldloc.0
0x300c1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x300c6  ldstr    aSetPathFunctio// ".set_path = function(value) {\r\n"
0x300cb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x300d0  pop
0x300d1  ldarg.0
0x300d2  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x300d7  ldloc.0
0x300d8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x300dd  ldstr    aStaticinstance_2// "._staticInstance.set_path(value); }\r\n"
0x300e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x300e7  pop
0x300e8  ldarg.0
0x300e9  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x300ee  ldloc.0
0x300ef  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x300f4  ldstr    aGetPathFunctio_0// ".get_path = function() { \r\n/// <value"...
0x300f9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x300fe  pop
0x300ff  ldarg.0
0x30100  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30105  ldloc.0
0x30106  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3010b  ldstr    aStaticinstance_3// "._staticInstance.get_path();}\r\n"
0x30110  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30115  pop
0x30116  ldarg.0
0x30117  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x3011c  ldloc.0
0x3011d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30122  ldstr    aSetTimeoutFunc// ".set_timeout = function(value) {\r\n"
0x30127  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3012c  pop
0x3012d  ldarg.0
0x3012e  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30133  ldloc.0
0x30134  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30139  ldstr    aStaticinstance_4// "._staticInstance.set_timeout(value); }"...
0x3013e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30143  pop
0x30144  ldarg.0
0x30145  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x3014a  ldloc.0
0x3014b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30150  ldstr    aGetTimeoutFunc// ".get_timeout = function() { \r\n/// <va"...
0x30155  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3015a  pop
0x3015b  ldarg.0
0x3015c  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30161  ldloc.0
0x30162  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30167  ldstr    aStaticinstance_5// "._staticInstance.get_timeout(); }\r\n"
0x3016c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30171  pop
0x30172  ldarg.0
0x30173  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30178  ldloc.0
0x30179  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3017e  ldstr    aSetDefaultuser// ".set_defaultUserContext = function(valu"...
0x30183  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30188  pop
0x30189  ldarg.0
0x3018a  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x3018f  ldloc.0
0x30190  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30195  ldstr    aStaticinstance_6// "._staticInstance.set_defaultUserContext"...
0x3019a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3019f  pop
0x301a0  ldarg.0
0x301a1  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x301a6  ldloc.0
0x301a7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x301ac  ldstr    aGetDefaultuser// ".get_defaultUserContext = function() { "...
0x301b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x301b6  pop
0x301b7  ldarg.0
0x301b8  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x301bd  ldloc.0
0x301be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x301c3  ldstr    aStaticinstance_7// "._staticInstance.get_defaultUserContext"...
0x301c8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x301cd  pop
0x301ce  ldarg.0
0x301cf  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x301d4  ldloc.0
0x301d5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x301da  ldstr    aSetDefaultsucc// ".set_defaultSucceededCallback = functio"...
0x301df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x301e4  pop
0x301e5  ldarg.0
0x301e6  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x301eb  ldloc.0
0x301ec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x301f1  ldstr    aStaticinstance_8// "._staticInstance.set_defaultSucceededCa"...
0x301f6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x301fb  pop
0x301fc  ldarg.0
0x301fd  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30202  ldloc.0
0x30203  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30208  ldstr    aGetDefaultsucc// ".get_defaultSucceededCallback = functio"...
0x3020d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30212  pop
0x30213  ldarg.0
0x30214  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30219  ldloc.0
0x3021a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3021f  ldstr    aStaticinstance_9// "._staticInstance.get_defaultSucceededCa"...
0x30224  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30229  pop
0x3022a  ldarg.0
0x3022b  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30230  ldloc.0
0x30231  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30236  ldstr    aSetDefaultfail// ".set_defaultFailedCallback = function(v"...
0x3023b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30240  pop
0x30241  ldarg.0
0x30242  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30247  ldloc.0
0x30248  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3024d  ldstr    aStaticinstance_10// "._staticInstance.set_defaultFailedCallb"...
0x30252  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30257  pop
0x30258  ldarg.0
0x30259  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x3025e  ldloc.0
0x3025f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30264  ldstr    aGetDefaultfail// ".get_defaultFailedCallback = function()"...
0x30269  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3026e  pop
0x3026f  ldarg.0
0x30270  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30275  ldloc.0
0x30276  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3027b  ldstr    aStaticinstance_11// "._staticInstance.get_defaultFailedCallb"...
0x30280  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30285  pop
0x30286  ldarg.0
0x30287  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x3028c  ldloc.0
0x3028d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30292  ldstr    aSetEnablejsonp// ".set_enableJsonp = function(value) { "
0x30297  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3029c  pop
0x3029d  ldarg.0
0x3029e  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x302a3  ldloc.0
0x302a4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x302a9  ldstr    aStaticinstance_12// "._staticInstance.set_enableJsonp(value)"...
0x302ae  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x302b3  pop
0x302b4  ldarg.0
0x302b5  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x302ba  ldloc.0
0x302bb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x302c0  ldstr    aGetEnablejsonp// ".get_enableJsonp = function() { \r\n///"...
0x302c5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x302ca  pop
0x302cb  ldarg.0
0x302cc  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x302d1  ldloc.0
0x302d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x302d7  ldstr    aStaticinstance_13// "._staticInstance.get_enableJsonp(); }\r"...
0x302dc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x302e1  pop
0x302e2  ldarg.0
0x302e3  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x302e8  ldloc.0
0x302e9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x302ee  ldstr    aSetJsonpcallba// ".set_jsonpCallbackParameter = function("...
0x302f3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x302f8  pop
0x302f9  ldarg.0
0x302fa  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x302ff  ldloc.0
0x30300  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30305  ldstr    aStaticinstance_14// "._staticInstance.set_jsonpCallbackParam"...
0x3030a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3030f  pop
0x30310  ldarg.0
0x30311  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30316  ldloc.0
0x30317  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3031c  ldstr    aGetJsonpcallba// ".get_jsonpCallbackParameter = function("...
0x30321  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30326  pop
0x30327  ldarg.0
0x30328  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x3032d  ldloc.0
0x3032e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30333  ldstr    aStaticinstance_15// "._staticInstance.get_jsonpCallbackParam"...
0x30338  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3033d  pop
0x3033e  br       loc_305C7
0x30343  ldarg.0
0x30344  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30349  ldloc.0
0x3034a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3034f  ldstr    aSetPathFunctio_0// ".set_path = function(value) { "
0x30354  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30359  pop
0x3035a  ldarg.0
0x3035b  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30360  ldloc.0
0x30361  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30366  ldstr    aStaticinstance_2// "._staticInstance.set_path(value); }\r\n"
0x3036b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30370  pop
0x30371  ldarg.0
0x30372  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30377  ldloc.0
0x30378  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3037d  ldstr    aGetPathFunctio_1// ".get_path = function() { return "
0x30382  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30387  pop
0x30388  ldarg.0
0x30389  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x3038e  ldloc.0
0x3038f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30394  ldstr    aStaticinstance_16// "._staticInstance.get_path(); }\r\n"
0x30399  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3039e  pop
0x3039f  ldarg.0
0x303a0  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x303a5  ldloc.0
0x303a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x303ab  ldstr    aSetTimeoutFunc_0// ".set_timeout = function(value) { "
0x303b0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x303b5  pop
0x303b6  ldarg.0
0x303b7  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x303bc  ldloc.0
0x303bd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x303c2  ldstr    aStaticinstance_4// "._staticInstance.set_timeout(value); }"...
0x303c7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x303cc  pop
0x303cd  ldarg.0
0x303ce  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x303d3  ldloc.0
0x303d4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x303d9  ldstr    aGetTimeoutFunc_0// ".get_timeout = function() { return "
0x303de  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x303e3  pop
0x303e4  ldarg.0
0x303e5  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x303ea  ldloc.0
0x303eb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x303f0  ldstr    aStaticinstance_5// "._staticInstance.get_timeout(); }\r\n"
0x303f5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x303fa  pop
0x303fb  ldarg.0
0x303fc  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30401  ldloc.0
0x30402  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30407  ldstr    aSetDefaultuser_0// ".set_defaultUserContext = function(valu"...
0x3040c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30411  pop
0x30412  ldarg.0
0x30413  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30418  ldloc.0
0x30419  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3041e  ldstr    aStaticinstance_6// "._staticInstance.set_defaultUserContext"...
0x30423  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30428  pop
0x30429  ldarg.0
0x3042a  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x3042f  ldloc.0
0x30430  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30435  ldstr    aGetDefaultuser_0// ".get_defaultUserContext = function() { "...
0x3043a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3043f  pop
0x30440  ldarg.0
0x30441  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30446  ldloc.0
0x30447  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3044c  ldstr    aStaticinstance_7// "._staticInstance.get_defaultUserContext"...
0x30451  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30456  pop
0x30457  ldarg.0
  ... truncated ...
```
