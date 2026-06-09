# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::get_ScopeId

- ea: `0x10e0`
- end: `0x10fa`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::get_ScopeId`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x10e0`
- `0x1100`

## pseudocode

```c

```

## disassembly

```asm
0x10e0  ldarg.0
0x10e1  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::_scopeId
0x10e6  dup
0x10e7  brtrue.s loc_10F9
0x10e9  pop
0x10ea  ldarg.0
0x10eb  ldarg.0
0x10ec  call     instance string Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::GenerateNewScopeId()
0x10f1  dup
0x10f2  stloc.0
0x10f3  stfld    string Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::_scopeId
0x10f8  ldloc.0
0x10f9  ret
```
