# System.Web.Security.DirectoryInformation::.ctor

- ea: `0x1159d0`
- end: `0x11617e`
- name: `System.Web.Security.DirectoryInformation::.ctor`
- size: `1966`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1117c0`

## callees

- `0x34f20`
- `0x34fa0`
- `0x1159d0`
- `0x1161f0`
- `0x116210`
- `0x1163a0`
- `0x116410`
- `0x116480`
- `0x1164e0`
- `0x116540`
- `0x116550`
- `0x116560`
- `0x1165b0`
- `0x116620`
- `0x1166e0`
- `0x116780`
- `0x1169c0`
- `0x116c30`
- `0x1a8c10`
- `0x1a8c30`
- `0x1a8c50`
- `0x1a8d10`
- `0x1a8d30`

## string_xrefs

- `0x115a95`: `ADMembership_invalid_path`
- `0x115ac8`: `ADMembership_ServerlessADsPath_not_supported`

## pseudocode

```c

```

## disassembly

```asm
0x1159d0  ldarg.0
0x1159d1  ldc.i4   0x185
0x1159d6  stfld    int32 System.Web.Security.DirectoryInformation::port
0x1159db  ldarg.0
0x1159dc  ldc.i4.2
0x1159dd  stfld    valuetype System.Web.Security.DirectoryType System.Web.Security.DirectoryInformation::directoryType
0x1159e2  ldarg.0
0x1159e3  ldc.i4.m1
0x1159e4  stfld    int32 System.Web.Security.DirectoryInformation::clientSearchTimeout
0x1159e9  ldarg.0
0x1159ea  ldc.i4.m1
0x1159eb  stfld    int32 System.Web.Security.DirectoryInformation::serverSearchTimeout
0x1159f0  ldarg.0
0x1159f1  ldc.i4.1
0x1159f2  stfld    valuetype [System.DirectoryServices.Protocols]System.DirectoryServices.Protocols.AuthType System.Web.Security.DirectoryInformation::ldapAuthType
0x1159f7  ldarg.0
0x1159f8  ldc.i4.3
0x1159f9  ldc.i4.2
0x1159fa  newobj   instance void valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes[0...,0...]::.ctor(int32, int32)
0x1159ff  dup
0x115a00  ldtoken  valuetype __StaticArrayInitTypeSize=24 <PrivateImplementationDetails>::'5744C3703BDDD0AADCC6C51BEFA4D69E15D26AC0190D41D0745C315F43F44100'
0x115a05  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x115a0a  stfld    valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes[0...,0...] System.Web.Security.DirectoryInformation::authTypes
0x115a0f  ldarg.0
0x115a10  ldc.i4.3
0x115a11  ldc.i4.2
0x115a12  newobj   instance void valuetype [System.DirectoryServices.Protocols]System.DirectoryServices.Protocols.AuthType[0...,0...]::.ctor(int32, int32)
0x115a17  dup
0x115a18  ldtoken  valuetype __StaticArrayInitTypeSize=24 <PrivateImplementationDetails>::'180DB6FC148F0002B00E8AFC8BB28AE0BD194C9443A45D1F99B2E9C6790E88AF'
0x115a1d  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x115a22  stfld    valuetype [System.DirectoryServices.Protocols]System.DirectoryServices.Protocols.AuthType[0...,0...] System.Web.Security.DirectoryInformation::ldapAuthTypes
0x115a27  ldarg.0
0x115a28  call     instance void [mscorlib]System.Object::.ctor()
0x115a2d  ldarg.0
0x115a2e  ldarg.1
0x115a2f  stfld    string System.Web.Security.DirectoryInformation::adspath
0x115a34  ldarg.0
0x115a35  ldarg.2
0x115a36  stfld    class [System]System.Net.NetworkCredential System.Web.Security.DirectoryInformation::credentials
0x115a3b  ldarg.0
0x115a3c  ldarg.s  4
0x115a3e  stfld    int32 System.Web.Security.DirectoryInformation::clientSearchTimeout
0x115a43  ldarg.0
0x115a44  ldarg.s  5
0x115a46  stfld    int32 System.Web.Security.DirectoryInformation::serverSearchTimeout
0x115a4b  ldarg.0
0x115a4c  ldarg.s  7
0x115a4e  stfld    valuetype System.Web.Util.TimeUnit System.Web.Security.DirectoryInformation::timeUnit
0x115a53  ldarg.1
0x115a54  ldstr    aLdap_0// "LDAP"
0x115a59  ldc.i4.4
0x115a5a  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x115a5f  brtrue.s loc_115A71
0x115a61  ldstr    aAdmembershipOn_0// "ADMembership_OnlyLdap_supported"
0x115a66  call     string System.Web.SR::GetString(string name)
0x115a6b  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x115a70  throw
0x115a71  newobj   instance void Pathname::.ctor()
0x115a76  castclass IAdsPathname
0x115a7b  stloc.0
0x115a7c  ldloc.0
0x115a7d  ldarg.1
0x115a7e  ldc.i4.1
0x115a7f  callvirt instance int32 IAdsPathname::Set([in] [hasfieldmarshal] string bstrADsPath, [in] [hasfieldmarshal] int32 lnSetType)
0x115a84  pop
0x115a85  leave.s  loc_115AA7
0x115a87  stloc.3
0x115a88  ldloc.3
0x115a89  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x115a8e  ldc.i4   0x80005000
0x115a93  bne.un.s loc_115AA5
0x115a95  ldstr    aAdmembershipIn_1// "ADMembership_invalid_path"
0x115a9a  call     string System.Web.SR::GetString(string name)
0x115a9f  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x115aa4  throw
0x115aa5  rethrow
0x115aa7  nop
0x115aa8  ldarg.0
0x115aa9  ldloc.0
0x115aaa  ldc.i4.s 9
0x115aac  callvirt instance string IAdsPathname::Retrieve([hasfieldmarshal] int32)
0x115ab1  stfld    string System.Web.Security.DirectoryInformation::serverName
0x115ab6  leave.s  loc_115ADA
0x115ab8  stloc.s  4
0x115aba  ldloc.s  4
0x115abc  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x115ac1  ldc.i4   0x80005000
0x115ac6  bne.un.s loc_115AD8
0x115ac8  ldstr    aAdmembershipSe_1// "ADMembership_ServerlessADsPath_not_supp"...
0x115acd  call     string System.Web.SR::GetString(string name)
0x115ad2  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x115ad7  throw
0x115ad8  rethrow
0x115ada  ldarg.0
0x115adb  ldarg.0
0x115adc  ldloc.0
0x115add  ldc.i4.7
0x115ade  callvirt instance string IAdsPathname::Retrieve([hasfieldmarshal] int32)
0x115ae3  dup
0x115ae4  stloc.s  5
0x115ae6  stfld    string System.Web.Security.DirectoryInformation::containerDN
0x115aeb  ldloc.s  5
0x115aed  stfld    string System.Web.Security.DirectoryInformation::creationContainerDN
0x115af2  ldarg.0
0x115af3  ldfld    string System.Web.Security.DirectoryInformation::serverName
0x115af8  ldc.i4.s 0x3A
0x115afa  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x115aff  stloc.1
0x115b00  ldloc.1
0x115b01  ldc.i4.m1
0x115b02  beq.s    loc_115B3C
0x115b04  ldarg.0
0x115b05  ldfld    string System.Web.Security.DirectoryInformation::serverName
0x115b0a  stloc.s  6
0x115b0c  ldarg.0
0x115b0d  ldloc.s  6
0x115b0f  ldc.i4.0
0x115b10  ldloc.1
0x115b11  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x115b16  stfld    string System.Web.Security.DirectoryInformation::serverName
0x115b1b  ldarg.0
0x115b1c  ldloc.s  6
0x115b1e  ldloc.1
0x115b1f  ldc.i4.1
0x115b20  add
0x115b21  callvirt instance string [mscorlib]System.String::Substring(int32)
0x115b26  call     class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.NumberFormatInfo::get_InvariantInfo()
0x115b2b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x115b30  stfld    int32 System.Web.Security.DirectoryInformation::port
0x115b35  ldarg.0
0x115b36  ldc.i4.1
0x115b37  stfld    bool System.Web.Security.DirectoryInformation::portSpecified
0x115b3c  ldarg.3
0x115b3d  ldstr    aSecure// "Secure"
0x115b42  ldc.i4.4
0x115b43  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x115b48  brtrue   loc_115D17
0x115b4d  ldc.i4.0
0x115b4e  stloc.s  7
0x115b50  ldc.i4.0
0x115b51  stloc.s  8
0x115b53  ldarg.0
0x115b54  call     instance bool System.Web.Security.DirectoryInformation::IsDefaultCredential()
0x115b59  brtrue   loc_115BFC
0x115b5e  ldarg.0
0x115b5f  ldarg.0
0x115b60  ldc.i4.1
0x115b61  ldc.i4.1
0x115b62  call     instance valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes System.Web.Security.DirectoryInformation::GetAuthenticationTypes(valuetype System.Web.Security.ActiveDirectoryConnectionProtection connectionProtection, valuetype System.Web.Security.CredentialsType type)
0x115b67  stfld    valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes System.Web.Security.DirectoryInformation::authenticationType
0x115b6c  ldarg.0
0x115b6d  ldarg.0
0x115b6e  ldc.i4.1
0x115b6f  ldc.i4.1
0x115b70  call     instance valuetype [System.DirectoryServices.Protocols]System.DirectoryServices.Protocols.AuthType System.Web.Security.DirectoryInformation::GetLdapAuthenticationTypes(valuetype System.Web.Security.ActiveDirectoryConnectionProtection connectionProtection, valuetype System.Web.Security.CredentialsType type)
0x115b75  stfld    valuetype [System.DirectoryServices.Protocols]System.DirectoryServices.Protocols.AuthType System.Web.Security.DirectoryInformation::ldapAuthType
0x115b7a  ldarg.0
0x115b7b  ldarg.0
0x115b7c  ldstr    aRootdse_0// "rootdse"
0x115b81  call     instance string System.Web.Security.DirectoryInformation::GetADsPath(string dn)
0x115b86  ldarg.0
0x115b87  call     instance string System.Web.Security.DirectoryInformation::GetUsername()
0x115b8c  ldarg.0
0x115b8d  call     instance string System.Web.Security.DirectoryInformation::GetPassword()
0x115b92  ldarg.0
0x115b93  ldfld    valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes System.Web.Security.DirectoryInformation::authenticationType
0x115b98  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string, string, string, valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes)
0x115b9d  stfld    class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry System.Web.Security.DirectoryInformation::rootdse
0x115ba2  ldarg.0
0x115ba3  ldfld    class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry System.Web.Security.DirectoryInformation::rootdse
0x115ba8  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::RefreshCache()
0x115bad  ldarg.0
0x115bae  ldc.i4.1
0x115baf  stfld    valuetype System.Web.Security.ActiveDirectoryConnectionProtection System.Web.Security.DirectoryInformation::connectionProtection
0x115bb4  ldarg.0
0x115bb5  ldfld    bool System.Web.Security.DirectoryInformation::portSpecified
0x115bba  brtrue.s loc_115BCE
0x115bbc  ldarg.0
0x115bbd  ldc.i4   0x27C
0x115bc2  stfld    int32 System.Web.Security.DirectoryInformation::port
0x115bc7  ldarg.0
0x115bc8  ldc.i4.1
0x115bc9  stfld    bool System.Web.Security.DirectoryInformation::portSpecified
0x115bce  leave.s  loc_115BFF
0x115bd0  stloc.s  9
0x115bd2  ldloc.s  9
0x115bd4  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x115bd9  ldc.i4   0x8007052E
0x115bde  bne.un.s loc_115BE5
0x115be0  ldc.i4.1
0x115be1  stloc.s  8
0x115be3  br.s     loc_115BFA
0x115be5  ldloc.s  9
0x115be7  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x115bec  ldc.i4   0x8007203A
0x115bf1  bne.un.s loc_115BF8
0x115bf3  ldc.i4.1
0x115bf4  stloc.s  7
0x115bf6  br.s     loc_115BFA
0x115bf8  rethrow
0x115bfa  leave.s  loc_115BFF
0x115bfc  ldc.i4.1
0x115bfd  stloc.s  8
0x115bff  ldloc.s  8
0x115c01  brfalse  loc_115C91
0x115c06  ldarg.0
0x115c07  ldarg.0
0x115c08  ldc.i4.1
0x115c09  ldc.i4.0
0x115c0a  call     instance valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes System.Web.Security.DirectoryInformation::GetAuthenticationTypes(valuetype System.Web.Security.ActiveDirectoryConnectionProtection connectionProtection, valuetype System.Web.Security.CredentialsType type)
0x115c0f  stfld    valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes System.Web.Security.DirectoryInformation::authenticationType
0x115c14  ldarg.0
0x115c15  ldarg.0
0x115c16  ldc.i4.1
0x115c17  ldc.i4.0
0x115c18  call     instance valuetype [System.DirectoryServices.Protocols]System.DirectoryServices.Protocols.AuthType System.Web.Security.DirectoryInformation::GetLdapAuthenticationTypes(valuetype System.Web.Security.ActiveDirectoryConnectionProtection connectionProtection, valuetype System.Web.Security.CredentialsType type)
0x115c1d  stfld    valuetype [System.DirectoryServices.Protocols]System.DirectoryServices.Protocols.AuthType System.Web.Security.DirectoryInformation::ldapAuthType
0x115c22  ldarg.0
0x115c23  ldarg.0
0x115c24  ldstr    aRootdse_0// "rootdse"
0x115c29  call     instance string System.Web.Security.DirectoryInformation::GetADsPath(string dn)
0x115c2e  ldarg.0
0x115c2f  call     instance string System.Web.Security.DirectoryInformation::GetUsername()
0x115c34  ldarg.0
0x115c35  call     instance string System.Web.Security.DirectoryInformation::GetPassword()
0x115c3a  ldarg.0
0x115c3b  ldfld    valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes System.Web.Security.DirectoryInformation::authenticationType
0x115c40  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string, string, string, valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes)
0x115c45  stfld    class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry System.Web.Security.DirectoryInformation::rootdse
0x115c4a  ldarg.0
0x115c4b  ldfld    class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry System.Web.Security.DirectoryInformation::rootdse
0x115c50  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::RefreshCache()
0x115c55  ldarg.0
0x115c56  ldc.i4.1
0x115c57  stfld    valuetype System.Web.Security.ActiveDirectoryConnectionProtection System.Web.Security.DirectoryInformation::connectionProtection
0x115c5c  ldarg.0
0x115c5d  ldfld    bool System.Web.Security.DirectoryInformation::portSpecified
0x115c62  brtrue.s loc_115C76
0x115c64  ldarg.0
0x115c65  ldc.i4   0x27C
0x115c6a  stfld    int32 System.Web.Security.DirectoryInformation::port
0x115c6f  ldarg.0
0x115c70  ldc.i4.1
0x115c71  stfld    bool System.Web.Security.DirectoryInformation::portSpecified
0x115c76  leave.s  loc_115C91
0x115c78  stloc.s  0xA
0x115c7a  ldloc.s  0xA
0x115c7c  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x115c81  ldc.i4   0x8007203A
0x115c86  bne.un.s loc_115C8D
0x115c88  ldc.i4.1
0x115c89  stloc.s  7
0x115c8b  br.s     loc_115C8F
0x115c8d  rethrow
0x115c8f  leave.s  loc_115C91
0x115c91  ldloc.s  7
0x115c93  brfalse  loc_115D7D
0x115c98  ldarg.0
0x115c99  ldarg.0
0x115c9a  ldc.i4.2
0x115c9b  ldc.i4.0
0x115c9c  call     instance valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes System.Web.Security.DirectoryInformation::GetAuthenticationTypes(valuetype System.Web.Security.ActiveDirectoryConnectionProtection connectionProtection, valuetype System.Web.Security.CredentialsType type)
0x115ca1  stfld    valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes System.Web.Security.DirectoryInformation::authenticationType
0x115ca6  ldarg.0
0x115ca7  ldarg.0
0x115ca8  ldc.i4.2
0x115ca9  ldc.i4.0
0x115caa  call     instance valuetype [System.DirectoryServices.Protocols]System.DirectoryServices.Protocols.AuthType System.Web.Security.DirectoryInformation::GetLdapAuthenticationTypes(valuetype System.Web.Security.ActiveDirectoryConnectionProtection connectionProtection, valuetype System.Web.Security.CredentialsType type)
0x115caf  stfld    valuetype [System.DirectoryServices.Protocols]System.DirectoryServices.Protocols.AuthType System.Web.Security.DirectoryInformation::ldapAuthType
0x115cb4  ldarg.0
0x115cb5  ldarg.0
0x115cb6  ldstr    aRootdse_0// "rootdse"
0x115cbb  call     instance string System.Web.Security.DirectoryInformation::GetADsPath(string dn)
0x115cc0  ldarg.0
0x115cc1  call     instance string System.Web.Security.DirectoryInformation::GetUsername()
0x115cc6  ldarg.0
0x115cc7  call     instance string System.Web.Security.DirectoryInformation::GetPassword()
0x115ccc  ldarg.0
0x115ccd  ldfld    valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes System.Web.Security.DirectoryInformation::authenticationType
0x115cd2  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string, string, string, valuetype [System.DirectoryServices]System.DirectoryServices.AuthenticationTypes)
0x115cd7  stfld    class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry System.Web.Security.DirectoryInformation::rootdse
0x115cdc  ldarg.0
0x115cdd  ldfld    class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry System.Web.Security.DirectoryInformation::rootdse
0x115ce2  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::RefreshCache()
0x115ce7  ldarg.0
0x115ce8  ldc.i4.2
0x115ce9  stfld    valuetype System.Web.Security.ActiveDirectoryConnectionProtection System.Web.Security.DirectoryInformation::connectionProtection
0x115cee  leave    loc_115D7D
0x115cf3  stloc.s  0xB
0x115cf5  ldstr    aAdmembershipSe_2// "ADMembership_Secure_connection_not_esta"...
0x115cfa  ldc.i4.1
0x115cfb  newarr   [mscorlib]System.Object
0x115d00  dup
0x115d01  ldc.i4.0
0x115d02  ldloc.s  0xB
0x115d04  callvirt instance string [mscorlib]System.Exception::get_Message()
0x115d09  stelem.ref
0x115d0a  call     string System.Web.SR::GetString(string name, object[] args)
0x115d0f  ldloc.s  0xB
0x115d11  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string, class [mscorlib]System.Exception)
  ... truncated ...
```
