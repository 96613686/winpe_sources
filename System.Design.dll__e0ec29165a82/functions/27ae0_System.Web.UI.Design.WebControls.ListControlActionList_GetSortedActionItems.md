# System.Web.UI.Design.WebControls.ListControlActionList::GetSortedActionItems

- ea: `0x27ae0`
- end: `0x27be9`
- name: `System.Web.UI.Design.WebControls.ListControlActionList::GetSortedActionItems`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x27ae0`
- `0x584f0`
- `0x59950`
- `0x59990`
- `0x5af90`
- `0x5d870`
- `0x5d880`
- `0x5d8b0`
- `0x8ef40`

## string_xrefs

- `0x27b29`: `BaseDataBoundControl_ConfigureDataVerbDesc`
- `0x27b15`: `ListControl_ConfigureDataVerb`

## pseudocode

```c

```

## disassembly

```asm
0x27ae0  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0x27ae5  stloc.0
0x27ae6  ldarg.0
0x27ae7  ldfld    class System.Web.UI.Design.WebControls.ListControlDesigner System.Web.UI.Design.WebControls.ListControlActionList::_listControlDesigner
0x27aec  callvirt instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x27af1  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x27af6  stloc.1
0x27af7  ldloc.1
0x27af8  ldstr    aDatasourceid// "DataSourceID"
0x27afd  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x27b02  stloc.2
0x27b03  ldloc.2
0x27b04  brfalse.s loc_27B3E
0x27b06  ldloc.2
0x27b07  callvirt instance bool [System]System.ComponentModel.MemberDescriptor::get_IsBrowsable()
0x27b0c  brfalse.s loc_27B3E
0x27b0e  ldloc.0
0x27b0f  ldarg.0
0x27b10  ldstr    aConnecttodatas// "ConnectToDataSource"
0x27b15  ldstr    aListcontrolCon// "ListControl_ConfigureDataVerb"
0x27b1a  call     string System.Design.SR::GetString(string name)
0x27b1f  ldstr    aBasedataboundc_1// "BaseDataBoundControl_DataActionGroup"
0x27b24  call     string System.Design.SR::GetString(string name)
0x27b29  ldstr    aBasedataboundc_2// "BaseDataBoundControl_ConfigureDataVerbD"...
0x27b2e  call     string System.Design.SR::GetString(string name)
0x27b33  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x27b38  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x27b3d  pop
0x27b3e  ldarg.0
0x27b3f  ldfld    class System.Web.UI.Design.IDataSourceDesigner System.Web.UI.Design.WebControls.ListControlActionList::_dataSourceDesigner
0x27b44  isinst   System.Web.UI.Design.ControlDesigner
0x27b49  stloc.3
0x27b4a  ldloc.3
0x27b4b  brfalse.s loc_27B64
0x27b4d  ldloc.0
0x27b4e  ldc.i4.0
0x27b4f  callvirt instance class System.ComponentModel.Design.DesignerActionItem System.ComponentModel.Design.DesignerActionItemCollection::get_Item(int32 index)
0x27b54  castclass System.ComponentModel.Design.DesignerActionMethodItem
0x27b59  ldloc.3
0x27b5a  callvirt instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x27b5f  callvirt instance void System.ComponentModel.Design.DesignerActionMethodItem::set_RelatedComponent(class [System]System.ComponentModel.IComponent value)
0x27b64  ldloc.1
0x27b65  ldstr    aItems// "Items"
0x27b6a  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x27b6f  stloc.2
0x27b70  ldloc.2
0x27b71  brfalse.s loc_27BA6
0x27b73  ldloc.2
0x27b74  callvirt instance bool [System]System.ComponentModel.MemberDescriptor::get_IsBrowsable()
0x27b79  brfalse.s loc_27BA6
0x27b7b  ldloc.0
0x27b7c  ldarg.0
0x27b7d  ldstr    aEdititems// "EditItems"
0x27b82  ldstr    aListcontrolEdi// "ListControl_EditItems"
0x27b87  call     string System.Design.SR::GetString(string name)
0x27b8c  ldstr    aActions// "Actions"
0x27b91  ldstr    aListcontrolEdi_0// "ListControl_EditItemsDesc"
0x27b96  call     string System.Design.SR::GetString(string name)
0x27b9b  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x27ba0  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x27ba5  pop
0x27ba6  ldloc.1
0x27ba7  ldstr    aAutopostback// "AutoPostBack"
0x27bac  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x27bb1  stloc.2
0x27bb2  ldloc.2
0x27bb3  brfalse.s loc_27BE7
0x27bb5  ldloc.2
0x27bb6  callvirt instance bool [System]System.ComponentModel.MemberDescriptor::get_IsBrowsable()
0x27bbb  brfalse.s loc_27BE7
0x27bbd  ldloc.0
0x27bbe  ldstr    aAutopostback// "AutoPostBack"
0x27bc3  ldstr    aListcontrolEna// "ListControl_EnableAutoPostBack"
0x27bc8  call     string System.Design.SR::GetString(string name)
0x27bcd  ldstr    aBehavior// "Behavior"
0x27bd2  ldstr    aListcontrolEna_0// "ListControl_EnableAutoPostBackDesc"
0x27bd7  call     string System.Design.SR::GetString(string name)
0x27bdc  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x27be1  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x27be6  pop
0x27be7  ldloc.0
0x27be8  ret
```
