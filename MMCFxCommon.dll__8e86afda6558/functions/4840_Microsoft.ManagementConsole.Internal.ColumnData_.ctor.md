# Microsoft.ManagementConsole.Internal.ColumnData::.ctor

- ea: `0x4840`
- end: `0x48a5`
- name: `Microsoft.ManagementConsole.Internal.ColumnData::.ctor`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x60`
- `0xa0`
- `0x290`
- `0x4840`

## string_xrefs

- `0x487a`: `The max value for Column identifiers has been reached; no new columns can be created.`

## pseudocode

```c

```

## disassembly

```asm
0x4840  ldarg.0
0x4841  ldsfld   string [mscorlib]System.String::Empty
0x4846  stfld    string Microsoft.ManagementConsole.Internal.ColumnData::_title
0x484b  ldarg.0
0x484c  ldc.i4.m1
0x484d  stfld    int32 Microsoft.ManagementConsole.Internal.ColumnData::_width
0x4852  ldarg.0
0x4853  ldc.i4.1
0x4854  stfld    bool Microsoft.ManagementConsole.Internal.ColumnData::_visible
0x4859  ldarg.0
0x485a  ldc.i4.m1
0x485b  stfld    int32 Microsoft.ManagementConsole.Internal.ColumnData::_id
0x4860  ldarg.0
0x4861  call     instance void [mscorlib]System.Object::.ctor()
0x4866  ldsfld   int32 Microsoft.ManagementConsole.Internal.ColumnData::_identifierSeed
0x486b  ldc.i4   0x7FFFFFFF
0x4870  bne.un.s loc_4894
0x4872  call     class [System]System.Diagnostics.TraceSource Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x4877  ldc.i4.2
0x4878  ldc.i4.s 0xC
0x487a  ldstr    aTheMaxValueFor_0// "The max value for Column identifiers ha"...
0x487f  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0x4884  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionMMCOutOfResources()
0x4889  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x488e  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x4893  throw
0x4894  ldarg.0
0x4895  ldsflda  int32 Microsoft.ManagementConsole.Internal.ColumnData::_identifierSeed
0x489a  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x489f  stfld    int32 Microsoft.ManagementConsole.Internal.ColumnData::_id
0x48a4  ret
```
