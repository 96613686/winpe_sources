# Microsoft.ManagementConsole.SelectionData::EndUpdates

- ea: `0xd550`
- end: `0xd597`
- name: `Microsoft.ManagementConsole.SelectionData::EndUpdates`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0xa000`
- `0xb2d0`
- `0xd550`
- `0xd7e0`

## string_xrefs

- `0xd551`: `EndUpdates`
- `0xd58c`: `SelectionData.EndUpdates called without a matching SelectionData.BeginUpdates.`

## pseudocode

```c

```

## disassembly

```asm
0xd550  ldarg.0
0xd551  ldstr    aEndupdates// "EndUpdates"
0xd556  call     instance void Microsoft.ManagementConsole.SelectionData::ThrowIfViewShutdown(string viewOperation)
0xd55b  ldarg.0
0xd55c  ldfld    bool Microsoft.ManagementConsole.SelectionData::_batchUpdates
0xd561  brfalse.s loc_D584
0xd563  ldarg.0
0xd564  ldc.i4.0
0xd565  stfld    bool Microsoft.ManagementConsole.SelectionData::_batchUpdates
0xd56a  ldarg.0
0xd56b  ldfld    class Microsoft.ManagementConsole.View Microsoft.ManagementConsole.SelectionData::_view
0xd570  callvirt instance bool Microsoft.ManagementConsole.View::get_Initialized()
0xd575  brfalse.s loc_D596
0xd577  ldarg.0
0xd578  ldfld    class Microsoft.ManagementConsole.View Microsoft.ManagementConsole.SelectionData::_view
0xd57d  ldc.i4.0
0xd57e  callvirt instance void Microsoft.ManagementConsole.View::BatchSelectionDataUpdates(bool begin)
0xd583  ret
0xd584  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xd589  ldc.i4.4
0xd58a  ldc.i4.s 0xC
0xd58c  ldstr    aSelectiondataE// "SelectionData.EndUpdates called without"...
0xd591  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0xd596  ret
```
