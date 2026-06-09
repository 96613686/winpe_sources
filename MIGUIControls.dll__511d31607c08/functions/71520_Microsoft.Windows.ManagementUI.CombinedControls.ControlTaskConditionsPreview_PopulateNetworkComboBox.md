# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::PopulateNetworkComboBox

- ea: `0x71520`
- end: `0x7179f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::PopulateNetworkComboBox`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x717a0`

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
- `0x71520`

## string_xrefs

- `0x71531`: `ComboEntryNetworkAnyConnection`

## pseudocode

```c

```

## disassembly

```asm
0x71520  ldarg.0
0x71521  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x71526  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::ClearComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo)
0x7152b  ldarg.0
0x7152c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x71531  ldstr    aComboentrynetw// "ComboEntryNetworkAnyConnection"
0x71536  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7153b  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x71540  ldarg.0
0x71541  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x71546  brfalse  loc_7179E
0x7154b  ldarg.0
0x7154c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x71551  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x71556  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x7155b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x71560  ldsfld   string [mscorlib]System.String::Empty
0x71565  stloc.0
0x71566  ldc.i4.0
0x71567  stloc.2
0x71568  brfalse  loc_716EA
0x7156d  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.NetworkListManager::.ctor()
0x71572  stloc.3
0x71573  ldarg.0
0x71574  ldloc.3
0x71575  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.NetworkListManager::GetNetworkList()
0x7157a  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::networkList
0x7157f  ldarg.0
0x71580  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::networkList
0x71585  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList::Networks
0x7158a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x7158f  stloc.s  4
0x71591  br.s     loc_715E3
0x71593  ldloc.s  4
0x71595  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7159a  castclass Microsoft.Windows.ManagementUI.CombinedControls.UINetwork
0x7159f  stloc.s  5
0x715a1  ldloc.s  5
0x715a3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Guid()
0x715a8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x715ad  brtrue.s loc_715E3
0x715af  ldloc.s  5
0x715b1  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Name()
0x715b6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x715bb  brtrue.s loc_715D1
0x715bd  ldarg.0
0x715be  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x715c3  ldloc.s  5
0x715c5  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Name()
0x715ca  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x715cf  br.s     loc_715E3
0x715d1  ldarg.0
0x715d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x715d7  ldloc.s  5
0x715d9  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Guid()
0x715de  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x715e3  ldloc.s  4
0x715e5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x715ea  brtrue.s loc_71593
0x715ec  leave.s  loc_71603
0x715ee  ldloc.s  4
0x715f0  isinst   [mscorlib]System.IDisposable
0x715f5  stloc.s  6
0x715f7  ldloc.s  6
0x715f9  brfalse.s loc_71602
0x715fb  ldloc.s  6
0x715fd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x71602  endfinally
0x71603  ldarg.0
0x71604  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIConditions Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::uiTaskConditionsForTask
0x71609  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings Microsoft.Windows.ManagementUI.CombinedControls.UIConditions::get_NetworkSettings()
0x7160e  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings::get_Guid()
0x71613  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x71618  brtrue   loc_71770
0x7161d  ldarg.0
0x7161e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::networkList
0x71623  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UINetworkList::Networks
0x71628  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x7162d  stloc.s  4
0x7162f  br.s     loc_71678
0x71631  ldloc.s  4
0x71633  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x71638  castclass Microsoft.Windows.ManagementUI.CombinedControls.UINetwork
0x7163d  stloc.s  7
0x7163f  ldarg.0
0x71640  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIConditions Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::uiTaskConditionsForTask
0x71645  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings Microsoft.Windows.ManagementUI.CombinedControls.UIConditions::get_NetworkSettings()
0x7164a  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings::get_Guid()
0x7164f  ldloc.s  7
0x71651  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Guid()
0x71656  ldc.i4.5
0x71657  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x7165c  brtrue.s loc_71678
0x7165e  ldloc.s  7
0x71660  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Name()
0x71665  stloc.0
0x71666  ldloc.0
0x71667  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7166c  brfalse.s loc_71681
0x7166e  ldloc.s  7
0x71670  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetwork::get_Guid()
0x71675  stloc.0
0x71676  leave.s  loc_71698
0x71678  ldloc.s  4
0x7167a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7167f  brtrue.s loc_71631
0x71681  leave.s  loc_71698
0x71683  ldloc.s  4
0x71685  isinst   [mscorlib]System.IDisposable
0x7168a  stloc.s  6
0x7168c  ldloc.s  6
0x7168e  brfalse.s loc_71697
0x71690  ldloc.s  6
0x71692  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x71697  endfinally
0x71698  ldc.i4.0
0x71699  stloc.1
0x7169a  br.s     loc_716D2
0x7169c  ldloc.0
0x7169d  ldarg.0
0x7169e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x716a3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x716a8  ldloc.1
0x716a9  callvirt instance object [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::get_Item(int32)
0x716ae  callvirt instance string [mscorlib]System.Object::ToString()
0x716b3  ldc.i4.1
0x716b4  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x716b9  brtrue.s loc_716CE
0x716bb  ldarg.0
0x716bc  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x716c1  ldloc.1
0x716c2  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetSelectedItem(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, int32 index)
0x716c7  ldc.i4.1
0x716c8  stloc.2
0x716c9  br       loc_71770
0x716ce  ldloc.1
0x716cf  ldc.i4.1
0x716d0  add
0x716d1  stloc.1
0x716d2  ldloc.1
0x716d3  ldarg.0
0x716d4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x716d9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x716de  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::get_Count()
0x716e3  blt.s    loc_7169C
0x716e5  br       loc_71770
0x716ea  ldarg.0
0x716eb  ldarg.0
0x716ec  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIConditions Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::uiTaskConditionsForTask
0x716f1  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings Microsoft.Windows.ManagementUI.CombinedControls.UIConditions::get_NetworkSettings()
0x716f6  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings::get_Name()
0x716fb  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::stringCachedRemoteNetworkName
0x71700  ldarg.0
0x71701  ldarg.0
0x71702  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIConditions Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::uiTaskConditionsForTask
0x71707  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings Microsoft.Windows.ManagementUI.CombinedControls.UIConditions::get_NetworkSettings()
0x7170c  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UINetworkSettings::get_Guid()
0x71711  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::stringCachedRemoteNetworkGuid
0x71716  ldarg.0
0x71717  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::stringCachedRemoteNetworkName
0x7171c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x71721  brtrue.s loc_71744
0x71723  ldarg.0
0x71724  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x71729  ldarg.0
0x7172a  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::stringCachedRemoteNetworkName
0x7172f  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x71734  ldarg.0
0x71735  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x7173a  ldc.i4.1
0x7173b  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetSelectedItem(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, int32 index)
0x71740  ldc.i4.1
0x71741  stloc.2
0x71742  br.s     loc_71770
0x71744  ldarg.0
0x71745  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::stringCachedRemoteNetworkGuid
0x7174a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7174f  brtrue.s loc_71770
0x71751  ldarg.0
0x71752  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x71757  ldarg.0
0x71758  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::stringCachedRemoteNetworkGuid
0x7175d  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x71762  ldarg.0
0x71763  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x71768  ldc.i4.1
0x71769  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetSelectedItem(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, int32 index)
0x7176e  ldc.i4.1
0x7176f  stloc.2
0x71770  ldloc.2
0x71771  brtrue.s loc_7177F
0x71773  ldarg.0
0x71774  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x71779  ldc.i4.0
0x7177a  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetSelectedItem(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, int32 index)
0x7177f  ldc.i4.1
0x71780  ldarg.0
0x71781  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x71786  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x7178b  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::get_Count()
0x71790  bne.un.s loc_7179E
0x71792  ldarg.0
0x71793  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x71798  ldc.i4.0
0x71799  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::EnableControl(class [System.Windows.Forms]System.Windows.Forms.Control ctl, bool enable)
0x7179e  ret
```
