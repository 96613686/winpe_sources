# Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::InitializeInHostedProcess

- ea: `0x4e30`
- end: `0x4eb8`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::InitializeInHostedProcess`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4f00`

## callees

- `0x7e0`
- `0x820`
- `0x3530`
- `0x3c60`
- `0x3cf0`
- `0x3f50`
- `0x4dc0`
- `0x4e30`
- `0x4f20`
- `0x4f60`

## string_xrefs

- `0x4e36`: `rsConfigFilePath`
- `0x4e53`: `Hosting-url-ManagementService`

## pseudocode

```c

```

## disassembly

```asm
0x4e30  ldsfld   class Microsoft.BIServer.HostingEnvironment.StaticConfig Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x4e35  dup
0x4e36  ldstr    aRsconfigfilepa// "rsConfigFilePath"
0x4e3b  callvirt instance string Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrException(string key)
0x4e40  stloc.0
0x4e41  dup
0x4e42  ldstr    aHostingDatabas// "Hosting-databaseValidationStatus"
0x4e47  callvirt instance string Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrException(string key)
0x4e4c  call     valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::ParseDatabaseValidationStatus(string str)
0x4e51  stloc.1
0x4e52  dup
0x4e53  ldstr    aHostingUrlMana// "Hosting-url-ManagementService"
0x4e58  ldstr    aHttpManagement// "http://managementUrl/NotSet"
0x4e5d  callvirt instance string Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string key, string defaultValue)
0x4e62  newobj   instance void [System]System.Uri::.ctor(string)
0x4e67  stloc.2
0x4e68  ldstr    aHostingUrlRepo// "Hosting-url-ReportServerWebApp"
0x4e6d  ldstr    aHttpPortalurlN// "http://portalUrl/NotSet"
0x4e72  callvirt instance string Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string key, string defaultValue)
0x4e77  newobj   instance void [System]System.Uri::.ctor(string)
0x4e7c  stloc.3
0x4e7d  call     class Microsoft.BIServer.HostingEnvironment.Cryptography.NoCrypto Microsoft.BIServer.HostingEnvironment.Cryptography.NoCrypto::get_Instance()
0x4e82  stloc.s  4
0x4e84  ldloc.1
0x4e85  ldc.i4.2
0x4e86  bne.un.s loc_4EA2
0x4e88  call     unsigned int8[] Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::FetchEncryptionKeyFromEnvironment()
0x4e8d  stloc.s  5
0x4e8f  call     class Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x4e94  ldloc.s  5
0x4e96  callvirt instance void Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::SetPublicKeyEncryptedSymmetricKey(unsigned int8[] symmetricKeyBlob)
0x4e9b  call     class Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x4ea0  stloc.s  4
0x4ea2  ldloc.0
0x4ea3  ldloc.s  4
0x4ea5  ldloc.1
0x4ea6  ldloc.2
0x4ea7  newobj   instance void Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::.ctor(class [System]System.Uri managementUrl)
0x4eac  ldloc.3
0x4ead  newobj   instance void Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::.ctor(string rsConfigFilePath, class Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto catalogCrypto, valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus databaseValidationStatus, class Microsoft.BIServer.HostingEnvironment.ManagementAdapter.IManagementService managementService, class [System]System.Uri portalUrl)
0x4eb2  stsfld   class Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::_hostedProcessInstance
0x4eb7  ret
```
