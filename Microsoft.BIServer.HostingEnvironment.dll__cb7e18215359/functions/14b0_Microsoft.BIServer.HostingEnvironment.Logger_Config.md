# Microsoft.BIServer.HostingEnvironment.Logger::Config

- ea: `0x14b0`
- end: `0x14c2`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::Config`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x14b5`: `CONFIG : {0} = [{1}]`

## pseudocode

```c

```

## disassembly

```asm
0x14b0  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0x14b5  ldstr    aConfig01// "CONFIG : {0} = [{1}]"
0x14ba  ldarg.0
0x14bb  ldarg.1
0x14bc  callvirt T0x2B00000C
0x14c1  ret
```
