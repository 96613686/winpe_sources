# Microsoft.BIServer.BIService.ServiceConfig::ConfigureServiceConfig

- ea: `0x2280`
- end: `0x230d`
- name: `Microsoft.BIServer.BIService.ServiceConfig::ConfigureServiceConfig`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x21c0`
- `0x2250`

## callees

- `0x2280`
- `0x2370`

## string_xrefs

- `0x2289`: `Config`

## pseudocode

```c

```

## disassembly

```asm
0x2280  ldarg.1
0x2281  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Parse(string)
0x2286  stloc.0
0x2287  ldarg.0
0x2288  ldloc.0
0x2289  ldstr    aConfig// "Config"
0x228e  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x2293  callvirt T0x2B000018
0x2298  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ServiceConfig::_serviceProperties
0x229d  ldarg.0
0x229e  ldstr    aManagementurl// "managementUrl"
0x22a3  call     instance string Microsoft.BIServer.BIService.ServiceConfig::GetRequiredConfig(string key)
0x22a8  stloc.1
0x22a9  ldarg.0
0x22aa  ldloc.1
0x22ab  newobj   instance void [System]System.Uri::.ctor(string)
0x22b0  stfld    class [System]System.Uri Microsoft.BIServer.BIService.ServiceConfig::_managementUri
0x22b5  ldloc.0
0x22b6  ldstr    aManagementproc// "ManagementProcess"
0x22bb  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x22c0  stloc.2
0x22c1  ldarg.0
0x22c2  ldloc.2
0x22c3  callvirt instance string [mscorlib]System.Object::ToString()
0x22c8  call     T0x2B000019
0x22cd  stfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ServiceConfig::_managementProcessConfig
0x22d2  ldarg.0
0x22d3  ldloc.0
0x22d4  ldstr    aManagedprocess// "ManagedProcesses"
0x22d9  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0x22de  ldsfld   class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken, class Microsoft.BIServer.BIService.ProcessConfig> <>c::<>9__8_0
0x22e3  dup
0x22e4  brtrue.s loc_22FD
0x22e6  pop
0x22e7  ldsfld   class <>c <>c::<>9
0x22ec  ldftn    instance class Microsoft.BIServer.BIService.ProcessConfig <>c::<ConfigureServiceConfig>b__8_0(class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken entry)
0x22f2  newobj   instance void class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken, class Microsoft.BIServer.BIService.ProcessConfig>::.ctor(object, native int)
0x22f7  dup
0x22f8  stsfld   class [mscorlib]System.Func`2<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken, class Microsoft.BIServer.BIService.ProcessConfig> <>c::<>9__8_0
0x22fd  call     T0x2B00001A
0x2302  call     T0x2B00001B
0x2307  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.BIServer.BIService.ProcessConfig> Microsoft.BIServer.BIService.ServiceConfig::_managedProcesses
0x230c  ret
```
