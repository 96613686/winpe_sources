# Microsoft.ManagementConsole.Internal.ViewDescriptionData::.ctor

- ea: `0x32a0`
- end: `0x32fb`
- name: `Microsoft.ManagementConsole.Internal.ViewDescriptionData::.ctor`
- size: `91`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x3410`
- `0x3430`
- `0x3550`
- `0x3560`
- `0x35e0`
- `0x3620`
- `0x3630`

## callees

- `0x60`
- `0xa0`
- `0x290`
- `0x32a0`

## string_xrefs

- `0x32d0`: `The max value for View identifiers has been reached; no new views can be created.`

## pseudocode

```c

```

## disassembly

```asm
0x32a0  ldarg.0
0x32a1  ldsfld   string [mscorlib]System.String::Empty
0x32a6  stfld    string Microsoft.ManagementConsole.Internal.ViewDescriptionData::_displayName
0x32ab  ldarg.0
0x32ac  ldsfld   string [mscorlib]System.String::Empty
0x32b1  stfld    string Microsoft.ManagementConsole.Internal.ViewDescriptionData::_languageIndependentName
0x32b6  ldarg.0
0x32b7  call     instance void [mscorlib]System.Object::.ctor()
0x32bc  ldsfld   int32 Microsoft.ManagementConsole.Internal.ViewDescriptionData::_identifierSeed
0x32c1  ldc.i4   0x7FFFFFFF
0x32c6  bne.un.s loc_32EA
0x32c8  call     class [System]System.Diagnostics.TraceSource Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x32cd  ldc.i4.2
0x32ce  ldc.i4.s 0xC
0x32d0  ldstr    aTheMaxValueFor// "The max value for View identifiers has "...
0x32d5  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0x32da  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionMMCOutOfResources()
0x32df  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x32e4  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x32e9  throw
0x32ea  ldarg.0
0x32eb  ldsflda  int32 Microsoft.ManagementConsole.Internal.ViewDescriptionData::_identifierSeed
0x32f0  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x32f5  stfld    int32 Microsoft.ManagementConsole.Internal.ViewDescriptionData::_id
0x32fa  ret
```
