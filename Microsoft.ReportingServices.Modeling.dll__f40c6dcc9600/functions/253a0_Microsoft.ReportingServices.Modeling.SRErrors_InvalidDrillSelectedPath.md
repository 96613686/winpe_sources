# Microsoft.ReportingServices.Modeling.SRErrors::InvalidDrillSelectedPath

- ea: `0x253a0`
- end: `0x253ad`
- name: `Microsoft.ReportingServices.Modeling.SRErrors::InvalidDrillSelectedPath`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x17d40`

## callees

- `0x38e70`

## string_xrefs

- `0x253a0`: `InvalidDrillSelectedPath`

## pseudocode

```c

```

## disassembly

```asm
0x253a0  ldstr    aInvaliddrillse_0// "InvalidDrillSelectedPath"
0x253a5  ldarg.0
0x253a6  ldarg.1
0x253a7  call     string Keys::GetString(string key, object arg0, object arg1)
0x253ac  ret
```
