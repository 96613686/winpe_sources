# CompositionUI::.ctor

- ea: `0x116670`
- end: `0x116821`
- name: `CompositionUI::.ctor`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x9f470`

## callees

- `0x58ca0`
- `0x8ef40`
- `0x8efb0`
- `0x9ca30`
- `0x1165c0`
- `0x116670`

## string_xrefs

- `0x1166f9`: `CompositionDesignerWaterMark`
- `0x116786`: `CompositionDesignerWaterMarkFirstLink`
- `0x1167c2`: `CompositionDesignerWaterMarkSecondLink`

## pseudocode

```c

```

## disassembly

```asm
0x116670  ldarg.0
0x116671  ldarg.1
0x116672  ldarg.2
0x116673  call     instance void System.Windows.Forms.Design.ComponentTray::.ctor(class [System]System.ComponentModel.Design.IDesigner mainDesigner, class [mscorlib]System.IServiceProvider serviceProvider)
0x116678  ldarg.0
0x116679  ldarg.1
0x11667a  stfld    class System.Windows.Forms.Design.ComponentDocumentDesigner CompositionUI::compositionDesigner
0x11667f  ldarg.0
0x116680  ldarg.2
0x116681  stfld    class [mscorlib]System.IServiceProvider CompositionUI::serviceProvider
0x116686  ldarg.0
0x116687  ldarg.0
0x116688  newobj   instance void WatermarkLabel::.ctor(class CompositionUI compositionUI)
0x11668d  stfld    class WatermarkLabel CompositionUI::watermark
0x116692  ldarg.0
0x116693  ldfld    class WatermarkLabel CompositionUI::watermark
0x116698  ldarg.0
0x116699  ldfld    class WatermarkLabel CompositionUI::watermark
0x11669e  callvirt instance class [System.Drawing]System.Drawing.Font [System.Windows.Forms]System.Windows.Forms.Control::get_Font()
0x1166a3  callvirt instance class [System.Drawing]System.Drawing.FontFamily [System.Drawing]System.Drawing.Font::get_FontFamily()
0x1166a8  ldc.r4   11.0
0x1166ad  newobj   instance void [System.Drawing]System.Drawing.Font::.ctor(class [System.Drawing]System.Drawing.FontFamily, float32)
0x1166b2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0x1166b7  ldarg.0
0x1166b8  ldfld    class WatermarkLabel CompositionUI::watermark
0x1166bd  ldc.i4.s 0x20
0x1166bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0x1166c4  ldarg.0
0x1166c5  ldfld    class WatermarkLabel CompositionUI::watermark
0x1166ca  ldarg.0
0x1166cb  ldftn    instance void CompositionUI::OnLinkClick(object sender, class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
0x1166d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler::.ctor(object, native int)
0x1166d6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::add_LinkClicked(class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler)
0x1166db  ldarg.0
0x1166dc  ldfld    class WatermarkLabel CompositionUI::watermark
0x1166e1  ldc.i4.5
0x1166e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x1166e7  ldarg.0
0x1166e8  ldfld    class WatermarkLabel CompositionUI::watermark
0x1166ed  ldc.i4.0
0x1166ee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::set_TabStop(bool)
0x1166f3  ldarg.0
0x1166f4  ldfld    class WatermarkLabel CompositionUI::watermark
0x1166f9  ldstr    aCompositiondes// "CompositionDesignerWaterMark"
0x1166fe  call     string System.Design.SR::GetString(string name)
0x116703  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x116708  ldarg.1
0x116709  ldtoken  [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0x11670e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x116713  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0x116718  castclass [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0x11671d  stloc.0
0x11671e  ldloc.0
0x11671f  brfalse.s loc_116785
0x116721  ldloc.0
0x116722  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x116727  ldstr    aVscolorpanelgr// "VsColorPanelGradientDark"
0x11672c  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x116731  isinst   [System.Drawing]System.Drawing.Color
0x116736  brfalse.s loc_116753
0x116738  ldarg.0
0x116739  ldloc.0
0x11673a  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x11673f  ldstr    aVscolorpanelgr// "VsColorPanelGradientDark"
0x116744  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x116749  unbox.any [System.Drawing]System.Drawing.Color
0x11674e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x116753  ldloc.0
0x116754  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x116759  ldstr    aVscolorpanelte// "VsColorPanelText"
0x11675e  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x116763  isinst   [System.Drawing]System.Drawing.Color
0x116768  brfalse.s loc_116785
0x11676a  ldarg.0
0x11676b  ldloc.0
0x11676c  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x116771  ldstr    aVscolorpanelte// "VsColorPanelText"
0x116776  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x11677b  unbox.any [System.Drawing]System.Drawing.Color
0x116780  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ForeColor(valuetype [System.Drawing]System.Drawing.Color)
0x116785  nop
0x116786  ldstr    aCompositiondes_0// "CompositionDesignerWaterMarkFirstLink"
0x11678b  call     string System.Design.SR::GetString(string name)
0x116790  stloc.1
0x116791  ldarg.0
0x116792  ldfld    class WatermarkLabel CompositionUI::watermark
0x116797  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x11679c  ldloc.1
0x11679d  callvirt instance int32 [mscorlib]System.String::IndexOf(string)
0x1167a2  stloc.2
0x1167a3  ldloc.1
0x1167a4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1167a9  stloc.3
0x1167aa  ldarg.0
0x1167ab  ldfld    class WatermarkLabel CompositionUI::watermark
0x1167b0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.LinkLabel/LinkCollection [System.Windows.Forms]System.Windows.Forms.LinkLabel::get_Links()
0x1167b5  ldloc.2
0x1167b6  ldloc.3
0x1167b7  ldstr    aToolbox// "Toolbox"
0x1167bc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.LinkLabel/Link [System.Windows.Forms]System.Windows.Forms.LinkLabel/LinkCollection::Add(int32, int32, object)
0x1167c1  pop
0x1167c2  ldstr    aCompositiondes_1// "CompositionDesignerWaterMarkSecondLink"
0x1167c7  call     string System.Design.SR::GetString(string name)
0x1167cc  stloc.1
0x1167cd  ldarg.0
0x1167ce  ldfld    class WatermarkLabel CompositionUI::watermark
0x1167d3  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x1167d8  ldloc.1
0x1167d9  callvirt instance int32 [mscorlib]System.String::IndexOf(string)
0x1167de  stloc.2
0x1167df  ldloc.1
0x1167e0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1167e5  stloc.3
0x1167e6  ldarg.0
0x1167e7  ldfld    class WatermarkLabel CompositionUI::watermark
0x1167ec  callvirt instance class [System.Windows.Forms]System.Windows.Forms.LinkLabel/LinkCollection [System.Windows.Forms]System.Windows.Forms.LinkLabel::get_Links()
0x1167f1  ldloc.2
0x1167f2  ldloc.3
0x1167f3  ldstr    aCodeview// "CodeView"
0x1167f8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.LinkLabel/Link [System.Windows.Forms]System.Windows.Forms.LinkLabel/LinkCollection::Add(int32, int32, object)
0x1167fd  pop
0x1167fe  leave.s  loc_11680F
0x116800  stloc.s  4
0x116802  ldloc.s  4
0x116804  call     bool System.Windows.Forms.ClientUtils::IsCriticalException(class [mscorlib]System.Exception ex)
0x116809  brfalse.s loc_11680D
0x11680b  rethrow
0x11680d  leave.s  loc_11680F
0x11680f  ldarg.0
0x116810  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x116815  ldarg.0
0x116816  ldfld    class WatermarkLabel CompositionUI::watermark
0x11681b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x116820  ret
```
