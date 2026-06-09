# Microsoft.BIServer.Configuration.Key.KeyRepository::ReloadEncryptedSymmetricKey

- ea: `0x60e0`
- end: `0x6108`
- name: `Microsoft.BIServer.Configuration.Key.KeyRepository::ReloadEncryptedSymmetricKey`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60c0`

## callees

- `0xe40`
- `0xef0`
- `0x6110`
- `0x61a0`

## pseudocode

```c

```

## disassembly

```asm
0x60e0  call     class Microsoft.BIServer.Configuration.ConfigReader Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x60e5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.BIServer.Configuration.ConfigReader::get_InstallationId()
0x60ea  stloc.0
0x60eb  ldarg.0
0x60ec  ldloc.0
0x60ed  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.InstallationInfo Microsoft.BIServer.Configuration.Key.KeyRepository::GetAnnouncedKeyResults(valuetype [mscorlib]System.Guid installationId)
0x60f2  stloc.1
0x60f3  ldarg.0
0x60f4  ldloc.1
0x60f5  call     instance unsigned int8[] Microsoft.BIServer.Configuration.Key.KeyRepository::GetEncryptedSymmetricKey(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.InstallationInfo installationInfo)
0x60fa  stloc.2
0x60fb  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x6100  ldloc.2
0x6101  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::SetPublicKeyEncryptedSymmetricKey(unsigned int8[])
0x6106  ldloc.2
0x6107  ret
```
