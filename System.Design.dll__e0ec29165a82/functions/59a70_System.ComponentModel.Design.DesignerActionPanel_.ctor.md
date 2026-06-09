# System.ComponentModel.Design.DesignerActionPanel::.ctor

- ea: `0x59a70`
- end: `0x59d8a`
- name: `System.ComponentModel.Design.DesignerActionPanel::.ctor`
- size: `794`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xe62b0`

## callees

- `0x59a70`
- `0x59f80`

## string_xrefs

- `0x59bee`: `VsColorPanelHyperLink`
- `0x59c06`: `VsColorPanelHyperLink`
- `0x59c20`: `VsColorPanelHyperLinkPressed`
- `0x59c38`: `VsColorPanelHyperLinkPressed`

## pseudocode

```c

```

## disassembly

```asm
0x59a70  ldarg.0
0x59a71  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0x59a76  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_gradientLightColor
0x59a7b  ldarg.0
0x59a7c  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0x59a81  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_gradientDarkColor
0x59a86  ldarg.0
0x59a87  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ActiveCaption()
0x59a8c  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_titleBarColor
0x59a91  ldarg.0
0x59a92  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_InactiveCaption()
0x59a97  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_titleBarUnselectedColor
0x59a9c  ldarg.0
0x59a9d  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ActiveCaptionText()
0x59aa2  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_titleBarTextColor
0x59aa7  ldarg.0
0x59aa8  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlDark()
0x59aad  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_separatorColor
0x59ab2  ldarg.0
0x59ab3  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ActiveBorder()
0x59ab8  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_borderColor
0x59abd  ldarg.0
0x59abe  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_HotTrack()
0x59ac3  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_linkColor
0x59ac8  ldarg.0
0x59ac9  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_HotTrack()
0x59ace  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_activeLinkColor
0x59ad3  ldarg.0
0x59ad4  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlText()
0x59ad9  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_labelForeColor
0x59ade  ldarg.0
0x59adf  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::.ctor()
0x59ae4  ldarg.0
0x59ae5  ldc.i4   0x2000
0x59aea  ldc.i4.1
0x59aeb  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SetStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ControlStyles, bool)
0x59af0  ldarg.0
0x59af1  ldc.i4.4
0x59af2  ldc.i4.1
0x59af3  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SetStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ControlStyles, bool)
0x59af8  ldarg.0
0x59af9  ldc.i4   0x20000
0x59afe  ldc.i4.1
0x59aff  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SetStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ControlStyles, bool)
0x59b04  ldarg.0
0x59b05  ldc.i4.s 0x10
0x59b07  ldc.i4.1
0x59b08  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SetStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ControlStyles, bool)
0x59b0d  ldarg.0
0x59b0e  ldc.i4.2
0x59b0f  ldc.i4.1
0x59b10  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SetStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ControlStyles, bool)
0x59b15  ldarg.0
0x59b16  ldarg.1
0x59b17  stfld    class [mscorlib]System.IServiceProvider System.ComponentModel.Design.DesignerActionPanel::_serviceProvider
0x59b1c  ldarg.0
0x59b1d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Line>::.ctor()
0x59b22  stfld    class [mscorlib]System.Collections.Generic.List`1<class Line> System.ComponentModel.Design.DesignerActionPanel::_lines
0x59b27  ldarg.0
0x59b28  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x59b2d  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> System.ComponentModel.Design.DesignerActionPanel::_lineHeights
0x59b32  ldarg.0
0x59b33  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x59b38  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> System.ComponentModel.Design.DesignerActionPanel::_lineYPositions
0x59b3d  ldarg.0
0x59b3e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolTip::.ctor()
0x59b43  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolTip System.ComponentModel.Design.DesignerActionPanel::_toolTip
0x59b48  ldarg.0
0x59b49  call     instance class [mscorlib]System.IServiceProvider System.ComponentModel.Design.DesignerActionPanel::get_ServiceProvider()
0x59b4e  ldtoken  [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0x59b53  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x59b58  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x59b5d  castclass [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0x59b62  stloc.0
0x59b63  ldloc.0
0x59b64  brfalse  loc_59D78
0x59b69  ldarg.0
0x59b6a  ldloc.0
0x59b6b  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59b70  ldstr    aDialogfont// "DialogFont"
0x59b75  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59b7a  castclass [System.Drawing]System.Drawing.Font
0x59b7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0x59b84  ldloc.0
0x59b85  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59b8a  ldstr    aVscolorpanelgr// "VsColorPanelGradientDark"
0x59b8f  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59b94  isinst   [System.Drawing]System.Drawing.Color
0x59b99  brfalse.s loc_59BB6
0x59b9b  ldarg.0
0x59b9c  ldloc.0
0x59b9d  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59ba2  ldstr    aVscolorpanelgr// "VsColorPanelGradientDark"
0x59ba7  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59bac  unbox.any [System.Drawing]System.Drawing.Color
0x59bb1  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_gradientDarkColor
0x59bb6  ldloc.0
0x59bb7  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59bbc  ldstr    aVscolorpanelgr_0// "VsColorPanelGradientLight"
0x59bc1  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59bc6  isinst   [System.Drawing]System.Drawing.Color
0x59bcb  brfalse.s loc_59BE8
0x59bcd  ldarg.0
0x59bce  ldloc.0
0x59bcf  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59bd4  ldstr    aVscolorpanelgr_0// "VsColorPanelGradientLight"
0x59bd9  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59bde  unbox.any [System.Drawing]System.Drawing.Color
0x59be3  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_gradientLightColor
0x59be8  ldloc.0
0x59be9  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59bee  ldstr    aVscolorpanelhy// "VsColorPanelHyperLink"
0x59bf3  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59bf8  isinst   [System.Drawing]System.Drawing.Color
0x59bfd  brfalse.s loc_59C1A
0x59bff  ldarg.0
0x59c00  ldloc.0
0x59c01  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59c06  ldstr    aVscolorpanelhy// "VsColorPanelHyperLink"
0x59c0b  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59c10  unbox.any [System.Drawing]System.Drawing.Color
0x59c15  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_linkColor
0x59c1a  ldloc.0
0x59c1b  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59c20  ldstr    aVscolorpanelhy_0// "VsColorPanelHyperLinkPressed"
0x59c25  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59c2a  isinst   [System.Drawing]System.Drawing.Color
0x59c2f  brfalse.s loc_59C4C
0x59c31  ldarg.0
0x59c32  ldloc.0
0x59c33  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59c38  ldstr    aVscolorpanelhy_0// "VsColorPanelHyperLinkPressed"
0x59c3d  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59c42  unbox.any [System.Drawing]System.Drawing.Color
0x59c47  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_activeLinkColor
0x59c4c  ldloc.0
0x59c4d  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59c52  ldstr    aVscolorpanelti// "VsColorPanelTitleBar"
0x59c57  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59c5c  isinst   [System.Drawing]System.Drawing.Color
0x59c61  brfalse.s loc_59C7E
0x59c63  ldarg.0
0x59c64  ldloc.0
0x59c65  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59c6a  ldstr    aVscolorpanelti// "VsColorPanelTitleBar"
0x59c6f  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59c74  unbox.any [System.Drawing]System.Drawing.Color
0x59c79  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_titleBarColor
0x59c7e  ldloc.0
0x59c7f  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59c84  ldstr    aVscolorpanelti_0// "VsColorPanelTitleBarUnselected"
0x59c89  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59c8e  isinst   [System.Drawing]System.Drawing.Color
0x59c93  brfalse.s loc_59CB0
0x59c95  ldarg.0
0x59c96  ldloc.0
0x59c97  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59c9c  ldstr    aVscolorpanelti_0// "VsColorPanelTitleBarUnselected"
0x59ca1  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59ca6  unbox.any [System.Drawing]System.Drawing.Color
0x59cab  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_titleBarUnselectedColor
0x59cb0  ldloc.0
0x59cb1  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59cb6  ldstr    aVscolorpanelti_1// "VsColorPanelTitleBarText"
0x59cbb  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59cc0  isinst   [System.Drawing]System.Drawing.Color
0x59cc5  brfalse.s loc_59CE2
0x59cc7  ldarg.0
0x59cc8  ldloc.0
0x59cc9  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59cce  ldstr    aVscolorpanelti_1// "VsColorPanelTitleBarText"
0x59cd3  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59cd8  unbox.any [System.Drawing]System.Drawing.Color
0x59cdd  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_titleBarTextColor
0x59ce2  ldloc.0
0x59ce3  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59ce8  ldstr    aVscolorpanelbo// "VsColorPanelBorder"
0x59ced  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59cf2  isinst   [System.Drawing]System.Drawing.Color
0x59cf7  brfalse.s loc_59D14
0x59cf9  ldarg.0
0x59cfa  ldloc.0
0x59cfb  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59d00  ldstr    aVscolorpanelbo// "VsColorPanelBorder"
0x59d05  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59d0a  unbox.any [System.Drawing]System.Drawing.Color
0x59d0f  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_borderColor
0x59d14  ldloc.0
0x59d15  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59d1a  ldstr    aVscolorpanelse// "VsColorPanelSeparator"
0x59d1f  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59d24  isinst   [System.Drawing]System.Drawing.Color
0x59d29  brfalse.s loc_59D46
0x59d2b  ldarg.0
0x59d2c  ldloc.0
0x59d2d  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59d32  ldstr    aVscolorpanelse// "VsColorPanelSeparator"
0x59d37  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59d3c  unbox.any [System.Drawing]System.Drawing.Color
0x59d41  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_separatorColor
0x59d46  ldloc.0
0x59d47  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59d4c  ldstr    aVscolorpanelte// "VsColorPanelText"
0x59d51  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59d56  isinst   [System.Drawing]System.Drawing.Color
0x59d5b  brfalse.s loc_59D78
0x59d5d  ldarg.0
0x59d5e  ldloc.0
0x59d5f  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0x59d64  ldstr    aVscolorpanelte// "VsColorPanelText"
0x59d69  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x59d6e  unbox.any [System.Drawing]System.Drawing.Color
0x59d73  stfld    valuetype [System.Drawing]System.Drawing.Color System.ComponentModel.Design.DesignerActionPanel::_labelForeColor
0x59d78  ldarg.0
0x59d79  ldc.i4   0x96
0x59d7e  ldc.i4.0
0x59d7f  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x59d84  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x59d89  ret
```
