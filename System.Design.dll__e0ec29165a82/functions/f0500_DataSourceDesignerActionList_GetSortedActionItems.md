# DataSourceDesignerActionList::GetSortedActionItems

- ea: `0xf0500`
- end: `0xf0596`
- name: `DataSourceDesignerActionList::GetSortedActionItems`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0xa570`
- `0xa580`
- `0x59370`
- `0x598e0`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`
- `0xf0500`

## string_xrefs

- `0xf0514`: `Configure`
- `0xf0519`: `DataSourceDesigner_ConfigureDataSourceVerb`
- `0xf052d`: `DataSourceDesigner_ConfigureDataSourceVerbDesc`

## pseudocode

```c

```

## disassembly

```asm
0xf0500  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0xf0505  stloc.0
0xf0506  ldarg.0
0xf0507  ldfld    class System.Web.UI.Design.DataSourceDesigner DataSourceDesignerActionList::_parent
0xf050c  callvirt instance bool System.Web.UI.Design.DataSourceDesigner::get_CanConfigure()
0xf0511  brfalse.s loc_F054D
0xf0513  ldarg.0
0xf0514  ldstr    aConfigure// "Configure"
0xf0519  ldstr    aDatasourcedesi_0// "DataSourceDesigner_ConfigureDataSourceV"...
0xf051e  call     string System.Design.SR::GetString(string name)
0xf0523  ldstr    aDatasourcedesi_1// "DataSourceDesigner_DataActionGroup"
0xf0528  call     string System.Design.SR::GetString(string name)
0xf052d  ldstr    aDatasourcedesi_2// "DataSourceDesigner_ConfigureDataSourceV"...
0xf0532  call     string System.Design.SR::GetString(string name)
0xf0537  ldc.i4.1
0xf0538  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf053d  stloc.1
0xf053e  ldloc.1
0xf053f  ldc.i4.1
0xf0540  callvirt instance void System.ComponentModel.Design.DesignerActionItem::set_AllowAssociate(bool value)
0xf0545  ldloc.0
0xf0546  ldloc.1
0xf0547  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf054c  pop
0xf054d  ldarg.0
0xf054e  ldfld    class System.Web.UI.Design.DataSourceDesigner DataSourceDesignerActionList::_parent
0xf0553  callvirt instance bool System.Web.UI.Design.DataSourceDesigner::get_CanRefreshSchema()
0xf0558  brfalse.s loc_F0594
0xf055a  ldarg.0
0xf055b  ldstr    aRefreshschema// "RefreshSchema"
0xf0560  ldstr    aDatasourcedesi_3// "DataSourceDesigner_RefreshSchemaVerb"
0xf0565  call     string System.Design.SR::GetString(string name)
0xf056a  ldstr    aDatasourcedesi_1// "DataSourceDesigner_DataActionGroup"
0xf056f  call     string System.Design.SR::GetString(string name)
0xf0574  ldstr    aDatasourcedesi_4// "DataSourceDesigner_RefreshSchemaVerbDes"...
0xf0579  call     string System.Design.SR::GetString(string name)
0xf057e  ldc.i4.0
0xf057f  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf0584  stloc.2
0xf0585  ldloc.2
0xf0586  ldc.i4.1
0xf0587  callvirt instance void System.ComponentModel.Design.DesignerActionItem::set_AllowAssociate(bool value)
0xf058c  ldloc.0
0xf058d  ldloc.2
0xf058e  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf0593  pop
0xf0594  ldloc.0
0xf0595  ret
```
