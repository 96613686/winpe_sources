# Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::CreateSymmetricKey

- ea: `0x4070`
- end: `0x40d2`
- name: `Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::CreateSymmetricKey`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1550`
- `0x1590`
- `0x4070`
- `0x40f0`
- `0x4180`

## string_xrefs

- `0x40c1`: `SymmetricKeyCrypto [created]`

## pseudocode

```c

```

## disassembly

```asm
0x4070  ldarg.0
0x4071  call     instance bool Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_IsInitialized()
0x4076  brfalse.s loc_4089
0x4078  ldstr    aRecreatingSymm// "Recreating Symmetric key"
0x407d  call     T0x2B00000A
0x4082  call     void Microsoft.BIServer.HostingEnvironment.Logger::Warning(string formatString, object[] formatParams)
0x4087  br.s     loc_4098
0x4089  ldstr    aCreatingSymmet// "Creating Symmetric Key"
0x408e  call     T0x2B00000A
0x4093  call     void Microsoft.BIServer.HostingEnvironment.Logger::Info(string formatString, object[] formatParams)
0x4098  ldarg.0
0x4099  ldstr    aSymmetrickeycr_3// "SymmetricKeyCrypto [creating...]"
0x409e  stfld    string Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_name
0x40a3  ldarg.0
0x40a4  ldfld    class [mscorlib]System.Security.Cryptography.TripleDESCryptoServiceProvider Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_crypto
0x40a9  callvirt instance void [mscorlib]System.Security.Cryptography.SymmetricAlgorithm::GenerateKey()
0x40ae  ldarg.0
0x40af  ldfld    class [mscorlib]System.Security.Cryptography.TripleDESCryptoServiceProvider Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_crypto
0x40b4  callvirt instance void [mscorlib]System.Security.Cryptography.SymmetricAlgorithm::GenerateIV()
0x40b9  ldarg.0
0x40ba  ldc.i4.1
0x40bb  stfld    bool Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_intialized
0x40c0  ldarg.0
0x40c1  ldstr    aSymmetrickeycr_4// "SymmetricKeyCrypto [created]"
0x40c6  stfld    string Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_name
0x40cb  ldarg.0
0x40cc  call     instance void Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::SetCurrentSafeKey()
0x40d1  ret
```
