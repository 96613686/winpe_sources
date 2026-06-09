# System.Deployment.Application.ComponentVerifier::GetHashAlgorithm

- ea: `0x10470`
- end: `0x1053d`
- name: `System.Deployment.Application.ComponentVerifier::GetHashAlgorithm`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x103c0`

## callees

- `0x10470`
- `0x1c700`
- `0x1c730`
- `0x23020`

## string_xrefs

- `0x10493`: `System.Security.Cryptography.SHA256CryptoServiceProvider`
- `0x104c5`: `System.Security.Cryptography.SHA384CryptoServiceProvider`
- `0x104f1`: `System.Security.Cryptography.SHA512CryptoServiceProvider`

## pseudocode

```c

```

## disassembly

```asm
0x10470  ldnull
0x10471  stloc.0
0x10472  ldarg.0
0x10473  ldc.i4.1
0x10474  bne.un.s loc_10481
0x10476  newobj   instance void [mscorlib]System.Security.Cryptography.SHA1CryptoServiceProvider::.ctor()
0x1047b  stloc.0
0x1047c  br       loc_1053B
0x10481  ldarg.0
0x10482  ldc.i4.2
0x10483  bne.un.s loc_104B3
0x10485  call     bool System.Deployment.Application.PlatformSpecific::get_OnWindows2003()
0x1048a  brtrue.s loc_10493
0x1048c  call     bool System.Deployment.Application.PlatformSpecific::get_OnVistaOrAbove()
0x10491  brfalse.s loc_104A8
0x10493  ldstr    aSystemSecurity// "System.Security.Cryptography.SHA256Cryp"...
0x10498  call     object [mscorlib]System.Security.Cryptography.CryptoConfig::CreateFromName(string)
0x1049d  isinst   [mscorlib]System.Security.Cryptography.HashAlgorithm
0x104a2  stloc.0
0x104a3  br       loc_1053B
0x104a8  newobj   instance void [mscorlib]System.Security.Cryptography.SHA256Managed::.ctor()
0x104ad  stloc.0
0x104ae  br       loc_1053B
0x104b3  ldarg.0
0x104b4  ldc.i4.3
0x104b5  bne.un.s loc_104DF
0x104b7  call     bool System.Deployment.Application.PlatformSpecific::get_OnWindows2003()
0x104bc  brtrue.s loc_104C5
0x104be  call     bool System.Deployment.Application.PlatformSpecific::get_OnVistaOrAbove()
0x104c3  brfalse.s loc_104D7
0x104c5  ldstr    aSystemSecurity_0// "System.Security.Cryptography.SHA384Cryp"...
0x104ca  call     object [mscorlib]System.Security.Cryptography.CryptoConfig::CreateFromName(string)
0x104cf  isinst   [mscorlib]System.Security.Cryptography.HashAlgorithm
0x104d4  stloc.0
0x104d5  br.s     loc_1053B
0x104d7  newobj   instance void [mscorlib]System.Security.Cryptography.SHA384Managed::.ctor()
0x104dc  stloc.0
0x104dd  br.s     loc_1053B
0x104df  ldarg.0
0x104e0  ldc.i4.4
0x104e1  bne.un.s loc_1050B
0x104e3  call     bool System.Deployment.Application.PlatformSpecific::get_OnWindows2003()
0x104e8  brtrue.s loc_104F1
0x104ea  call     bool System.Deployment.Application.PlatformSpecific::get_OnVistaOrAbove()
0x104ef  brfalse.s loc_10503
0x104f1  ldstr    aSystemSecurity_1// "System.Security.Cryptography.SHA512Cryp"...
0x104f6  call     object [mscorlib]System.Security.Cryptography.CryptoConfig::CreateFromName(string)
0x104fb  isinst   [mscorlib]System.Security.Cryptography.HashAlgorithm
0x10500  stloc.0
0x10501  br.s     loc_1053B
0x10503  newobj   instance void [mscorlib]System.Security.Cryptography.SHA512Managed::.ctor()
0x10508  stloc.0
0x10509  br.s     loc_1053B
0x1050b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x10510  ldstr    aExDigestmethod// "Ex_DigestMethodNotSupported"
0x10515  call     string System.Deployment.Application.Resources::GetString(string s)
0x1051a  ldc.i4.1
0x1051b  newarr   [mscorlib]System.Object
0x10520  dup
0x10521  ldc.i4.0
0x10522  ldarga.s 0
0x10524  constrained. System.Deployment.Internal.Isolation.Manifest.CMS_HASH_DIGESTMETHOD
0x1052a  callvirt instance string [mscorlib]System.Object::ToString()
0x1052f  stelem.ref
0x10530  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10535  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1053a  throw
0x1053b  ldloc.0
0x1053c  ret
```
