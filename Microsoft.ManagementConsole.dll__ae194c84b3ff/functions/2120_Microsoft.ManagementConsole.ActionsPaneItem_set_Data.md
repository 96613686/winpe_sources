# Microsoft.ManagementConsole.ActionsPaneItem::set_Data

- ea: `0x2120`
- end: `0x2173`
- name: `Microsoft.ManagementConsole.ActionsPaneItem::set_Data`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2400`
- `0x2b20`

## callees

- `0x120`
- `0x2120`
- `0x8440`

## string_xrefs

- `0x2143`: `The max value for Action identifiers has been reached; no new actions can be created.`

## pseudocode

```c

```

## disassembly

```asm
0x2120  ldarg.0
0x2121  ldarg.1
0x2122  stfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ActionsPaneItemData Microsoft.ManagementConsole.ActionsPaneItem::_data
0x2127  ldarg.0
0x2128  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ActionsPaneItemData Microsoft.ManagementConsole.ActionsPaneItem::_data
0x212d  brfalse.s loc_2172
0x212f  ldsfld   int32 Microsoft.ManagementConsole.ActionsPaneItem::_idCounter
0x2134  ldc.i4   0x7FFFFFFF
0x2139  bne.un.s loc_215D
0x213b  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x2140  ldc.i4.2
0x2141  ldc.i4.s 0xC
0x2143  ldstr    aTheMaxValueFor_0// "The max value for Action identifiers ha"...
0x2148  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0x214d  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionMMCOutOfResources()
0x2152  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x2157  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x215c  throw
0x215d  ldarg.0
0x215e  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ActionsPaneItemData Microsoft.ManagementConsole.ActionsPaneItem::_data
0x2163  ldsflda  int32 Microsoft.ManagementConsole.ActionsPaneItem::_idCounter
0x2168  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x216d  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ActionsPaneItemData::set_Id(int32)
0x2172  ret
```
