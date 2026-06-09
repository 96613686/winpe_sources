# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::GenerateNewScopeId

- ea: `0x1100`
- end: `0x112f`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::GenerateNewScopeId`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x10e0`

## pseudocode

```c

```

## disassembly

```asm
0x1100  ldc.i4.0
0x1101  ldc.i4.8
0x1102  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<int32> [System.Core]System.Linq.Enumerable::Range(int32, int32)
0x1107  ldarg.0
0x1108  ldftn    instance char Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::<GenerateNewScopeId>b__6_0(int32 i)
0x110e  newobj   instance void class [mscorlib]System.Func`2<int32, char>::.ctor(object, native int)
0x1113  call     T0x2B000004
0x1118  call     T0x2B000005
0x111d  stloc.0
0x111e  ldstr    asc_57C4// "["
0x1123  ldloc.0
0x1124  ldstr    asc_57C8// "]"
0x1129  call     string [mscorlib]System.String::Concat(string, string, string)
0x112e  ret
```
