# LoginDesignerActionList::GetSortedActionItems

- ea: `0xf8f80`
- end: `0xf902e`
- name: `LoginDesignerActionList::GetSortedActionItems`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x2660`
- `0x292e0`
- `0x598e0`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`
- `0xf8f80`

## string_xrefs

- `0xf8fad`: `WebControls_ConvertToTemplate`
- `0xf8fa8`: `ConvertToTemplate`
- `0xf8fbc`: `WebControls_ConvertToTemplateDescription`

## pseudocode

```c

```

## disassembly

```asm
0xf8f80  ldarg.0
0xf8f81  ldfld    class System.Web.UI.Design.WebControls.LoginDesigner LoginDesignerActionList::_parent
0xf8f86  callvirt instance bool System.Web.UI.Design.ControlDesigner::get_InTemplateMode()
0xf8f8b  brfalse.s loc_F8F93
0xf8f8d  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0xf8f92  ret
0xf8f93  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0xf8f98  stloc.0
0xf8f99  ldarg.0
0xf8f9a  ldfld    class System.Web.UI.Design.WebControls.LoginDesigner LoginDesignerActionList::_parent
0xf8f9f  callvirt instance bool System.Web.UI.Design.WebControls.LoginDesigner::get_Templated()
0xf8fa4  brtrue.s loc_F8FD4
0xf8fa6  ldloc.0
0xf8fa7  ldarg.0
0xf8fa8  ldstr    aConverttotempl// "ConvertToTemplate"
0xf8fad  ldstr    aWebcontrolsCon// "WebControls_ConvertToTemplate"
0xf8fb2  call     string System.Design.SR::GetString(string name)
0xf8fb7  ldsfld   string [mscorlib]System.String::Empty
0xf8fbc  ldstr    aWebcontrolsCon_1// "WebControls_ConvertToTemplateDescriptio"...
0xf8fc1  call     string System.Design.SR::GetString(string name)
0xf8fc6  ldc.i4.1
0xf8fc7  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf8fcc  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf8fd1  pop
0xf8fd2  br.s     loc_F9000
0xf8fd4  ldloc.0
0xf8fd5  ldarg.0
0xf8fd6  ldstr    aReset// "Reset"
0xf8fdb  ldstr    aWebcontrolsRes// "WebControls_Reset"
0xf8fe0  call     string System.Design.SR::GetString(string name)
0xf8fe5  ldsfld   string [mscorlib]System.String::Empty
0xf8fea  ldstr    aWebcontrolsRes_1// "WebControls_ResetDescription"
0xf8fef  call     string System.Design.SR::GetString(string name)
0xf8ff4  ldc.i4.1
0xf8ff5  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf8ffa  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf8fff  pop
0xf9000  ldloc.0
0xf9001  ldarg.0
0xf9002  ldstr    aLaunchwebadmin// "LaunchWebAdmin"
0xf9007  ldstr    aLoginLaunchweb// "Login_LaunchWebAdmin"
0xf900c  call     string System.Design.SR::GetString(string name)
0xf9011  ldsfld   string [mscorlib]System.String::Empty
0xf9016  ldstr    aLoginLaunchweb_0// "Login_LaunchWebAdminDescription"
0xf901b  call     string System.Design.SR::GetString(string name)
0xf9020  ldc.i4.1
0xf9021  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf9026  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf902b  pop
0xf902c  ldloc.0
0xf902d  ret
```
