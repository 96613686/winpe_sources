# Microsoft.ManagementConsole.PropertySheetManager::CreatePropertySheet

- ea: `0xe960`
- end: `0xe987`
- name: `Microsoft.ManagementConsole.PropertySheetManager::CreatePropertySheet`
- size: `39`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1c80`
- `0x1d40`
- `0x4d80`
- `0xa680`
- `0xd3c0`

## callees

- `0xe3e0`
- `0xe5f0`
- `0xe960`
- `0xea90`

## pseudocode

```c

```

## disassembly

```asm
0xe960  ldarg.2
0xe961  brtrue.s loc_E96E
0xe963  ldstr    aPagecollection// "pageCollection"
0xe968  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe96d  throw
0xe96e  ldarg.0
0xe96f  ldarg.1
0xe970  ldarg.3
0xe971  newobj   instance void Microsoft.ManagementConsole.PropertySheet::.ctor(class Microsoft.ManagementConsole.PropertySheetManager manager, int32 sheetId, class Microsoft.ManagementConsole.AuxiliarySelectionData auxiliarySelectionData)
0xe976  stloc.0
0xe977  ldloc.0
0xe978  ldarg.2
0xe979  callvirt instance void Microsoft.ManagementConsole.PropertySheet::AddPropertyPages(class Microsoft.ManagementConsole.PropertyPageCollection pageCollection)
0xe97e  ldarg.0
0xe97f  ldloc.0
0xe980  call     instance void Microsoft.ManagementConsole.PropertySheetManager::AddPropertySheet(class Microsoft.ManagementConsole.PropertySheet sheet)
0xe985  ldloc.0
0xe986  ret
```
