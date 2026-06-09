# Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::StoreProcessProperty

- ea: `0x4d90`
- end: `0x4db1`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::StoreProcessProperty`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4ca0`
- `0x4d60`

## callees

- `0x1470`

## pseudocode

```c

```

## disassembly

```asm
0x4d90  ldarg.1
0x4d91  ldc.i4.2
0x4d92  newarr   [mscorlib]System.Object
0x4d97  dup
0x4d98  ldc.i4.0
0x4d99  ldarg.2
0x4d9a  stelem.ref
0x4d9b  dup
0x4d9c  ldc.i4.1
0x4d9d  ldstr    aStoringToSubpr// "Storing to SubProcess Environment"
0x4da2  stelem.ref
0x4da3  call     void Microsoft.BIServer.HostingEnvironment.Logger::Debug(string formatString, object[] formatParams)
0x4da8  ldarg.0
0x4da9  ldarg.1
0x4daa  ldarg.2
0x4dab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x4db0  ret
```
