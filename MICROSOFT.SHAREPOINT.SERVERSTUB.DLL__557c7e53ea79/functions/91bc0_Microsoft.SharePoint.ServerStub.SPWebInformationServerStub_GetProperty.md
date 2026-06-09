# Microsoft.SharePoint.ServerStub.SPWebInformationServerStub::GetProperty

- ea: `0x91bc0`
- end: `0x91dec`
- name: `Microsoft.SharePoint.ServerStub.SPWebInformationServerStub::GetProperty`
- size: `556`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x91bc0`

## string_xrefs

- `0x91c23`: `Created`
- `0x91d07`: `Created`
- `0x91c83`: `WebTemplate`
- `0x91db8`: `WebTemplate`
- `0x91c17`: `Configuration`
- `0x91cef`: `Configuration`
- `0x91c90`: `WebTemplateId`
- `0x91dcb`: `WebTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x91bc0  ldarg.2
0x91bc1  brtrue.s loc_91BCE
0x91bc3  ldstr    aPropname// "propName"
0x91bc8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x91bcd  throw
0x91bce  ldarg.3
0x91bcf  brtrue.s loc_91BDC
0x91bd1  ldstr    aProxycontext// "proxyContext"
0x91bd6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x91bdb  throw
0x91bdc  ldarg.1
0x91bdd  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation
0x91be2  stloc.0
0x91be3  ldloc.0
0x91be4  brtrue.s loc_91BF1
0x91be6  ldstr    aTarget// "target"
0x91beb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x91bf0  throw
0x91bf1  ldarg.0
0x91bf2  ldarg.2
0x91bf3  ldarg.3
0x91bf4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91bf9  starg.s  2
0x91bfb  ldarg.2
0x91bfc  dup
0x91bfd  stloc.1
0x91bfe  brfalse  loc_91DE2
0x91c03  volatile.
0x91c05  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001824-1
0x91c0a  brtrue   loc_91CA3
0x91c0f  ldc.i4.s 0xB
0x91c11  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x91c16  dup
0x91c17  ldstr    aConfiguration// "Configuration"
0x91c1c  ldc.i4.0
0x91c1d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91c22  dup
0x91c23  ldstr    aCreated// "Created"
0x91c28  ldc.i4.1
0x91c29  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91c2e  dup
0x91c2f  ldstr    aDescription// "Description"
0x91c34  ldc.i4.2
0x91c35  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91c3a  dup
0x91c3b  ldstr    aId_0// "Id"
0x91c40  ldc.i4.3
0x91c41  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91c46  dup
0x91c47  ldstr    aLanguage// "Language"
0x91c4c  ldc.i4.4
0x91c4d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91c52  dup
0x91c53  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x91c58  ldc.i4.5
0x91c59  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91c5e  dup
0x91c5f  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x91c64  ldc.i4.6
0x91c65  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91c6a  dup
0x91c6b  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x91c70  ldc.i4.7
0x91c71  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91c76  dup
0x91c77  ldstr    aTitle// "Title"
0x91c7c  ldc.i4.8
0x91c7d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91c82  dup
0x91c83  ldstr    aWebtemplate// "WebTemplate"
0x91c88  ldc.i4.s 9
0x91c8a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91c8f  dup
0x91c90  ldstr    aWebtemplateid// "WebTemplateId"
0x91c95  ldc.i4.s 0xA
0x91c97  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x91c9c  volatile.
0x91c9e  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001824-1
0x91ca3  volatile.
0x91ca5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001824-1
0x91caa  ldloc.1
0x91cab  ldloca.s 2
0x91cad  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x91cb2  brfalse  loc_91DE2
0x91cb7  ldloc.2
0x91cb8  switch   loc_91CEE, loc_91D06, loc_91D1E, loc_91D31, loc_91D49, loc_91D61, loc_91D79, loc_91D91, loc_91DA4, loc_91DB7, loc_91DCA
0x91ce9  br       loc_91DE2
0x91cee  ldarg.0
0x91cef  ldstr    aConfiguration// "Configuration"
0x91cf4  ldarg.3
0x91cf5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91cfa  ldloc.0
0x91cfb  callvirt instance int16 [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Configuration()
0x91d00  box      [mscorlib]System.Int16
0x91d05  ret
0x91d06  ldarg.0
0x91d07  ldstr    aCreated// "Created"
0x91d0c  ldarg.3
0x91d0d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91d12  ldloc.0
0x91d13  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Created()
0x91d18  box      [mscorlib]System.DateTime
0x91d1d  ret
0x91d1e  ldarg.0
0x91d1f  ldstr    aDescription// "Description"
0x91d24  ldarg.3
0x91d25  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91d2a  ldloc.0
0x91d2b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Description()
0x91d30  ret
0x91d31  ldarg.0
0x91d32  ldstr    aId_0// "Id"
0x91d37  ldarg.3
0x91d38  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91d3d  ldloc.0
0x91d3e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Id()
0x91d43  box      [mscorlib]System.Guid
0x91d48  ret
0x91d49  ldarg.0
0x91d4a  ldstr    aLanguage// "Language"
0x91d4f  ldarg.3
0x91d50  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91d55  ldloc.0
0x91d56  callvirt instance unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Language()
0x91d5b  box      [mscorlib]System.UInt32
0x91d60  ret
0x91d61  ldarg.0
0x91d62  ldstr    aLastitemmodifi// "LastItemModifiedDate"
0x91d67  ldarg.3
0x91d68  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91d6d  ldloc.0
0x91d6e  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_LastItemModifiedDate()
0x91d73  box      [mscorlib]System.DateTime
0x91d78  ret
0x91d79  ldarg.0
0x91d7a  ldstr    aLastitemusermo// "LastItemUserModifiedDate"
0x91d7f  ldarg.3
0x91d80  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91d85  ldloc.0
0x91d86  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_LastItemUserModifiedDate()
0x91d8b  box      [mscorlib]System.DateTime
0x91d90  ret
0x91d91  ldarg.0
0x91d92  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x91d97  ldarg.3
0x91d98  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91d9d  ldloc.0
0x91d9e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_ServerRelativeUrl()
0x91da3  ret
0x91da4  ldarg.0
0x91da5  ldstr    aTitle// "Title"
0x91daa  ldarg.3
0x91dab  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91db0  ldloc.0
0x91db1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_Title()
0x91db6  ret
0x91db7  ldarg.0
0x91db8  ldstr    aWebtemplate// "WebTemplate"
0x91dbd  ldarg.3
0x91dbe  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91dc3  ldloc.0
0x91dc4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_WebTemplate()
0x91dc9  ret
0x91dca  ldarg.0
0x91dcb  ldstr    aWebtemplateid// "WebTemplateId"
0x91dd0  ldarg.3
0x91dd1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91dd6  ldloc.0
0x91dd7  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPWebInformation::get_WebTemplateId()
0x91ddc  box      [mscorlib]System.Int32
0x91de1  ret
0x91de2  ldarg.0
0x91de3  ldarg.1
0x91de4  ldarg.2
0x91de5  ldarg.3
0x91de6  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91deb  ret
```
