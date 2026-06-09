# System.ComponentModel.Design.InheritanceService::.cctor

- ea: `0x5c1d0`
- end: `0x5c1e5`
- name: `System.ComponentModel.Design.InheritanceService::.cctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x5c1d0`: `InheritanceService`
- `0x5c1d5`: `InheritanceService : Debug inheritance scan.`

## pseudocode

```c

```

## disassembly

```asm
0x5c1d0  ldstr    aInheritanceser// "InheritanceService"
0x5c1d5  ldstr    aInheritanceser_0// "InheritanceService : Debug inheritance "...
0x5c1da  newobj   instance void [System]System.Diagnostics.TraceSwitch::.ctor(string, string)
0x5c1df  stsfld   class [System]System.Diagnostics.TraceSwitch System.ComponentModel.Design.InheritanceService::InheritanceServiceSwitch
0x5c1e4  ret
```
