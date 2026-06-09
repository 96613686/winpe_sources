# System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::GenerateCodeAndConfiguration

- ea: `0x4280`
- end: `0x4384`
- name: `System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::GenerateCodeAndConfiguration`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xdd0`

## callees

- `0x2f60`
- `0x3e70`
- `0x41b0`
- `0x4280`
- `0x4390`
- `0x4600`
- `0x4f20`
- `0x5510`
- `0x5830`
- `0x59e0`

## string_xrefs

- `0x42a6`: `typedDataSetSchemaImporterExtension`

## pseudocode

```c

```

## disassembly

```asm
0x4280  ldarg.0
0x4281  brtrue.s loc_428E
0x4283  ldstr    aSvcmapfile// "svcMapFile"
0x4288  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x428d  throw
0x428e  ldarg.2
0x428f  brtrue.s loc_429C
0x4291  ldstr    aCodedomprovide// "codeDomProvider"
0x4296  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x429b  throw
0x429c  ldarg.s  9
0x429e  ldnull
0x429f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x42a4  brfalse.s loc_42B1
0x42a6  ldstr    aTypeddatasetsc// "typedDataSetSchemaImporterExtension"
0x42ab  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42b0  throw
0x42b1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ProxyGenerationError>::.ctor()
0x42b6  stloc.0
0x42b7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ProxyGenerationError>::.ctor()
0x42bc  stloc.1
0x42bd  newobj   instance void [System]System.CodeDom.CodeCompileUnit::.ctor()
0x42c2  stloc.2
0x42c3  ldarg.0
0x42c4  ldarg.1
0x42c5  ldloc.2
0x42c6  ldarg.2
0x42c7  ldarg.3
0x42c8  ldarg.s  6
0x42ca  ldarg.s  7
0x42cc  ldarg.s  8
0x42ce  ldloc.0
0x42cf  ldarg.s  9
0x42d1  call     class [System.ServiceModel]System.ServiceModel.Description.WsdlImporter System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::CreateWsdlImporter(class System.Web.Compilation.WCFModel.SvcMapFile svcMapFile, class [System.Configuration]System.Configuration.Configuration toolConfiguration, class [System]System.CodeDom.CodeCompileUnit targetCompileUnit, class [System]System.CodeDom.Compiler.CodeDomProvider codeDomProvider, string targetNamespace, class [mscorlib]System.IServiceProvider serviceProviderForImportExtensions, class System.Web.Compilation.WCFModel.IContractGeneratorReferenceTypeLoader typeLoader, int32 targetFrameworkVersion, class [mscorlib]System.Collections.Generic.IList`1<class System.Web.Compilation.WCFModel.ProxyGenerationError> importErrors, class [mscorlib]System.Type typedDataSetSchemaImporterExtension)
0x42d6  stloc.3
0x42d7  ldarg.0
0x42d8  callvirt instance class System.Web.Compilation.WCFModel.ClientOptions System.Web.Compilation.WCFModel.SvcMapFile::get_ClientOptions()
0x42dd  ldloc.3
0x42de  ldloc.2
0x42df  ldarg.3
0x42e0  ldarg.s  4
0x42e2  ldarg.s  7
0x42e4  ldarg.s  8
0x42e6  ldloc.0
0x42e7  call     class [System.ServiceModel]System.ServiceModel.Description.ServiceContractGenerator System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::CreateContractGenerator(class System.Web.Compilation.WCFModel.ClientOptions proxyOptions, class [System.ServiceModel]System.ServiceModel.Description.WsdlImporter wsdlImporter, class [System]System.CodeDom.CodeCompileUnit targetCompileUnit, string proxyNamespace, class [System.Configuration]System.Configuration.Configuration targetConfiguration, class System.Web.Compilation.WCFModel.IContractGeneratorReferenceTypeLoader typeLoader, int32 targetFrameworkVersion, class [mscorlib]System.Collections.Generic.IList`1<class System.Web.Compilation.WCFModel.ProxyGenerationError> importErrors)
0x42ec  stloc.s  4
0x42ee  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::.ctor()
0x42f3  stloc.s  5
0x42f5  ldloc.3
0x42f6  ldloc.2
0x42f7  ldloc.0
0x42f8  ldloca.s 5
0x42fa  ldloca.s 6
0x42fc  ldloca.s 7
0x42fe  call     void System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::ImportWCFModel(class [System.ServiceModel]System.ServiceModel.Description.WsdlImporter importer, class [System]System.CodeDom.CodeCompileUnit compileUnit, class [mscorlib]System.Collections.Generic.IList`1<class System.Web.Compilation.WCFModel.ProxyGenerationError> generationErrors, [out] class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>& serviceEndpointList, [out] class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Channels.Binding>& bindingCollection, [out] class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Description.ContractDescription>& contractCollection)
0x4303  ldloc.3
0x4304  ldloc.s  4
0x4306  ldloc.2
0x4307  ldarg.3
0x4308  ldarg.s  5
0x430a  ldloc.s  7
0x430c  ldloc.s  6
0x430e  ldloc.s  5
0x4310  ldloc.1
0x4311  ldloca.s 8
0x4313  ldloca.s 9
0x4315  call     void System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::GenerateProxy(class [System.ServiceModel]System.ServiceModel.Description.WsdlImporter importer, class [System.ServiceModel]System.ServiceModel.Description.ServiceContractGenerator contractGenerator, class [System]System.CodeDom.CodeCompileUnit targetCompileUnit, string proxyNamespace, string configurationNamespace, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Description.ContractDescription> contractCollection, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Channels.Binding> bindingCollection, class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint> serviceEndpointList, class [mscorlib]System.Collections.Generic.IList`1<class System.Web.Compilation.WCFModel.ProxyGenerationError> proxyGenerationErrors, [out] class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint, class [System.ServiceModel]System.ServiceModel.Configuration.ChannelEndpointElement>& serviceEndpointToChannelEndpointElementMap, [out] class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.GeneratedContractType>& proxyGeneratedContractTypes)
0x431a  ldarg.2
0x431b  call     bool System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::IsVBCodeDomProvider(class [System]System.CodeDom.Compiler.CodeDomProvider codeDomProvider)
0x4320  brfalse.s loc_4328
0x4322  ldloc.2
0x4323  call     void System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::PatchOutParametersInVB(class [System]System.CodeDom.CodeCompileUnit codeCompileUnit)
0x4328  ldloc.0
0x4329  ldloc.2
0x432a  ldarg.s  4
0x432c  ldloc.s  6
0x432e  ldloc.s  7
0x4330  ldloc.s  5
0x4332  ldloc.s  8
0x4334  ldloc.s  9
0x4336  ldloc.1
0x4337  newobj   instance void System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::.ctor(class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ProxyGenerationError> importErrors, class [System]System.CodeDom.CodeCompileUnit targetCompileUnit, class [System.Configuration]System.Configuration.Configuration targetConfiguration, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Channels.Binding> bindingCollection, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Description.ContractDescription> contractCollection, class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint> serviceEndpointList, class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint, class [System.ServiceModel]System.ServiceModel.Configuration.ChannelEndpointElement> serviceEndpointToChannelEndpointElementMap, class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.GeneratedContractType> proxyGeneratedContractTypes, class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Web.Compilation.WCFModel.ProxyGenerationError> proxyGenerationErrors)
0x433c  stloc.s  0xA
0x433e  leave.s  loc_4381
0x4340  stloc.s  0xB
0x4342  ldloc.1
0x4343  ldc.i4.2
0x4344  ldsfld   string [mscorlib]System.String::Empty
0x4349  ldloc.s  0xB
0x434b  ldc.i4.0
0x434c  newobj   instance void System.Web.Compilation.WCFModel.ProxyGenerationError::.ctor(valuetype GeneratorState generatorState, string fileName, class [mscorlib]System.Exception errorException, bool isWarning)
0x4351  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ProxyGenerationError>::Add(var<u1>)
0x4356  ldloc.0
0x4357  newobj   instance void [System]System.CodeDom.CodeCompileUnit::.ctor()
0x435c  ldarg.s  4
0x435e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Channels.Binding>::.ctor()
0x4363  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.ContractDescription>::.ctor()
0x4368  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::.ctor()
0x436d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint, class [System.ServiceModel]System.ServiceModel.Configuration.ChannelEndpointElement>::.ctor()
0x4372  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.GeneratedContractType>::.ctor()
0x4377  ldloc.1
0x4378  newobj   instance void System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::.ctor(class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ProxyGenerationError> importErrors, class [System]System.CodeDom.CodeCompileUnit targetCompileUnit, class [System.Configuration]System.Configuration.Configuration targetConfiguration, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Channels.Binding> bindingCollection, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Description.ContractDescription> contractCollection, class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint> serviceEndpointList, class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint, class [System.ServiceModel]System.ServiceModel.Configuration.ChannelEndpointElement> serviceEndpointToChannelEndpointElementMap, class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.GeneratedContractType> proxyGeneratedContractTypes, class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Web.Compilation.WCFModel.ProxyGenerationError> proxyGenerationErrors)
0x437d  stloc.s  0xA
0x437f  leave.s  loc_4381
0x4381  ldloc.s  0xA
0x4383  ret
```
