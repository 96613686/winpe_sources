# Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError

- ea: `0x25b70`
- end: `0x25b7f`
- name: `Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError`
- size: `15`
- prototype: ``
- caller_count: `56`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x8830`
- `0x8940`
- `0x8990`
- `0xaa90`
- `0xbda0`
- `0xc120`
- `0xc510`
- `0xc930`
- `0xca00`
- `0xfa30`
- `0xfc40`
- `0x10a50`
- `0x10d00`
- `0x111a0`
- `0x118c0`
- `0x126f0`
- `0x14390`
- `0x143e0`
- `0x14930`
- `0x155d0`
- `0x15960`
- `0x15b40`
- `0x15bb0`
- `0x16580`
- `0x16e60`
- `0x17160`
- `0x17ba0`
- `0x17d40`
- `0x17e10`
- `0x18fe0`
- `0x192f0`
- `0x193f0`
- `0x1a530`
- `0x1a8a0`
- `0x1aa10`
- `0x1aec0`
- `0x1af20`
- `0x1b570`
- `0x1b600`
- `0x1bcc0`
- `0x1c1a0`
- `0x1d3f0`
- `0x1d410`
- `0x1e260`
- `0x1ee70`
- `0x213b0`
- `0x21b30`
- `0x21f00`
- `0x22530`
- `0x22d70`

## callees

- `0x25b00`
- `0x25b90`

## pseudocode

```c

```

## disassembly

```asm
0x25b70  ldarg.0
0x25b71  ldarg.0
0x25b72  ldarg.1
0x25b73  ldarg.2
0x25b74  call     instance class Microsoft.ReportingServices.Modeling.ValidationMessage Microsoft.ReportingServices.Modeling.ValidationContext::CreateScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x25b79  call     instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddMessage(class Microsoft.ReportingServices.Modeling.ValidationMessage message)
0x25b7e  ret
```
