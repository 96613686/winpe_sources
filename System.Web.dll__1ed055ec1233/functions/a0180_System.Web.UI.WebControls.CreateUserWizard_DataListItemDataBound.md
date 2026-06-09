# System.Web.UI.WebControls.CreateUserWizard::DataListItemDataBound

- ea: `0xa0180`
- end: `0xa0255`
- name: `System.Web.UI.WebControls.CreateUserWizard::DataListItemDataBound`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation`

## callees

- `0x34f20`
- `0x5f060`
- `0x5f1b0`
- `0xa0180`
- `0xbcd00`
- `0xeae20`
- `0xeba30`
- `0xec120`
- `0xec250`
- `0xed650`
- `0xed670`
- `0xed6e0`
- `0xed700`
- `0xeda00`

## string_xrefs

- `0xa01ca`: `SideBarLabel`
- `0xa01fa`: `SideBarLabel`
- `0xa01e5`: `CreateUserWizard_SideBar_Label_Not_Found`

## pseudocode

```c

```

## disassembly

```asm
0xa0180  ldarg.2
0xa0181  callvirt instance class System.Web.UI.WebControls.WizardSideBarListControlItem System.Web.UI.WebControls.WizardSideBarListControlItemEventArgs::get_Item()
0xa0186  stloc.0
0xa0187  ldloc.0
0xa0188  callvirt instance valuetype System.Web.UI.WebControls.ListItemType System.Web.UI.WebControls.WizardSideBarListControlItem::get_ItemType()
0xa018d  ldc.i4.2
0xa018e  beq.s    loc_A01AC
0xa0190  ldloc.0
0xa0191  callvirt instance valuetype System.Web.UI.WebControls.ListItemType System.Web.UI.WebControls.WizardSideBarListControlItem::get_ItemType()
0xa0196  ldc.i4.3
0xa0197  beq.s    loc_A01AC
0xa0199  ldloc.0
0xa019a  callvirt instance valuetype System.Web.UI.WebControls.ListItemType System.Web.UI.WebControls.WizardSideBarListControlItem::get_ItemType()
0xa019f  ldc.i4.4
0xa01a0  beq.s    loc_A01AC
0xa01a2  ldloc.0
0xa01a3  callvirt instance valuetype System.Web.UI.WebControls.ListItemType System.Web.UI.WebControls.WizardSideBarListControlItem::get_ItemType()
0xa01a8  ldc.i4.5
0xa01a9  beq.s    loc_A01AC
0xa01ab  ret
0xa01ac  ldloc.0
0xa01ad  ldsfld   string System.Web.UI.WebControls.Wizard::SideBarButtonID
0xa01b2  callvirt instance class System.Web.UI.Control System.Web.UI.WebControls.WizardSideBarListControlItem::FindControl(string id)
0xa01b7  isinst   System.Web.UI.WebControls.IButtonControl
0xa01bc  stloc.1
0xa01bd  ldloc.1
0xa01be  brfalse.s loc_A01C9
0xa01c0  ldarg.0
0xa01c1  ldarg.1
0xa01c2  ldarg.2
0xa01c3  call     instance void System.Web.UI.WebControls.Wizard::DataListItemDataBound(object sender, class System.Web.UI.WebControls.WizardSideBarListControlItemEventArgs e)
0xa01c8  ret
0xa01c9  ldloc.0
0xa01ca  ldstr    aSidebarlabel// "SideBarLabel"
0xa01cf  callvirt instance class System.Web.UI.Control System.Web.UI.WebControls.WizardSideBarListControlItem::FindControl(string id)
0xa01d4  isinst   System.Web.UI.WebControls.Label
0xa01d9  stloc.2
0xa01da  ldloc.2
0xa01db  brtrue.s loc_A020C
0xa01dd  ldarg.0
0xa01de  call     instance bool System.Web.UI.Control::get_DesignMode()
0xa01e3  brtrue.s loc_A020B
0xa01e5  ldstr    aCreateuserwiza_24// "CreateUserWizard_SideBar_Label_Not_Foun"...
0xa01ea  ldc.i4.2
0xa01eb  newarr   [mscorlib]System.Object
0xa01f0  dup
0xa01f1  ldc.i4.0
0xa01f2  ldsfld   string System.Web.UI.WebControls.Wizard::DataListID
0xa01f7  stelem.ref
0xa01f8  dup
0xa01f9  ldc.i4.1
0xa01fa  ldstr    aSidebarlabel// "SideBarLabel"
0xa01ff  stelem.ref
0xa0200  call     string System.Web.SR::GetString(string name, object[] args)
0xa0205  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xa020a  throw
0xa020b  ret
0xa020c  ldloc.2
0xa020d  ldarg.0
0xa020e  call     instance class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Wizard::get_SideBarButtonStyle()
0xa0213  callvirt instance void System.Web.UI.WebControls.WebControl::MergeStyle(class System.Web.UI.WebControls.Style s)
0xa0218  ldloc.0
0xa0219  callvirt instance object System.Web.UI.WebControls.WizardSideBarListControlItem::get_DataItem()
0xa021e  isinst   System.Web.UI.WebControls.WizardStepBase
0xa0223  stloc.3
0xa0224  ldloc.3
0xa0225  brfalse.s loc_A0254
0xa0227  ldarg.0
0xa0228  call     instance void System.Web.UI.WebControls.Wizard::RegisterSideBarDataListForRender()
0xa022d  ldloc.3
0xa022e  callvirt instance string System.Web.UI.WebControls.WizardStepBase::get_Title()
0xa0233  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa0238  ldc.i4.0
0xa0239  ble.s    loc_A0248
0xa023b  ldloc.2
0xa023c  ldloc.3
0xa023d  callvirt instance string System.Web.UI.WebControls.WizardStepBase::get_Title()
0xa0242  callvirt instance void System.Web.UI.WebControls.Label::set_Text(string value)
0xa0247  ret
0xa0248  ldloc.2
0xa0249  ldloc.3
0xa024a  callvirt instance string System.Web.UI.Control::get_ID()
0xa024f  callvirt instance void System.Web.UI.WebControls.Label::set_Text(string value)
0xa0254  ret
```
