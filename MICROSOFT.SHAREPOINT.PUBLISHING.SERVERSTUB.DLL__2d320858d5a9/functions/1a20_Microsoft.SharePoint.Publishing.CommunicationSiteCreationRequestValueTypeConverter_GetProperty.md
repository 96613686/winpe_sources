# Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter::GetProperty

- ea: `0x1a20`
- end: `0x1b68`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter::GetProperty`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1a20`

## string_xrefs

- `0x1ac7`: `WebTemplateExtensionId`

## pseudocode

```c

```

## disassembly

```asm
0x1a20  ldarg.3
0x1a21  brtrue.s loc_1A2E
0x1a23  ldstr    aProxycontext// "proxyContext"
0x1a28  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1a2d  throw
0x1a2e  ldarg.1
0x1a2f  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest
0x1a34  stloc.0
0x1a35  ldloc.0
0x1a36  brtrue.s loc_1A43
0x1a38  ldstr    aTarget// "target"
0x1a3d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1a42  throw
0x1a43  ldarg.2
0x1a44  brtrue.s loc_1A51
0x1a46  ldstr    aPropname// "propName"
0x1a4b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1a50  throw
0x1a51  ldarg.0
0x1a52  ldarg.2
0x1a53  ldarg.3
0x1a54  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1a59  starg.s  2
0x1a5b  ldarg.2
0x1a5c  dup
0x1a5d  stloc.1
0x1a5e  brfalse  loc_1B5E
0x1a63  volatile.
0x1a65  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600003b-1
0x1a6a  brtrue.s loc_1AD9
0x1a6c  ldc.i4.8
0x1a6d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x1a72  dup
0x1a73  ldstr    aAllowfileshari// "AllowFileSharingForGuestUsers"
0x1a78  ldc.i4.0
0x1a79  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1a7e  dup
0x1a7f  ldstr    aClassification// "Classification"
0x1a84  ldc.i4.1
0x1a85  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1a8a  dup
0x1a8b  ldstr    aDescription// "Description"
0x1a90  ldc.i4.2
0x1a91  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1a96  dup
0x1a97  ldstr    aLcid_0// "lcid"
0x1a9c  ldc.i4.3
0x1a9d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1aa2  dup
0x1aa3  ldstr    aSitedesignid// "SiteDesignId"
0x1aa8  ldc.i4.4
0x1aa9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1aae  dup
0x1aaf  ldstr    aTitle// "Title"
0x1ab4  ldc.i4.5
0x1ab5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1aba  dup
0x1abb  ldstr    aUrl// "Url"
0x1ac0  ldc.i4.6
0x1ac1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1ac6  dup
0x1ac7  ldstr    aWebtemplateext// "WebTemplateExtensionId"
0x1acc  ldc.i4.7
0x1acd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1ad2  volatile.
0x1ad4  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600003b-1
0x1ad9  volatile.
0x1adb  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600003b-1
0x1ae0  ldloc.1
0x1ae1  ldloca.s 2
0x1ae3  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x1ae8  brfalse.s loc_1B5E
0x1aea  ldloc.2
0x1aeb  switch   loc_1B12, loc_1B1E, loc_1B25, loc_1B2C, loc_1B38, loc_1B44, loc_1B4B, loc_1B52
0x1b10  br.s     loc_1B5E
0x1b12  ldloc.0
0x1b13  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_AllowFileSharingForGuestUsers()
0x1b18  box      [mscorlib]System.Boolean
0x1b1d  ret
0x1b1e  ldloc.0
0x1b1f  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_Classification()
0x1b24  ret
0x1b25  ldloc.0
0x1b26  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_Description()
0x1b2b  ret
0x1b2c  ldloc.0
0x1b2d  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_lcid()
0x1b32  box      [mscorlib]System.Int32
0x1b37  ret
0x1b38  ldloc.0
0x1b39  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_SiteDesignId()
0x1b3e  box      [mscorlib]System.Guid
0x1b43  ret
0x1b44  ldloc.0
0x1b45  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_Title()
0x1b4a  ret
0x1b4b  ldloc.0
0x1b4c  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_Url()
0x1b51  ret
0x1b52  ldloc.0
0x1b53  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_WebTemplateExtensionId()
0x1b58  box      [mscorlib]System.Guid
0x1b5d  ret
0x1b5e  ldarg.0
0x1b5f  ldarg.1
0x1b60  ldarg.2
0x1b61  ldarg.3
0x1b62  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1b67  ret
```
