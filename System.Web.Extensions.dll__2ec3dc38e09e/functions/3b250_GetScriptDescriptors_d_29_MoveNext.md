# <GetScriptDescriptors>d__29::MoveNext

- ea: `0x3b250`
- end: `0x3b34e`
- name: `<GetScriptDescriptors>d__29::MoveNext`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0xfe80`
- `0x12ea0`
- `0x13400`
- `0x144c0`
- `0x1a010`
- `0x1a080`
- `0x1a0d0`
- `0x1a0f0`
- `0x2b630`
- `0x3b250`

## string_xrefs

- `0x3b297`: `Sys.UI._UpdateProgress`
- `0x3b2fe`: `associatedUpdatePanelId`

## pseudocode

```c

```

## disassembly

```asm
0x3b250  ldarg.0
0x3b251  ldfld    int32 <GetScriptDescriptors>d__29::<>1__state
0x3b256  stloc.0
0x3b257  ldarg.0
0x3b258  ldfld    class System.Web.UI.UpdateProgress <GetScriptDescriptors>d__29::<>4__this
0x3b25d  stloc.1
0x3b25e  ldloc.0
0x3b25f  brfalse.s loc_3B26A
0x3b261  ldloc.0
0x3b262  ldc.i4.1
0x3b263  beq      loc_3B345
0x3b268  ldc.i4.0
0x3b269  ret
0x3b26a  ldarg.0
0x3b26b  ldc.i4.m1
0x3b26c  stfld    int32 <GetScriptDescriptors>d__29::<>1__state
0x3b271  ldloc.1
0x3b272  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3b277  brfalse  loc_3B34C
0x3b27c  ldloc.1
0x3b27d  call     instance class System.Web.UI.ScriptManager System.Web.UI.UpdateProgress::get_ScriptManager()
0x3b282  callvirt instance bool System.Web.UI.ScriptManager::get_SupportsPartialRendering()
0x3b287  brfalse  loc_3B34C
0x3b28c  ldloc.1
0x3b28d  callvirt instance bool [System.Web]System.Web.UI.Control::get_Visible()
0x3b292  brfalse  loc_3B34C
0x3b297  ldstr    aSysUiUpdatepro// "Sys.UI._UpdateProgress"
0x3b29c  ldloc.1
0x3b29d  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3b2a2  newobj   instance void System.Web.UI.ScriptControlDescriptor::.ctor(string type, string elementID)
0x3b2a7  stloc.2
0x3b2a8  ldnull
0x3b2a9  stloc.3
0x3b2aa  ldloc.1
0x3b2ab  call     instance string System.Web.UI.UpdateProgress::get_AssociatedUpdatePanelID()
0x3b2b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3b2b5  brtrue.s loc_3B2FD
0x3b2b7  ldloc.1
0x3b2b8  call     instance string System.Web.UI.UpdateProgress::get_AssociatedUpdatePanelID()
0x3b2bd  ldloc.1
0x3b2be  ldc.i4.1
0x3b2bf  call     class [System.Web]System.Web.UI.Control System.Web.UI.ControlUtil::FindTargetControl(string controlID, class [System.Web]System.Web.UI.Control control, bool searchNamingContainers)
0x3b2c4  isinst   System.Web.UI.UpdatePanel
0x3b2c9  stloc.s  4
0x3b2cb  ldloc.s  4
0x3b2cd  brfalse.s loc_3B2D9
0x3b2cf  ldloc.s  4
0x3b2d1  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3b2d6  stloc.3
0x3b2d7  br.s     loc_3B2FD
0x3b2d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b2de  call     string System.Web.Resources.AtlasWeb::get_UpdateProgress_NoUpdatePanel()
0x3b2e3  ldc.i4.1
0x3b2e4  newarr   [mscorlib]System.Object
0x3b2e9  dup
0x3b2ea  ldc.i4.0
0x3b2eb  ldloc.1
0x3b2ec  call     instance string System.Web.UI.UpdateProgress::get_AssociatedUpdatePanelID()
0x3b2f1  stelem.ref
0x3b2f2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3b2f7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3b2fc  throw
0x3b2fd  ldloc.2
0x3b2fe  ldstr    aAssociatedupda// "associatedUpdatePanelId"
0x3b303  ldloc.3
0x3b304  callvirt instance void System.Web.UI.ScriptComponentDescriptor::AddProperty(string name, object value)
0x3b309  ldloc.2
0x3b30a  ldstr    aDynamiclayout// "dynamicLayout"
0x3b30f  ldloc.1
0x3b310  call     instance bool System.Web.UI.UpdateProgress::get_DynamicLayout()
0x3b315  box      [mscorlib]System.Boolean
0x3b31a  callvirt instance void System.Web.UI.ScriptComponentDescriptor::AddProperty(string name, object value)
0x3b31f  ldloc.2
0x3b320  ldstr    aDisplayafter// "displayAfter"
0x3b325  ldloc.1
0x3b326  call     instance int32 System.Web.UI.UpdateProgress::get_DisplayAfter()
0x3b32b  box      [mscorlib]System.Int32
0x3b330  callvirt instance void System.Web.UI.ScriptComponentDescriptor::AddProperty(string name, object value)
0x3b335  ldarg.0
0x3b336  ldloc.2
0x3b337  stfld    class System.Web.UI.ScriptDescriptor <GetScriptDescriptors>d__29::<>2__current
0x3b33c  ldarg.0
0x3b33d  ldc.i4.1
0x3b33e  stfld    int32 <GetScriptDescriptors>d__29::<>1__state
0x3b343  ldc.i4.1
0x3b344  ret
0x3b345  ldarg.0
0x3b346  ldc.i4.m1
0x3b347  stfld    int32 <GetScriptDescriptors>d__29::<>1__state
0x3b34c  ldc.i4.0
0x3b34d  ret
```
