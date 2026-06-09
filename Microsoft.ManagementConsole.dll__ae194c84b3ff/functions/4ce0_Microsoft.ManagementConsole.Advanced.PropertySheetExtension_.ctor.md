# Microsoft.ManagementConsole.Advanced.PropertySheetExtension::.ctor

- ea: `0x4ce0`
- end: `0x4d09`
- name: `Microsoft.ManagementConsole.Advanced.PropertySheetExtension::.ctor`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4340`
- `0x4eb0`
- `0x5150`
- `0x51b0`

## pseudocode

```c

```

## disassembly

```asm
0x4ce0  ldarg.0
0x4ce1  newobj   instance void Microsoft.ManagementConsole.SharedData::.ctor()
0x4ce6  stfld    class Microsoft.ManagementConsole.SharedData Microsoft.ManagementConsole.Advanced.PropertySheetExtension::_sharedData
0x4ceb  ldarg.0
0x4cec  call     instance void Microsoft.ManagementConsole.SnapInBase::.ctor()
0x4cf1  ldarg.0
0x4cf2  ldfld    class Microsoft.ManagementConsole.SharedData Microsoft.ManagementConsole.Advanced.PropertySheetExtension::_sharedData
0x4cf7  ldarg.0
0x4cf8  ldftn    instance void Microsoft.ManagementConsole.Advanced.PropertySheetExtension::SharedDataChanged(object sender, class Microsoft.ManagementConsole.SharedDataChangedEventArgs e)
0x4cfe  newobj   instance void SharedDataChangedEventHandler::.ctor(object object, native int method)
0x4d03  callvirt instance void Microsoft.ManagementConsole.SharedData::add_Changed(class SharedDataChangedEventHandler value)
0x4d08  ret
```
