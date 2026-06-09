# Microsoft.BIServer.Configuration.LSA.LocalSecurityAuthority::AddRegistryReadPermission

- ea: `0x5fd0`
- end: `0x606b`
- name: `Microsoft.BIServer.Configuration.LSA.LocalSecurityAuthority::AddRegistryReadPermission`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x5fd0`

## string_xrefs

- `0x5fef`: `Registry root does not exist for SID {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5fd0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::Users
0x5fd5  ldarg.0
0x5fd6  callvirt instance string [mscorlib]System.Security.Principal.IdentityReference::get_Value()
0x5fdb  ldstr    aSoftwareMicros_1// "\\Software\\Microsoft"
0x5fe0  call     string [mscorlib]System.String::Concat(string, string)
0x5fe5  ldc.i4.1
0x5fe6  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x5feb  stloc.0
0x5fec  ldloc.0
0x5fed  brtrue.s loc_6005
0x5fef  ldstr    aRegistryRootDo// "Registry root does not exist for SID {0"...
0x5ff4  ldarg.0
0x5ff5  callvirt instance string [mscorlib]System.Security.Principal.IdentityReference::get_Value()
0x5ffa  call     string [mscorlib]System.String::Format(string, object)
0x5fff  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x6004  throw
0x6005  ldloc.0
0x6006  ldstr    aAvalonGraphics// "Avalon.Graphics"
0x600b  ldc.i4.1
0x600c  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x6011  stloc.1
0x6012  ldloc.1
0x6013  brtrue.s loc_603E
0x6015  ldloc.0
0x6016  ldstr    aAvalonGraphics// "Avalon.Graphics"
0x601b  ldc.i4.1
0x601c  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string, bool)
0x6021  pop
0x6022  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::Users
0x6027  ldarg.0
0x6028  callvirt instance string [mscorlib]System.Security.Principal.IdentityReference::get_Value()
0x602d  ldstr    aSoftwareMicros_2// "\\Software\\Microsoft\\Avalon.Graphics"
0x6032  call     string [mscorlib]System.String::Concat(string, string)
0x6037  ldc.i4.1
0x6038  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x603d  stloc.1
0x603e  newobj   instance void [mscorlib]System.Security.AccessControl.RegistrySecurity::.ctor()
0x6043  stloc.2
0x6044  ldloc.1
0x6045  callvirt instance class [mscorlib]System.Security.AccessControl.RegistrySecurity [mscorlib]Microsoft.Win32.RegistryKey::GetAccessControl()
0x604a  stloc.2
0x604b  ldloc.2
0x604c  ldc.i4.1
0x604d  ldnull
0x604e  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(valuetype [mscorlib]System.Security.Principal.WellKnownSidType, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x6053  ldc.i4   0x20019
0x6058  ldc.i4.0
0x6059  newobj   instance void [mscorlib]System.Security.AccessControl.RegistryAccessRule::.ctor(class [mscorlib]System.Security.Principal.IdentityReference, valuetype [mscorlib]System.Security.AccessControl.RegistryRights, valuetype [mscorlib]System.Security.AccessControl.AccessControlType)
0x605e  callvirt instance void [mscorlib]System.Security.AccessControl.RegistrySecurity::AddAccessRule(class [mscorlib]System.Security.AccessControl.RegistryAccessRule)
0x6063  ldloc.1
0x6064  ldloc.2
0x6065  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetAccessControl(class [mscorlib]System.Security.AccessControl.RegistrySecurity)
0x606a  ret
```
