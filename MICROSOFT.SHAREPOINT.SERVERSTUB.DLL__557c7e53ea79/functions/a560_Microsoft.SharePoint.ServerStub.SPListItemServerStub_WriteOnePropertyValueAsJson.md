# Microsoft.SharePoint.ServerStub.SPListItemServerStub::WriteOnePropertyValueAsJson

- ea: `0xa560`
- end: `0xae9f`
- name: `Microsoft.SharePoint.ServerStub.SPListItemServerStub::WriteOnePropertyValueAsJson`
- size: `2367`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11e0`
- `0xa560`

## string_xrefs

- `0xa5b0`: `CommentsDisabled`
- `0xa817`: `CommentsDisabled`
- `0xa5bc`: `CommentsDisabledScope`
- `0xa861`: `CommentsDisabledScope`
- `0xa693`: `ServerRedirectedEmbedUri`
- `0xad91`: `ServerRedirectedEmbedUri`

## pseudocode

```c

```

## disassembly

```asm
0xa560  ldc.i4.0
0xa561  stloc.0
0xa562  ldarg.2
0xa563  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0xa568  stloc.1
0xa569  ldloc.1
0xa56a  brtrue.s loc_A577
0xa56c  ldstr    aTarget// "target"
0xa571  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa576  throw
0xa577  ldarg.3
0xa578  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0xa57d  dup
0xa57e  stloc.2
0xa57f  brfalse  loc_AE91
0xa584  volatile.
0xa586  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000139-1
0xa58b  brtrue   loc_A6CD
0xa590  ldc.i4.s 0x18
0xa592  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xa597  dup
0xa598  ldstr    aActivities// "Activities"
0xa59d  ldc.i4.0
0xa59e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa5a3  dup
0xa5a4  ldstr    aAttachmentfile// "AttachmentFiles"
0xa5a9  ldc.i4.1
0xa5aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa5af  dup
0xa5b0  ldstr    aCommentsdisabl// "CommentsDisabled"
0xa5b5  ldc.i4.2
0xa5b6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa5bb  dup
0xa5bc  ldstr    aCommentsdisabl_0// "CommentsDisabledScope"
0xa5c1  ldc.i4.3
0xa5c2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa5c7  dup
0xa5c8  ldstr    aContenttype// "ContentType"
0xa5cd  ldc.i4.4
0xa5ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa5d3  dup
0xa5d4  ldstr    aDisplayname// "DisplayName"
0xa5d9  ldc.i4.5
0xa5da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa5df  dup
0xa5e0  ldstr    aGetdlppolicyti// "GetDlpPolicyTip"
0xa5e5  ldc.i4.6
0xa5e6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa5eb  dup
0xa5ec  ldstr    aEffectivebasep// "EffectiveBasePermissions"
0xa5f1  ldc.i4.7
0xa5f2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa5f7  dup
0xa5f8  ldstr    aEffectivebasep_0// "EffectiveBasePermissionsForUI"
0xa5fd  ldc.i4.8
0xa5fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa603  dup
0xa604  ldstr    aFieldvaluesash// "FieldValuesAsHtml"
0xa609  ldc.i4.s 9
0xa60b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa610  dup
0xa611  ldstr    aFieldvaluesast// "FieldValuesAsText"
0xa616  ldc.i4.s 0xA
0xa618  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa61d  dup
0xa61e  ldstr    aFieldvaluesfor// "FieldValuesForEdit"
0xa623  ldc.i4.s 0xB
0xa625  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa62a  dup
0xa62b  ldstr    aFile// "File"
0xa630  ldc.i4.s 0xC
0xa632  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa637  dup
0xa638  ldstr    aFilesystemobje// "FileSystemObjectType"
0xa63d  ldc.i4.s 0xD
0xa63f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa644  dup
0xa645  ldstr    aFolder// "Folder"
0xa64a  ldc.i4.s 0xE
0xa64c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa651  dup
0xa652  ldstr    aIconoverlay// "IconOverlay"
0xa657  ldc.i4.s 0xF
0xa659  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa65e  dup
0xa65f  ldstr    aId_0// "Id"
0xa664  ldc.i4.s 0x10
0xa666  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa66b  dup
0xa66c  ldstr    aLikedbyinforma// "LikedByInformation"
0xa671  ldc.i4.s 0x11
0xa673  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa678  dup
0xa679  ldstr    aParentlist// "ParentList"
0xa67e  ldc.i4.s 0x12
0xa680  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa685  dup
0xa686  ldstr    aProperties// "Properties"
0xa68b  ldc.i4.s 0x13
0xa68d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa692  dup
0xa693  ldstr    aServerredirect// "ServerRedirectedEmbedUri"
0xa698  ldc.i4.s 0x14
0xa69a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa69f  dup
0xa6a0  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xa6a5  ldc.i4.s 0x15
0xa6a7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6ac  dup
0xa6ad  ldstr    aClientTitle// "Client_Title"
0xa6b2  ldc.i4.s 0x16
0xa6b4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6b9  dup
0xa6ba  ldstr    aVersions// "Versions"
0xa6bf  ldc.i4.s 0x17
0xa6c1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6c6  volatile.
0xa6c8  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000139-1
0xa6cd  volatile.
0xa6cf  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000139-1
0xa6d4  ldloc.2
0xa6d5  ldloca.s 3
0xa6d7  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xa6dc  brfalse  loc_AE91
0xa6e1  ldloc.3
0xa6e2  switch   loc_A74C, loc_A79D, loc_A7EE, loc_A838, loc_A882, loc_A8D3, loc_A91D, loc_A96E, loc_A9B8, loc_AA02, loc_AA53, loc_AAA4, loc_AAF5, loc_AB46, loc_AB90, loc_ABE1, loc_AC2B, loc_AC75, loc_ACC6, loc_AD17, loc_AD68, loc_ADB2, loc_ADFC, loc_AE43
0xa747  br       loc_AE91
0xa74c  ldarg.3
0xa74d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa752  stloc.s  4
0xa754  ldloca.s 4
0xa756  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa75b  brfalse.s loc_A774
0xa75d  ldarg.3
0xa75e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa763  stloc.s  5
0xa765  ldloca.s 5
0xa767  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa76c  brfalse.s loc_A774
0xa76e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa773  throw
0xa774  ldarg.0
0xa775  ldstr    aActivities// "Activities"
0xa77a  ldarg.s  4
0xa77c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa781  ldc.i4.1
0xa782  stloc.0
0xa783  ldarg.0
0xa784  ldarg.1
0xa785  ldloc.1
0xa786  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityEntitySet [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_Activities()
0xa78b  ldarg.3
0xa78c  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0xa791  ldarg.s  4
0xa793  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa798  br       loc_AE9D
0xa79d  ldarg.3
0xa79e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa7a3  stloc.s  6
0xa7a5  ldloca.s 6
0xa7a7  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa7ac  brfalse.s loc_A7C5
0xa7ae  ldarg.3
0xa7af  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa7b4  stloc.s  7
0xa7b6  ldloca.s 7
0xa7b8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa7bd  brfalse.s loc_A7C5
0xa7bf  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa7c4  throw
0xa7c5  ldarg.0
0xa7c6  ldstr    aAttachmentfile// "AttachmentFiles"
0xa7cb  ldarg.s  4
0xa7cd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa7d2  ldc.i4.1
0xa7d3  stloc.0
0xa7d4  ldarg.0
0xa7d5  ldarg.1
0xa7d6  ldloc.1
0xa7d7  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPAttachmentCollection_Client [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_Attachments_Client()
0xa7dc  ldarg.3
0xa7dd  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0xa7e2  ldarg.s  4
0xa7e4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa7e9  br       loc_AE9D
0xa7ee  ldarg.3
0xa7ef  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa7f4  stloc.s  8
0xa7f6  ldloca.s 8
0xa7f8  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa7fd  brfalse.s loc_A816
0xa7ff  ldarg.3
0xa800  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa805  stloc.s  9
0xa807  ldloca.s 9
0xa809  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa80e  brtrue.s loc_A816
0xa810  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa815  throw
0xa816  ldarg.0
0xa817  ldstr    aCommentsdisabl// "CommentsDisabled"
0xa81c  ldarg.s  4
0xa81e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa823  ldc.i4.1
0xa824  stloc.0
0xa825  ldarg.1
0xa826  ldloc.1
0xa827  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_CommentsDisabled()
0xa82c  ldarg.s  4
0xa82e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa833  br       loc_AE9D
0xa838  ldarg.3
0xa839  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa83e  stloc.s  0xA
0xa840  ldloca.s 0xA
0xa842  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa847  brfalse.s loc_A860
0xa849  ldarg.3
0xa84a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa84f  stloc.s  0xB
0xa851  ldloca.s 0xB
0xa853  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa858  brtrue.s loc_A860
0xa85a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa85f  throw
0xa860  ldarg.0
0xa861  ldstr    aCommentsdisabl_0// "CommentsDisabledScope"
0xa866  ldarg.s  4
0xa868  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa86d  ldc.i4.1
0xa86e  stloc.0
0xa86f  ldarg.1
0xa870  ldloc.1
0xa871  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Comments.SPCommentsDisabledScope [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_CommentsDisabledScope()
0xa876  ldarg.s  4
0xa878  call     T0x2B000050
0xa87d  br       loc_AE9D
0xa882  ldarg.3
0xa883  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa888  stloc.s  0xC
0xa88a  ldloca.s 0xC
0xa88c  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa891  brfalse.s loc_A8AA
0xa893  ldarg.3
0xa894  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa899  stloc.s  0xD
0xa89b  ldloca.s 0xD
0xa89d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa8a2  brfalse.s loc_A8AA
0xa8a4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa8a9  throw
0xa8aa  ldarg.0
0xa8ab  ldstr    aContenttype// "ContentType"
0xa8b0  ldarg.s  4
0xa8b2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa8b7  ldc.i4.1
0xa8b8  stloc.0
0xa8b9  ldarg.0
0xa8ba  ldarg.1
0xa8bb  ldloc.1
0xa8bc  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_ContentType()
0xa8c1  ldarg.3
0xa8c2  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0xa8c7  ldarg.s  4
0xa8c9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa8ce  br       loc_AE9D
0xa8d3  ldarg.3
0xa8d4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa8d9  stloc.s  0xE
0xa8db  ldloca.s 0xE
0xa8dd  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa8e2  brfalse.s loc_A8FB
0xa8e4  ldarg.3
0xa8e5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa8ea  stloc.s  0xF
0xa8ec  ldloca.s 0xF
0xa8ee  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa8f3  brtrue.s loc_A8FB
0xa8f5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa8fa  throw
0xa8fb  ldarg.0
0xa8fc  ldstr    aDisplayname// "DisplayName"
0xa901  ldarg.s  4
0xa903  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa908  ldc.i4.1
0xa909  stloc.0
0xa90a  ldarg.1
0xa90b  ldloc.1
0xa90c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem::get_DisplayName()
0xa911  ldarg.s  4
0xa913  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa918  br       loc_AE9D
0xa91d  ldarg.3
0xa91e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa923  stloc.s  0x10
0xa925  ldloca.s 0x10
0xa927  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa92c  brfalse.s loc_A945
0xa92e  ldarg.3
0xa92f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
  ... truncated ...
```
