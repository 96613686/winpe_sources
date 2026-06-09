# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::PopulateNetworkComboBox

- ea: `0x70350`
- end: `0x70602`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::PopulateNetworkComboBox`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x706b0`

## callees

- `0x12ed0`
- `0x13610`
- `0x137d0`
- `0x137e0`
- `0x13800`
- `0x1e660`
- `0x1e670`
- `0x1e730`
- `0x1e740`
- `0x63460`
- `0x63480`
- `0x63660`
- `0x64710`
- `0x67bb0`
- `0x70350`

## string_xrefs

- `0x70361`: `ComboEntryNetworkAnyConnection`

## pseudocode

```c

```

## disassembly

```asm
0x70350  ldarg.0
0x70351  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x70356  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::ClearComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo)
0x7035b  ldarg.0
0x7035c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x70361  ldstr    aComboentrynetw// "ComboEntryNetworkAnyConnection"
0x70366  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7036b  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x70370  ldarg.0
0x70371  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x70376  brfalse  loc_70601
0x7037b  ldarg.0
0x7037c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x70381  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x70386  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x7038b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x70390  ldsfld   string [mscorlib]System.String::Empty
0x70395  stloc.0
0x70396  ldc.i4.0
0x70397  stloc.2
0x70398  brfalse  loc_7054D
0x7039d  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.NetworkListManager::.ctor()
0x703a2  stloc.3
0x703a3  ldarg.0
0x703a4  ldloc.3
0x703a5  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.NetworkListManager::GetNetworkList()
0x703aa  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::networkList
0x703af  ldarg.0
0x703b0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::networkList
0x703b5  brfalse  loc_7044E
0x703ba  ldarg.0
0x703bb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::networkList
0x703c0  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList::Networks
0x703c5  brfalse  loc_7044E
0x703ca  ldarg.0
0x703cb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::networkList
0x703d0  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList::Networks
0x703d5  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x703da  stloc.s  4
0x703dc  br.s     loc_7042E
0x703de  ldloc.s  4
0x703e0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x703e5  castclass Microsoft.Windows.ManagementUI.CombinedControls.UINetwork
0x703ea  stloc.s  5
0x703ec  ldloc.s  5
0x703ee  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Guid()
0x703f3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x703f8  brtrue.s loc_7042E
0x703fa  ldloc.s  5
0x703fc  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Name()
0x70401  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x70406  brtrue.s loc_7041C
0x70408  ldarg.0
0x70409  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x7040e  ldloc.s  5
0x70410  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Name()
0x70415  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x7041a  br.s     loc_7042E
0x7041c  ldarg.0
0x7041d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x70422  ldloc.s  5
0x70424  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Guid()
0x70429  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x7042e  ldloc.s  4
0x70430  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x70435  brtrue.s loc_703DE
0x70437  leave.s  loc_7044E
0x70439  ldloc.s  4
0x7043b  isinst   [mscorlib]System.IDisposable
0x70440  stloc.s  6
0x70442  ldloc.s  6
0x70444  brfalse.s loc_7044D
0x70446  ldloc.s  6
0x70448  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7044d  endfinally
0x7044e  ldarg.0
0x7044f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIConditions Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::uiTaskConditionsForTask
0x70454  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings Microsoft.Windows.ManagementUI.CombinedControls.UIConditions::get_NetworkSettings()
0x70459  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings::get_Guid()
0x7045e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x70463  brtrue   loc_705D3
0x70468  ldarg.0
0x70469  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::networkList
0x7046e  brfalse  loc_704FB
0x70473  ldarg.0
0x70474  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::networkList
0x70479  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList::Networks
0x7047e  brfalse.s loc_704FB
0x70480  ldarg.0
0x70481  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::networkList
0x70486  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList::Networks
0x7048b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x70490  stloc.s  4
0x70492  br.s     loc_704DB
0x70494  ldloc.s  4
0x70496  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7049b  castclass Microsoft.Windows.ManagementUI.CombinedControls.UINetwork
0x704a0  stloc.s  7
0x704a2  ldarg.0
0x704a3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIConditions Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::uiTaskConditionsForTask
0x704a8  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings Microsoft.Windows.ManagementUI.CombinedControls.UIConditions::get_NetworkSettings()
0x704ad  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings::get_Guid()
0x704b2  ldloc.s  7
0x704b4  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Guid()
0x704b9  ldc.i4.5
0x704ba  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x704bf  brtrue.s loc_704DB
0x704c1  ldloc.s  7
0x704c3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Name()
0x704c8  stloc.0
0x704c9  ldloc.0
0x704ca  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x704cf  brfalse.s loc_704E4
0x704d1  ldloc.s  7
0x704d3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Guid()
0x704d8  stloc.0
0x704d9  leave.s  loc_704FB
0x704db  ldloc.s  4
0x704dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x704e2  brtrue.s loc_70494
0x704e4  leave.s  loc_704FB
0x704e6  ldloc.s  4
0x704e8  isinst   [mscorlib]System.IDisposable
0x704ed  stloc.s  6
0x704ef  ldloc.s  6
0x704f1  brfalse.s loc_704FA
0x704f3  ldloc.s  6
0x704f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x704fa  endfinally
0x704fb  ldc.i4.0
0x704fc  stloc.1
0x704fd  br.s     loc_70535
0x704ff  ldloc.0
0x70500  ldarg.0
0x70501  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x70506  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x7050b  ldloc.1
0x7050c  callvirt instance object [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::get_Item(int32)
0x70511  callvirt instance string [mscorlib]System.Object::ToString()
0x70516  ldc.i4.1
0x70517  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7051c  brtrue.s loc_70531
0x7051e  ldarg.0
0x7051f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x70524  ldloc.1
0x70525  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetSelectedItem(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, int32 index)
0x7052a  ldc.i4.1
0x7052b  stloc.2
0x7052c  br       loc_705D3
0x70531  ldloc.1
0x70532  ldc.i4.1
0x70533  add
0x70534  stloc.1
0x70535  ldloc.1
0x70536  ldarg.0
0x70537  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x7053c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x70541  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::get_Count()
0x70546  blt.s    loc_704FF
0x70548  br       loc_705D3
0x7054d  ldarg.0
0x7054e  ldarg.0
0x7054f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIConditions Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::uiTaskConditionsForTask
0x70554  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings Microsoft.Windows.ManagementUI.CombinedControls.UIConditions::get_NetworkSettings()
0x70559  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings::get_Name()
0x7055e  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::stringCachedRemoteNetworkName
0x70563  ldarg.0
0x70564  ldarg.0
0x70565  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIConditions Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::uiTaskConditionsForTask
0x7056a  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings Microsoft.Windows.ManagementUI.CombinedControls.UIConditions::get_NetworkSettings()
0x7056f  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings::get_Guid()
0x70574  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::stringCachedRemoteNetworkGuid
0x70579  ldarg.0
0x7057a  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::stringCachedRemoteNetworkName
0x7057f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x70584  brtrue.s loc_705A7
0x70586  ldarg.0
0x70587  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x7058c  ldarg.0
0x7058d  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::stringCachedRemoteNetworkName
0x70592  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x70597  ldarg.0
0x70598  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x7059d  ldc.i4.1
0x7059e  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetSelectedItem(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, int32 index)
0x705a3  ldc.i4.1
0x705a4  stloc.2
0x705a5  br.s     loc_705D3
0x705a7  ldarg.0
0x705a8  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::stringCachedRemoteNetworkGuid
0x705ad  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x705b2  brtrue.s loc_705D3
0x705b4  ldarg.0
0x705b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x705ba  ldarg.0
0x705bb  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::stringCachedRemoteNetworkGuid
0x705c0  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x705c5  ldarg.0
0x705c6  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x705cb  ldc.i4.1
0x705cc  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetSelectedItem(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, int32 index)
0x705d1  ldc.i4.1
0x705d2  stloc.2
0x705d3  ldloc.2
0x705d4  brtrue.s loc_705E2
0x705d6  ldarg.0
0x705d7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x705dc  ldc.i4.0
0x705dd  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetSelectedItem(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, int32 index)
0x705e2  ldc.i4.1
0x705e3  ldarg.0
0x705e4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x705e9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x705ee  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::get_Count()
0x705f3  bne.un.s loc_70601
0x705f5  ldarg.0
0x705f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x705fb  ldc.i4.0
0x705fc  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::EnableControl(class [System.Windows.Forms]System.Windows.Forms.Control ctl, bool enable)
0x70601  ret
```
