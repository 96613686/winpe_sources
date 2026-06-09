# System.Deployment.Application.UpdatePiece::InitializeContent

- ea: `0x21780`
- end: `0x21850`
- name: `System.Deployment.Application.UpdatePiece::InitializeContent`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x20b50`

## callees

- `0x21780`
- `0x21f20`
- `0x21f50`
- `0x23020`
- `0x230a0`

## string_xrefs

- `0x217a7`: `UI_UpdateSubHeader`

## pseudocode

```c

```

## disassembly

```asm
0x21780  ldarg.0
0x21781  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.UpdatePiece::pictureDesktop
0x21786  ldstr    aFormIco// "form.ico"
0x2178b  ldc.i4.0
0x2178c  ldc.i4.0
0x2178d  call     class [System.Drawing]System.Drawing.Icon System.Deployment.Application.Resources::GetIcon(string iconName, [opt] int32 width, [opt] int32 height)
0x21792  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x21797  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_Image(class [System.Drawing]System.Drawing.Image)
0x2179c  ldarg.0
0x2179d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblSubHeader
0x217a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x217a7  ldstr    aUiUpdatesubhea// "UI_UpdateSubHeader"
0x217ac  call     string System.Deployment.Application.Resources::GetString(string s)
0x217b1  ldc.i4.1
0x217b2  newarr   [mscorlib]System.Object
0x217b7  dup
0x217b8  ldc.i4.0
0x217b9  ldarg.0
0x217ba  ldfld    class System.Deployment.Application.UserInterfaceInfo System.Deployment.Application.UpdatePiece::_info
0x217bf  ldfld    string System.Deployment.Application.UserInterfaceInfo::productName
0x217c4  call     string System.Deployment.Application.UserInterface::LimitDisplayTextLength(string displayText)
0x217c9  stelem.ref
0x217ca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x217cf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x217d4  ldarg.0
0x217d5  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.UpdatePiece::linkAppId
0x217da  ldarg.0
0x217db  ldfld    class System.Deployment.Application.UserInterfaceInfo System.Deployment.Application.UpdatePiece::_info
0x217e0  ldfld    string System.Deployment.Application.UserInterfaceInfo::productName
0x217e5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x217ea  ldarg.0
0x217eb  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.UpdatePiece::linkAppId
0x217f0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.LinkLabel/LinkCollection [System.Windows.Forms]System.Windows.Forms.LinkLabel::get_Links()
0x217f5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel/LinkCollection::Clear()
0x217fa  ldarg.0
0x217fb  ldfld    class System.Deployment.Application.UserInterfaceInfo System.Deployment.Application.UpdatePiece::_info
0x21800  ldfld    string System.Deployment.Application.UserInterfaceInfo::supportUrl
0x21805  call     bool System.Deployment.Application.UserInterface::IsValidHttpUrl(string url)
0x2180a  brfalse.s loc_21839
0x2180c  ldarg.0
0x2180d  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.UpdatePiece::linkAppId
0x21812  callvirt instance class [System.Windows.Forms]System.Windows.Forms.LinkLabel/LinkCollection [System.Windows.Forms]System.Windows.Forms.LinkLabel::get_Links()
0x21817  ldc.i4.0
0x21818  ldarg.0
0x21819  ldfld    class System.Deployment.Application.UserInterfaceInfo System.Deployment.Application.UpdatePiece::_info
0x2181e  ldfld    string System.Deployment.Application.UserInterfaceInfo::productName
0x21823  callvirt instance int32 [mscorlib]System.String::get_Length()
0x21828  ldarg.0
0x21829  ldfld    class System.Deployment.Application.UserInterfaceInfo System.Deployment.Application.UpdatePiece::_info
0x2182e  ldfld    string System.Deployment.Application.UserInterfaceInfo::supportUrl
0x21833  callvirt instance class [System.Windows.Forms]System.Windows.Forms.LinkLabel/Link [System.Windows.Forms]System.Windows.Forms.LinkLabel/LinkCollection::Add(int32, int32, object)
0x21838  pop
0x21839  ldarg.0
0x2183a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblFromId
0x2183f  ldarg.0
0x21840  ldfld    class System.Deployment.Application.UserInterfaceInfo System.Deployment.Application.UpdatePiece::_info
0x21845  ldfld    string System.Deployment.Application.UserInterfaceInfo::sourceSite
0x2184a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x2184f  ret
```
