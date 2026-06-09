# Microsoft.ReportingServices.ComponentLibrary.Engine.SR::ComponentItem_CircularDependencyConjunction

- ea: `0xd30`
- end: `0xd3d`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.SR::ComponentItem_CircularDependencyConjunction`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1a60`

## callees

- `0x22c0`

## string_xrefs

- `0xd30`: `ComponentItem_CircularDependencyConjunction`

## pseudocode

```c

```

## disassembly

```asm
0xd30  ldstr    aComponentitemC_1// "ComponentItem_CircularDependencyConjunc"...
0xd35  ldarg.0
0xd36  ldarg.1
0xd37  call     string Keys::GetString(string key, object arg0, object arg1)
0xd3c  ret
```
