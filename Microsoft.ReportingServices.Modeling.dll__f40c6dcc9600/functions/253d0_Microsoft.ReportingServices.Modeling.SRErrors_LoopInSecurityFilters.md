# Microsoft.ReportingServices.Modeling.SRErrors::LoopInSecurityFilters

- ea: `0x253d0`
- end: `0x253e1`
- name: `Microsoft.ReportingServices.Modeling.SRErrors::LoopInSecurityFilters`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x10a50`

## callees

- `0x38e50`

## string_xrefs

- `0x253d0`: `LoopInSecurityFilters`

## pseudocode

```c

```

## disassembly

```asm
0x253d0  ldstr    aLoopinsecurity// "LoopInSecurityFilters"
0x253d5  ldarg.0
0x253d6  box      Microsoft.ReportingServices.Modeling.SRObjectDescriptor
0x253db  call     string Keys::GetString(string key, object arg0)
0x253e0  ret
```
