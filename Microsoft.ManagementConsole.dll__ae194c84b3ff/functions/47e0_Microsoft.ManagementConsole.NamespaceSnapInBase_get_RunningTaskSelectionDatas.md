# Microsoft.ManagementConsole.NamespaceSnapInBase::get_RunningTaskSelectionDatas

- ea: `0x47e0`
- end: `0x47fa`
- name: `Microsoft.ManagementConsole.NamespaceSnapInBase::get_RunningTaskSelectionDatas`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xa5d0`
- `0xda50`

## callees

- `0x47e0`
- `0xdd00`

## pseudocode

```c

```

## disassembly

```asm
0x47e0  ldarg.0
0x47e1  ldfld    class Microsoft.ManagementConsole.AuxiliarySelectionDataCollection Microsoft.ManagementConsole.NamespaceSnapInBase::_runningTaskSelectionDatas
0x47e6  brtrue.s loc_47F3
0x47e8  ldarg.0
0x47e9  newobj   instance void Microsoft.ManagementConsole.AuxiliarySelectionDataCollection::.ctor()
0x47ee  stfld    class Microsoft.ManagementConsole.AuxiliarySelectionDataCollection Microsoft.ManagementConsole.NamespaceSnapInBase::_runningTaskSelectionDatas
0x47f3  ldarg.0
0x47f4  ldfld    class Microsoft.ManagementConsole.AuxiliarySelectionDataCollection Microsoft.ManagementConsole.NamespaceSnapInBase::_runningTaskSelectionDatas
0x47f9  ret
```
