# System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::.ctor

- ea: `0x41b0`
- end: `0x4272`
- name: `System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::.ctor`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4280`

## callees

- `0x41b0`

## string_xrefs

- `0x41c7`: `targetCompileUnit`
- `0x41f4`: `serviceEndpointList`
- `0x4203`: `serviceEndpointToChannelEndpointElementMap`

## pseudocode

```c

```

## disassembly

```asm
0x41b0  ldarg.0
0x41b1  call     instance void [mscorlib]System.Object::.ctor()
0x41b6  ldarg.1
0x41b7  brtrue.s loc_41C4
0x41b9  ldstr    aImporterrors// "importErrors"
0x41be  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x41c3  throw
0x41c4  ldarg.2
0x41c5  brtrue.s loc_41D2
0x41c7  ldstr    aTargetcompileu// "targetCompileUnit"
0x41cc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x41d1  throw
0x41d2  ldarg.s  4
0x41d4  brtrue.s loc_41E1
0x41d6  ldstr    aBindingcollect// "bindingCollection"
0x41db  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x41e0  throw
0x41e1  ldarg.s  5
0x41e3  brtrue.s loc_41F0
0x41e5  ldstr    aContractcollec// "contractCollection"
0x41ea  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x41ef  throw
0x41f0  ldarg.s  6
0x41f2  brtrue.s loc_41FF
0x41f4  ldstr    aServiceendpoin// "serviceEndpointList"
0x41f9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x41fe  throw
0x41ff  ldarg.s  7
0x4201  brtrue.s loc_420E
0x4203  ldstr    aServiceendpoin_0// "serviceEndpointToChannelEndpointElement"...
0x4208  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x420d  throw
0x420e  ldarg.s  8
0x4210  brtrue.s loc_421D
0x4212  ldstr    aProxygenerated// "proxyGeneratedContractTypes"
0x4217  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x421c  throw
0x421d  ldarg.s  9
0x421f  brtrue.s loc_422C
0x4221  ldstr    aProxygeneratio// "proxyGenerationErrors"
0x4226  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x422b  throw
0x422c  ldarg.0
0x422d  ldarg.1
0x422e  stfld    class [mscorlib]System.Collections.Generic.IList`1<class System.Web.Compilation.WCFModel.ProxyGenerationError> System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::importErrors
0x4233  ldarg.0
0x4234  ldarg.2
0x4235  stfld    class [System]System.CodeDom.CodeCompileUnit System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::targetCompileUnit
0x423a  ldarg.0
0x423b  ldarg.3
0x423c  stfld    class [System.Configuration]System.Configuration.Configuration System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::targetConfiguration
0x4241  ldarg.0
0x4242  ldarg.s  4
0x4244  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Channels.Binding> System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::bindingCollection
0x4249  ldarg.0
0x424a  ldarg.s  5
0x424c  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Description.ContractDescription> System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::contractCollection
0x4251  ldarg.0
0x4252  ldarg.s  6
0x4254  stfld    class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint> System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::serviceEndpointList
0x4259  ldarg.0
0x425a  ldarg.s  7
0x425c  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint, class [System.ServiceModel]System.ServiceModel.Configuration.ChannelEndpointElement> System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::serviceEndpointToChannelEndpointElementMap
0x4261  ldarg.0
0x4262  ldarg.s  8
0x4264  stfld    class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.GeneratedContractType> System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::proxyGeneratedContractTypes
0x4269  ldarg.0
0x426a  ldarg.s  9
0x426c  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Web.Compilation.WCFModel.ProxyGenerationError> System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::proxyGenerationErrors
0x4271  ret
```
