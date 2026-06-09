# MenuRendererClassic::PreRender

- ea: `0x1a1250`
- end: `0x1a1692`
- name: `MenuRendererClassic::PreRender`
- size: `1090`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: ``

## callees

- `0x1c230`
- `0x5d420`
- `0x5dac0`
- `0x5de10`
- `0x5ef10`
- `0x5f680`
- `0x71aa0`
- `0x72180`
- `0x721a0`
- `0x73d90`
- `0x85fb0`
- `0xc2d60`
- `0xc2dc0`
- `0xc2eb0`
- `0xc3110`
- `0xdb670`
- `0xdb7e0`
- `0x1a0d60`
- `0x1a0e00`
- `0x1a1250`

## string_xrefs

- `0x1a1414`: `.hoverHyperLinkClass = '`
- `0x1a154e`: `.staticHoverHyperLinkClass = '`
- `0x1a167b`: `_CreateDataObject`

## pseudocode

```c

```

## disassembly

```asm
0x1a1250  ldarg.0
0x1a1251  call     instance void MenuRendererClassic::EnsureRenderSettings()
0x1a1256  ldarg.0
0x1a1257  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a125c  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0x1a1261  ldnull
0x1a1262  cgt.un
0x1a1264  ldarg.1
0x1a1265  and
0x1a1266  brfalse  loc_1A1691
0x1a126b  ldarg.0
0x1a126c  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1271  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0x1a1276  callvirt instance void System.Web.UI.Page::RegisterWebFormsScript()
0x1a127b  ldarg.0
0x1a127c  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1281  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0x1a1286  callvirt instance class System.Web.UI.ClientScriptManager System.Web.UI.Page::get_ClientScript()
0x1a128b  ldarg.0
0x1a128c  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1291  ldtoken  System.Web.UI.WebControls.Menu
0x1a1296  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a129b  ldstr    aMenuJs// "Menu.js"
0x1a12a0  callvirt instance void System.Web.UI.ClientScriptManager::RegisterClientScriptResource(class System.Web.UI.Control control, class [mscorlib]System.Type type, string resourceName)
0x1a12a5  ldarg.0
0x1a12a6  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a12ab  callvirt instance string System.Web.UI.WebControls.Menu::get_ClientDataObjectID()
0x1a12b0  stloc.0
0x1a12b1  ldstr    aVar// "var "
0x1a12b6  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x1a12bb  stloc.1
0x1a12bc  ldloc.1
0x1a12bd  ldloc.0
0x1a12be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a12c3  pop
0x1a12c4  ldloc.1
0x1a12c5  ldstr    aNewObject// " = new Object();\r\n"
0x1a12ca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a12cf  pop
0x1a12d0  ldloc.1
0x1a12d1  ldloc.0
0x1a12d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a12d7  pop
0x1a12d8  ldloc.1
0x1a12d9  ldstr    aDisappearafter_0// ".disappearAfter = "
0x1a12de  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a12e3  pop
0x1a12e4  ldloc.1
0x1a12e5  ldarg.0
0x1a12e6  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a12eb  callvirt instance int32 System.Web.UI.WebControls.Menu::get_DisappearAfter()
0x1a12f0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x1a12f5  pop
0x1a12f6  ldloc.1
0x1a12f7  ldstr    asc_1DB6C2// ";\r\n"
0x1a12fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1301  pop
0x1a1302  ldloc.1
0x1a1303  ldloc.0
0x1a1304  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1309  pop
0x1a130a  ldloc.1
0x1a130b  ldstr    aHorizontaloffs// ".horizontalOffset = "
0x1a1310  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1315  pop
0x1a1316  ldloc.1
0x1a1317  ldarg.0
0x1a1318  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a131d  callvirt instance int32 System.Web.UI.WebControls.Menu::get_DynamicHorizontalOffset()
0x1a1322  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x1a1327  pop
0x1a1328  ldloc.1
0x1a1329  ldstr    asc_1DB6C2// ";\r\n"
0x1a132e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1333  pop
0x1a1334  ldloc.1
0x1a1335  ldloc.0
0x1a1336  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a133b  pop
0x1a133c  ldloc.1
0x1a133d  ldstr    aVerticaloffset// ".verticalOffset = "
0x1a1342  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1347  pop
0x1a1348  ldloc.1
0x1a1349  ldarg.0
0x1a134a  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a134f  callvirt instance int32 System.Web.UI.WebControls.Menu::get_DynamicVerticalOffset()
0x1a1354  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x1a1359  pop
0x1a135a  ldloc.1
0x1a135b  ldstr    asc_1DB6C2// ";\r\n"
0x1a1360  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1365  pop
0x1a1366  ldarg.0
0x1a1367  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a136c  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_dynamicHoverStyle
0x1a1371  brfalse  loc_1A1490
0x1a1376  ldloc.1
0x1a1377  ldloc.0
0x1a1378  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a137d  pop
0x1a137e  ldloc.1
0x1a137f  ldstr    aHoverclass// ".hoverClass = '"
0x1a1384  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1389  pop
0x1a138a  ldloc.1
0x1a138b  ldarg.0
0x1a138c  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1391  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_dynamicHoverStyle
0x1a1396  callvirt instance string System.Web.UI.WebControls.Style::get_RegisteredCssClass()
0x1a139b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a13a0  pop
0x1a13a1  ldarg.0
0x1a13a2  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a13a7  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_dynamicHoverStyle
0x1a13ac  callvirt instance string System.Web.UI.WebControls.Style::get_CssClass()
0x1a13b1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a13b6  brtrue.s loc_1A13EF
0x1a13b8  ldarg.0
0x1a13b9  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a13be  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_dynamicHoverStyle
0x1a13c3  callvirt instance string System.Web.UI.WebControls.Style::get_RegisteredCssClass()
0x1a13c8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a13cd  brtrue.s loc_1A13D8
0x1a13cf  ldloc.1
0x1a13d0  ldc.i4.s 0x20
0x1a13d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1a13d7  pop
0x1a13d8  ldloc.1
0x1a13d9  ldarg.0
0x1a13da  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a13df  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_dynamicHoverStyle
0x1a13e4  callvirt instance string System.Web.UI.WebControls.Style::get_CssClass()
0x1a13e9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a13ee  pop
0x1a13ef  ldloc.1
0x1a13f0  ldstr    asc_1DB73A// "';\r\n"
0x1a13f5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a13fa  pop
0x1a13fb  ldarg.0
0x1a13fc  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1401  ldfld    class System.Web.UI.WebControls.HyperLinkStyle System.Web.UI.WebControls.Menu::_dynamicHoverHyperLinkStyle
0x1a1406  brfalse  loc_1A1490
0x1a140b  ldloc.1
0x1a140c  ldloc.0
0x1a140d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1412  pop
0x1a1413  ldloc.1
0x1a1414  ldstr    aHoverhyperlink// ".hoverHyperLinkClass = '"
0x1a1419  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a141e  pop
0x1a141f  ldloc.1
0x1a1420  ldarg.0
0x1a1421  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1426  ldfld    class System.Web.UI.WebControls.HyperLinkStyle System.Web.UI.WebControls.Menu::_dynamicHoverHyperLinkStyle
0x1a142b  callvirt instance string System.Web.UI.WebControls.Style::get_RegisteredCssClass()
0x1a1430  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1435  pop
0x1a1436  ldarg.0
0x1a1437  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a143c  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_dynamicHoverStyle
0x1a1441  callvirt instance string System.Web.UI.WebControls.Style::get_CssClass()
0x1a1446  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a144b  brtrue.s loc_1A1484
0x1a144d  ldarg.0
0x1a144e  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1453  ldfld    class System.Web.UI.WebControls.HyperLinkStyle System.Web.UI.WebControls.Menu::_dynamicHoverHyperLinkStyle
0x1a1458  callvirt instance string System.Web.UI.WebControls.Style::get_RegisteredCssClass()
0x1a145d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a1462  brtrue.s loc_1A146D
0x1a1464  ldloc.1
0x1a1465  ldc.i4.s 0x20
0x1a1467  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1a146c  pop
0x1a146d  ldloc.1
0x1a146e  ldarg.0
0x1a146f  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1474  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_dynamicHoverStyle
0x1a1479  callvirt instance string System.Web.UI.WebControls.Style::get_CssClass()
0x1a147e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1483  pop
0x1a1484  ldloc.1
0x1a1485  ldstr    asc_1DB73A// "';\r\n"
0x1a148a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a148f  pop
0x1a1490  ldarg.0
0x1a1491  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1496  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_staticHoverStyle
0x1a149b  brfalse  loc_1A15CA
0x1a14a0  ldarg.0
0x1a14a1  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a14a6  ldfld    class System.Web.UI.WebControls.HyperLinkStyle System.Web.UI.WebControls.Menu::_staticHoverHyperLinkStyle
0x1a14ab  brfalse  loc_1A15CA
0x1a14b0  ldloc.1
0x1a14b1  ldloc.0
0x1a14b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a14b7  pop
0x1a14b8  ldloc.1
0x1a14b9  ldstr    aStatichovercla// ".staticHoverClass = '"
0x1a14be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a14c3  pop
0x1a14c4  ldloc.1
0x1a14c5  ldarg.0
0x1a14c6  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a14cb  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_staticHoverStyle
0x1a14d0  callvirt instance string System.Web.UI.WebControls.Style::get_RegisteredCssClass()
0x1a14d5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a14da  pop
0x1a14db  ldarg.0
0x1a14dc  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a14e1  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_staticHoverStyle
0x1a14e6  callvirt instance string System.Web.UI.WebControls.Style::get_CssClass()
0x1a14eb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a14f0  brtrue.s loc_1A1529
0x1a14f2  ldarg.0
0x1a14f3  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a14f8  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_staticHoverStyle
0x1a14fd  callvirt instance string System.Web.UI.WebControls.Style::get_RegisteredCssClass()
0x1a1502  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a1507  brtrue.s loc_1A1512
0x1a1509  ldloc.1
0x1a150a  ldc.i4.s 0x20
0x1a150c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1a1511  pop
0x1a1512  ldloc.1
0x1a1513  ldarg.0
0x1a1514  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1519  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_staticHoverStyle
0x1a151e  callvirt instance string System.Web.UI.WebControls.Style::get_CssClass()
0x1a1523  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1528  pop
0x1a1529  ldloc.1
0x1a152a  ldstr    asc_1DB73A// "';\r\n"
0x1a152f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1534  pop
0x1a1535  ldarg.0
0x1a1536  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a153b  ldfld    class System.Web.UI.WebControls.HyperLinkStyle System.Web.UI.WebControls.Menu::_staticHoverHyperLinkStyle
0x1a1540  brfalse  loc_1A15CA
0x1a1545  ldloc.1
0x1a1546  ldloc.0
0x1a1547  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a154c  pop
0x1a154d  ldloc.1
0x1a154e  ldstr    aStatichoverhyp// ".staticHoverHyperLinkClass = '"
0x1a1553  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a1558  pop
0x1a1559  ldloc.1
0x1a155a  ldarg.0
0x1a155b  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1560  ldfld    class System.Web.UI.WebControls.HyperLinkStyle System.Web.UI.WebControls.Menu::_staticHoverHyperLinkStyle
0x1a1565  callvirt instance string System.Web.UI.WebControls.Style::get_RegisteredCssClass()
0x1a156a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a156f  pop
0x1a1570  ldarg.0
0x1a1571  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a1576  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_staticHoverStyle
0x1a157b  callvirt instance string System.Web.UI.WebControls.Style::get_CssClass()
0x1a1580  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a1585  brtrue.s loc_1A15BE
0x1a1587  ldarg.0
0x1a1588  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a158d  ldfld    class System.Web.UI.WebControls.HyperLinkStyle System.Web.UI.WebControls.Menu::_staticHoverHyperLinkStyle
0x1a1592  callvirt instance string System.Web.UI.WebControls.Style::get_RegisteredCssClass()
0x1a1597  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a159c  brtrue.s loc_1A15A7
0x1a159e  ldloc.1
0x1a159f  ldc.i4.s 0x20
0x1a15a1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1a15a6  pop
0x1a15a7  ldloc.1
0x1a15a8  ldarg.0
0x1a15a9  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a15ae  ldfld    class System.Web.UI.WebControls.Style System.Web.UI.WebControls.Menu::_staticHoverStyle
0x1a15b3  callvirt instance string System.Web.UI.WebControls.Style::get_CssClass()
0x1a15b8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a15bd  pop
0x1a15be  ldloc.1
0x1a15bf  ldstr    asc_1DB73A// "';\r\n"
0x1a15c4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a15c9  pop
0x1a15ca  ldarg.0
0x1a15cb  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a15d0  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0x1a15d5  callvirt instance class System.Web.HttpRequest System.Web.UI.Page::get_RequestInternal()
0x1a15da  brfalse.s loc_1A1654
0x1a15dc  ldarg.0
0x1a15dd  call     instance class System.Web.UI.WebControls.Menu MenuRenderer::get_Menu()
0x1a15e2  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0x1a15e7  callvirt instance class System.Web.HttpRequest System.Web.UI.Page::get_Request()
0x1a15ec  callvirt instance class [System]System.Uri System.Web.HttpRequest::get_Url()
0x1a15f1  callvirt instance string [System]System.Uri::get_Scheme()
0x1a15f6  ldstr    aHttps_0// "https"
0x1a15fb  ldc.i4.5
0x1a15fc  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1a1601  brfalse.s loc_1A1654
0x1a1603  ldloc.1
0x1a1604  ldloc.0
0x1a1605  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1a160a  pop
  ... truncated ...
```
