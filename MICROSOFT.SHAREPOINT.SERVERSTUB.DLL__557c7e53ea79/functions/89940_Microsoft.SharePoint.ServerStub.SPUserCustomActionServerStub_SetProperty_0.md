# Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub::SetProperty_0

- ea: `0x89940`
- end: `0x89c71`
- name: `Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub::SetProperty_0`
- size: `817`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x89940`

## string_xrefs

- `0x89999`: `ClientSideComponentId`
- `0x89ac6`: `ClientSideComponentId`
- `0x899a5`: `ClientSideComponentProperties`
- `0x89ae0`: `ClientSideComponentProperties`
- `0x899b1`: `CommandUIExtension`
- `0x89afa`: `CommandUIExtension`

## pseudocode

```c

```

## disassembly

```asm
0x89940  ldarg.s  4
0x89942  brtrue.s loc_8994F
0x89944  ldstr    aProxycontext// "proxyContext"
0x89949  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8994e  throw
0x8994f  ldarg.1
0x89950  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction
0x89955  stloc.0
0x89956  ldloc.0
0x89957  brtrue.s loc_89964
0x89959  ldstr    aTarget// "target"
0x8995e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x89963  throw
0x89964  ldarg.2
0x89965  brtrue.s loc_89972
0x89967  ldstr    aPropname// "propName"
0x8996c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x89971  throw
0x89972  ldarg.0
0x89973  ldarg.2
0x89974  ldarg.s  4
0x89976  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8997b  starg.s  2
0x8997d  ldarg.2
0x8997e  dup
0x8997f  stloc.1
0x89980  brfalse  loc_89C65
0x89985  volatile.
0x89987  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016f0-1
0x8998c  brtrue   loc_89A66
0x89991  ldc.i4.s 0x10
0x89993  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x89998  dup
0x89999  ldstr    aClientsidecomp// "ClientSideComponentId"
0x8999e  ldc.i4.0
0x8999f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x899a4  dup
0x899a5  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x899aa  ldc.i4.1
0x899ab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x899b0  dup
0x899b1  ldstr    aCommanduiexten// "CommandUIExtension"
0x899b6  ldc.i4.2
0x899b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x899bc  dup
0x899bd  ldstr    aDescription// "Description"
0x899c2  ldc.i4.3
0x899c3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x899c8  dup
0x899c9  ldstr    aGroup// "Group"
0x899ce  ldc.i4.4
0x899cf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x899d4  dup
0x899d5  ldstr    aImageurl// "ImageUrl"
0x899da  ldc.i4.5
0x899db  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x899e0  dup
0x899e1  ldstr    aLocation// "Location"
0x899e6  ldc.i4.6
0x899e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x899ec  dup
0x899ed  ldstr    aName// "Name"
0x899f2  ldc.i4.7
0x899f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x899f8  dup
0x899f9  ldstr    aRegistrationid// "RegistrationId"
0x899fe  ldc.i4.8
0x899ff  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x89a04  dup
0x89a05  ldstr    aRegistrationty// "RegistrationType"
0x89a0a  ldc.i4.s 9
0x89a0c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x89a11  dup
0x89a12  ldstr    aRights// "Rights"
0x89a17  ldc.i4.s 0xA
0x89a19  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x89a1e  dup
0x89a1f  ldstr    aScriptblock// "ScriptBlock"
0x89a24  ldc.i4.s 0xB
0x89a26  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x89a2b  dup
0x89a2c  ldstr    aScriptsrc// "ScriptSrc"
0x89a31  ldc.i4.s 0xC
0x89a33  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x89a38  dup
0x89a39  ldstr    aSequence// "Sequence"
0x89a3e  ldc.i4.s 0xD
0x89a40  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x89a45  dup
0x89a46  ldstr    aTitle// "Title"
0x89a4b  ldc.i4.s 0xE
0x89a4d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x89a52  dup
0x89a53  ldstr    aUrl// "Url"
0x89a58  ldc.i4.s 0xF
0x89a5a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x89a5f  volatile.
0x89a61  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016f0-1
0x89a66  volatile.
0x89a68  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016f0-1
0x89a6d  ldloc.1
0x89a6e  ldloca.s 2
0x89a70  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x89a75  brfalse  loc_89C65
0x89a7a  ldloc.2
0x89a7b  switch   loc_89AC5, loc_89ADF, loc_89AF9, loc_89B13, loc_89B2D, loc_89B47, loc_89B61, loc_89B7B, loc_89B95, loc_89BAF, loc_89BC9, loc_89BE3, loc_89BFD, loc_89C17, loc_89C31, loc_89C4B
0x89ac0  br       loc_89C65
0x89ac5  ldarg.0
0x89ac6  ldstr    aClientsidecomp// "ClientSideComponentId"
0x89acb  ldarg.s  4
0x89acd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89ad2  ldloc.0
0x89ad3  ldarg.3
0x89ad4  callvirt T0x2B00002D
0x89ad9  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_ClientSideComponentId(valuetype [mscorlib]System.Guid)
0x89ade  ret
0x89adf  ldarg.0
0x89ae0  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x89ae5  ldarg.s  4
0x89ae7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89aec  ldloc.0
0x89aed  ldarg.3
0x89aee  callvirt T0x2B000008
0x89af3  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_ClientSideComponentProperties(string)
0x89af8  ret
0x89af9  ldarg.0
0x89afa  ldstr    aCommanduiexten// "CommandUIExtension"
0x89aff  ldarg.s  4
0x89b01  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89b06  ldloc.0
0x89b07  ldarg.3
0x89b08  callvirt T0x2B000008
0x89b0d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_CommandUIExtension(string)
0x89b12  ret
0x89b13  ldarg.0
0x89b14  ldstr    aDescription// "Description"
0x89b19  ldarg.s  4
0x89b1b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89b20  ldloc.0
0x89b21  ldarg.3
0x89b22  callvirt T0x2B000008
0x89b27  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Description(string)
0x89b2c  ret
0x89b2d  ldarg.0
0x89b2e  ldstr    aGroup// "Group"
0x89b33  ldarg.s  4
0x89b35  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89b3a  ldloc.0
0x89b3b  ldarg.3
0x89b3c  callvirt T0x2B000008
0x89b41  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Group(string)
0x89b46  ret
0x89b47  ldarg.0
0x89b48  ldstr    aImageurl// "ImageUrl"
0x89b4d  ldarg.s  4
0x89b4f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89b54  ldloc.0
0x89b55  ldarg.3
0x89b56  callvirt T0x2B000008
0x89b5b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_ImageUrl(string)
0x89b60  ret
0x89b61  ldarg.0
0x89b62  ldstr    aLocation// "Location"
0x89b67  ldarg.s  4
0x89b69  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89b6e  ldloc.0
0x89b6f  ldarg.3
0x89b70  callvirt T0x2B000008
0x89b75  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Location(string)
0x89b7a  ret
0x89b7b  ldarg.0
0x89b7c  ldstr    aName// "Name"
0x89b81  ldarg.s  4
0x89b83  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89b88  ldloc.0
0x89b89  ldarg.3
0x89b8a  callvirt T0x2B000008
0x89b8f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Name(string)
0x89b94  ret
0x89b95  ldarg.0
0x89b96  ldstr    aRegistrationid// "RegistrationId"
0x89b9b  ldarg.s  4
0x89b9d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89ba2  ldloc.0
0x89ba3  ldarg.3
0x89ba4  callvirt T0x2B000008
0x89ba9  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_RegistrationId(string)
0x89bae  ret
0x89baf  ldarg.0
0x89bb0  ldstr    aRegistrationty// "RegistrationType"
0x89bb5  ldarg.s  4
0x89bb7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89bbc  ldloc.0
0x89bbd  ldarg.3
0x89bbe  callvirt T0x2B000223
0x89bc3  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_RegistrationType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomActionRegistrationType)
0x89bc8  ret
0x89bc9  ldarg.0
0x89bca  ldstr    aRights// "Rights"
0x89bcf  ldarg.s  4
0x89bd1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89bd6  ldloc.0
0x89bd7  ldarg.3
0x89bd8  callvirt T0x2B0001FF
0x89bdd  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Rights_Client(class [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions_Client)
0x89be2  ret
0x89be3  ldarg.0
0x89be4  ldstr    aScriptblock// "ScriptBlock"
0x89be9  ldarg.s  4
0x89beb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89bf0  ldloc.0
0x89bf1  ldarg.3
0x89bf2  callvirt T0x2B000008
0x89bf7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_ScriptBlock(string)
0x89bfc  ret
0x89bfd  ldarg.0
0x89bfe  ldstr    aScriptsrc// "ScriptSrc"
0x89c03  ldarg.s  4
0x89c05  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89c0a  ldloc.0
0x89c0b  ldarg.3
0x89c0c  callvirt T0x2B000008
0x89c11  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_ScriptSrc(string)
0x89c16  ret
0x89c17  ldarg.0
0x89c18  ldstr    aSequence// "Sequence"
0x89c1d  ldarg.s  4
0x89c1f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89c24  ldloc.0
0x89c25  ldarg.3
0x89c26  callvirt T0x2B000009
0x89c2b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Sequence(int32)
0x89c30  ret
0x89c31  ldarg.0
0x89c32  ldstr    aTitle// "Title"
0x89c37  ldarg.s  4
0x89c39  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89c3e  ldloc.0
0x89c3f  ldarg.3
0x89c40  callvirt T0x2B000008
0x89c45  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Title(string)
0x89c4a  ret
0x89c4b  ldarg.0
0x89c4c  ldstr    aUrl// "Url"
0x89c51  ldarg.s  4
0x89c53  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89c58  ldloc.0
0x89c59  ldarg.3
0x89c5a  callvirt T0x2B000008
0x89c5f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Url(string)
0x89c64  ret
0x89c65  ldarg.0
0x89c66  ldarg.1
0x89c67  ldarg.2
0x89c68  ldarg.3
0x89c69  ldarg.s  4
0x89c6b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89c70  ret
```
