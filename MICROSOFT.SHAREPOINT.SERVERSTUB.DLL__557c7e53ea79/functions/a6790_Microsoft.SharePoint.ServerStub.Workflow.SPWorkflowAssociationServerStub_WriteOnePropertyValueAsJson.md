# Microsoft.SharePoint.ServerStub.Workflow.SPWorkflowAssociationServerStub::WriteOnePropertyValueAsJson

- ea: `0xa6790`
- end: `0xa6e52`
- name: `Microsoft.SharePoint.ServerStub.Workflow.SPWorkflowAssociationServerStub::WriteOnePropertyValueAsJson`
- size: `1730`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa6790`

## string_xrefs

- `0xa6804`: `Created`
- `0xa6ab1`: `Created`
- `0xa67ec`: `AutoStartCreate`
- `0xa6a1d`: `AutoStartCreate`
- `0xa688f`: `TaskListTitle`
- `0xa6ddf`: `TaskListTitle`

## pseudocode

```c

```

## disassembly

```asm
0xa6790  ldc.i4.0
0xa6791  stloc.0
0xa6792  ldarg.2
0xa6793  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation
0xa6798  stloc.1
0xa6799  ldloc.1
0xa679a  brtrue.s loc_A67A7
0xa679c  ldstr    aTarget// "target"
0xa67a1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa67a6  throw
0xa67a7  ldarg.3
0xa67a8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0xa67ad  dup
0xa67ae  stloc.2
0xa67af  brfalse  loc_A6E44
0xa67b4  volatile.
0xa67b6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001b41-1
0xa67bb  brtrue   loc_A68AF
0xa67c0  ldc.i4.s 0x12
0xa67c2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xa67c7  dup
0xa67c8  ldstr    aAllowmanual// "AllowManual"
0xa67cd  ldc.i4.0
0xa67ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa67d3  dup
0xa67d4  ldstr    aAssociationdat// "AssociationData"
0xa67d9  ldc.i4.1
0xa67da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa67df  dup
0xa67e0  ldstr    aAutostartchang// "AutoStartChange"
0xa67e5  ldc.i4.2
0xa67e6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa67eb  dup
0xa67ec  ldstr    aAutostartcreat// "AutoStartCreate"
0xa67f1  ldc.i4.3
0xa67f2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa67f7  dup
0xa67f8  ldstr    aBaseid// "BaseId"
0xa67fd  ldc.i4.4
0xa67fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6803  dup
0xa6804  ldstr    aCreated// "Created"
0xa6809  ldc.i4.5
0xa680a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa680f  dup
0xa6810  ldstr    aDescription// "Description"
0xa6815  ldc.i4.6
0xa6816  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa681b  dup
0xa681c  ldstr    aEnabled_0// "Enabled"
0xa6821  ldc.i4.7
0xa6822  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6827  dup
0xa6828  ldstr    aHistorylisttit// "HistoryListTitle"
0xa682d  ldc.i4.8
0xa682e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6833  dup
0xa6834  ldstr    aId_0// "Id"
0xa6839  ldc.i4.s 9
0xa683b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6840  dup
0xa6841  ldstr    aInstantiationu// "InstantiationUrl"
0xa6846  ldc.i4.s 0xA
0xa6848  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa684d  dup
0xa684e  ldstr    aInternalname// "InternalName"
0xa6853  ldc.i4.s 0xB
0xa6855  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa685a  dup
0xa685b  ldstr    aIsdeclarative// "IsDeclarative"
0xa6860  ldc.i4.s 0xC
0xa6862  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6867  dup
0xa6868  ldstr    aListid_0// "ListId"
0xa686d  ldc.i4.s 0xD
0xa686f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6874  dup
0xa6875  ldstr    aModified// "Modified"
0xa687a  ldc.i4.s 0xE
0xa687c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6881  dup
0xa6882  ldstr    aName// "Name"
0xa6887  ldc.i4.s 0xF
0xa6889  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa688e  dup
0xa688f  ldstr    aTasklisttitle// "TaskListTitle"
0xa6894  ldc.i4.s 0x10
0xa6896  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa689b  dup
0xa689c  ldstr    aWebid_0// "WebId"
0xa68a1  ldc.i4.s 0x11
0xa68a3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa68a8  volatile.
0xa68aa  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001b41-1
0xa68af  volatile.
0xa68b1  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001b41-1
0xa68b6  ldloc.2
0xa68b7  ldloca.s 3
0xa68b9  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xa68be  brfalse  loc_A6E44
0xa68c3  ldloc.3
0xa68c4  switch   loc_A6916, loc_A6960, loc_A69AA, loc_A69F4, loc_A6A3E, loc_A6A88, loc_A6AD2, loc_A6B1C, loc_A6B66, loc_A6BB0, loc_A6BFA, loc_A6C44, loc_A6C8E, loc_A6CD8, loc_A6D22, loc_A6D6C, loc_A6DB6, loc_A6DFD
0xa6911  br       loc_A6E44
0xa6916  ldarg.3
0xa6917  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa691c  stloc.s  4
0xa691e  ldloca.s 4
0xa6920  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa6925  brfalse.s loc_A693E
0xa6927  ldarg.3
0xa6928  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa692d  stloc.s  5
0xa692f  ldloca.s 5
0xa6931  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa6936  brtrue.s loc_A693E
0xa6938  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa693d  throw
0xa693e  ldarg.0
0xa693f  ldstr    aAllowmanual// "AllowManual"
0xa6944  ldarg.s  4
0xa6946  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa694b  ldc.i4.1
0xa694c  stloc.0
0xa694d  ldarg.1
0xa694e  ldloc.1
0xa694f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AllowManual()
0xa6954  ldarg.s  4
0xa6956  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa695b  br       loc_A6E50
0xa6960  ldarg.3
0xa6961  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa6966  stloc.s  6
0xa6968  ldloca.s 6
0xa696a  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa696f  brfalse.s loc_A6988
0xa6971  ldarg.3
0xa6972  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa6977  stloc.s  7
0xa6979  ldloca.s 7
0xa697b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa6980  brtrue.s loc_A6988
0xa6982  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa6987  throw
0xa6988  ldarg.0
0xa6989  ldstr    aAssociationdat// "AssociationData"
0xa698e  ldarg.s  4
0xa6990  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6995  ldc.i4.1
0xa6996  stloc.0
0xa6997  ldarg.1
0xa6998  ldloc.1
0xa6999  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AssociationData()
0xa699e  ldarg.s  4
0xa69a0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa69a5  br       loc_A6E50
0xa69aa  ldarg.3
0xa69ab  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa69b0  stloc.s  8
0xa69b2  ldloca.s 8
0xa69b4  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa69b9  brfalse.s loc_A69D2
0xa69bb  ldarg.3
0xa69bc  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa69c1  stloc.s  9
0xa69c3  ldloca.s 9
0xa69c5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa69ca  brtrue.s loc_A69D2
0xa69cc  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa69d1  throw
0xa69d2  ldarg.0
0xa69d3  ldstr    aAutostartchang// "AutoStartChange"
0xa69d8  ldarg.s  4
0xa69da  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa69df  ldc.i4.1
0xa69e0  stloc.0
0xa69e1  ldarg.1
0xa69e2  ldloc.1
0xa69e3  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AutoStartChange()
0xa69e8  ldarg.s  4
0xa69ea  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa69ef  br       loc_A6E50
0xa69f4  ldarg.3
0xa69f5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa69fa  stloc.s  0xA
0xa69fc  ldloca.s 0xA
0xa69fe  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa6a03  brfalse.s loc_A6A1C
0xa6a05  ldarg.3
0xa6a06  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa6a0b  stloc.s  0xB
0xa6a0d  ldloca.s 0xB
0xa6a0f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa6a14  brtrue.s loc_A6A1C
0xa6a16  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa6a1b  throw
0xa6a1c  ldarg.0
0xa6a1d  ldstr    aAutostartcreat// "AutoStartCreate"
0xa6a22  ldarg.s  4
0xa6a24  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6a29  ldc.i4.1
0xa6a2a  stloc.0
0xa6a2b  ldarg.1
0xa6a2c  ldloc.1
0xa6a2d  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AutoStartCreate()
0xa6a32  ldarg.s  4
0xa6a34  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6a39  br       loc_A6E50
0xa6a3e  ldarg.3
0xa6a3f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa6a44  stloc.s  0xC
0xa6a46  ldloca.s 0xC
0xa6a48  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa6a4d  brfalse.s loc_A6A66
0xa6a4f  ldarg.3
0xa6a50  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa6a55  stloc.s  0xD
0xa6a57  ldloca.s 0xD
0xa6a59  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa6a5e  brtrue.s loc_A6A66
0xa6a60  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa6a65  throw
0xa6a66  ldarg.0
0xa6a67  ldstr    aBaseid// "BaseId"
0xa6a6c  ldarg.s  4
0xa6a6e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6a73  ldc.i4.1
0xa6a74  stloc.0
0xa6a75  ldarg.1
0xa6a76  ldloc.1
0xa6a77  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_BaseId()
0xa6a7c  ldarg.s  4
0xa6a7e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6a83  br       loc_A6E50
0xa6a88  ldarg.3
0xa6a89  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa6a8e  stloc.s  0xE
0xa6a90  ldloca.s 0xE
0xa6a92  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa6a97  brfalse.s loc_A6AB0
0xa6a99  ldarg.3
0xa6a9a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa6a9f  stloc.s  0xF
0xa6aa1  ldloca.s 0xF
0xa6aa3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa6aa8  brtrue.s loc_A6AB0
0xa6aaa  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa6aaf  throw
0xa6ab0  ldarg.0
0xa6ab1  ldstr    aCreated// "Created"
0xa6ab6  ldarg.s  4
0xa6ab8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6abd  ldc.i4.1
0xa6abe  stloc.0
0xa6abf  ldarg.1
0xa6ac0  ldloc.1
0xa6ac1  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Created()
0xa6ac6  ldarg.s  4
0xa6ac8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6acd  br       loc_A6E50
0xa6ad2  ldarg.3
0xa6ad3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa6ad8  stloc.s  0x10
0xa6ada  ldloca.s 0x10
0xa6adc  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa6ae1  brfalse.s loc_A6AFA
0xa6ae3  ldarg.3
0xa6ae4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa6ae9  stloc.s  0x11
0xa6aeb  ldloca.s 0x11
0xa6aed  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa6af2  brtrue.s loc_A6AFA
0xa6af4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa6af9  throw
0xa6afa  ldarg.0
0xa6afb  ldstr    aDescription// "Description"
0xa6b00  ldarg.s  4
0xa6b02  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6b07  ldc.i4.1
0xa6b08  stloc.0
0xa6b09  ldarg.1
0xa6b0a  ldloc.1
0xa6b0b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Description()
0xa6b10  ldarg.s  4
0xa6b12  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6b17  br       loc_A6E50
0xa6b1c  ldarg.3
0xa6b1d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa6b22  stloc.s  0x12
0xa6b24  ldloca.s 0x12
0xa6b26  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xa6b2b  brfalse.s loc_A6B44
0xa6b2d  ldarg.3
0xa6b2e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xa6b33  stloc.s  0x13
0xa6b35  ldloca.s 0x13
0xa6b37  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xa6b3c  brtrue.s loc_A6B44
0xa6b3e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xa6b43  throw
0xa6b44  ldarg.0
  ... truncated ...
```
