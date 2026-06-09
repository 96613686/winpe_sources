# Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::GetRegistrySnapInType

- ea: `0x4cc0`
- end: `0x4d1f`
- name: `Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::GetRegistrySnapInType`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x4b30`

## callees

- `0xa0`
- `0x4cc0`
- `0x4d20`
- `0x53d0`

## string_xrefs

- `0x4cd6`: `Extension`
- `0x4cfb`: `Snap-in is neither a stand-alone snap-in or extension`

## pseudocode

```c

```

## disassembly

```asm
0x4cc0  ldc.i4.m1
0x4cc1  stloc.0
0x4cc2  ldarg.0
0x4cc3  ldstr    aStandalone// "Standalone"
0x4cc8  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x4ccd  stloc.1
0x4cce  ldloc.1
0x4ccf  brfalse.s loc_4CD5
0x4cd1  ldc.i4.0
0x4cd2  stloc.0
0x4cd3  br.s     loc_4D11
0x4cd5  ldarg.0
0x4cd6  ldstr    aExtension// "Extension"
0x4cdb  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x4ce0  stloc.2
0x4ce1  ldloc.2
0x4ce2  brfalse.s loc_4CF3
0x4ce4  ldloc.2
0x4ce5  ldnull
0x4ce6  call     string Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::GetRegistryStringValue(class [mscorlib]Microsoft.Win32.RegistryKey key, string value)
0x4ceb  call     valuetype Microsoft.ManagementConsole.Internal.SnapInType Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::GetExtensionTypeFromString(string snapInType)
0x4cf0  stloc.0
0x4cf1  br.s     loc_4D05
0x4cf3  call     class [System]System.Diagnostics.TraceSource Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x4cf8  ldc.i4.2
0x4cf9  ldc.i4.s 0xA
0x4cfb  ldstr    aSnapInIsNeithe// "Snap-in is neither a stand-alone snap-i"...
0x4d00  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0x4d05  leave.s  loc_4D11
0x4d07  ldloc.2
0x4d08  brfalse.s loc_4D10
0x4d0a  ldloc.2
0x4d0b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d10  endfinally
0x4d11  leave.s  loc_4D1D
0x4d13  ldloc.1
0x4d14  brfalse.s loc_4D1C
0x4d16  ldloc.1
0x4d17  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d1c  endfinally
0x4d1d  ldloc.0
0x4d1e  ret
```
