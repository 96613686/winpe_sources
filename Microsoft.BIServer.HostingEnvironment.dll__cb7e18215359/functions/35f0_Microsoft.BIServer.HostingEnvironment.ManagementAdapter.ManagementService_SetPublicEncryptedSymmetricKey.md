# Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::SetPublicEncryptedSymmetricKey

- ea: `0x35f0`
- end: `0x360f`
- name: `Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::SetPublicEncryptedSymmetricKey`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x68c0`

## callees

- `0x15f0`
- `0x35f0`
- `0x3cf0`
- `0x3f50`

## pseudocode

```c

```

## disassembly

```asm
0x35f0  call     class Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x35f5  ldarg.0
0x35f6  callvirt instance void Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::SetPublicKeyEncryptedSymmetricKey(unsigned int8[] symmetricKeyBlob)
0x35fb  leave.s  loc_360E
0x35fd  ldstr    aCouldnTImportS// "Couldn't import symmetric key"
0x3602  call     T0x2B00000A
0x3607  call     void Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception ex, string formatString, object[] formatParams)
0x360c  rethrow
0x360e  ret
```
