# Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceActiveHostFactory::CreateServiceHost

- ea: `0x1fcc0`
- end: `0x1ffaf`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenServiceActiveHostFactory::CreateServiceHost`
- size: `751`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1fcc0`
- `0x27920`

## string_xrefs

- `0x1fd96`: `Microsoft.IdentityModel.Protocols.WSTrust.IWSTrust13SyncContract`
- `0x1fdc4`: `Microsoft.IdentityModel.Protocols.WSTrust.IWSTrust13SyncContract`
- `0x1fe7d`: `Microsoft.IdentityModel.Protocols.WSTrust.IWSTrust13SyncContract`
- `0x1ffa3`: `STS Active Host Factory: The SecurityTokenServiceBehavior is attached to the ActiveServiceHost.`

## pseudocode

```c

```

## disassembly

```asm
0x1fcc0  ldarg.0
0x1fcc1  ldarg.1
0x1fcc2  ldarg.2
0x1fcc3  call     instance class [System.ServiceModel]System.ServiceModel.ServiceHostBase [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.WSTrustServiceHostFactory::CreateServiceHost(string, class [System]System.Uri[])
0x1fcc8  stloc.0
0x1fcc9  ldloc.0
0x1fcca  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceDescription [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Description()
0x1fccf  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IServiceBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceDescription::get_Behaviors()
0x1fcd4  newobj   instance void Microsoft.SharePoint.IdentityModel.SPWsdlAlternateAccessBehavior::.ctor()
0x1fcd9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IServiceBehavior>::Add(var<u1>)
0x1fcde  ldc.i4.0
0x1fcdf  stloc.1
0x1fce0  ldc.i4.0
0x1fce1  stloc.2
0x1fce2  ldarg.2
0x1fce3  stloc.s  0xF
0x1fce5  ldc.i4.0
0x1fce6  stloc.s  0x10
0x1fce8  br.s     loc_1FD20
0x1fcea  ldloc.s  0xF
0x1fcec  ldloc.s  0x10
0x1fcee  ldelem.ref
0x1fcef  stloc.3
0x1fcf0  ldloc.3
0x1fcf1  callvirt instance string [System]System.Uri::get_Scheme()
0x1fcf6  ldsfld   string [System]System.Uri::UriSchemeHttp
0x1fcfb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1fd00  brfalse.s loc_1FD06
0x1fd02  ldc.i4.1
0x1fd03  stloc.1
0x1fd04  br.s     loc_1FD1A
0x1fd06  ldloc.3
0x1fd07  callvirt instance string [System]System.Uri::get_Scheme()
0x1fd0c  ldsfld   string [System]System.Uri::UriSchemeHttps
0x1fd11  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1fd16  brfalse.s loc_1FD1A
0x1fd18  ldc.i4.1
0x1fd19  stloc.2
0x1fd1a  ldloc.s  0x10
0x1fd1c  ldc.i4.1
0x1fd1d  add
0x1fd1e  stloc.s  0x10
0x1fd20  ldloc.s  0x10
0x1fd22  ldloc.s  0xF
0x1fd24  ldlen
0x1fd25  conv.i4
0x1fd26  blt.s    loc_1FCEA
0x1fd28  ldloc.0
0x1fd29  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceDescription [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Description()
0x1fd2e  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IServiceBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceDescription::get_Behaviors()
0x1fd33  callvirt T0x2B00001E
0x1fd38  stloc.s  4
0x1fd3a  ldloc.s  4
0x1fd3c  brfalse.s loc_1FD92
0x1fd3e  ldloc.1
0x1fd3f  brtrue.s loc_1FD49
0x1fd41  ldloc.s  4
0x1fd43  ldc.i4.0
0x1fd44  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceMetadataBehavior::set_HttpGetEnabled(bool)
0x1fd49  ldloc.2
0x1fd4a  brtrue.s loc_1FD54
0x1fd4c  ldloc.s  4
0x1fd4e  ldc.i4.0
0x1fd4f  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceMetadataBehavior::set_HttpsGetEnabled(bool)
0x1fd54  ldloc.s  4
0x1fd56  callvirt instance bool [System.ServiceModel]System.ServiceModel.Description.ServiceMetadataBehavior::get_HttpGetEnabled()
0x1fd5b  brfalse.s loc_1FD73
0x1fd5d  ldloc.0
0x1fd5e  ldstr    aImetadataexcha// "IMetadataExchange"
0x1fd63  call     class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeBindings::CreateMexHttpBinding()
0x1fd68  ldstr    aMex// "mex"
0x1fd6d  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint [System.ServiceModel]System.ServiceModel.ServiceHostBase::AddServiceEndpoint(string, class [System.ServiceModel]System.ServiceModel.Channels.Binding, string)
0x1fd72  pop
0x1fd73  ldloc.s  4
0x1fd75  callvirt instance bool [System.ServiceModel]System.ServiceModel.Description.ServiceMetadataBehavior::get_HttpsGetEnabled()
0x1fd7a  brfalse.s loc_1FD92
0x1fd7c  ldloc.0
0x1fd7d  ldstr    aImetadataexcha// "IMetadataExchange"
0x1fd82  call     class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeBindings::CreateMexHttpsBinding()
0x1fd87  ldstr    aMex// "mex"
0x1fd8c  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint [System.ServiceModel]System.ServiceModel.ServiceHostBase::AddServiceEndpoint(string, class [System.ServiceModel]System.ServiceModel.Channels.Binding, string)
0x1fd91  pop
0x1fd92  ldloc.1
0x1fd93  brfalse.s loc_1FDBD
0x1fd95  ldloc.0
0x1fd96  ldstr    aMicrosoftIdent// "Microsoft.IdentityModel.Protocols.WSTru"...
0x1fd9b  ldstr    aAsymmetricwind// "AsymmetricWindowsHttpBinding"
0x1fda0  newobj   instance void [System.ServiceModel]System.ServiceModel.Channels.CustomBinding::.ctor(string)
0x1fda5  ldstr    aWindows_0// "windows"
0x1fdaa  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint [System.ServiceModel]System.ServiceModel.ServiceHostBase::AddServiceEndpoint(string, class [System.ServiceModel]System.ServiceModel.Channels.Binding, string)
0x1fdaf  stloc.s  5
0x1fdb1  ldloc.s  5
0x1fdb3  ldstr    aAsymmetricwind_0// "AsymmetricWindowsHttp"
0x1fdb8  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::set_Name(string)
0x1fdbd  ldloc.2
0x1fdbe  brfalse  loc_1FECA
0x1fdc3  ldloc.0
0x1fdc4  ldstr    aMicrosoftIdent// "Microsoft.IdentityModel.Protocols.WSTru"...
0x1fdc9  ldstr    aAsymmetricwind_1// "AsymmetricWindowsHttpsBinding"
0x1fdce  newobj   instance void [System.ServiceModel]System.ServiceModel.Channels.CustomBinding::.ctor(string)
0x1fdd3  ldstr    aWindows_0// "windows"
0x1fdd8  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint [System.ServiceModel]System.ServiceModel.ServiceHostBase::AddServiceEndpoint(string, class [System.ServiceModel]System.ServiceModel.Channels.Binding, string)
0x1fddd  stloc.s  6
0x1fddf  ldloc.s  6
0x1fde1  ldstr    aAsymmetricwind_2// "AsymmetricWindowsHttps"
0x1fde6  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::set_Name(string)
0x1fdeb  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0x1fdf0  stloc.s  7
0x1fdf2  ldnull
0x1fdf3  stloc.s  8
0x1fdf5  ldloc.s  7
0x1fdf7  brfalse.s loc_1FE56
0x1fdf9  ldloc.s  7
0x1fdfb  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x1fe00  ldc.i4.s 0x18
0x1fe02  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x1fe07  brtrue.s loc_1FE29
0x1fe09  ldloc.s  7
0x1fe0b  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x1fe10  ldc.i4.s 0x17
0x1fe12  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x1fe17  brtrue.s loc_1FE29
0x1fe19  ldloc.s  7
0x1fe1b  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x1fe20  ldc.i4.s 0x16
0x1fe22  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x1fe27  brfalse.s loc_1FE48
0x1fe29  ldstr    aHost// "host/"
0x1fe2e  ldloc.s  6
0x1fe30  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_ListenUri()
0x1fe35  callvirt instance string [System]System.Uri::get_Host()
0x1fe3a  call     string [mscorlib]System.String::Concat(string, string)
0x1fe3f  call     class [System.ServiceModel]System.ServiceModel.EndpointIdentity [System.ServiceModel]System.ServiceModel.EndpointIdentity::CreateSpnIdentity(string)
0x1fe44  stloc.s  8
0x1fe46  br.s     loc_1FE56
0x1fe48  ldloc.s  7
0x1fe4a  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x1fe4f  call     class [System.ServiceModel]System.ServiceModel.EndpointIdentity [System.ServiceModel]System.ServiceModel.EndpointIdentity::CreateUpnIdentity(string)
0x1fe54  stloc.s  8
0x1fe56  ldloc.s  6
0x1fe58  ldloc.s  6
0x1fe5a  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Address()
0x1fe5f  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x1fe64  ldloc.s  8
0x1fe66  ldloc.s  6
0x1fe68  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Address()
0x1fe6d  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.AddressHeaderCollection [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Headers()
0x1fe72  newobj   instance void [System.ServiceModel]System.ServiceModel.EndpointAddress::.ctor(class [System]System.Uri, class [System.ServiceModel]System.ServiceModel.EndpointIdentity, class [System.ServiceModel]System.ServiceModel.Channels.AddressHeaderCollection)
0x1fe77  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::set_Address(class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x1fe7c  ldloc.0
0x1fe7d  ldstr    aMicrosoftIdent// "Microsoft.IdentityModel.Protocols.WSTru"...
0x1fe82  ldstr    aAsymmetriccook// "AsymmetricCookieHttpsBinding"
0x1fe87  newobj   instance void [System.ServiceModel]System.ServiceModel.Channels.CustomBinding::.ctor(string)
0x1fe8c  ldstr    aCookie// "cookie"
0x1fe91  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint [System.ServiceModel]System.ServiceModel.ServiceHostBase::AddServiceEndpoint(string, class [System.ServiceModel]System.ServiceModel.Channels.Binding, string)
0x1fe96  stloc.s  9
0x1fe98  ldloc.s  9
0x1fe9a  ldloc.s  9
0x1fe9c  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Address()
0x1fea1  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x1fea6  ldloc.s  8
0x1fea8  ldloc.s  9
0x1feaa  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Address()
0x1feaf  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.AddressHeaderCollection [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Headers()
0x1feb4  newobj   instance void [System.ServiceModel]System.ServiceModel.EndpointAddress::.ctor(class [System]System.Uri, class [System.ServiceModel]System.ServiceModel.EndpointIdentity, class [System.ServiceModel]System.ServiceModel.Channels.AddressHeaderCollection)
0x1feb9  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::set_Address(class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x1febe  ldloc.s  9
0x1fec0  ldstr    aAsymmetriccook_0// "AsymmetricCookieHttps"
0x1fec5  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::set_Name(string)
0x1feca  ldloc.0
0x1fecb  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceDescription [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Description()
0x1fed0  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpointCollection [System.ServiceModel]System.ServiceModel.Description.ServiceDescription::get_Endpoints()
0x1fed5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::GetEnumerator()
0x1feda  stloc.s  0x11
0x1fedc  br       loc_1FF77
0x1fee1  ldloc.s  0x11
0x1fee3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::get_Current()
0x1fee8  stloc.s  0xA
0x1feea  ldloc.s  0xA
0x1feec  callvirt instance string [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Name()
0x1fef1  ldstr    aAsymmetric// "Asymmetric"
0x1fef6  ldc.i4.5
0x1fef7  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x1fefc  brfalse.s loc_1FF77
0x1fefe  ldloc.s  0xA
0x1ff00  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x1ff05  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Channels.Binding::CreateBindingElements()
0x1ff0a  stloc.s  0xB
0x1ff0c  ldloc.s  0xB
0x1ff0e  newobj   instance void [System.ServiceModel]System.ServiceModel.Channels.CustomBinding::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Channels.BindingElement>)
0x1ff13  stloc.s  0xC
0x1ff15  ldloc.s  0xB
0x1ff17  callvirt T0x2B00001D
0x1ff1c  stloc.s  0xD
0x1ff1e  newobj   instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.RsaSecurityTokenParameters::.ctor()
0x1ff23  stloc.s  0xE
0x1ff25  ldloc.s  0xE
0x1ff27  ldc.i4.1
0x1ff28  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters::set_InclusionMode(valuetype [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode)
0x1ff2d  ldloc.s  0xE
0x1ff2f  ldc.i4.0
0x1ff30  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters::set_RequireDerivedKeys(bool)
0x1ff35  ldloc.s  0xD
0x1ff37  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_OptionalEndpointSupportingTokenParameters()
0x1ff3c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Endorsing()
0x1ff41  ldloc.s  0xE
0x1ff43  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::Add(var<u1>)
0x1ff48  ldc.i4.0
0x1ff49  ldloc.s  0xA
0x1ff4b  callvirt instance string [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Name()
0x1ff50  ldstr    aCookie_0// "Cookie"
0x1ff55  ldc.i4.5
0x1ff56  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1ff5b  bgt.s    loc_1FF6E
0x1ff5d  ldloc.s  0xD
0x1ff5f  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x1ff64  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Endorsing()
0x1ff69  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::Clear()
0x1ff6e  ldloc.s  0xA
0x1ff70  ldloc.s  0xC
0x1ff72  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::set_Binding(class [System.ServiceModel]System.ServiceModel.Channels.Binding)
0x1ff77  ldloc.s  0x11
0x1ff79  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1ff7e  brtrue   loc_1FEE1
0x1ff83  leave.s  loc_1FF91
0x1ff85  ldloc.s  0x11
0x1ff87  brfalse.s loc_1FF90
0x1ff89  ldloc.s  0x11
0x1ff8b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ff90  endfinally
0x1ff91  ldloc.0
0x1ff92  call     void [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityTokenServiceBehavior::Attach(class [System.ServiceModel]System.ServiceModel.ServiceHostBase)
0x1ff97  ldc.i4   0x1005DE
0x1ff9c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1ffa1  ldc.i4.s 0x64
0x1ffa3  ldstr    aStsActiveHostF// "STS Active Host Factory: The SecurityTo"...
0x1ffa8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1ffad  ldloc.0
0x1ffae  ret
```
