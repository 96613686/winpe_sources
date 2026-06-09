# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::.cctor

- ea: `0x1150`
- end: `0x1172`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::.cctor`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1150  newobj   instance void [mscorlib]System.Random::.ctor()
0x1155  stsfld   class [mscorlib]System.Random Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::Rng
0x115a  ldc.i4.s 0x24
0x115c  newarr   [mscorlib]System.Char
0x1161  dup
0x1162  ldtoken  valuetype __StaticArrayInitTypeSize=72 <PrivateImplementationDetails>::'7131B822A03BF66704984F23A1198C1811D63906'
0x1167  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x116c  stsfld   char[] Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::ValidChars
0x1171  ret
```
