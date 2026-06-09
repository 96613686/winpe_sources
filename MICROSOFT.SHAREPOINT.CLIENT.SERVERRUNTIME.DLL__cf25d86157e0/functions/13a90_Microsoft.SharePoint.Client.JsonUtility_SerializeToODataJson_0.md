# Microsoft.SharePoint.Client.JsonUtility::SerializeToODataJson_0

- ea: `0x13a90`
- end: `0x13aea`
- name: `Microsoft.SharePoint.Client.JsonUtility::SerializeToODataJson_0`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x13a80`

## callees

- `0x6700`
- `0x12ec0`
- `0x13a90`
- `0x14f70`
- `0x152f0`
- `0x279d0`

## string_xrefs

- `0x13a93`: `writer`
- `0x13aa7`: `baseUri`

## pseudocode

```c

```

## disassembly

```asm
0x13a90  ldarg.3
0x13a91  brtrue.s loc_13A9E
0x13a93  ldstr    aWriter// "writer"
0x13a98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13a9d  throw
0x13a9e  ldarg.2
0x13a9f  ldnull
0x13aa0  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x13aa5  brfalse.s loc_13AB2
0x13aa7  ldstr    aBaseuri// "baseUri"
0x13aac  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13ab1  throw
0x13ab2  ldnull
0x13ab3  stloc.0
0x13ab4  ldarg.1
0x13ab5  stloc.2
0x13ab6  ldloc.2
0x13ab7  ldc.i4.2
0x13ab8  bne.un.s loc_13AD8
0x13aba  newobj   instance void Microsoft.SharePoint.Client.ProxyContext::.ctor()
0x13abf  stloc.1
0x13ac0  ldloc.1
0x13ac1  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x13ac6  call     class [mscorlib]System.Type Microsoft.SharePoint.Client.ClientRequestService::GetOData4RestServiceType(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x13acb  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x13ad0  castclass Microsoft.SharePoint.Client.IRESTfulService
0x13ad5  stloc.0
0x13ad6  br.s     loc_13ADE
0x13ad8  newobj   instance void Microsoft.SharePoint.Client.Rest.RestService::.ctor()
0x13add  stloc.0
0x13ade  ldloc.0
0x13adf  ldarg.0
0x13ae0  ldarg.2
0x13ae1  ldarg.s  4
0x13ae3  ldarg.3
0x13ae4  callvirt instance void Microsoft.SharePoint.Client.IRESTfulService::SerializeToOData(object value, class [System]System.Uri baseUri, class Microsoft.SharePoint.Client.ODataSerializationOptions options, class [mscorlib]System.IO.TextWriter writer)
0x13ae9  ret
```
