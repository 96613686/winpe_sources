# Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::JsonTransportableStringToObject

- ea: `0x4e10`
- end: `0x4e26`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::JsonTransportableStringToObject`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x4e10  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x4e15  ldarg.0
0x4e16  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x4e1b  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x4e20  call     T0x2B000036
0x4e25  ret
```
