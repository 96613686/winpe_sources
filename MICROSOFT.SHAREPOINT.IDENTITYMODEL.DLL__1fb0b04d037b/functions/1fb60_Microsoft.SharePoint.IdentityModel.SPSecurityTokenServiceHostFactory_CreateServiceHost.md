# Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceHostFactory::CreateServiceHost

- ea: `0x1fb60`
- end: `0x1fca0`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceHostFactory::CreateServiceHost`
- size: `320`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1fb60`

## string_xrefs

- `0x1fb6c`: `STS Host Factory: Attempting to create ServiceHost.`
- `0x1fc56`: `STS Host Factory: The SecurityTokenServiceBehavior is attached to the ServiceHost.`
- `0x1fc7e`: `STS Host Factory: The SPSecurityTokenServiceBehaviorV2 is attached to the ServiceHost.`
- `0x1fc94`: `STS Host Factory: Succesfully created ServiceHost.`

## pseudocode

```c

```

## disassembly

```asm
0x1fb60  ldc.i4   0x15D65D
0x1fb65  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1fb6a  ldc.i4.s 0x64
0x1fb6c  ldstr    aStsHostFactory// "STS Host Factory: Attempting to create "...
0x1fb71  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1fb76  ldarg.0
0x1fb77  ldarg.1
0x1fb78  ldarg.2
0x1fb79  call     instance class [System.ServiceModel]System.ServiceModel.ServiceHostBase [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.WSTrustServiceHostFactory::CreateServiceHost(string, class [System]System.Uri[])
0x1fb7e  stloc.0
0x1fb7f  ldloc.0
0x1fb80  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceDescription [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Description()
0x1fb85  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpointCollection [System.ServiceModel]System.ServiceModel.Description.ServiceDescription::get_Endpoints()
0x1fb8a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::GetEnumerator()
0x1fb8f  stloc.s  6
0x1fb91  br       loc_1FC23
0x1fb96  ldloc.s  6
0x1fb98  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::get_Current()
0x1fb9d  stloc.1
0x1fb9e  ldloc.1
0x1fb9f  callvirt instance string [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Name()
0x1fba4  ldstr    aActas// "ActAs"
0x1fba9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1fbae  brfalse.s loc_1FC23
0x1fbb0  ldloc.1
0x1fbb1  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x1fbb6  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Channels.Binding::CreateBindingElements()
0x1fbbb  stloc.2
0x1fbbc  ldloc.2
0x1fbbd  newobj   instance void [System.ServiceModel]System.ServiceModel.Channels.CustomBinding::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Channels.BindingElement>)
0x1fbc2  stloc.3
0x1fbc3  ldloc.2
0x1fbc4  callvirt T0x2B00001D
0x1fbc9  stloc.s  4
0x1fbcb  ldloc.s  4
0x1fbcd  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x1fbd2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Endorsing()
0x1fbd7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::Clear()
0x1fbdc  newobj   instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.RsaSecurityTokenParameters::.ctor()
0x1fbe1  stloc.s  5
0x1fbe3  ldloc.s  5
0x1fbe5  ldc.i4.1
0x1fbe6  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters::set_InclusionMode(valuetype [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode)
0x1fbeb  ldloc.s  5
0x1fbed  ldc.i4.0
0x1fbee  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters::set_RequireDerivedKeys(bool)
0x1fbf3  ldloc.s  4
0x1fbf5  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_OptionalEndpointSupportingTokenParameters()
0x1fbfa  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Endorsing()
0x1fbff  ldloc.s  5
0x1fc01  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::Add(var<u1>)
0x1fc06  ldloc.1
0x1fc07  ldloc.3
0x1fc08  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::set_Binding(class [System.ServiceModel]System.ServiceModel.Channels.Binding)
0x1fc0d  ldc.i4   0x15D65E
0x1fc12  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1fc17  ldc.i4.s 0x64
0x1fc19  ldstr    aStsHostFactory_0// "STS Host Factory: Fixed ActAs endpoint "...
0x1fc1e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1fc23  ldloc.s  6
0x1fc25  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1fc2a  brtrue   loc_1FB96
0x1fc2f  leave.s  loc_1FC3D
0x1fc31  ldloc.s  6
0x1fc33  brfalse.s loc_1FC3C
0x1fc35  ldloc.s  6
0x1fc37  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fc3c  endfinally
0x1fc3d  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityTokenServiceBehavior::AttacheBhaviour()
0x1fc42  brfalse.s loc_1FC60
0x1fc44  ldloc.0
0x1fc45  call     void [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityTokenServiceBehavior::Attach(class [System.ServiceModel]System.ServiceModel.ServiceHostBase)
0x1fc4a  ldc.i4   0x1005DD
0x1fc4f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1fc54  ldc.i4.s 0x32
0x1fc56  ldstr    aStsHostFactory_1// "STS Host Factory: The SecurityTokenServ"...
0x1fc5b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1fc60  ldc.i4   0x168
0x1fc65  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x1fc6a  brfalse.s loc_1FC88
0x1fc6c  ldloc.0
0x1fc6d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityTokenServiceBehaviorV2::Attach(class [System.ServiceModel]System.ServiceModel.ServiceHostBase)
0x1fc72  ldc.i4   0x17DF29D
0x1fc77  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1fc7c  ldc.i4.s 0x32
0x1fc7e  ldstr    aStsHostFactory_2// "STS Host Factory: The SPSecurityTokenSe"...
0x1fc83  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1fc88  ldc.i4   0x15D65F
0x1fc8d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1fc92  ldc.i4.s 0x64
0x1fc94  ldstr    aStsHostFactory_3// "STS Host Factory: Succesfully created S"...
0x1fc99  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1fc9e  ldloc.0
0x1fc9f  ret
```
