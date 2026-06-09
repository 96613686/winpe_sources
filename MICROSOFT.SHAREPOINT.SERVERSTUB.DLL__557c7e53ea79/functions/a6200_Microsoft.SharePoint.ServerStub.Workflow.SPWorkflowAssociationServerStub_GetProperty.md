# Microsoft.SharePoint.ServerStub.Workflow.SPWorkflowAssociationServerStub::GetProperty

- ea: `0xa6200`
- end: `0xa653c`
- name: `Microsoft.SharePoint.ServerStub.Workflow.SPWorkflowAssociationServerStub::GetProperty`
- size: `828`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xa6200`

## string_xrefs

- `0xa6293`: `Created`
- `0xa6419`: `Created`
- `0xa627b`: `AutoStartCreate`
- `0xa63e9`: `AutoStartCreate`
- `0xa631e`: `TaskListTitle`
- `0xa6508`: `TaskListTitle`

## pseudocode

```c

```

## disassembly

```asm
0xa6200  ldarg.2
0xa6201  brtrue.s loc_A620E
0xa6203  ldstr    aPropname// "propName"
0xa6208  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa620d  throw
0xa620e  ldarg.3
0xa620f  brtrue.s loc_A621C
0xa6211  ldstr    aProxycontext// "proxyContext"
0xa6216  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa621b  throw
0xa621c  ldarg.1
0xa621d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation
0xa6222  stloc.0
0xa6223  ldloc.0
0xa6224  brtrue.s loc_A6231
0xa6226  ldstr    aTarget// "target"
0xa622b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa6230  throw
0xa6231  ldarg.0
0xa6232  ldarg.2
0xa6233  ldarg.3
0xa6234  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6239  starg.s  2
0xa623b  ldarg.2
0xa623c  dup
0xa623d  stloc.1
0xa623e  brfalse  loc_A6532
0xa6243  volatile.
0xa6245  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001b3e-1
0xa624a  brtrue   loc_A633E
0xa624f  ldc.i4.s 0x12
0xa6251  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xa6256  dup
0xa6257  ldstr    aAllowmanual// "AllowManual"
0xa625c  ldc.i4.0
0xa625d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6262  dup
0xa6263  ldstr    aAssociationdat// "AssociationData"
0xa6268  ldc.i4.1
0xa6269  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa626e  dup
0xa626f  ldstr    aAutostartchang// "AutoStartChange"
0xa6274  ldc.i4.2
0xa6275  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa627a  dup
0xa627b  ldstr    aAutostartcreat// "AutoStartCreate"
0xa6280  ldc.i4.3
0xa6281  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6286  dup
0xa6287  ldstr    aBaseid// "BaseId"
0xa628c  ldc.i4.4
0xa628d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6292  dup
0xa6293  ldstr    aCreated// "Created"
0xa6298  ldc.i4.5
0xa6299  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa629e  dup
0xa629f  ldstr    aDescription// "Description"
0xa62a4  ldc.i4.6
0xa62a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa62aa  dup
0xa62ab  ldstr    aEnabled_0// "Enabled"
0xa62b0  ldc.i4.7
0xa62b1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa62b6  dup
0xa62b7  ldstr    aHistorylisttit// "HistoryListTitle"
0xa62bc  ldc.i4.8
0xa62bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa62c2  dup
0xa62c3  ldstr    aId_0// "Id"
0xa62c8  ldc.i4.s 9
0xa62ca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa62cf  dup
0xa62d0  ldstr    aInstantiationu// "InstantiationUrl"
0xa62d5  ldc.i4.s 0xA
0xa62d7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa62dc  dup
0xa62dd  ldstr    aInternalname// "InternalName"
0xa62e2  ldc.i4.s 0xB
0xa62e4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa62e9  dup
0xa62ea  ldstr    aIsdeclarative// "IsDeclarative"
0xa62ef  ldc.i4.s 0xC
0xa62f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa62f6  dup
0xa62f7  ldstr    aListid_0// "ListId"
0xa62fc  ldc.i4.s 0xD
0xa62fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6303  dup
0xa6304  ldstr    aModified// "Modified"
0xa6309  ldc.i4.s 0xE
0xa630b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6310  dup
0xa6311  ldstr    aName// "Name"
0xa6316  ldc.i4.s 0xF
0xa6318  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa631d  dup
0xa631e  ldstr    aTasklisttitle// "TaskListTitle"
0xa6323  ldc.i4.s 0x10
0xa6325  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa632a  dup
0xa632b  ldstr    aWebid_0// "WebId"
0xa6330  ldc.i4.s 0x11
0xa6332  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xa6337  volatile.
0xa6339  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001b3e-1
0xa633e  volatile.
0xa6340  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001b3e-1
0xa6345  ldloc.1
0xa6346  ldloca.s 2
0xa6348  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xa634d  brfalse  loc_A6532
0xa6352  ldloc.2
0xa6353  switch   loc_A63A5, loc_A63BD, loc_A63D0, loc_A63E8, loc_A6400, loc_A6418, loc_A6430, loc_A6443, loc_A645B, loc_A646E, loc_A6486, loc_A6499, loc_A64AC, loc_A64C4, loc_A64DC, loc_A64F4, loc_A6507, loc_A651A
0xa63a0  br       loc_A6532
0xa63a5  ldarg.0
0xa63a6  ldstr    aAllowmanual// "AllowManual"
0xa63ab  ldarg.3
0xa63ac  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa63b1  ldloc.0
0xa63b2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AllowManual()
0xa63b7  box      [mscorlib]System.Boolean
0xa63bc  ret
0xa63bd  ldarg.0
0xa63be  ldstr    aAssociationdat// "AssociationData"
0xa63c3  ldarg.3
0xa63c4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa63c9  ldloc.0
0xa63ca  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AssociationData()
0xa63cf  ret
0xa63d0  ldarg.0
0xa63d1  ldstr    aAutostartchang// "AutoStartChange"
0xa63d6  ldarg.3
0xa63d7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa63dc  ldloc.0
0xa63dd  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AutoStartChange()
0xa63e2  box      [mscorlib]System.Boolean
0xa63e7  ret
0xa63e8  ldarg.0
0xa63e9  ldstr    aAutostartcreat// "AutoStartCreate"
0xa63ee  ldarg.3
0xa63ef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa63f4  ldloc.0
0xa63f5  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_AutoStartCreate()
0xa63fa  box      [mscorlib]System.Boolean
0xa63ff  ret
0xa6400  ldarg.0
0xa6401  ldstr    aBaseid// "BaseId"
0xa6406  ldarg.3
0xa6407  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa640c  ldloc.0
0xa640d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_BaseId()
0xa6412  box      [mscorlib]System.Guid
0xa6417  ret
0xa6418  ldarg.0
0xa6419  ldstr    aCreated// "Created"
0xa641e  ldarg.3
0xa641f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6424  ldloc.0
0xa6425  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Created()
0xa642a  box      [mscorlib]System.DateTime
0xa642f  ret
0xa6430  ldarg.0
0xa6431  ldstr    aDescription// "Description"
0xa6436  ldarg.3
0xa6437  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa643c  ldloc.0
0xa643d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Description()
0xa6442  ret
0xa6443  ldarg.0
0xa6444  ldstr    aEnabled_0// "Enabled"
0xa6449  ldarg.3
0xa644a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa644f  ldloc.0
0xa6450  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Enabled()
0xa6455  box      [mscorlib]System.Boolean
0xa645a  ret
0xa645b  ldarg.0
0xa645c  ldstr    aHistorylisttit// "HistoryListTitle"
0xa6461  ldarg.3
0xa6462  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6467  ldloc.0
0xa6468  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_HistoryListTitle()
0xa646d  ret
0xa646e  ldarg.0
0xa646f  ldstr    aId_0// "Id"
0xa6474  ldarg.3
0xa6475  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa647a  ldloc.0
0xa647b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Id()
0xa6480  box      [mscorlib]System.Guid
0xa6485  ret
0xa6486  ldarg.0
0xa6487  ldstr    aInstantiationu// "InstantiationUrl"
0xa648c  ldarg.3
0xa648d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6492  ldloc.0
0xa6493  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_InstantiationUrl()
0xa6498  ret
0xa6499  ldarg.0
0xa649a  ldstr    aInternalname// "InternalName"
0xa649f  ldarg.3
0xa64a0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa64a5  ldloc.0
0xa64a6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_InternalName()
0xa64ab  ret
0xa64ac  ldarg.0
0xa64ad  ldstr    aIsdeclarative// "IsDeclarative"
0xa64b2  ldarg.3
0xa64b3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa64b8  ldloc.0
0xa64b9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_IsDeclarative()
0xa64be  box      [mscorlib]System.Boolean
0xa64c3  ret
0xa64c4  ldarg.0
0xa64c5  ldstr    aListid_0// "ListId"
0xa64ca  ldarg.3
0xa64cb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa64d0  ldloc.0
0xa64d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_ListId()
0xa64d6  box      [mscorlib]System.Guid
0xa64db  ret
0xa64dc  ldarg.0
0xa64dd  ldstr    aModified// "Modified"
0xa64e2  ldarg.3
0xa64e3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa64e8  ldloc.0
0xa64e9  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Modified()
0xa64ee  box      [mscorlib]System.DateTime
0xa64f3  ret
0xa64f4  ldarg.0
0xa64f5  ldstr    aName// "Name"
0xa64fa  ldarg.3
0xa64fb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6500  ldloc.0
0xa6501  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_Name()
0xa6506  ret
0xa6507  ldarg.0
0xa6508  ldstr    aTasklisttitle// "TaskListTitle"
0xa650d  ldarg.3
0xa650e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6513  ldloc.0
0xa6514  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_TaskListTitle()
0xa6519  ret
0xa651a  ldarg.0
0xa651b  ldstr    aWebid_0// "WebId"
0xa6520  ldarg.3
0xa6521  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6526  ldloc.0
0xa6527  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Workflow.SPWorkflowAssociation::get_WebId()
0xa652c  box      [mscorlib]System.Guid
0xa6531  ret
0xa6532  ldarg.0
0xa6533  ldarg.1
0xa6534  ldarg.2
0xa6535  ldarg.3
0xa6536  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa653b  ret
```
