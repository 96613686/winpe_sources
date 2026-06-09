# System.Web.UI.Design.WebControls.HierarchicalDataBoundControlActionList::GetSortedActionItems

- ea: `0x27320`
- end: `0x273a3`
- name: `System.Web.UI.Design.WebControls.HierarchicalDataBoundControlActionList::GetSortedActionItems`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x27320`
- `0x584f0`
- `0x5af90`
- `0x5aff0`
- `0x5d870`
- `0x5d880`
- `0x5d8b0`
- `0x8ef40`

## string_xrefs

- `0x27352`: `BaseDataBoundControl_ConfigureDataVerb`
- `0x27366`: `BaseDataBoundControl_ConfigureDataVerbDesc`

## pseudocode

```c

```

## disassembly

```asm
0x27320  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0x27325  stloc.0
0x27326  ldarg.0
0x27327  ldfld    class System.Web.UI.Design.WebControls.HierarchicalDataBoundControlDesigner System.Web.UI.Design.WebControls.HierarchicalDataBoundControlActionList::_controlDesigner
0x2732c  callvirt instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x27331  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x27336  ldstr    aDatasourceid// "DataSourceID"
0x2733b  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x27340  stloc.1
0x27341  ldloc.1
0x27342  brfalse.s loc_2737B
0x27344  ldloc.1
0x27345  callvirt instance bool [System]System.ComponentModel.MemberDescriptor::get_IsBrowsable()
0x2734a  brfalse.s loc_2737B
0x2734c  ldloc.0
0x2734d  ldstr    aDatasourceid// "DataSourceID"
0x27352  ldstr    aBasedataboundc_0// "BaseDataBoundControl_ConfigureDataVerb"
0x27357  call     string System.Design.SR::GetString(string name)
0x2735c  ldstr    aBasedataboundc_1// "BaseDataBoundControl_DataActionGroup"
0x27361  call     string System.Design.SR::GetString(string name)
0x27366  ldstr    aBasedataboundc_2// "BaseDataBoundControl_ConfigureDataVerbD"...
0x2736b  call     string System.Design.SR::GetString(string name)
0x27370  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x27375  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x2737a  pop
0x2737b  ldarg.0
0x2737c  ldfld    class System.Web.UI.Design.IHierarchicalDataSourceDesigner System.Web.UI.Design.WebControls.HierarchicalDataBoundControlActionList::_dataSourceDesigner
0x27381  isinst   System.Web.UI.Design.ControlDesigner
0x27386  stloc.2
0x27387  ldloc.2
0x27388  brfalse.s loc_273A1
0x2738a  ldloc.0
0x2738b  ldc.i4.0
0x2738c  callvirt instance class System.ComponentModel.Design.DesignerActionItem System.ComponentModel.Design.DesignerActionItemCollection::get_Item(int32 index)
0x27391  castclass System.ComponentModel.Design.DesignerActionPropertyItem
0x27396  ldloc.2
0x27397  callvirt instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x2739c  callvirt instance void System.ComponentModel.Design.DesignerActionPropertyItem::set_RelatedComponent(class [System]System.ComponentModel.IComponent value)
0x273a1  ldloc.0
0x273a2  ret
```
