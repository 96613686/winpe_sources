# Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::RemoveFromStore

- ea: `0x4d90`
- end: `0x4f53`
- name: `Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::RemoveFromStore`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4ad0`
- `0x4b00`
- `0x4d90`
- `0x4f60`

## string_xrefs

- `0x4e03`: `Extensions`
- `0x4ee6`: `Extensions`
- `0x4e45`: `{0}{1:B}\Extensions`

## pseudocode

```c

```

## disassembly

```asm
0x4d90  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x4d95  ldstr    aSoftwareMicros// "SOFTWARE\\Microsoft\\MMC\\SnapIns\\"
0x4d9a  ldc.i4.1
0x4d9b  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x4da0  stloc.0
0x4da1  ldloc.0
0x4da2  brfalse.s loc_4DB0
0x4da4  ldloc.0
0x4da5  ldarg.0
0x4da6  call     instance string Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_Id()
0x4dab  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteSubKeyTree(string)
0x4db0  leave.s  loc_4DBC
0x4db2  ldloc.0
0x4db3  brfalse.s loc_4DBB
0x4db5  ldloc.0
0x4db6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4dbb  endfinally
0x4dbc  ldarg.0
0x4dbd  call     instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_ExtendedNodeTypes()
0x4dc2  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x4dc7  stloc.s  6
0x4dc9  br       loc_4F36
0x4dce  ldloca.s 6
0x4dd0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x4dd5  stloc.1
0x4dd6  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x4ddb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4de0  ldstr    a01B23// "{0}{1:B}\\{2}\\{3}"
0x4de5  ldc.i4.4
0x4de6  newarr   [mscorlib]System.Object
0x4deb  stloc.s  7
0x4ded  ldloc.s  7
0x4def  ldc.i4.0
0x4df0  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\MMC\\NodeTypes\\"
0x4df5  stelem.ref
0x4df6  ldloc.s  7
0x4df8  ldc.i4.1
0x4df9  ldloc.1
0x4dfa  box      [mscorlib]System.Guid
0x4dff  stelem.ref
0x4e00  ldloc.s  7
0x4e02  ldc.i4.2
0x4e03  ldstr    aExtensions// "Extensions"
0x4e08  stelem.ref
0x4e09  ldloc.s  7
0x4e0b  ldc.i4.3
0x4e0c  ldstr    aNamespace// "Namespace"
0x4e11  stelem.ref
0x4e12  ldloc.s  7
0x4e14  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e19  ldc.i4.1
0x4e1a  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x4e1f  stloc.2
0x4e20  ldloc.2
0x4e21  brfalse.s loc_4E2F
0x4e23  ldloc.2
0x4e24  ldarg.0
0x4e25  call     instance string Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_Id()
0x4e2a  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string)
0x4e2f  leave.s  loc_4E3B
0x4e31  ldloc.2
0x4e32  brfalse.s loc_4E3A
0x4e34  ldloc.2
0x4e35  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e3a  endfinally
0x4e3b  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x4e40  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e45  ldstr    a01BExtensions// "{0}{1:B}\\Extensions"
0x4e4a  ldc.i4.2
0x4e4b  newarr   [mscorlib]System.Object
0x4e50  stloc.s  8
0x4e52  ldloc.s  8
0x4e54  ldc.i4.0
0x4e55  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\MMC\\NodeTypes\\"
0x4e5a  stelem.ref
0x4e5b  ldloc.s  8
0x4e5d  ldc.i4.1
0x4e5e  ldloc.1
0x4e5f  box      [mscorlib]System.Guid
0x4e64  stelem.ref
0x4e65  ldloc.s  8
0x4e67  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e6c  ldc.i4.1
0x4e6d  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x4e72  stloc.3
0x4e73  ldloc.3
0x4e74  brfalse.s loc_4E9A
0x4e76  ldarg.0
0x4e77  ldloc.3
0x4e78  ldstr    aNamespace// "Namespace"
0x4e7d  call     instance void Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::RemoveSubkeyIfEmpty(class [mscorlib]Microsoft.Win32.RegistryKey key, string subKeyName)
0x4e82  ldarg.0
0x4e83  ldloc.3
0x4e84  ldstr    aPropertysheet// "PropertySheet"
0x4e89  call     instance void Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::RemoveSubkeyIfEmpty(class [mscorlib]Microsoft.Win32.RegistryKey key, string subKeyName)
0x4e8e  ldarg.0
0x4e8f  ldloc.3
0x4e90  ldstr    aActions// "Actions"
0x4e95  call     instance void Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::RemoveSubkeyIfEmpty(class [mscorlib]Microsoft.Win32.RegistryKey key, string subKeyName)
0x4e9a  leave.s  loc_4EA6
0x4e9c  ldloc.3
0x4e9d  brfalse.s loc_4EA5
0x4e9f  ldloc.3
0x4ea0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ea5  endfinally
0x4ea6  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x4eab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4eb0  ldstr    a01B// "{0}{1:B}"
0x4eb5  ldc.i4.2
0x4eb6  newarr   [mscorlib]System.Object
0x4ebb  stloc.s  9
0x4ebd  ldloc.s  9
0x4ebf  ldc.i4.0
0x4ec0  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\MMC\\NodeTypes\\"
0x4ec5  stelem.ref
0x4ec6  ldloc.s  9
0x4ec8  ldc.i4.1
0x4ec9  ldloc.1
0x4eca  box      [mscorlib]System.Guid
0x4ecf  stelem.ref
0x4ed0  ldloc.s  9
0x4ed2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4ed7  ldc.i4.1
0x4ed8  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x4edd  stloc.s  4
0x4edf  ldloc.s  4
0x4ee1  brfalse.s loc_4EF0
0x4ee3  ldarg.0
0x4ee4  ldloc.s  4
0x4ee6  ldstr    aExtensions// "Extensions"
0x4eeb  call     instance void Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::RemoveSubkeyIfEmpty(class [mscorlib]Microsoft.Win32.RegistryKey key, string subKeyName)
0x4ef0  leave.s  loc_4EFE
0x4ef2  ldloc.s  4
0x4ef4  brfalse.s loc_4EFD
0x4ef6  ldloc.s  4
0x4ef8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4efd  endfinally
0x4efe  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x4f03  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\MMC\\NodeTypes\\"
0x4f08  ldc.i4.1
0x4f09  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x4f0e  stloc.s  5
0x4f10  ldloc.s  5
0x4f12  brfalse.s loc_4F28
0x4f14  ldarg.0
0x4f15  ldloc.s  5
0x4f17  ldloca.s 1
0x4f19  ldstr    aB// "B"
0x4f1e  call     instance string [mscorlib]System.Guid::ToString(string)
0x4f23  call     instance void Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::RemoveSubkeyIfEmpty(class [mscorlib]Microsoft.Win32.RegistryKey key, string subKeyName)
0x4f28  leave.s  loc_4F36
0x4f2a  ldloc.s  5
0x4f2c  brfalse.s loc_4F35
0x4f2e  ldloc.s  5
0x4f30  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4f35  endfinally
0x4f36  ldloca.s 6
0x4f38  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x4f3d  brtrue   loc_4DCE
0x4f42  leave.s  loc_4F52
0x4f44  ldloca.s 6
0x4f46  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x4f4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4f51  endfinally
0x4f52  ret
```
