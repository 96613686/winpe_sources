# Microsoft.BIServer.HostingEnvironment.Logger::Config_0

- ea: `0x14d0`
- end: `0x14e3`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::Config_0`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x14d5`: `CONFIG : {0} = [{1}] ({2})`

## pseudocode

```c

```

## disassembly

```asm
0x14d0  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0x14d5  ldstr    aConfig012// "CONFIG : {0} = [{1}] ({2})"
0x14da  ldarg.0
0x14db  ldarg.1
0x14dc  ldarg.2
0x14dd  callvirt T0x2B00000D
0x14e2  ret
```
