# ContentDesignerActionList::GetSortedActionItems

- ea: `0xf5b90`
- end: `0xf5c33`
- name: `ContentDesignerActionList::GetSortedActionItems`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x24f0`
- `0xdfa0`
- `0x18c90`
- `0x18dd0`
- `0x593e0`
- `0x598e0`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`
- `0xf5b90`

## string_xrefs

- `0xf5bd8`: `CreateBlankContent`
- `0xf5bdd`: `Content_CreateBlankContent`

## pseudocode

```c

```

## disassembly

```asm
0xf5b90  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0xf5b95  stloc.0
0xf5b96  ldc.i4.0
0xf5b97  stloc.1
0xf5b98  ldarg.0
0xf5b99  ldfld    class System.Web.UI.Design.WebControls.ContentDesigner ContentDesignerActionList::_parent
0xf5b9e  callvirt instance class System.Web.UI.Design.IContentResolutionService System.Web.UI.Design.WebControls.ContentDesigner::get_ContentResolutionService()
0xf5ba3  brfalse.s loc_F5BD3
0xf5ba5  ldarg.0
0xf5ba6  ldfld    class System.Web.UI.Design.WebControls.ContentDesigner ContentDesignerActionList::_parent
0xf5bab  callvirt instance class System.Web.UI.Design.ContentDefinition System.Web.UI.Design.WebControls.ContentDesigner::GetContentDefinition()
0xf5bb0  brfalse.s loc_F5BD3
0xf5bb2  ldarg.0
0xf5bb3  ldfld    class System.Web.UI.Design.WebControls.ContentDesigner ContentDesignerActionList::_parent
0xf5bb8  callvirt instance class System.Web.UI.Design.IContentResolutionService System.Web.UI.Design.WebControls.ContentDesigner::get_ContentResolutionService()
0xf5bbd  ldarg.0
0xf5bbe  ldfld    class System.Web.UI.Design.WebControls.ContentDesigner ContentDesignerActionList::_parent
0xf5bc3  callvirt instance class System.Web.UI.Design.ContentDefinition System.Web.UI.Design.WebControls.ContentDesigner::GetContentDefinition()
0xf5bc8  callvirt instance string System.Web.UI.Design.ContentDefinition::get_ContentPlaceHolderID()
0xf5bcd  callvirt instance valuetype System.Web.UI.Design.ContentDesignerState System.Web.UI.Design.IContentResolutionService::GetContentDesignerState(string identifier)
0xf5bd2  stloc.1
0xf5bd3  ldloc.1
0xf5bd4  brtrue.s loc_F5C06
0xf5bd6  ldloc.0
0xf5bd7  ldarg.0
0xf5bd8  ldstr    aCreateblankcon// "CreateBlankContent"
0xf5bdd  ldstr    aContentCreateb// "Content_CreateBlankContent"
0xf5be2  call     string System.Design.SR::GetString(string name)
0xf5be7  ldsfld   string [mscorlib]System.String::Empty
0xf5bec  ldsfld   string [mscorlib]System.String::Empty
0xf5bf1  ldc.i4.1
0xf5bf2  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf5bf7  dup
0xf5bf8  ldc.i4.0
0xf5bf9  callvirt instance void System.ComponentModel.Design.DesignerActionItem::set_ShowInSourceView(bool value)
0xf5bfe  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf5c03  pop
0xf5c04  br.s     loc_F5C31
0xf5c06  ldc.i4.1
0xf5c07  ldloc.1
0xf5c08  bne.un.s loc_F5C31
0xf5c0a  ldloc.0
0xf5c0b  ldarg.0
0xf5c0c  ldstr    aClearregion// "ClearRegion"
0xf5c11  ldstr    aContentClearre// "Content_ClearRegion"
0xf5c16  call     string System.Design.SR::GetString(string name)
0xf5c1b  ldsfld   string [mscorlib]System.String::Empty
0xf5c20  ldsfld   string [mscorlib]System.String::Empty
0xf5c25  ldc.i4.1
0xf5c26  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf5c2b  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf5c30  pop
0xf5c31  ldloc.0
0xf5c32  ret
```
