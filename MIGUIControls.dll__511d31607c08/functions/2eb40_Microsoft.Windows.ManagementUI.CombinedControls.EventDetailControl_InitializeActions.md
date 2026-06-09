# Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::InitializeActions

- ea: `0x2eb40`
- end: `0x2ed28`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::InitializeActions`
- size: `488`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x2bb70`
- `0x2f840`

## callees

- `0x12ed0`
- `0x2b7b0`
- `0x2d550`
- `0x2eb40`
- `0x2ed30`
- `0x37100`
- `0x37160`
- `0x37170`
- `0x371a0`
- `0x37740`
- `0x37800`

## string_xrefs

- `0x2ebc4`: `ActionCopyToClipboard`
- `0x2ec86`: `ActionCopyToClipboard`
- `0x2ebdd`: `ActionCopyTable`
- `0x2eca1`: `ActionCopyTable`
- `0x2ec08`: `ActionCopyDetailsAsText`
- `0x2ecd0`: `ActionCopyDetailsAsText`

## pseudocode

```c

```

## disassembly

```asm
0x2eb40  ldarg.0
0x2eb41  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::actions
0x2eb46  ldc.i4.0
0x2eb47  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::set_ActionsChanged(bool value)
0x2eb4c  ldarg.0
0x2eb4d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::actions
0x2eb52  ldc.i4.s 0x18
0x2eb54  ldc.i4.0
0x2eb55  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2eb5a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x2eb5f  ldarg.0
0x2eb60  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ListViewEx Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::mainListView
0x2eb65  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x2eb6a  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::get_Count()
0x2eb6f  ldc.i4.0
0x2eb70  ble      loc_2EC4C
0x2eb75  ldarg.0
0x2eb76  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::actions
0x2eb7b  ldc.i4.8
0x2eb7c  ldc.i4.0
0x2eb7d  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2eb82  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x2eb87  ldarg.0
0x2eb88  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::actions
0x2eb8d  ldc.i4.s 0xE
0x2eb8f  ldarg.0
0x2eb90  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::attachTaskHidden
0x2eb95  brtrue.s loc_2EBAF
0x2eb97  ldarg.0
0x2eb98  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::get_SessionPtr()
0x2eb9d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2eba2  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x2eba7  brtrue.s loc_2EBAC
0x2eba9  ldc.i4.1
0x2ebaa  br.s     loc_2EBB0
0x2ebac  ldc.i4.0
0x2ebad  br.s     loc_2EBB0
0x2ebaf  ldc.i4.2
0x2ebb0  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2ebb5  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x2ebba  ldc.i4.s 0x13
0x2ebbc  ldc.i4.0
0x2ebbd  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2ebc2  stloc.0
0x2ebc3  ldloc.0
0x2ebc4  ldstr    aActioncopytocl// "ActionCopyToClipboard"
0x2ebc9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x2ebce  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::set_Name(string value)
0x2ebd3  ldc.i4.s 0x14
0x2ebd5  ldc.i4.0
0x2ebd6  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2ebdb  stloc.1
0x2ebdc  ldloc.1
0x2ebdd  ldstr    aActioncopytabl// "ActionCopyTable"
0x2ebe2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x2ebe7  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::set_Name(string value)
0x2ebec  ldloc.0
0x2ebed  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Items()
0x2ebf2  ldloc.1
0x2ebf3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Name()
0x2ebf8  ldloc.1
0x2ebf9  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x2ebfe  ldc.i4.s 0x15
0x2ec00  ldc.i4.0
0x2ec01  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2ec06  stloc.2
0x2ec07  ldloc.2
0x2ec08  ldstr    aActioncopydeta// "ActionCopyDetailsAsText"
0x2ec0d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x2ec12  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::set_Name(string value)
0x2ec17  ldloc.0
0x2ec18  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Items()
0x2ec1d  ldloc.2
0x2ec1e  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Name()
0x2ec23  ldloc.2
0x2ec24  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x2ec29  ldarg.0
0x2ec2a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::actions
0x2ec2f  ldloc.0
0x2ec30  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x2ec35  ldarg.0
0x2ec36  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::actions
0x2ec3b  ldc.i4.5
0x2ec3c  ldc.i4.0
0x2ec3d  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2ec42  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x2ec47  br       loc_2ED1E
0x2ec4c  ldarg.0
0x2ec4d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::actions
0x2ec52  ldc.i4.8
0x2ec53  ldc.i4.1
0x2ec54  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2ec59  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x2ec5e  ldarg.0
0x2ec5f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::actions
0x2ec64  ldc.i4.s 0xE
0x2ec66  ldarg.0
0x2ec67  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::attachTaskHidden
0x2ec6c  brtrue.s loc_2EC71
0x2ec6e  ldc.i4.1
0x2ec6f  br.s     loc_2EC72
0x2ec71  ldc.i4.2
0x2ec72  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2ec77  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x2ec7c  ldc.i4.s 0x13
0x2ec7e  ldc.i4.2
0x2ec7f  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2ec84  stloc.3
0x2ec85  ldloc.3
0x2ec86  ldstr    aActioncopytocl// "ActionCopyToClipboard"
0x2ec8b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x2ec90  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::set_Name(string value)
0x2ec95  ldc.i4.s 0x14
0x2ec97  ldc.i4.0
0x2ec98  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2ec9d  stloc.s  4
0x2ec9f  ldloc.s  4
0x2eca1  ldstr    aActioncopytabl// "ActionCopyTable"
0x2eca6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x2ecab  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::set_Name(string value)
0x2ecb0  ldloc.3
0x2ecb1  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Items()
0x2ecb6  ldloc.s  4
0x2ecb8  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Name()
0x2ecbd  ldloc.s  4
0x2ecbf  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x2ecc4  ldc.i4.s 0x15
0x2ecc6  ldc.i4.0
0x2ecc7  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2eccc  stloc.s  5
0x2ecce  ldloc.s  5
0x2ecd0  ldstr    aActioncopydeta// "ActionCopyDetailsAsText"
0x2ecd5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x2ecda  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::set_Name(string value)
0x2ecdf  ldloc.3
0x2ece0  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Items()
0x2ece5  ldloc.s  5
0x2ece7  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Name()
0x2ecec  ldloc.s  5
0x2ecee  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x2ecf3  ldarg.0
0x2ecf4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::actions
0x2ecf9  ldloc.3
0x2ecfa  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x2ecff  ldarg.0
0x2ed00  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::actions
0x2ed05  ldc.i4.5
0x2ed06  ldc.i4.1
0x2ed07  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::.ctor(valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers id, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus stat)
0x2ed0c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ManagementActions::SetAction(class Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x2ed11  ldarg.0
0x2ed12  ldsfld   string [mscorlib]System.String::Empty
0x2ed17  ldnull
0x2ed18  ldnull
0x2ed19  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::FireSelectionChangedEvent(string displayName, int32[] index, class Microsoft.Windows.ManagementUI.CombinedControls.IEventBase evt)
0x2ed1e  ldarg.1
0x2ed1f  brfalse.s loc_2ED27
0x2ed21  ldarg.0
0x2ed22  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventDetailControl::FireActionChangedEvent()
0x2ed27  ret
```
