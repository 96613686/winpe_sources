# Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::.ctor

- ea: `0x3d00`
- end: `0x3d8b`
- name: `Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::.ctor`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x41a0`

## callees

- `0x1550`
- `0x3a30`

## string_xrefs

- `0x3d20`: `Microsoft SQL Server Reporting Services Key Container 2010`

## pseudocode

```c

```

## disassembly

```asm
0x3d00  ldarg.0
0x3d01  ldstr    aSymmetrickeycr// "SymmetricKeyCrypto [Uninitialized]"
0x3d06  stfld    string Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_name
0x3d0b  ldarg.0
0x3d0c  call     instance void Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::.ctor()
0x3d11  ldarg.0
0x3d12  newobj   instance void [mscorlib]System.Security.Cryptography.TripleDESCryptoServiceProvider::.ctor()
0x3d17  stfld    class [mscorlib]System.Security.Cryptography.TripleDESCryptoServiceProvider Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_crypto
0x3d1c  ldarg.0
0x3d1d  ldc.i4.s 0x18
0x3d1f  ldnull
0x3d20  ldstr    aMicrosoftSqlSe// "Microsoft SQL Server Reporting Services"...
0x3d25  newobj   instance void [mscorlib]System.Security.Cryptography.CspParameters::.ctor(int32, string, string)
0x3d2a  stfld    class [mscorlib]System.Security.Cryptography.CspParameters Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_rsaKeyStore
0x3d2f  ldarg.0
0x3d30  ldfld    class [mscorlib]System.Security.Cryptography.CspParameters Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_rsaKeyStore
0x3d35  ldc.i4.8
0x3d36  callvirt instance void [mscorlib]System.Security.Cryptography.CspParameters::set_Flags(valuetype [mscorlib]System.Security.Cryptography.CspProviderFlags)
0x3d3b  ldarg.0
0x3d3c  ldfld    class [mscorlib]System.Security.Cryptography.CspParameters Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_rsaKeyStore
0x3d41  ldc.i4.1
0x3d42  stfld    int32 [mscorlib]System.Security.Cryptography.CspParameters::KeyNumber
0x3d47  ldstr    aProviderName0// "Provider name {0}"
0x3d4c  ldc.i4.1
0x3d4d  newarr   [mscorlib]System.Object
0x3d52  dup
0x3d53  ldc.i4.0
0x3d54  ldarg.0
0x3d55  ldfld    class [mscorlib]System.Security.Cryptography.CspParameters Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_rsaKeyStore
0x3d5a  ldfld    string [mscorlib]System.Security.Cryptography.CspParameters::ProviderName
0x3d5f  stelem.ref
0x3d60  call     void Microsoft.BIServer.HostingEnvironment.Logger::Info(string formatString, object[] formatParams)
0x3d65  ldstr    aContainerName0// "Container name {0}"
0x3d6a  ldc.i4.1
0x3d6b  newarr   [mscorlib]System.Object
0x3d70  dup
0x3d71  ldc.i4.0
0x3d72  ldarg.0
0x3d73  ldfld    class [mscorlib]System.Security.Cryptography.CspParameters Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_rsaKeyStore
0x3d78  ldfld    string [mscorlib]System.Security.Cryptography.CspParameters::KeyContainerName
0x3d7d  stelem.ref
0x3d7e  call     void Microsoft.BIServer.HostingEnvironment.Logger::Info(string formatString, object[] formatParams)
0x3d83  ldarg.0
0x3d84  ldnull
0x3d85  stfld    unsigned int8[] Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_currentSafeKey
0x3d8a  ret
```
