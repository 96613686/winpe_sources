# System.Deployment.Application.MaintenancePiece::InitializeContent

- ea: `0x18d10`
- end: `0x18e02`
- name: `System.Deployment.Application.MaintenancePiece::InitializeContent`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000`

## callees

- `0x21f50`
- `0x230a0`

## string_xrefs

- `0x18d69`: `remove.ico`

## pseudocode

```c

```

## disassembly

```asm
0x18d10  ldarg.0
0x18d11  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureDesktop
0x18d16  ldstr    aFormIco// "form.ico"
0x18d1b  ldc.i4.0
0x18d1c  ldc.i4.0
0x18d1d  call     class [System.Drawing]System.Drawing.Icon System.Deployment.Application.Resources::GetIcon(string iconName, [opt] int32 width, [opt] int32 height)
0x18d22  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x18d27  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_Image(class [System.Drawing]System.Drawing.Image)
0x18d2c  ldarg.0
0x18d2d  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRestore
0x18d32  ldarg.0
0x18d33  ldfld    class System.Deployment.Application.MaintenanceInfo System.Deployment.Application.MaintenancePiece::_maintenanceInfo
0x18d38  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x18d3d  ldc.i4.1
0x18d3e  and
0x18d3f  ldc.i4.0
0x18d40  cgt.un
0x18d42  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x18d47  ldarg.0
0x18d48  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRestore
0x18d4d  ldstr    aRestoreIco// "restore.ico"
0x18d52  ldc.i4.0
0x18d53  ldc.i4.0
0x18d54  call     class [System.Drawing]System.Drawing.Icon System.Deployment.Application.Resources::GetIcon(string iconName, [opt] int32 width, [opt] int32 height)
0x18d59  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x18d5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_Image(class [System.Drawing]System.Drawing.Image)
0x18d63  ldarg.0
0x18d64  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRemove
0x18d69  ldstr    aRemoveIco// "remove.ico"
0x18d6e  ldc.i4.0
0x18d6f  ldc.i4.0
0x18d70  call     class [System.Drawing]System.Drawing.Icon System.Deployment.Application.Resources::GetIcon(string iconName, [opt] int32 width, [opt] int32 height)
0x18d75  callvirt instance class [System.Drawing]System.Drawing.Bitmap [System.Drawing]System.Drawing.Icon::ToBitmap()
0x18d7a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_Image(class [System.Drawing]System.Drawing.Image)
0x18d7f  ldarg.0
0x18d80  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.MaintenancePiece::lblHeader
0x18d85  ldarg.0
0x18d86  ldfld    class System.Deployment.Application.UserInterfaceInfo System.Deployment.Application.MaintenancePiece::_info
0x18d8b  ldfld    string System.Deployment.Application.UserInterfaceInfo::productName
0x18d90  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x18d95  ldarg.0
0x18d96  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRestore
0x18d9b  ldarg.0
0x18d9c  ldfld    class System.Deployment.Application.MaintenanceInfo System.Deployment.Application.MaintenancePiece::_maintenanceInfo
0x18da1  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x18da6  ldc.i4.1
0x18da7  and
0x18da8  ldc.i4.0
0x18da9  cgt.un
0x18dab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x18db0  ldarg.0
0x18db1  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRestore
0x18db6  ldarg.0
0x18db7  ldfld    class System.Deployment.Application.MaintenanceInfo System.Deployment.Application.MaintenancePiece::_maintenanceInfo
0x18dbc  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x18dc1  ldc.i4.1
0x18dc2  and
0x18dc3  ldc.i4.0
0x18dc4  cgt.un
0x18dc6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x18dcb  ldarg.0
0x18dcc  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRemove
0x18dd1  ldarg.0
0x18dd2  ldfld    class System.Deployment.Application.MaintenanceInfo System.Deployment.Application.MaintenancePiece::_maintenanceInfo
0x18dd7  ldfld    valuetype System.Deployment.Application.MaintenanceFlags System.Deployment.Application.MaintenanceInfo::maintenanceFlags
0x18ddc  ldc.i4.1
0x18ddd  and
0x18dde  ldc.i4.0
0x18ddf  ceq
0x18de1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x18de6  ldarg.0
0x18de7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.MaintenancePiece::btnHelp
0x18dec  ldarg.0
0x18ded  ldfld    class System.Deployment.Application.UserInterfaceInfo System.Deployment.Application.MaintenancePiece::_info
0x18df2  ldfld    string System.Deployment.Application.UserInterfaceInfo::supportUrl
0x18df7  call     bool System.Deployment.Application.UserInterface::IsValidHttpUrl(string url)
0x18dfc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x18e01  ret
```
