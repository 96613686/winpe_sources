# Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub::SetProperty

- ea: `0x887f0`
- end: `0x88b41`
- name: `Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub::SetProperty`
- size: `849`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x887f0`

## string_xrefs

- `0x88849`: `ClientSideComponentId`
- `0x88976`: `ClientSideComponentId`
- `0x88855`: `ClientSideComponentProperties`
- `0x88992`: `ClientSideComponentProperties`
- `0x88861`: `CommandUIExtension`
- `0x889ae`: `CommandUIExtension`

## pseudocode

```c

```

## disassembly

```asm
0x887f0  ldarg.s  4
0x887f2  brtrue.s loc_887FF
0x887f4  ldstr    aProxycontext// "proxyContext"
0x887f9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x887fe  throw
0x887ff  ldarg.1
0x88800  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction
0x88805  stloc.0
0x88806  ldloc.0
0x88807  brtrue.s loc_88814
0x88809  ldstr    aTarget// "target"
0x8880e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x88813  throw
0x88814  ldarg.2
0x88815  brtrue.s loc_88822
0x88817  ldstr    aPropname// "propName"
0x8881c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x88821  throw
0x88822  ldarg.0
0x88823  ldarg.2
0x88824  ldarg.s  4
0x88826  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8882b  starg.s  2
0x8882d  ldarg.2
0x8882e  dup
0x8882f  stloc.1
0x88830  brfalse  loc_88B35
0x88835  volatile.
0x88837  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016e4-1
0x8883c  brtrue   loc_88916
0x88841  ldc.i4.s 0x10
0x88843  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x88848  dup
0x88849  ldstr    aClientsidecomp// "ClientSideComponentId"
0x8884e  ldc.i4.0
0x8884f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88854  dup
0x88855  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x8885a  ldc.i4.1
0x8885b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88860  dup
0x88861  ldstr    aCommanduiexten// "CommandUIExtension"
0x88866  ldc.i4.2
0x88867  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8886c  dup
0x8886d  ldstr    aDescription// "Description"
0x88872  ldc.i4.3
0x88873  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88878  dup
0x88879  ldstr    aGroup// "Group"
0x8887e  ldc.i4.4
0x8887f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88884  dup
0x88885  ldstr    aImageurl// "ImageUrl"
0x8888a  ldc.i4.5
0x8888b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88890  dup
0x88891  ldstr    aLocation// "Location"
0x88896  ldc.i4.6
0x88897  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8889c  dup
0x8889d  ldstr    aName// "Name"
0x888a2  ldc.i4.7
0x888a3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x888a8  dup
0x888a9  ldstr    aRegistrationid// "RegistrationId"
0x888ae  ldc.i4.8
0x888af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x888b4  dup
0x888b5  ldstr    aRegistrationty// "RegistrationType"
0x888ba  ldc.i4.s 9
0x888bc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x888c1  dup
0x888c2  ldstr    aRights// "Rights"
0x888c7  ldc.i4.s 0xA
0x888c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x888ce  dup
0x888cf  ldstr    aScriptblock// "ScriptBlock"
0x888d4  ldc.i4.s 0xB
0x888d6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x888db  dup
0x888dc  ldstr    aScriptsrc// "ScriptSrc"
0x888e1  ldc.i4.s 0xC
0x888e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x888e8  dup
0x888e9  ldstr    aSequence// "Sequence"
0x888ee  ldc.i4.s 0xD
0x888f0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x888f5  dup
0x888f6  ldstr    aTitle// "Title"
0x888fb  ldc.i4.s 0xE
0x888fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88902  dup
0x88903  ldstr    aUrl// "Url"
0x88908  ldc.i4.s 0xF
0x8890a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8890f  volatile.
0x88911  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016e4-1
0x88916  volatile.
0x88918  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016e4-1
0x8891d  ldloc.1
0x8891e  ldloca.s 2
0x88920  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x88925  brfalse  loc_88B35
0x8892a  ldloc.2
0x8892b  switch   loc_88975, loc_88991, loc_889AD, loc_889C9, loc_889E5, loc_88A01, loc_88A1D, loc_88A39, loc_88A55, loc_88A71, loc_88A8D, loc_88AA9, loc_88AC5, loc_88AE1, loc_88AFD, loc_88B19
0x88970  br       loc_88B35
0x88975  ldarg.0
0x88976  ldstr    aClientsidecomp// "ClientSideComponentId"
0x8897b  ldarg.s  4
0x8897d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88982  ldloc.0
0x88983  ldarg.3
0x88984  ldarg.s  4
0x88986  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToGuid(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8898b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_ClientSideComponentId(valuetype [mscorlib]System.Guid)
0x88990  ret
0x88991  ldarg.0
0x88992  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x88997  ldarg.s  4
0x88999  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8899e  ldloc.0
0x8899f  ldarg.3
0x889a0  ldarg.s  4
0x889a2  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x889a7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_ClientSideComponentProperties(string)
0x889ac  ret
0x889ad  ldarg.0
0x889ae  ldstr    aCommanduiexten// "CommandUIExtension"
0x889b3  ldarg.s  4
0x889b5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x889ba  ldloc.0
0x889bb  ldarg.3
0x889bc  ldarg.s  4
0x889be  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x889c3  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_CommandUIExtension(string)
0x889c8  ret
0x889c9  ldarg.0
0x889ca  ldstr    aDescription// "Description"
0x889cf  ldarg.s  4
0x889d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x889d6  ldloc.0
0x889d7  ldarg.3
0x889d8  ldarg.s  4
0x889da  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x889df  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Description(string)
0x889e4  ret
0x889e5  ldarg.0
0x889e6  ldstr    aGroup// "Group"
0x889eb  ldarg.s  4
0x889ed  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x889f2  ldloc.0
0x889f3  ldarg.3
0x889f4  ldarg.s  4
0x889f6  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x889fb  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Group(string)
0x88a00  ret
0x88a01  ldarg.0
0x88a02  ldstr    aImageurl// "ImageUrl"
0x88a07  ldarg.s  4
0x88a09  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88a0e  ldloc.0
0x88a0f  ldarg.3
0x88a10  ldarg.s  4
0x88a12  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88a17  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_ImageUrl(string)
0x88a1c  ret
0x88a1d  ldarg.0
0x88a1e  ldstr    aLocation// "Location"
0x88a23  ldarg.s  4
0x88a25  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88a2a  ldloc.0
0x88a2b  ldarg.3
0x88a2c  ldarg.s  4
0x88a2e  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88a33  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Location(string)
0x88a38  ret
0x88a39  ldarg.0
0x88a3a  ldstr    aName// "Name"
0x88a3f  ldarg.s  4
0x88a41  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88a46  ldloc.0
0x88a47  ldarg.3
0x88a48  ldarg.s  4
0x88a4a  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88a4f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Name(string)
0x88a54  ret
0x88a55  ldarg.0
0x88a56  ldstr    aRegistrationid// "RegistrationId"
0x88a5b  ldarg.s  4
0x88a5d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88a62  ldloc.0
0x88a63  ldarg.3
0x88a64  ldarg.s  4
0x88a66  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88a6b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_RegistrationId(string)
0x88a70  ret
0x88a71  ldarg.0
0x88a72  ldstr    aRegistrationty// "RegistrationType"
0x88a77  ldarg.s  4
0x88a79  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88a7e  ldloc.0
0x88a7f  ldarg.3
0x88a80  ldarg.s  4
0x88a82  call     T0x2B000221
0x88a87  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_RegistrationType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomActionRegistrationType)
0x88a8c  ret
0x88a8d  ldarg.0
0x88a8e  ldstr    aRights// "Rights"
0x88a93  ldarg.s  4
0x88a95  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88a9a  ldloc.0
0x88a9b  ldarg.3
0x88a9c  ldarg.s  4
0x88a9e  call     T0x2B0001FE
0x88aa3  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Rights_Client(class [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions_Client)
0x88aa8  ret
0x88aa9  ldarg.0
0x88aaa  ldstr    aScriptblock// "ScriptBlock"
0x88aaf  ldarg.s  4
0x88ab1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88ab6  ldloc.0
0x88ab7  ldarg.3
0x88ab8  ldarg.s  4
0x88aba  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88abf  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_ScriptBlock(string)
0x88ac4  ret
0x88ac5  ldarg.0
0x88ac6  ldstr    aScriptsrc// "ScriptSrc"
0x88acb  ldarg.s  4
0x88acd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88ad2  ldloc.0
0x88ad3  ldarg.3
0x88ad4  ldarg.s  4
0x88ad6  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88adb  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_ScriptSrc(string)
0x88ae0  ret
0x88ae1  ldarg.0
0x88ae2  ldstr    aSequence// "Sequence"
0x88ae7  ldarg.s  4
0x88ae9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88aee  ldloc.0
0x88aef  ldarg.3
0x88af0  ldarg.s  4
0x88af2  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88af7  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Sequence(int32)
0x88afc  ret
0x88afd  ldarg.0
0x88afe  ldstr    aTitle// "Title"
0x88b03  ldarg.s  4
0x88b05  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88b0a  ldloc.0
0x88b0b  ldarg.3
0x88b0c  ldarg.s  4
0x88b0e  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88b13  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Title(string)
0x88b18  ret
0x88b19  ldarg.0
0x88b1a  ldstr    aUrl// "Url"
0x88b1f  ldarg.s  4
0x88b21  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88b26  ldloc.0
0x88b27  ldarg.3
0x88b28  ldarg.s  4
0x88b2a  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88b2f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::set_Url(string)
0x88b34  ret
0x88b35  ldarg.0
0x88b36  ldarg.1
0x88b37  ldarg.2
0x88b38  ldarg.3
0x88b39  ldarg.s  4
0x88b3b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88b40  ret
```
