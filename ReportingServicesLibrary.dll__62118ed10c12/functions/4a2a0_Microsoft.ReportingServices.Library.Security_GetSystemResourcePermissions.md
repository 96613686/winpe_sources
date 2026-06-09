# Microsoft.ReportingServices.Library.Security::GetSystemResourcePermissions

- ea: `0x4a2a0`
- end: `0x4a2c4`
- name: `Microsoft.ReportingServices.Library.Security::GetSystemResourcePermissions`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4a200`

## callees

- `0x4a2a0`

## string_xrefs

- `0x4a2a6`: `Read Properties`
- `0x4a2b7`: `Read Content`

## pseudocode

```c

```

## disassembly

```asm
0x4a2a0  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0x4a2a5  dup
0x4a2a6  ldstr    aReadProperties// "Read Properties"
0x4a2ab  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x4a2b0  pop
0x4a2b1  stloc.0
0x4a2b2  ldarg.1
0x4a2b3  ldc.i4.3
0x4a2b4  bne.un.s loc_4A2C2
0x4a2b6  ldloc.0
0x4a2b7  ldstr    aReadContent// "Read Content"
0x4a2bc  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x4a2c1  pop
0x4a2c2  ldloc.0
0x4a2c3  ret
```
