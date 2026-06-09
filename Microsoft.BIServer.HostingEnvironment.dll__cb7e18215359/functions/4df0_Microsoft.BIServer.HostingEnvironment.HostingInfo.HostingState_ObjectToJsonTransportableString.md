# Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::ObjectToJsonTransportableString

- ea: `0x4df0`
- end: `0x4e0d`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::ObjectToJsonTransportableString`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x4df0  ldarg.0
0x4df1  box      mvar<u1>
0x4df6  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x4dfb  stloc.0
0x4dfc  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x4e01  ldloc.0
0x4e02  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x4e07  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x4e0c  ret
```
