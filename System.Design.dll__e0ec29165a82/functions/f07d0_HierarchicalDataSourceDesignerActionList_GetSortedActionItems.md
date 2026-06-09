# HierarchicalDataSourceDesignerActionList::GetSortedActionItems

- ea: `0xf07d0`
- end: `0xf0866`
- name: `HierarchicalDataSourceDesignerActionList::GetSortedActionItems`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0xdaa0`
- `0xdab0`
- `0x59370`
- `0x598e0`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`
- `0xf07d0`

## string_xrefs

- `0xf07e4`: `Configure`
- `0xf07e9`: `DataSourceDesigner_ConfigureDataSourceVerb`
- `0xf07fd`: `DataSourceDesigner_ConfigureDataSourceVerbDesc`

## pseudocode

```c

```

## disassembly

```asm
0xf07d0  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0xf07d5  stloc.0
0xf07d6  ldarg.0
0xf07d7  ldfld    class System.Web.UI.Design.HierarchicalDataSourceDesigner HierarchicalDataSourceDesignerActionList::_parent
0xf07dc  callvirt instance bool System.Web.UI.Design.HierarchicalDataSourceDesigner::get_CanConfigure()
0xf07e1  brfalse.s loc_F081D
0xf07e3  ldarg.0
0xf07e4  ldstr    aConfigure// "Configure"
0xf07e9  ldstr    aDatasourcedesi_0// "DataSourceDesigner_ConfigureDataSourceV"...
0xf07ee  call     string System.Design.SR::GetString(string name)
0xf07f3  ldstr    aDatasourcedesi_1// "DataSourceDesigner_DataActionGroup"
0xf07f8  call     string System.Design.SR::GetString(string name)
0xf07fd  ldstr    aDatasourcedesi_2// "DataSourceDesigner_ConfigureDataSourceV"...
0xf0802  call     string System.Design.SR::GetString(string name)
0xf0807  ldc.i4.1
0xf0808  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf080d  stloc.1
0xf080e  ldloc.1
0xf080f  ldc.i4.1
0xf0810  callvirt instance void System.ComponentModel.Design.DesignerActionItem::set_AllowAssociate(bool value)
0xf0815  ldloc.0
0xf0816  ldloc.1
0xf0817  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf081c  pop
0xf081d  ldarg.0
0xf081e  ldfld    class System.Web.UI.Design.HierarchicalDataSourceDesigner HierarchicalDataSourceDesignerActionList::_parent
0xf0823  callvirt instance bool System.Web.UI.Design.HierarchicalDataSourceDesigner::get_CanRefreshSchema()
0xf0828  brfalse.s loc_F0864
0xf082a  ldarg.0
0xf082b  ldstr    aRefreshschema// "RefreshSchema"
0xf0830  ldstr    aDatasourcedesi_3// "DataSourceDesigner_RefreshSchemaVerb"
0xf0835  call     string System.Design.SR::GetString(string name)
0xf083a  ldstr    aDatasourcedesi_1// "DataSourceDesigner_DataActionGroup"
0xf083f  call     string System.Design.SR::GetString(string name)
0xf0844  ldstr    aDatasourcedesi_4// "DataSourceDesigner_RefreshSchemaVerbDes"...
0xf0849  call     string System.Design.SR::GetString(string name)
0xf084e  ldc.i4.0
0xf084f  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf0854  stloc.2
0xf0855  ldloc.2
0xf0856  ldc.i4.1
0xf0857  callvirt instance void System.ComponentModel.Design.DesignerActionItem::set_AllowAssociate(bool value)
0xf085c  ldloc.0
0xf085d  ldloc.2
0xf085e  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf0863  pop
0xf0864  ldloc.0
0xf0865  ret
```
