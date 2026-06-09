# Microsoft.ManagementConsole.SelectionData::BeginUpdates

- ea: `0xd510`
- end: `0xd544`
- name: `Microsoft.ManagementConsole.SelectionData::BeginUpdates`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0xa000`
- `0xb2d0`
- `0xd510`
- `0xd7e0`

## string_xrefs

- `0xd511`: `BeginUpdates`

## pseudocode

```c

```

## disassembly

```asm
0xd510  ldarg.0
0xd511  ldstr    aBeginupdates// "BeginUpdates"
0xd516  call     instance void Microsoft.ManagementConsole.SelectionData::ThrowIfViewShutdown(string viewOperation)
0xd51b  ldarg.0
0xd51c  ldfld    bool Microsoft.ManagementConsole.SelectionData::_batchUpdates
0xd521  brtrue.s loc_D543
0xd523  ldarg.0
0xd524  ldc.i4.1
0xd525  stfld    bool Microsoft.ManagementConsole.SelectionData::_batchUpdates
0xd52a  ldarg.0
0xd52b  ldfld    class Microsoft.ManagementConsole.View Microsoft.ManagementConsole.SelectionData::_view
0xd530  callvirt instance bool Microsoft.ManagementConsole.View::get_Initialized()
0xd535  brfalse.s loc_D543
0xd537  ldarg.0
0xd538  ldfld    class Microsoft.ManagementConsole.View Microsoft.ManagementConsole.SelectionData::_view
0xd53d  ldc.i4.1
0xd53e  callvirt instance void Microsoft.ManagementConsole.View::BatchSelectionDataUpdates(bool begin)
0xd543  ret
```
