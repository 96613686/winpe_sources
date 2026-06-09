# System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::GenerateProxy

- ea: `0x4600`
- end: `0x47d8`
- name: `System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::GenerateProxy`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x4280`

## callees

- `0x1e20`
- `0x1f50`
- `0x2ee0`
- `0x4600`
- `0x4c50`
- `0x39910`

## string_xrefs

- `0x4604`: `serviceEndpointList`

## pseudocode

```c

```

## disassembly

```asm
0x4600  ldarg.s  7
0x4602  brtrue.s loc_460F
0x4604  ldstr    aServiceendpoin// "serviceEndpointList"
0x4609  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x460e  throw
0x460f  ldarg.s  6
0x4611  brtrue.s loc_461E
0x4613  ldstr    aBindingcollect// "bindingCollection"
0x4618  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x461d  throw
0x461e  ldarg.s  5
0x4620  brtrue.s loc_462D
0x4622  ldstr    aContractcollec// "contractCollection"
0x4627  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x462c  throw
0x462d  ldarg.s  8
0x462f  brtrue.s loc_463C
0x4631  ldstr    aProxygeneratio// "proxyGenerationErrors"
0x4636  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x463b  throw
0x463c  ldarg.s  0xA
0x463e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.GeneratedContractType>::.ctor()
0x4643  stind.ref
0x4644  ldarg.s  9
0x4646  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint, class [System.ServiceModel]System.ServiceModel.Configuration.ChannelEndpointElement>::.ctor()
0x464b  stind.ref
0x464c  ldarg.0
0x464d  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IWsdlImportExtension> [System.ServiceModel]System.ServiceModel.Description.WsdlImporter::get_WsdlImportExtensions()
0x4652  callvirt T0x2B000007
0x4657  stloc.0
0x4658  ldarg.s  5
0x465a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Description.ContractDescription>::GetEnumerator()
0x465f  stloc.1
0x4660  br.s     loc_46DD
0x4662  newobj   instance void <>c__DisplayClass36_0::.ctor()
0x4667  stloc.2
0x4668  ldloc.2
0x4669  ldloc.1
0x466a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.ContractDescription>::get_Current()
0x466f  stfld    class [System.ServiceModel]System.ServiceModel.Description.ContractDescription <>c__DisplayClass36_0::contract
0x4674  ldloc.0
0x4675  brfalse.s loc_469A
0x4677  ldloc.0
0x4678  ldloc.2
0x4679  ldfld    class [System.ServiceModel]System.ServiceModel.Description.ContractDescription <>c__DisplayClass36_0::contract
0x467e  callvirt instance bool System.Web.Compilation.WCFModel.HttpBindingExtension::IsHttpBindingContract(class [System.ServiceModel]System.ServiceModel.Description.ContractDescription contract)
0x4683  brfalse.s loc_469A
0x4685  ldarg.s  7
0x4687  ldloc.2
0x4688  ldftn    instance bool <>c__DisplayClass36_0::<GenerateProxy>b__0(class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint endpoint)
0x468e  newobj   instance void class [mscorlib]System.Func`2<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint, bool>::.ctor(object, native int)
0x4693  call     T0x2B000008
0x4698  brfalse.s loc_46DD
0x469a  ldarg.1
0x469b  ldloc.2
0x469c  ldfld    class [System.ServiceModel]System.ServiceModel.Description.ContractDescription <>c__DisplayClass36_0::contract
0x46a1  callvirt instance class [System]System.CodeDom.CodeTypeReference [System.ServiceModel]System.ServiceModel.Description.ServiceContractGenerator::GenerateServiceContractType(class [System.ServiceModel]System.ServiceModel.Description.ContractDescription)
0x46a6  stloc.3
0x46a7  ldloc.3
0x46a8  brfalse.s loc_46DD
0x46aa  ldloc.3
0x46ab  callvirt instance string [System]System.CodeDom.CodeTypeReference::get_BaseType()
0x46b0  stloc.s  4
0x46b2  ldloc.2
0x46b3  ldfld    class [System.ServiceModel]System.ServiceModel.Description.ContractDescription <>c__DisplayClass36_0::contract
0x46b8  callvirt instance string [System.ServiceModel]System.ServiceModel.Description.ContractDescription::get_Namespace()
0x46bd  ldloc.2
0x46be  ldfld    class [System.ServiceModel]System.ServiceModel.Description.ContractDescription <>c__DisplayClass36_0::contract
0x46c3  callvirt instance string [System.ServiceModel]System.ServiceModel.Description.ContractDescription::get_Name()
0x46c8  ldloc.s  4
0x46ca  ldloc.s  4
0x46cc  newobj   instance void System.Web.Compilation.WCFModel.GeneratedContractType::.ctor(string targetNamespace, string portName, string contractType, string configurationName)
0x46d1  stloc.s  5
0x46d3  ldarg.s  0xA
0x46d5  ldind.ref
0x46d6  ldloc.s  5
0x46d8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.GeneratedContractType>::Add(var<u1>)
0x46dd  ldloc.1
0x46de  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x46e3  brtrue   loc_4662
0x46e8  leave.s  loc_46F4
0x46ea  ldloc.1
0x46eb  brfalse.s loc_46F3
0x46ed  ldloc.1
0x46ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x46f3  endfinally
0x46f4  ldarg.1
0x46f5  callvirt instance class [System.Configuration]System.Configuration.Configuration [System.ServiceModel]System.ServiceModel.Description.ServiceContractGenerator::get_Configuration()
0x46fa  brfalse  loc_4783
0x46ff  ldarg.s  7
0x4701  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::GetEnumerator()
0x4706  stloc.s  6
0x4708  br.s     loc_472D
0x470a  ldloca.s 6
0x470c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::get_Current()
0x4711  stloc.s  7
0x4713  ldnull
0x4714  stloc.s  8
0x4716  ldarg.1
0x4717  ldloc.s  7
0x4719  ldloca.s 8
0x471b  callvirt instance class [System]System.CodeDom.CodeTypeReference [System.ServiceModel]System.ServiceModel.Description.ServiceContractGenerator::GenerateServiceEndpoint(class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint, class [System.ServiceModel]System.ServiceModel.Configuration.ChannelEndpointElement&)
0x4720  pop
0x4721  ldarg.s  9
0x4723  ldind.ref
0x4724  ldloc.s  7
0x4726  ldloc.s  8
0x4728  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint, class [System.ServiceModel]System.ServiceModel.Configuration.ChannelEndpointElement>::set_Item(var<u1>, !!T0)
0x472d  ldloca.s 6
0x472f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::MoveNext()
0x4734  brtrue.s loc_470A
0x4736  leave.s  loc_4746
0x4738  ldloca.s 6
0x473a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>
0x4740  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4745  endfinally
0x4746  ldarg.s  6
0x4748  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Channels.Binding>::GetEnumerator()
0x474d  stloc.s  9
0x474f  br.s     loc_476C
0x4751  ldloc.s  9
0x4753  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Channels.Binding>::get_Current()
0x4758  stloc.s  0xA
0x475a  ldnull
0x475b  stloc.s  0xB
0x475d  ldnull
0x475e  stloc.s  0xC
0x4760  ldarg.1
0x4761  ldloc.s  0xA
0x4763  ldloca.s 0xB
0x4765  ldloca.s 0xC
0x4767  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceContractGenerator::GenerateBinding(class [System.ServiceModel]System.ServiceModel.Channels.Binding, string&, string&)
0x476c  ldloc.s  9
0x476e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4773  brtrue.s loc_4751
0x4775  leave.s  loc_4783
0x4777  ldloc.s  9
0x4779  brfalse.s loc_4782
0x477b  ldloc.s  9
0x477d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4782  endfinally
0x4783  ldarg.3
0x4784  ldarg.s  4
0x4786  ldarg.s  0xA
0x4788  ldind.ref
0x4789  ldarg.s  9
0x478b  ldind.ref
0x478c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint, class [System.ServiceModel]System.ServiceModel.Configuration.ChannelEndpointElement>::get_Values()
0x4791  ldarg.2
0x4792  call     void System.Web.Compilation.WCFModel.VSWCFServiceContractGenerator::PatchConfigurationName(string proxyNamespace, string configNamespace, class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Web.Compilation.WCFModel.GeneratedContractType> generatedContracts, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Configuration.ChannelEndpointElement> endpoints, class [System]System.CodeDom.CodeCompileUnit targetCompileUnit)
0x4797  leave.s  loc_47D7
0x4799  ldarg.1
0x479a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError> [System.ServiceModel]System.ServiceModel.Description.ServiceContractGenerator::get_Errors()
0x479f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError>::GetEnumerator()
0x47a4  stloc.s  0xD
0x47a6  br.s     loc_47BF
0x47a8  ldloc.s  0xD
0x47aa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError>::get_Current()
0x47af  stloc.s  0xE
0x47b1  ldarg.s  8
0x47b3  ldloc.s  0xE
0x47b5  newobj   instance void System.Web.Compilation.WCFModel.ProxyGenerationError::.ctor(class [System.ServiceModel]System.ServiceModel.Description.MetadataConversionError errorMessage)
0x47ba  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class System.Web.Compilation.WCFModel.ProxyGenerationError>::Add(var<u1>)
0x47bf  ldloc.s  0xD
0x47c1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x47c6  brtrue.s loc_47A8
0x47c8  leave.s  loc_47D6
0x47ca  ldloc.s  0xD
0x47cc  brfalse.s loc_47D5
0x47ce  ldloc.s  0xD
0x47d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47d5  endfinally
0x47d6  endfinally
0x47d7  ret
```
