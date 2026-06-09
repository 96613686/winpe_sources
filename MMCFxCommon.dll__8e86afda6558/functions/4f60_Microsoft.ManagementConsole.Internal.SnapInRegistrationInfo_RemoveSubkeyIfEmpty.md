# Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::RemoveSubkeyIfEmpty

- ea: `0x4f60`
- end: `0x4f98`
- name: `Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::RemoveSubkeyIfEmpty`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4d90`

## callees

- `0x4f60`

## pseudocode

```c

```

## disassembly

```asm
0x4f60  ldarg.1
0x4f61  ldarg.2
0x4f62  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x4f67  stloc.0
0x4f68  ldloc.0
0x4f69  brfalse.s loc_4F8B
0x4f6b  ldloc.0
0x4f6c  callvirt instance int32 [mscorlib]Microsoft.Win32.RegistryKey::get_ValueCount()
0x4f71  brtrue.s loc_4F8B
0x4f73  ldloc.0
0x4f74  callvirt instance int32 [mscorlib]Microsoft.Win32.RegistryKey::get_SubKeyCount()
0x4f79  brtrue.s loc_4F8B
0x4f7b  ldloc.0
0x4f7c  ldnull
0x4f7d  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x4f82  brtrue.s loc_4F8B
0x4f84  ldarg.1
0x4f85  ldarg.2
0x4f86  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteSubKeyTree(string)
0x4f8b  leave.s  loc_4F97
0x4f8d  ldloc.0
0x4f8e  brfalse.s loc_4F96
0x4f90  ldloc.0
0x4f91  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4f96  endfinally
0x4f97  ret
```
