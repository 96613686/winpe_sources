# Microsoft.BIServer.Configuration.Key.KeyRepository::GetEncryptedSymmetricKey

- ea: `0x60c0`
- end: `0x60de`
- name: `Microsoft.BIServer.Configuration.Key.KeyRepository::GetEncryptedSymmetricKey`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x60c0`
- `0x60e0`

## pseudocode

```c

```

## disassembly

```asm
0x60c0  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x60c5  callvirt instance bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_IsInitialized()
0x60ca  brtrue.s loc_60D3
0x60cc  ldarg.0
0x60cd  call     instance unsigned int8[] Microsoft.BIServer.Configuration.Key.KeyRepository::ReloadEncryptedSymmetricKey()
0x60d2  ret
0x60d3  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x60d8  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::GetPublicKeyEncryptedSymmetricKey()
0x60dd  ret
```
