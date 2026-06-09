# Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter::SetProperty

- ea: `0x1b70`
- end: `0x1ce9`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter::SetProperty`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1b70`

## string_xrefs

- `0x1c27`: `WebTemplateExtensionId`

## pseudocode

```c

```

## disassembly

```asm
0x1b70  ldarg.s  4
0x1b72  brtrue.s loc_1B7F
0x1b74  ldstr    aProxycontext// "proxyContext"
0x1b79  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1b7e  throw
0x1b7f  ldarg.1
0x1b80  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest
0x1b85  stloc.0
0x1b86  ldloc.0
0x1b87  brtrue.s loc_1B94
0x1b89  ldstr    aTarget// "target"
0x1b8e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1b93  throw
0x1b94  ldarg.2
0x1b95  brtrue.s loc_1BA2
0x1b97  ldstr    aPropname// "propName"
0x1b9c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1ba1  throw
0x1ba2  ldarg.3
0x1ba3  brtrue.s loc_1BB0
0x1ba5  ldstr    aPropvalue// "propValue"
0x1baa  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1baf  throw
0x1bb0  ldarg.0
0x1bb1  ldarg.2
0x1bb2  ldarg.s  4
0x1bb4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1bb9  starg.s  2
0x1bbb  ldarg.2
0x1bbc  dup
0x1bbd  stloc.1
0x1bbe  brfalse  loc_1CDD
0x1bc3  volatile.
0x1bc5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600003c-1
0x1bca  brtrue.s loc_1C39
0x1bcc  ldc.i4.8
0x1bcd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x1bd2  dup
0x1bd3  ldstr    aAllowfileshari// "AllowFileSharingForGuestUsers"
0x1bd8  ldc.i4.0
0x1bd9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1bde  dup
0x1bdf  ldstr    aClassification// "Classification"
0x1be4  ldc.i4.1
0x1be5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1bea  dup
0x1beb  ldstr    aDescription// "Description"
0x1bf0  ldc.i4.2
0x1bf1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1bf6  dup
0x1bf7  ldstr    aLcid_0// "lcid"
0x1bfc  ldc.i4.3
0x1bfd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1c02  dup
0x1c03  ldstr    aSitedesignid// "SiteDesignId"
0x1c08  ldc.i4.4
0x1c09  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1c0e  dup
0x1c0f  ldstr    aTitle// "Title"
0x1c14  ldc.i4.5
0x1c15  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1c1a  dup
0x1c1b  ldstr    aUrl// "Url"
0x1c20  ldc.i4.6
0x1c21  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1c26  dup
0x1c27  ldstr    aWebtemplateext// "WebTemplateExtensionId"
0x1c2c  ldc.i4.7
0x1c2d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1c32  volatile.
0x1c34  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600003c-1
0x1c39  volatile.
0x1c3b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600003c-1
0x1c40  ldloc.1
0x1c41  ldloca.s 2
0x1c43  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x1c48  brfalse  loc_1CDD
0x1c4d  ldloc.2
0x1c4e  switch   loc_1C75, loc_1C82, loc_1C8F, loc_1C9C, loc_1CA9, loc_1CB6, loc_1CC3, loc_1CD0
0x1c73  br.s     loc_1CDD
0x1c75  ldloc.0
0x1c76  ldarg.3
0x1c77  callvirt T0x2B000007
0x1c7c  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_AllowFileSharingForGuestUsers(bool)
0x1c81  ret
0x1c82  ldloc.0
0x1c83  ldarg.3
0x1c84  callvirt T0x2B000001
0x1c89  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_Classification(string)
0x1c8e  ret
0x1c8f  ldloc.0
0x1c90  ldarg.3
0x1c91  callvirt T0x2B000001
0x1c96  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_Description(string)
0x1c9b  ret
0x1c9c  ldloc.0
0x1c9d  ldarg.3
0x1c9e  callvirt T0x2B000002
0x1ca3  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_lcid(int32)
0x1ca8  ret
0x1ca9  ldloc.0
0x1caa  ldarg.3
0x1cab  callvirt T0x2B000006
0x1cb0  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_SiteDesignId(valuetype [mscorlib]System.Guid)
0x1cb5  ret
0x1cb6  ldloc.0
0x1cb7  ldarg.3
0x1cb8  callvirt T0x2B000001
0x1cbd  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_Title(string)
0x1cc2  ret
0x1cc3  ldloc.0
0x1cc4  ldarg.3
0x1cc5  callvirt T0x2B000001
0x1cca  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_Url(string)
0x1ccf  ret
0x1cd0  ldloc.0
0x1cd1  ldarg.3
0x1cd2  callvirt T0x2B000006
0x1cd7  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::set_WebTemplateExtensionId(valuetype [mscorlib]System.Guid)
0x1cdc  ret
0x1cdd  ldarg.0
0x1cde  ldarg.1
0x1cdf  ldarg.2
0x1ce0  ldarg.3
0x1ce1  ldarg.s  4
0x1ce3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1ce8  ret
```
