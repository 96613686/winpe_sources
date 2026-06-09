# Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub::GetProperty

- ea: `0x88460`
- end: `0x887ea`
- name: `Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub::GetProperty`
- size: `906`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x88460`

## string_xrefs

- `0x884b7`: `ClientSideComponentId`
- `0x88639`: `ClientSideComponentId`
- `0x884c3`: `ClientSideComponentProperties`
- `0x88651`: `ClientSideComponentProperties`
- `0x884cf`: `CommandUIExtension`
- `0x88664`: `CommandUIExtension`

## pseudocode

```c

```

## disassembly

```asm
0x88460  ldarg.2
0x88461  brtrue.s loc_8846E
0x88463  ldstr    aPropname// "propName"
0x88468  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8846d  throw
0x8846e  ldarg.3
0x8846f  brtrue.s loc_8847C
0x88471  ldstr    aProxycontext// "proxyContext"
0x88476  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8847b  throw
0x8847c  ldarg.1
0x8847d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction
0x88482  stloc.0
0x88483  ldloc.0
0x88484  brtrue.s loc_88491
0x88486  ldstr    aTarget// "target"
0x8848b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x88490  throw
0x88491  ldarg.0
0x88492  ldarg.2
0x88493  ldarg.3
0x88494  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88499  starg.s  2
0x8849b  ldarg.2
0x8849c  dup
0x8849d  stloc.1
0x8849e  brfalse  loc_887E0
0x884a3  volatile.
0x884a5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016e3-1
0x884aa  brtrue   loc_885C5
0x884af  ldc.i4.s 0x15
0x884b1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x884b6  dup
0x884b7  ldstr    aClientsidecomp// "ClientSideComponentId"
0x884bc  ldc.i4.0
0x884bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x884c2  dup
0x884c3  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x884c8  ldc.i4.1
0x884c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x884ce  dup
0x884cf  ldstr    aCommanduiexten// "CommandUIExtension"
0x884d4  ldc.i4.2
0x884d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x884da  dup
0x884db  ldstr    aDescription// "Description"
0x884e0  ldc.i4.3
0x884e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x884e6  dup
0x884e7  ldstr    aDescriptionres// "DescriptionResource"
0x884ec  ldc.i4.4
0x884ed  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x884f2  dup
0x884f3  ldstr    aGroup// "Group"
0x884f8  ldc.i4.5
0x884f9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x884fe  dup
0x884ff  ldstr    aId_0// "Id"
0x88504  ldc.i4.6
0x88505  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8850a  dup
0x8850b  ldstr    aImageurl// "ImageUrl"
0x88510  ldc.i4.7
0x88511  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88516  dup
0x88517  ldstr    aLocation// "Location"
0x8851c  ldc.i4.8
0x8851d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88522  dup
0x88523  ldstr    aName// "Name"
0x88528  ldc.i4.s 9
0x8852a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8852f  dup
0x88530  ldstr    aRegistrationid// "RegistrationId"
0x88535  ldc.i4.s 0xA
0x88537  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8853c  dup
0x8853d  ldstr    aRegistrationty// "RegistrationType"
0x88542  ldc.i4.s 0xB
0x88544  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88549  dup
0x8854a  ldstr    aRights// "Rights"
0x8854f  ldc.i4.s 0xC
0x88551  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88556  dup
0x88557  ldstr    aScope// "Scope"
0x8855c  ldc.i4.s 0xD
0x8855e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88563  dup
0x88564  ldstr    aScriptblock// "ScriptBlock"
0x88569  ldc.i4.s 0xE
0x8856b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88570  dup
0x88571  ldstr    aScriptsrc// "ScriptSrc"
0x88576  ldc.i4.s 0xF
0x88578  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8857d  dup
0x8857e  ldstr    aSequence// "Sequence"
0x88583  ldc.i4.s 0x10
0x88585  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8858a  dup
0x8858b  ldstr    aTitle// "Title"
0x88590  ldc.i4.s 0x11
0x88592  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88597  dup
0x88598  ldstr    aTitleresource// "TitleResource"
0x8859d  ldc.i4.s 0x12
0x8859f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x885a4  dup
0x885a5  ldstr    aUrl// "Url"
0x885aa  ldc.i4.s 0x13
0x885ac  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x885b1  dup
0x885b2  ldstr    aVersionofuserc// "VersionOfUserCustomAction"
0x885b7  ldc.i4.s 0x14
0x885b9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x885be  volatile.
0x885c0  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016e3-1
0x885c5  volatile.
0x885c7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016e3-1
0x885cc  ldloc.1
0x885cd  ldloca.s 2
0x885cf  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x885d4  brfalse  loc_887E0
0x885d9  ldloc.2
0x885da  switch   loc_88638, loc_88650, loc_88663, loc_88676, loc_88689, loc_8869C, loc_886AF, loc_886C7, loc_886DA, loc_886ED, loc_88700, loc_88713, loc_8872B, loc_8873E, loc_88756, loc_88769, loc_8877C, loc_88794, loc_887A7, loc_887BA, loc_887CD
0x88633  br       loc_887E0
0x88638  ldarg.0
0x88639  ldstr    aClientsidecomp// "ClientSideComponentId"
0x8863e  ldarg.3
0x8863f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88644  ldloc.0
0x88645  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ClientSideComponentId()
0x8864a  box      [mscorlib]System.Guid
0x8864f  ret
0x88650  ldarg.0
0x88651  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x88656  ldarg.3
0x88657  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8865c  ldloc.0
0x8865d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ClientSideComponentProperties()
0x88662  ret
0x88663  ldarg.0
0x88664  ldstr    aCommanduiexten// "CommandUIExtension"
0x88669  ldarg.3
0x8866a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8866f  ldloc.0
0x88670  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_CommandUIExtension()
0x88675  ret
0x88676  ldarg.0
0x88677  ldstr    aDescription// "Description"
0x8867c  ldarg.3
0x8867d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88682  ldloc.0
0x88683  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Description()
0x88688  ret
0x88689  ldarg.0
0x8868a  ldstr    aDescriptionres// "DescriptionResource"
0x8868f  ldarg.3
0x88690  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88695  ldloc.0
0x88696  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserResource [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_DescriptionResource()
0x8869b  ret
0x8869c  ldarg.0
0x8869d  ldstr    aGroup// "Group"
0x886a2  ldarg.3
0x886a3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x886a8  ldloc.0
0x886a9  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Group()
0x886ae  ret
0x886af  ldarg.0
0x886b0  ldstr    aId_0// "Id"
0x886b5  ldarg.3
0x886b6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x886bb  ldloc.0
0x886bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Id()
0x886c1  box      [mscorlib]System.Guid
0x886c6  ret
0x886c7  ldarg.0
0x886c8  ldstr    aImageurl// "ImageUrl"
0x886cd  ldarg.3
0x886ce  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x886d3  ldloc.0
0x886d4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ImageUrl()
0x886d9  ret
0x886da  ldarg.0
0x886db  ldstr    aLocation// "Location"
0x886e0  ldarg.3
0x886e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x886e6  ldloc.0
0x886e7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Location()
0x886ec  ret
0x886ed  ldarg.0
0x886ee  ldstr    aName// "Name"
0x886f3  ldarg.3
0x886f4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x886f9  ldloc.0
0x886fa  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Name()
0x886ff  ret
0x88700  ldarg.0
0x88701  ldstr    aRegistrationid// "RegistrationId"
0x88706  ldarg.3
0x88707  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8870c  ldloc.0
0x8870d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_RegistrationId()
0x88712  ret
0x88713  ldarg.0
0x88714  ldstr    aRegistrationty// "RegistrationType"
0x88719  ldarg.3
0x8871a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8871f  ldloc.0
0x88720  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomActionRegistrationType [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_RegistrationType()
0x88725  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomActionRegistrationType
0x8872a  ret
0x8872b  ldarg.0
0x8872c  ldstr    aRights// "Rights"
0x88731  ldarg.3
0x88732  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88737  ldloc.0
0x88738  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions_Client [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Rights_Client()
0x8873d  ret
0x8873e  ldarg.0
0x8873f  ldstr    aScope// "Scope"
0x88744  ldarg.3
0x88745  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8874a  ldloc.0
0x8874b  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomActionScope [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Scope()
0x88750  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomActionScope
0x88755  ret
0x88756  ldarg.0
0x88757  ldstr    aScriptblock// "ScriptBlock"
0x8875c  ldarg.3
0x8875d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88762  ldloc.0
0x88763  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ScriptBlock()
0x88768  ret
0x88769  ldarg.0
0x8876a  ldstr    aScriptsrc// "ScriptSrc"
0x8876f  ldarg.3
0x88770  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88775  ldloc.0
0x88776  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ScriptSrc()
0x8877b  ret
0x8877c  ldarg.0
0x8877d  ldstr    aSequence// "Sequence"
0x88782  ldarg.3
0x88783  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88788  ldloc.0
0x88789  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Sequence()
0x8878e  box      [mscorlib]System.Int32
0x88793  ret
0x88794  ldarg.0
0x88795  ldstr    aTitle// "Title"
0x8879a  ldarg.3
0x8879b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x887a0  ldloc.0
0x887a1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Title()
0x887a6  ret
0x887a7  ldarg.0
0x887a8  ldstr    aTitleresource// "TitleResource"
0x887ad  ldarg.3
0x887ae  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x887b3  ldloc.0
0x887b4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserResource [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_TitleResource()
0x887b9  ret
0x887ba  ldarg.0
0x887bb  ldstr    aUrl// "Url"
0x887c0  ldarg.3
0x887c1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x887c6  ldloc.0
0x887c7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Url()
0x887cc  ret
0x887cd  ldarg.0
0x887ce  ldstr    aVersionofuserc// "VersionOfUserCustomAction"
0x887d3  ldarg.3
0x887d4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x887d9  ldloc.0
0x887da  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_VersionOfUserCustomAction_Client()
0x887df  ret
0x887e0  ldarg.0
0x887e1  ldarg.1
0x887e2  ldarg.2
0x887e3  ldarg.3
0x887e4  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x887e9  ret
```
