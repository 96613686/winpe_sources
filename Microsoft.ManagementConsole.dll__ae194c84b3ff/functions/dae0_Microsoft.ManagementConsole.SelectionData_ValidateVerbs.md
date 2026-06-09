# Microsoft.ManagementConsole.SelectionData::ValidateVerbs

- ea: `0xdae0`
- end: `0xdb39`
- name: `Microsoft.ManagementConsole.SelectionData::ValidateVerbs`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0xd2f0`
- `0xd950`

## callees

- `0x1e0`
- `0x8440`
- `0xdae0`

## string_xrefs

- `0xdb06`: `Paste and Rename verbs will not be enabled in the UI for multiselection.`

## pseudocode

```c

```

## disassembly

```asm
0xdae0  ldarg.0
0xdae1  ldfld    valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.SelectionCardinality Microsoft.ManagementConsole.SelectionData::_type
0xdae6  ldc.i4.2
0xdae7  bne.un.s loc_DB10
0xdae9  ldarg.0
0xdaea  ldfld    valuetype Microsoft.ManagementConsole.StandardVerbs Microsoft.ManagementConsole.SelectionData::_enabledVerbs
0xdaef  ldc.i4.s 0x20
0xdaf1  and
0xdaf2  brtrue.s loc_DAFE
0xdaf4  ldarg.0
0xdaf5  ldfld    valuetype Microsoft.ManagementConsole.StandardVerbs Microsoft.ManagementConsole.SelectionData::_enabledVerbs
0xdafa  ldc.i4.4
0xdafb  and
0xdafc  brfalse.s loc_DB10
0xdafe  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xdb03  ldc.i4.4
0xdb04  ldc.i4.s 0xC
0xdb06  ldstr    aPasteAndRename// "Paste and Rename verbs will not be enab"...
0xdb0b  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0xdb10  ldarg.0
0xdb11  ldfld    class Microsoft.ManagementConsole.View Microsoft.ManagementConsole.SelectionData::_view
0xdb16  isinst   Microsoft.ManagementConsole.MmcListView
0xdb1b  brtrue.s loc_DB38
0xdb1d  ldarg.0
0xdb1e  ldfld    valuetype Microsoft.ManagementConsole.StandardVerbs Microsoft.ManagementConsole.SelectionData::_enabledVerbs
0xdb23  ldc.i4.s 0x20
0xdb25  and
0xdb26  brfalse.s loc_DB38
0xdb28  call     string Microsoft.ManagementConsole.Internal.Strings::get_SelectionDataStandardVerbsRenameVerbInvalidUpdate()
0xdb2d  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0xdb32  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xdb37  throw
0xdb38  ret
```
