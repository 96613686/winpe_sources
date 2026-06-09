# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::<GenerateNewScopeId>b__6_0

- ea: `0x1180`
- end: `0x1199`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::<GenerateNewScopeId>b__6_0`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1180  ldsfld   char[] Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::ValidChars
0x1185  ldarg.0
0x1186  ldfld    class [mscorlib]System.Func`2<int32, int32> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::RandomNext
0x118b  ldsfld   char[] Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::ValidChars
0x1190  ldlen
0x1191  conv.i4
0x1192  callvirt instance var<u1> class [mscorlib]System.Func`2<int32, int32>::Invoke(void)
0x1197  ldelem.u2
0x1198  ret
```
