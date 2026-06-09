# System.Web.UI.Design.WebControls.RenderOuterTableHelper::SetRenderOuterTable

- ea: `0x33fe0`
- end: `0x340c0`
- name: `System.Web.UI.Design.WebControls.RenderOuterTableHelper::SetRenderOuterTable`
- size: `224`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x18390`
- `0x24210`
- `0x29290`
- `0x32a10`

## callees

- `0x3290`
- `0x11680`
- `0x33f40`
- `0x33fe0`
- `0x52c90`
- `0x584f0`
- `0x8eec0`
- `0x8ef40`
- `0xfce60`

## string_xrefs

- `0x3403f`: `RenderOuterTable_RemoveOuterTableWarning`
- `0x34049`: `RenderOuterTable_RemoveOuterTableCaption`

## pseudocode

```c

```

## disassembly

```asm
0x33fe0  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x33fe5  stloc.0
0x33fe6  ldloc.0
0x33fe7  ldarg.2
0x33fe8  stfld    bool <>c__DisplayClass5_0::isFormView
0x33fed  ldloc.0
0x33fee  ldarg.1
0x33fef  callvirt instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x33ff4  stfld    class [System]System.ComponentModel.IComponent <>c__DisplayClass5_0::component
0x33ff9  ldloc.0
0x33ffa  ldloc.0
0x33ffb  ldfld    class [System]System.ComponentModel.IComponent <>c__DisplayClass5_0::component
0x34000  castclass [System.Web]System.Web.UI.IRenderOuterTableControl
0x34005  stfld    class [System.Web]System.Web.UI.IRenderOuterTableControl <>c__DisplayClass5_0::control
0x3400a  ldarg.0
0x3400b  ldloc.0
0x3400c  ldfld    class [System.Web]System.Web.UI.IRenderOuterTableControl <>c__DisplayClass5_0::control
0x34011  callvirt instance bool [System.Web]System.Web.UI.IRenderOuterTableControl::get_RenderOuterTable()
0x34016  beq      loc_340BF
0x3401b  ldarg.0
0x3401c  brtrue   loc_340A8
0x34021  ldloc.0
0x34022  ldfld    class [System]System.ComponentModel.IComponent <>c__DisplayClass5_0::component
0x34027  ldloc.0
0x34028  ldfld    bool <>c__DisplayClass5_0::isFormView
0x3402d  call     bool System.Web.UI.Design.WebControls.RenderOuterTableHelper::IsAnyPropertyOnOuterTableChanged(class [System]System.ComponentModel.IComponent component, bool isFormView)
0x34032  brfalse.s loc_340A8
0x34034  ldloc.0
0x34035  ldfld    class [System]System.ComponentModel.IComponent <>c__DisplayClass5_0::component
0x3403a  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x3403f  ldstr    aRenderoutertab_0// "RenderOuterTable_RemoveOuterTableWarnin"...
0x34044  call     string System.Design.SR::GetString(string name)
0x34049  ldstr    aRenderoutertab_1// "RenderOuterTable_RemoveOuterTableCaptio"...
0x3404e  ldc.i4.2
0x3404f  newarr   [mscorlib]System.Object
0x34054  dup
0x34055  ldc.i4.0
0x34056  ldloc.0
0x34057  ldfld    class [System.Web]System.Web.UI.IRenderOuterTableControl <>c__DisplayClass5_0::control
0x3405c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x34061  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x34066  stelem.ref
0x34067  dup
0x34068  ldc.i4.1
0x34069  ldloc.0
0x3406a  ldfld    class [System.Web]System.Web.UI.IRenderOuterTableControl <>c__DisplayClass5_0::control
0x3406f  callvirt instance string [System.Web]System.Web.UI.IRenderOuterTableControl::get_ID()
0x34074  stelem.ref
0x34075  call     string System.Design.SR::GetString(string name, object[] args)
0x3407a  ldc.i4.4
0x3407b  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult System.Web.UI.Design.Util.UIServiceHelper::ShowMessage(class [mscorlib]System.IServiceProvider serviceProvider, string message, string caption, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons)
0x34080  stloc.1
0x34081  ldloc.1
0x34082  ldc.i4.7
0x34083  bne.un.s loc_34086
0x34085  ret
0x34086  ldloc.0
0x34087  ldfld    class [System]System.ComponentModel.IComponent <>c__DisplayClass5_0::component
0x3408c  ldloc.0
0x3408d  ldftn    instance bool <>c__DisplayClass5_0::<SetRenderOuterTable>b__0(object context)
0x34093  newobj   instance void System.Web.UI.Design.TransactedChangeCallback::.ctor(object object, native int method)
0x34098  ldnull
0x34099  ldstr    aRenderoutertab_2// "RenderOuterTableHelper_ResetProperties"
0x3409e  call     string System.Design.SR::GetString(string name)
0x340a3  call     void System.Web.UI.Design.ControlDesigner::InvokeTransactedChange(class [System]System.ComponentModel.IComponent component, class System.Web.UI.Design.TransactedChangeCallback callback, object context, string description)
0x340a8  ldloc.0
0x340a9  ldfld    class [System.Web]System.Web.UI.IRenderOuterTableControl <>c__DisplayClass5_0::control
0x340ae  ldarg.0
0x340af  callvirt instance void [System.Web]System.Web.UI.IRenderOuterTableControl::set_RenderOuterTable(bool)
0x340b4  ldloc.0
0x340b5  ldfld    class [System]System.ComponentModel.IComponent <>c__DisplayClass5_0::component
0x340ba  call     void [System]System.ComponentModel.TypeDescriptor::Refresh(object)
0x340bf  ret
```
