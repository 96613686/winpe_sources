# System.Windows.Input.StylusWisp.WispTabletDeviceCollection::IsWisptisRegistered

- ea: `0x54540`
- end: `0x545e6`
- name: `System.Windows.Input.StylusWisp.WispTabletDeviceCollection::IsWisptisRegistered`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x54520`

## callees

- `0x54540`

## string_xrefs

- `0x54560`: `HKEY_CLASSES_ROOT\CLSID\{A5B020FD-E04B-4e67-B65A-E7DEED25B2CF}\LocalServer32`
- `0x54571`: `CLSID\{A5B020FD-E04B-4e67-B65A-E7DEED25B2CF}\LocalServer32`

## pseudocode

```c

```

## disassembly

```asm
0x54540  ldc.i4.0
0x54541  stloc.s  4
0x54543  ldnull
0x54544  stloc.0
0x54545  ldnull
0x54546  stloc.3
0x54547  call     class [mscorlib]System.OperatingSystem [mscorlib]System.Environment::get_OSVersion()
0x5454c  callvirt instance class [mscorlib]System.Version [mscorlib]System.OperatingSystem::get_Version()
0x54551  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x54556  ldc.i4.6
0x54557  clt
0x54559  ldc.i4.0
0x5455a  ceq
0x5455c  stloc.1
0x5455d  ldloc.1
0x5455e  brtrue.s loc_54567
0x54560  ldstr    aHkeyClassesRoo// "HKEY_CLASSES_ROOT\\CLSID\\{A5B020FD-E04"...
0x54565  br.s     loc_5456C
0x54567  ldstr    aHkeyClassesRoo_0// "HKEY_CLASSES_ROOT\\Interface\\{C247F616"...
0x5456c  stloc.s  7
0x5456e  ldloc.1
0x5456f  brtrue.s loc_54578
0x54571  ldstr    aClsidA5b020fdE// "CLSID\\{A5B020FD-E04B-4e67-B65A-E7DEED2"...
0x54576  br.s     loc_5457D
0x54578  ldstr    aInterfaceC247f// "Interface\\{C247F616-BBEB-406A-AED3-F75"...
0x5457d  stloc.s  6
0x5457f  ldloc.1
0x54580  brtrue.s loc_54589
0x54582  ldstr    aWisptisExe// "wisptis.exe"
0x54587  br.s     loc_5458E
0x54589  ldstr    aItablet2// "ITablet2"
0x5458e  stloc.s  5
0x54590  ldc.i4.1
0x54591  ldloc.s  7
0x54593  newobj   instance void [mscorlib]System.Security.Permissions.RegistryPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.RegistryPermissionAccess, string)
0x54598  call     instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x5459d  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::ClassesRoot
0x545a2  ldloc.s  6
0x545a4  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x545a9  stloc.0
0x545aa  ldloc.0
0x545ab  brfalse.s loc_545B9
0x545ad  ldloc.0
0x545ae  ldstr    asc_15E4E4// ""
0x545b3  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x545b8  stloc.3
0x545b9  leave.s  loc_545C1
0x545bb  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x545c0  endfinally
0x545c1  ldloc.0
0x545c2  brfalse.s loc_545E3
0x545c4  ldloc.3
0x545c5  isinst   [mscorlib]System.String
0x545ca  stloc.2
0x545cb  ldloc.2
0x545cc  brfalse.s loc_545DD
0x545ce  ldloc.2
0x545cf  ldloc.s  5
0x545d1  ldc.i4.5
0x545d2  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x545d7  ldc.i4.m1
0x545d8  beq.s    loc_545DD
0x545da  ldc.i4.1
0x545db  stloc.s  4
0x545dd  ldloc.0
0x545de  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::Close()
0x545e3  ldloc.s  4
0x545e5  ret
```
