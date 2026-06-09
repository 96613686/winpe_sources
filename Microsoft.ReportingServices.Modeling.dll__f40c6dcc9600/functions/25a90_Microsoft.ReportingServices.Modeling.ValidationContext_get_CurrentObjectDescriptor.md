# Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor

- ea: `0x25a90`
- end: `0x25a9c`
- name: `Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor`
- size: `12`
- prototype: ``
- caller_count: `54`
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
- `0x238e0`
- `0x23da0`
- `0x23f50`

## callees

- `0x25590`
- `0x25a70`

## pseudocode

```c

```

## disassembly

```asm
0x25a90  ldarg.0
0x25a91  call     instance class Microsoft.ReportingServices.Modeling.IValidationScope Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentScope()
0x25a96  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x25a9b  ret
```
