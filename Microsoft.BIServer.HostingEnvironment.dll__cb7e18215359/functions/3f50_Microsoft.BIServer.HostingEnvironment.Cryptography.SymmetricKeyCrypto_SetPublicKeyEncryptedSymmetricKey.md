# Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::SetPublicKeyEncryptedSymmetricKey

- ea: `0x3f50`
- end: `0x402d`
- name: `Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::SetPublicKeyEncryptedSymmetricKey`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x35f0`
- `0x4e30`

## callees

- `0x1430`
- `0x1550`
- `0x1590`
- `0x15f0`
- `0x3f50`
- `0x4030`
- `0x4150`
- `0x4180`
- `0x4300`

## pseudocode

```c

```

## disassembly

```asm
0x3f50  ldarg.0
0x3f51  call     instance bool Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_IsInitialized()
0x3f56  brfalse.s loc_3F87
0x3f58  ldarg.1
0x3f59  ldarg.0
0x3f5a  ldfld    unsigned int8[] Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_currentSafeKey
0x3f5f  call     T0x2B000029
0x3f64  brfalse.s loc_3F76
0x3f66  ldstr    aIgnoringSetOfS// "Ignoring set of symmetric key (encrypte"...
0x3f6b  call     T0x2B00000A
0x3f70  call     void Microsoft.BIServer.HostingEnvironment.Logger::Trace(string formatString, object[] formatParams)
0x3f75  ret
0x3f76  ldstr    aChangingSymmet// "Changing Symmetric key"
0x3f7b  call     T0x2B00000A
0x3f80  call     void Microsoft.BIServer.HostingEnvironment.Logger::Warning(string formatString, object[] formatParams)
0x3f85  br.s     loc_3F96
0x3f87  ldstr    aSettingSymmetr// "Setting Symmetric Key"
0x3f8c  call     T0x2B00000A
0x3f91  call     void Microsoft.BIServer.HostingEnvironment.Logger::Info(string formatString, object[] formatParams)
0x3f96  nop
0x3f97  ldarg.0
0x3f98  ldstr    aSymmetrickeycr_0// "SymmetricKeyCrypto [unknown]"
0x3f9d  stfld    string Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_name
0x3fa2  ldarg.0
0x3fa3  ldarg.1
0x3fa4  callvirt instance object [mscorlib]System.Array::Clone()
0x3fa9  castclass unsigned int8[]
0x3fae  stfld    unsigned int8[] Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_currentSafeKey
0x3fb3  ldarg.0
0x3fb4  ldfld    class [mscorlib]System.Security.Cryptography.TripleDESCryptoServiceProvider Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_crypto
0x3fb9  ldarg.0
0x3fba  ldarg.0
0x3fbb  ldarg.1
0x3fbc  call     instance unsigned int8[] Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::ConvertNativeRsCryptoToManagedRsaFormat(unsigned int8[] keyBlob)
0x3fc1  call     instance unsigned int8[] Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::RsaDecrypt(unsigned int8[] encryptedSymmetricKey)
0x3fc6  callvirt instance void [mscorlib]System.Security.Cryptography.SymmetricAlgorithm::set_Key(unsigned int8[])
0x3fcb  ldarg.0
0x3fcc  ldfld    class [mscorlib]System.Security.Cryptography.TripleDESCryptoServiceProvider Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_crypto
0x3fd1  callvirt instance void [mscorlib]System.Security.Cryptography.SymmetricAlgorithm::GenerateIV()
0x3fd6  ldarg.0
0x3fd7  ldc.i4.1
0x3fd8  stfld    bool Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_intialized
0x3fdd  ldarg.0
0x3fde  ldstr    aSymmetrickeycr_1// "SymmetricKeyCrypto [From Key Store]"
0x3fe3  stfld    string Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_name
0x3fe8  leave.s  loc_402C
0x3fea  stloc.0
0x3feb  ldstr    aFailed// "Failed: "
0x3ff0  ldloc.0
0x3ff1  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3ff6  call     string [mscorlib]System.String::Concat(string, string)
0x3ffb  stloc.1
0x3ffc  ldarg.0
0x3ffd  ldstr    aSymmetrickeycr_2// "SymmetricKeyCrypto [{0}]"
0x4002  ldloc.1
0x4003  call     string [mscorlib]System.String::Format(string, object)
0x4008  stfld    string Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_name
0x400d  ldarg.0
0x400e  ldnull
0x400f  stfld    unsigned int8[] Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::_currentSafeKey
0x4014  ldloc.0
0x4015  ldloc.1
0x4016  call     T0x2B00000A
0x401b  call     void Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception ex, string formatString, object[] formatParams)
0x4020  ldloc.0
0x4021  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4026  newobj   instance void Microsoft.BIServer.HostingEnvironment.Cryptography.Exceptions.SymmetricKeyNotInitializedException::.ctor(string message)
0x402b  throw
0x402c  ret
```
