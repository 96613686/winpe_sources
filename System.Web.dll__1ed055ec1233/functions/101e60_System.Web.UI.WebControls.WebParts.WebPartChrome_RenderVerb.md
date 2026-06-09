# System.Web.UI.WebControls.WebParts.WebPartChrome::RenderVerb

- ea: `0x101e60`
- end: `0x1022bf`
- name: `System.Web.UI.WebControls.WebParts.WebPartChrome::RenderVerb`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `46`
- tags: ``

## callers

- `0x1022c0`

## callees

- `0x5b170`
- `0x5f1b0`
- `0x5f6b0`
- `0x60ef0`
- `0x61560`
- `0x85fa0`
- `0x937d0`
- `0x93870`
- `0xb9930`
- `0xb9970`
- `0xb9a60`
- `0xb9ae0`
- `0xb9b30`
- `0xbd1b0`
- `0xbd230`
- `0xea4f0`
- `0xea6f0`
- `0xea820`
- `0xea980`
- `0xeabc0`
- `0x100b80`
- `0x100bc0`
- `0x100c70`
- `0x100ca0`
- `0x1016c0`
- `0x101700`
- `0x101e60`
- `0x103300`
- `0x1077a0`
- `0x107d40`
- `0x10cbf0`
- `0x10cc10`
- `0x10cc60`
- `0x10ccf0`
- `0x10cd60`
- `0x10ce10`
- `0x10d530`
- `0x10d590`
- `0x10d730`
- `0x10d7a0`
- `0x10db20`
- `0x10db70`
- `0x10f880`
- `0x10fe30`
- `0x10fed0`
- `0x10ff20`

## string_xrefs

- `0x101f24`: `window.open('`
- `0x102250`: `if (__wpmDeleteWarning.length >= 0 && !confirm(__wpmDeleteWarning)) { return false; }`

## pseudocode

```c

```

## disassembly

```asm
0x101e60  ldarg.0
0x101e61  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x101e66  callvirt instance bool System.Web.UI.WebControls.WebControl::get_IsEnabled()
0x101e6b  brfalse.s loc_101E75
0x101e6d  ldarg.3
0x101e6e  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPartVerb::get_Enabled()
0x101e73  br.s     loc_101E76
0x101e75  ldc.i4.0
0x101e76  stloc.1
0x101e77  ldarg.0
0x101e78  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x101e7d  callvirt instance valuetype System.Web.UI.WebControls.ButtonType System.Web.UI.WebControls.WebParts.WebPartZoneBase::get_TitleBarVerbButtonType()
0x101e82  stloc.2
0x101e83  ldarg.3
0x101e84  ldarg.0
0x101e85  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x101e8a  callvirt instance class System.Web.UI.WebControls.WebParts.WebPartVerb System.Web.UI.WebControls.WebParts.WebPartZoneBase::get_HelpVerb()
0x101e8f  bne.un   loc_102004
0x101e94  ldarg.0
0x101e95  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x101e9a  ldarg.2
0x101e9b  callvirt instance string System.Web.UI.WebControls.WebParts.WebPart::get_HelpUrl()
0x101ea0  callvirt instance string System.Web.UI.Control::ResolveClientUrl(string relativeUrl)
0x101ea5  stloc.3
0x101ea6  ldloc.2
0x101ea7  brtrue   loc_101F71
0x101eac  ldarg.0
0x101ead  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x101eb2  ldnull
0x101eb3  newobj   instance void System.Web.UI.WebControls.WebParts.ZoneButton::.ctor(class System.Web.UI.WebControls.WebParts.WebZone owner, string eventArgument)
0x101eb8  stloc.s  4
0x101eba  ldloc.1
0x101ebb  brfalse  loc_101F5C
0x101ec0  ldarg.0
0x101ec1  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x101ec6  callvirt instance bool System.Web.UI.WebControls.WebParts.WebZone::get_RenderClientScript()
0x101ecb  brfalse.s loc_101F19
0x101ecd  ldloc.s  4
0x101ecf  ldc.i4.5
0x101ed0  newarr   [mscorlib]System.String
0x101ed5  dup
0x101ed6  ldc.i4.0
0x101ed7  ldstr    aWpmShowhelp// "__wpm.ShowHelp('"
0x101edc  stelem.ref
0x101edd  dup
0x101ede  ldc.i4.1
0x101edf  ldloc.3
0x101ee0  call     string System.Web.UI.Util::QuoteJScriptString(string value)
0x101ee5  stelem.ref
0x101ee6  dup
0x101ee7  ldc.i4.2
0x101ee8  ldstr    asc_1E13B6// "', "
0x101eed  stelem.ref
0x101eee  dup
0x101eef  ldc.i4.3
0x101ef0  ldarg.2
0x101ef1  callvirt instance valuetype System.Web.UI.WebControls.WebParts.WebPartHelpMode System.Web.UI.WebControls.WebParts.WebPart::get_HelpMode()
0x101ef6  stloc.s  5
0x101ef8  ldloca.s 5
0x101efa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x101eff  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x101f04  stelem.ref
0x101f05  dup
0x101f06  ldc.i4.4
0x101f07  ldstr    aReturn// ");return;"
0x101f0c  stelem.ref
0x101f0d  call     string [mscorlib]System.String::Concat(string[])
0x101f12  callvirt instance void System.Web.UI.WebControls.Button::set_OnClientClick(string value)
0x101f17  br.s     loc_101F5C
0x101f19  ldarg.2
0x101f1a  callvirt instance valuetype System.Web.UI.WebControls.WebParts.WebPartHelpMode System.Web.UI.WebControls.WebParts.WebPart::get_HelpMode()
0x101f1f  ldc.i4.2
0x101f20  beq.s    loc_101F40
0x101f22  ldloc.s  4
0x101f24  ldstr    aWindowOpen// "window.open('"
0x101f29  ldloc.3
0x101f2a  call     string System.Web.UI.Util::QuoteJScriptString(string value)
0x101f2f  ldstr    aBlankScrollbar// "', '_blank', 'scrollbars=yes,resizable="...
0x101f34  call     string [mscorlib]System.String::Concat(string, string, string)
0x101f39  callvirt instance void System.Web.UI.WebControls.Button::set_OnClientClick(string value)
0x101f3e  br.s     loc_101F5C
0x101f40  ldloc.s  4
0x101f42  ldstr    aWindowLocation// "window.location.href='"
0x101f47  ldloc.3
0x101f48  call     string System.Web.UI.Util::QuoteJScriptString(string value)
0x101f4d  ldstr    aReturn_0// "';return;"
0x101f52  call     string [mscorlib]System.String::Concat(string, string, string)
0x101f57  callvirt instance void System.Web.UI.WebControls.Button::set_OnClientClick(string value)
0x101f5c  ldloc.s  4
0x101f5e  ldarg.3
0x101f5f  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartVerb::get_Text()
0x101f64  callvirt instance void System.Web.UI.WebControls.Button::set_Text(string value)
0x101f69  ldloc.s  4
0x101f6b  stloc.0
0x101f6c  br       loc_102269
0x101f71  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x101f76  stloc.s  6
0x101f78  ldarg.2
0x101f79  callvirt instance valuetype System.Web.UI.WebControls.WebParts.WebPartHelpMode System.Web.UI.WebControls.WebParts.WebPart::get_HelpMode()
0x101f7e  stloc.s  7
0x101f80  ldloc.s  7
0x101f82  switch   loc_101F95, loc_101FC0, loc_101FD6
0x101f93  br.s     loc_101FDE
0x101f95  ldarg.0
0x101f96  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x101f9b  callvirt instance bool System.Web.UI.WebControls.WebParts.WebZone::get_RenderClientScript()
0x101fa0  brfalse.s loc_101FC0
0x101fa2  ldloc.s  6
0x101fa4  ldstr    aJavascriptWpmS// "javascript:__wpm.ShowHelp('"
0x101fa9  ldloc.3
0x101faa  call     string System.Web.UI.Util::QuoteJScriptString(string value)
0x101faf  ldstr    a0_2// "', 0)"
0x101fb4  call     string [mscorlib]System.String::Concat(string, string, string)
0x101fb9  callvirt instance void System.Web.UI.WebControls.HyperLink::set_NavigateUrl(string value)
0x101fbe  br.s     loc_101FDE
0x101fc0  ldloc.s  6
0x101fc2  ldloc.3
0x101fc3  callvirt instance void System.Web.UI.WebControls.HyperLink::set_NavigateUrl(string value)
0x101fc8  ldloc.s  6
0x101fca  ldstr    aBlank// "_blank"
0x101fcf  callvirt instance void System.Web.UI.WebControls.HyperLink::set_Target(string value)
0x101fd4  br.s     loc_101FDE
0x101fd6  ldloc.s  6
0x101fd8  ldloc.3
0x101fd9  callvirt instance void System.Web.UI.WebControls.HyperLink::set_NavigateUrl(string value)
0x101fde  ldloc.s  6
0x101fe0  ldarg.3
0x101fe1  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartVerb::get_Text()
0x101fe6  callvirt instance void System.Web.UI.WebControls.HyperLink::set_Text(string value)
0x101feb  ldloc.2
0x101fec  ldc.i4.1
0x101fed  bne.un.s loc_101FFC
0x101fef  ldloc.s  6
0x101ff1  ldarg.3
0x101ff2  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartVerb::get_ImageUrl()
0x101ff7  callvirt instance void System.Web.UI.WebControls.HyperLink::set_ImageUrl(string value)
0x101ffc  ldloc.s  6
0x101ffe  stloc.0
0x101fff  br       loc_102269
0x102004  ldarg.3
0x102005  ldarg.0
0x102006  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x10200b  callvirt instance class System.Web.UI.WebControls.WebParts.WebPartVerb System.Web.UI.WebControls.WebParts.WebPartZoneBase::get_ExportVerb()
0x102010  bne.un   loc_10214A
0x102015  ldarg.0
0x102016  ldfld    class System.Web.UI.WebControls.WebParts.WebPartManager System.Web.UI.WebControls.WebParts.WebPartChrome::_manager
0x10201b  ldarg.2
0x10201c  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartManager::GetExportUrl(class System.Web.UI.WebControls.WebParts.WebPart webPart)
0x102021  stloc.s  8
0x102023  ldloc.2
0x102024  brtrue   loc_1020CC
0x102029  ldarg.0
0x10202a  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x10202f  ldsfld   string [mscorlib]System.String::Empty
0x102034  newobj   instance void System.Web.UI.WebControls.WebParts.ZoneButton::.ctor(class System.Web.UI.WebControls.WebParts.WebZone owner, string eventArgument)
0x102039  stloc.s  9
0x10203b  ldloc.s  9
0x10203d  ldarg.3
0x10203e  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartVerb::get_Text()
0x102043  callvirt instance void System.Web.UI.WebControls.Button::set_Text(string value)
0x102048  ldloc.1
0x102049  brfalse.s loc_1020C4
0x10204b  ldarg.2
0x10204c  callvirt instance valuetype System.Web.UI.WebControls.WebParts.WebPartExportMode System.Web.UI.WebControls.WebParts.WebPart::get_ExportMode()
0x102051  ldc.i4.1
0x102052  bne.un.s loc_1020A7
0x102054  ldarg.0
0x102055  ldfld    valuetype System.Web.UI.WebControls.WebParts.PersonalizationScope System.Web.UI.WebControls.WebParts.WebPartChrome::_personalizationScope
0x10205a  brtrue.s loc_1020A7
0x10205c  ldarg.0
0x10205d  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x102062  callvirt instance bool System.Web.UI.WebControls.WebParts.WebZone::get_RenderClientScript()
0x102067  brfalse.s loc_102088
0x102069  ldloc.s  9
0x10206b  ldstr    aWpmExportwebpa// "__wpm.ExportWebPart('"
0x102070  ldloc.s  8
0x102072  call     string System.Web.UI.Util::QuoteJScriptString(string value)
0x102077  ldstr    aTrueFalseRetur// "', true, false);return false;"
0x10207c  call     string [mscorlib]System.String::Concat(string, string, string)
0x102081  callvirt instance void System.Web.UI.WebControls.Button::set_OnClientClick(string value)
0x102086  br.s     loc_1020C4
0x102088  ldloc.s  9
0x10208a  ldstr    aIfWpmexportwar// "if(__wpmExportWarning.length == 0 || co"...
0x10208f  ldloc.s  8
0x102091  call     string System.Web.UI.Util::QuoteJScriptString(string value)
0x102096  ldstr    aReturnFalse_1// "';}return false;"
0x10209b  call     string [mscorlib]System.String::Concat(string, string, string)
0x1020a0  callvirt instance void System.Web.UI.WebControls.Button::set_OnClientClick(string value)
0x1020a5  br.s     loc_1020C4
0x1020a7  ldloc.s  9
0x1020a9  ldstr    aWindowLocation_0// "window.location='"
0x1020ae  ldloc.s  8
0x1020b0  call     string System.Web.UI.Util::QuoteJScriptString(string value)
0x1020b5  ldstr    aReturnFalse_2// "';return false;"
0x1020ba  call     string [mscorlib]System.String::Concat(string, string, string)
0x1020bf  callvirt instance void System.Web.UI.WebControls.Button::set_OnClientClick(string value)
0x1020c4  ldloc.s  9
0x1020c6  stloc.0
0x1020c7  br       loc_102269
0x1020cc  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x1020d1  stloc.s  0xA
0x1020d3  ldloc.s  0xA
0x1020d5  ldarg.3
0x1020d6  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartVerb::get_Text()
0x1020db  callvirt instance void System.Web.UI.WebControls.HyperLink::set_Text(string value)
0x1020e0  ldloc.2
0x1020e1  ldc.i4.1
0x1020e2  bne.un.s loc_1020F1
0x1020e4  ldloc.s  0xA
0x1020e6  ldarg.3
0x1020e7  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartVerb::get_ImageUrl()
0x1020ec  callvirt instance void System.Web.UI.WebControls.HyperLink::set_ImageUrl(string value)
0x1020f1  ldloc.s  0xA
0x1020f3  ldloc.s  8
0x1020f5  callvirt instance void System.Web.UI.WebControls.HyperLink::set_NavigateUrl(string value)
0x1020fa  ldarg.2
0x1020fb  callvirt instance valuetype System.Web.UI.WebControls.WebParts.WebPartExportMode System.Web.UI.WebControls.WebParts.WebPart::get_ExportMode()
0x102100  ldc.i4.1
0x102101  bne.un.s loc_102142
0x102103  ldarg.0
0x102104  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x102109  callvirt instance bool System.Web.UI.WebControls.WebParts.WebZone::get_RenderClientScript()
0x10210e  brfalse.s loc_102128
0x102110  ldloc.s  0xA
0x102112  callvirt instance class System.Web.UI.AttributeCollection System.Web.UI.WebControls.WebControl::get_Attributes()
0x102117  ldstr    aOnclick// "onclick"
0x10211c  ldstr    aReturnWpmExpor// "return __wpm.ExportWebPart('', true, tr"...
0x102121  callvirt instance void System.Web.UI.AttributeCollection::Add(string key, string value)
0x102126  br.s     loc_102142
0x102128  ldstr    aReturnWpmexpor// "return (__wpmExportWarning.length == 0 "...
0x10212d  stloc.s  0xB
0x10212f  ldloc.s  0xA
0x102131  callvirt instance class System.Web.UI.AttributeCollection System.Web.UI.WebControls.WebControl::get_Attributes()
0x102136  ldstr    aOnclick// "onclick"
0x10213b  ldloc.s  0xB
0x10213d  callvirt instance void System.Web.UI.AttributeCollection::Add(string key, string value)
0x102142  ldloc.s  0xA
0x102144  stloc.0
0x102145  br       loc_102269
0x10214a  ldarg.3
0x10214b  ldarg.2
0x10214c  callvirt instance string System.Web.UI.Control::get_ID()
0x102151  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartVerb::GetEventArgument(string webPartID)
0x102156  stloc.s  0xC
0x102158  ldarg.3
0x102159  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartVerb::get_ClientClickHandler()
0x10215e  stloc.s  0xD
0x102160  ldloc.2
0x102161  brtrue.s loc_10219B
0x102163  ldarg.0
0x102164  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x102169  ldloc.s  0xC
0x10216b  newobj   instance void System.Web.UI.WebControls.WebParts.ZoneButton::.ctor(class System.Web.UI.WebControls.WebParts.WebZone owner, string eventArgument)
0x102170  stloc.s  0xE
0x102172  ldloc.s  0xE
0x102174  ldarg.3
0x102175  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartVerb::get_Text()
0x10217a  callvirt instance void System.Web.UI.WebControls.Button::set_Text(string value)
0x10217f  ldloc.s  0xD
0x102181  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x102186  ldc.i4.0
0x102187  ceq
0x102189  ldloc.1
0x10218a  and
0x10218b  brfalse.s loc_102196
0x10218d  ldloc.s  0xE
0x10218f  ldloc.s  0xD
0x102191  callvirt instance void System.Web.UI.WebControls.Button::set_OnClientClick(string value)
0x102196  ldloc.s  0xE
0x102198  stloc.0
0x102199  br.s     loc_1021E2
0x10219b  ldarg.0
0x10219c  call     instance class System.Web.UI.WebControls.WebParts.WebPartZoneBase System.Web.UI.WebControls.WebParts.WebPartChrome::get_Zone()
0x1021a1  ldloc.s  0xC
0x1021a3  newobj   instance void System.Web.UI.WebControls.WebParts.ZoneLinkButton::.ctor(class System.Web.UI.WebControls.WebParts.WebZone owner, string eventArgument)
0x1021a8  stloc.s  0xF
0x1021aa  ldloc.s  0xF
0x1021ac  ldarg.3
0x1021ad  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartVerb::get_Text()
0x1021b2  callvirt instance void System.Web.UI.WebControls.LinkButton::set_Text(string value)
0x1021b7  ldloc.2
0x1021b8  ldc.i4.1
0x1021b9  bne.un.s loc_1021C8
0x1021bb  ldloc.s  0xF
0x1021bd  ldarg.3
0x1021be  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartVerb::get_ImageUrl()
0x1021c3  callvirt instance void System.Web.UI.WebControls.WebParts.ZoneLinkButton::set_ImageUrl(string value)
0x1021c8  ldloc.s  0xD
0x1021ca  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1021cf  ldc.i4.0
0x1021d0  ceq
0x1021d2  ldloc.1
0x1021d3  and
0x1021d4  brfalse.s loc_1021DF
0x1021d6  ldloc.s  0xF
0x1021d8  ldloc.s  0xD
0x1021da  callvirt instance void System.Web.UI.WebControls.LinkButton::set_OnClientClick(string value)
0x1021df  ldloc.s  0xF
0x1021e1  stloc.0
0x1021e2  ldarg.0
  ... truncated ...
```
