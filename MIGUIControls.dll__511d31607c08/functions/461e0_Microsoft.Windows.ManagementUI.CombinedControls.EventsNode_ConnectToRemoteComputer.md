# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ConnectToRemoteComputer

- ea: `0x461e0`
- end: `0x4645c`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::ConnectToRemoteComputer`
- size: `636`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x12ed0`
- `0x14de0`
- `0x14e30`
- `0x1b790`
- `0x37100`
- `0x37740`
- `0x37930`
- `0x37950`
- `0x37970`
- `0x37d10`
- `0x38840`
- `0x38850`
- `0x461e0`
- `0x46d20`
- `0x49a10`
- `0x4bdd0`
- `0x4c9b0`
- `0x4c9e0`

## string_xrefs

- `0x462d2`: `LocalComputerName`
- `0x46445`: `LocalComputerName`

## pseudocode

```c

```

## disassembly

```asm
0x461e0  ldc.i4.0
0x461e1  stloc.0
0x461e2  ldc.i4.0
0x461e3  stloc.1
0x461e4  ldarg.0
0x461e5  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::m_nodeType
0x461ea  ldc.i4.2
0x461eb  bne.un   loc_4645A
0x461f0  ldarg.s  5
0x461f2  brtrue.s loc_461FC
0x461f4  ldarg.0
0x461f5  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::SaveSubNodes()
0x461fa  br.s     loc_4620C
0x461fc  ldarg.0
0x461fd  ldstr    aViewerrootnode// "ViewerRootNode"
0x46202  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x46207  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x4620c  ldarg.0
0x4620d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::actions
0x46212  ldc.i4.0
0x46213  ldc.i4.0
0x46214  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x46219  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x4621e  ldarg.0
0x4621f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::actions
0x46224  ldc.i4.4
0x46225  ldc.i4.0
0x46226  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x4622b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x46230  ldarg.0
0x46231  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::actions
0x46236  ldc.i4.s 0x23
0x46238  ldc.i4.0
0x46239  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x4623e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x46243  ldarg.0
0x46244  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::FireActionChangedEvent()
0x46249  ldarg.0
0x4624a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x4624f  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_RemoteComputer()
0x46254  ldarg.1
0x46255  ldc.i4.5
0x46256  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4625b  brfalse.s loc_462B8
0x4625d  ldarg.s  5
0x4625f  brtrue.s loc_4627F
0x46261  ldarg.1
0x46262  ldarg.2
0x46263  ldarg.3
0x46264  ldarg.s  4
0x46266  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x4626b  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x46270  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::.ctor(string remoteComputerName, string userDomain, string userName, class [mscorlib]System.Security.SecureString encryptedPassword, int32 lcid)
0x46275  stloc.2
0x46276  ldarg.0
0x46277  ldloc.2
0x46278  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x4627d  br.s     loc_462B0
0x4627f  ldarg.0
0x46280  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x46285  ldarg.1
0x46286  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::set_RemoteComputer(string value)
0x4628b  ldarg.0
0x4628c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x46291  ldarg.2
0x46292  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::set_UserDomain(string value)
0x46297  ldarg.0
0x46298  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x4629d  ldarg.3
0x4629e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::set_UserName(string value)
0x462a3  ldarg.0
0x462a4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x462a9  ldarg.s  4
0x462ab  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::set_EncryptedPassword(class [mscorlib]System.Security.SecureString value)
0x462b0  ldarg.0
0x462b1  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::DeleteAllSubNodes()
0x462b6  ldc.i4.1
0x462b7  stloc.0
0x462b8  leave    loc_4645A
0x462bd  throw
0x462be  stloc.3
0x462bf  ldarg.1
0x462c0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x462c5  brfalse.s loc_462EB
0x462c7  ldarg.0
0x462c8  ldstr    aViewerrootnode// "ViewerRootNode"
0x462cd  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x462d2  ldstr    aLocalcomputern// "LocalComputerName"
0x462d7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x462dc  call     string [mscorlib]System.String::Concat(string, string)
0x462e1  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x462e6  br       loc_46378
0x462eb  ldarg.0
0x462ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x462f1  ldtoken  [mscorlib]System.String
0x462f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x462fb  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x46300  castclass [mscorlib]System.IFormatProvider
0x46305  ldstr    aViewerrootnode_0// "ViewerRootNodeForRemote"
0x4630a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4630f  ldc.i4.1
0x46310  newarr   [mscorlib]System.Object
0x46315  dup
0x46316  ldc.i4.0
0x46317  ldarg.1
0x46318  stelem.ref
0x46319  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4631e  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x46323  ldarg.0
0x46324  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::actions
0x46329  ldc.i4.0
0x4632a  ldc.i4.2
0x4632b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x46330  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x46335  ldarg.0
0x46336  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::actions
0x4633b  ldc.i4.4
0x4633c  ldc.i4.2
0x4633d  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x46342  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x46347  ldarg.0
0x46348  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::actions
0x4634d  ldc.i4.s 0x23
0x4634f  ldc.i4.2
0x46350  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x46355  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x4635a  ldarg.0
0x4635b  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::MarkAllSubNodesDeleted()
0x46360  ldarg.0
0x46361  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x46366  callvirt instance void [mscorlib]System.Collections.IDictionary::Clear()
0x4636b  ldarg.0
0x4636c  ldc.i4.0
0x4636d  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_SubNodesFetched(bool value)
0x46372  ldarg.0
0x46373  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::FireActionChangedEvent()
0x46378  ldc.i4.1
0x46379  stloc.1
0x4637a  ldloc.3
0x4637b  throw
0x4637c  ldc.i4.0
0x4637d  stloc.0
0x4637e  dup
0x4637f  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.ExceptionAction Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_ActionForException()
0x46384  ldc.i4.2
0x46385  beq.s    loc_463E0
0x46387  ldarg.s  5
0x46389  brfalse.s loc_463E0
0x4638b  ldarg.0
0x4638c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::actions
0x46391  ldc.i4.0
0x46392  ldc.i4.1
0x46393  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x46398  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x4639d  ldarg.0
0x4639e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::actions
0x463a3  ldc.i4.4
0x463a4  ldc.i4.1
0x463a5  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x463aa  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x463af  ldarg.0
0x463b0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::actions
0x463b5  ldc.i4.s 0x23
0x463b7  ldc.i4.1
0x463b8  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x463bd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x463c2  ldarg.0
0x463c3  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::MarkAllSubNodesDeleted()
0x463c8  ldarg.0
0x463c9  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x463ce  callvirt instance void [mscorlib]System.Collections.IDictionary::Clear()
0x463d3  ldarg.0
0x463d4  ldc.i4.0
0x463d5  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::set_SubNodesFetched(bool value)
0x463da  ldarg.0
0x463db  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::FireActionChangedEvent()
0x463e0  throw
0x463e1  ldloc.1
0x463e2  brtrue.s loc_46459
0x463e4  ldarg.0
0x463e5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x463ea  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_RemoteComputer()
0x463ef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x463f4  brtrue.s loc_4643A
0x463f6  ldarg.0
0x463f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x463fc  ldtoken  [mscorlib]System.String
0x46401  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46406  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x4640b  castclass [mscorlib]System.IFormatProvider
0x46410  ldstr    aViewerrootnode_0// "ViewerRootNodeForRemote"
0x46415  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4641a  ldc.i4.1
0x4641b  newarr   [mscorlib]System.Object
0x46420  dup
0x46421  ldc.i4.0
0x46422  ldarg.0
0x46423  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::context
0x46428  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_RemoteComputer()
0x4642d  stelem.ref
0x4642e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x46433  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x46438  br.s     loc_46459
0x4643a  ldarg.0
0x4643b  ldstr    aViewerrootnode// "ViewerRootNode"
0x46440  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x46445  ldstr    aLocalcomputern// "LocalComputerName"
0x4644a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x4644f  call     string [mscorlib]System.String::Concat(string, string)
0x46454  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::set_Name(string value)
0x46459  endfinally
0x4645a  ldloc.0
0x4645b  ret
```
