# System.Web.UI.Design.WebControls.DataBoundControlActionList::GetSortedActionItems

- ea: `0x1bdc0`
- end: `0x1be43`
- name: `System.Web.UI.Design.WebControls.DataBoundControlActionList::GetSortedActionItems`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x15970`

## callees

- `0x1bdc0`
- `0x584f0`
- `0x5af90`
- `0x5aff0`
- `0x5d870`
- `0x5d880`
- `0x5d8b0`
- `0x8ef40`

## string_xrefs

- `0x1bdf2`: `BaseDataBoundControl_ConfigureDataVerb`
- `0x1be06`: `BaseDataBoundControl_ConfigureDataVerbDesc`

## pseudocode

```c

```

## disassembly

```asm
0x1bdc0  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0x1bdc5  stloc.0
0x1bdc6  ldarg.0
0x1bdc7  ldfld    class System.Web.UI.Design.ControlDesigner System.Web.UI.Design.WebControls.DataBoundControlActionList::_controlDesigner
0x1bdcc  callvirt instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x1bdd1  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x1bdd6  ldstr    aDatasourceid// "DataSourceID"
0x1bddb  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x1bde0  stloc.1
0x1bde1  ldloc.1
0x1bde2  brfalse.s loc_1BE1B
0x1bde4  ldloc.1
0x1bde5  callvirt instance bool [System]System.ComponentModel.MemberDescriptor::get_IsBrowsable()
0x1bdea  brfalse.s loc_1BE1B
0x1bdec  ldloc.0
0x1bded  ldstr    aDatasourceid// "DataSourceID"
0x1bdf2  ldstr    aBasedataboundc_0// "BaseDataBoundControl_ConfigureDataVerb"
0x1bdf7  call     string System.Design.SR::GetString(string name)
0x1bdfc  ldstr    aBasedataboundc_1// "BaseDataBoundControl_DataActionGroup"
0x1be01  call     string System.Design.SR::GetString(string name)
0x1be06  ldstr    aBasedataboundc_2// "BaseDataBoundControl_ConfigureDataVerbD"...
0x1be0b  call     string System.Design.SR::GetString(string name)
0x1be10  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x1be15  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x1be1a  pop
0x1be1b  ldarg.0
0x1be1c  ldfld    class System.Web.UI.Design.IDataSourceDesigner System.Web.UI.Design.WebControls.DataBoundControlActionList::_dataSourceDesigner
0x1be21  isinst   System.Web.UI.Design.ControlDesigner
0x1be26  stloc.2
0x1be27  ldloc.2
0x1be28  brfalse.s loc_1BE41
0x1be2a  ldloc.0
0x1be2b  ldc.i4.0
0x1be2c  callvirt instance class System.ComponentModel.Design.DesignerActionItem System.ComponentModel.Design.DesignerActionItemCollection::get_Item(int32 index)
0x1be31  castclass System.ComponentModel.Design.DesignerActionPropertyItem
0x1be36  ldloc.2
0x1be37  callvirt instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x1be3c  callvirt instance void System.ComponentModel.Design.DesignerActionPropertyItem::set_RelatedComponent(class [System]System.ComponentModel.IComponent value)
0x1be41  ldloc.0
0x1be42  ret
```
