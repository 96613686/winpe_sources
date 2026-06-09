# Microsoft.ManagementConsole.SelectionData::ReplaceSharedData

- ea: `0xd910`
- end: `0xd949`
- name: `Microsoft.ManagementConsole.SelectionData::ReplaceSharedData`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xd200`
- `0xd950`

## callees

- `0x56f0`
- `0x5710`
- `0x58c0`

## pseudocode

```c

```

## disassembly

```asm
0xd910  ldarg.0
0xd911  ldfld    class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.SelectionData::_sharedData
0xd916  stloc.0
0xd917  ldloc.0
0xd918  ldarg.0
0xd919  ldftn    instance void Microsoft.ManagementConsole.SelectionData::OnSharedDataChanged(object source, class Microsoft.ManagementConsole.WritableSharedDataChangedEventArgs e)
0xd91f  newobj   instance void SharedDataChangedEventHandler::.ctor(object object, native int method)
0xd924  callvirt instance void Microsoft.ManagementConsole.WritableSharedData::remove_Changed(class SharedDataChangedEventHandler value)
0xd929  ldarg.0
0xd92a  ldarg.1
0xd92b  stfld    class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.SelectionData::_sharedData
0xd930  ldarg.0
0xd931  ldfld    class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.SelectionData::_sharedData
0xd936  ldarg.0
0xd937  ldftn    instance void Microsoft.ManagementConsole.SelectionData::OnSharedDataChanged(object source, class Microsoft.ManagementConsole.WritableSharedDataChangedEventArgs e)
0xd93d  newobj   instance void SharedDataChangedEventHandler::.ctor(object object, native int method)
0xd942  callvirt instance void Microsoft.ManagementConsole.WritableSharedData::add_Changed(class SharedDataChangedEventHandler value)
0xd947  ldloc.0
0xd948  ret
```
