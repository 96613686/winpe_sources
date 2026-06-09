# Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication

- ea: `0xa960`
- end: `0xa966`
- name: `Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication`
- size: `6`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x90d0`
- `0x94b0`
- `0x98d0`
- `0xa8e0`
- `0xa9a0`
- `0xa9c0`
- `0xaa00`
- `0xaae0`
- `0xab10`
- `0xca60`

## pseudocode

```c

```

## disassembly

```asm
0xa960  ldsfld   valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::<CurrentApplication>k__BackingField
0xa965  ret
```
