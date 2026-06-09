# Microsoft.SharePoint.Client.Services.EndpointCreator::.ctor

- ea: `0x71e0`
- end: `0x7218`
- name: `Microsoft.SharePoint.Client.Services.EndpointCreator::.ctor`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7440`
- `0x74e0`

## callees

- `0x71e0`

## string_xrefs

- `0x71e9`: `serviceHost`

## pseudocode

```c

```

## disassembly

```asm
0x71e0  ldarg.0
0x71e1  call     instance void [mscorlib]System.Object::.ctor()
0x71e6  ldarg.1
0x71e7  brtrue.s loc_71F4
0x71e9  ldstr    aServicehost// "serviceHost"
0x71ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x71f3  throw
0x71f4  ldarg.3
0x71f5  brtrue.s loc_7202
0x71f7  ldstr    aBaseaddresses// "baseAddresses"
0x71fc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7201  throw
0x7202  ldarg.0
0x7203  ldarg.1
0x7204  stfld    class [System.ServiceModel]System.ServiceModel.ServiceHost Microsoft.SharePoint.Client.Services.EndpointCreator::m_serviceHost
0x7209  ldarg.0
0x720a  ldarg.3
0x720b  stfld    class [System]System.Uri[] Microsoft.SharePoint.Client.Services.EndpointCreator::m_baseAddresses
0x7210  ldarg.0
0x7211  ldarg.2
0x7212  stfld    class [mscorlib]System.Type Microsoft.SharePoint.Client.Services.EndpointCreator::m_implementedContract
0x7217  ret
```
