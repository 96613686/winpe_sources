# System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::InitializeComponent

- ea: `0x49b30`
- end: `0x4a1a4`
- name: `System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::InitializeComponent`
- size: `1652`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x49a40`

## callees

- `0x51a90`

## string_xrefs

- `0x49ece`: `_xpathExpressionLabel`
- `0x49f26`: `_xpathExpressionTextBox`
- `0x49f7e`: `_xpathExpressionHelpLabel`
- `0x4a186`: `XmlDataSourceConfigureDataSourceForm`

## pseudocode

```c

```

## disassembly

```asm
0x49b30  ldarg.0
0x49b31  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x49b36  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_cancelButton
0x49b3b  ldarg.0
0x49b3c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x49b41  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_okButton
0x49b46  ldarg.0
0x49b47  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x49b4c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileLabel
0x49b51  ldarg.0
0x49b52  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x49b57  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileTextBox
0x49b5c  ldarg.0
0x49b5d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x49b62  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseDataFileButton
0x49b67  ldarg.0
0x49b68  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x49b6d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_helpLabel
0x49b72  ldarg.0
0x49b73  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x49b78  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseTransformFileButton
0x49b7d  ldarg.0
0x49b7e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x49b83  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileTextBox
0x49b88  ldarg.0
0x49b89  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x49b8e  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileLabel
0x49b93  ldarg.0
0x49b94  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x49b99  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileHelpLabel
0x49b9e  ldarg.0
0x49b9f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x49ba4  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionTextBox
0x49ba9  ldarg.0
0x49baa  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x49baf  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionLabel
0x49bb4  ldarg.0
0x49bb5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x49bba  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionHelpLabel
0x49bbf  ldarg.0
0x49bc0  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x49bc5  ldarg.0
0x49bc6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_helpLabel
0x49bcb  ldc.i4.s 0xD
0x49bcd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x49bd2  ldarg.0
0x49bd3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_helpLabel
0x49bd8  ldc.i4.s 0xC
0x49bda  ldc.i4.s 0xC
0x49bdc  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x49be1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x49be6  ldarg.0
0x49be7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_helpLabel
0x49bec  ldstr    aHelplabel// "_helpLabel"
0x49bf1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x49bf6  ldarg.0
0x49bf7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_helpLabel
0x49bfc  ldc.i4   0x1F5
0x49c01  ldc.i4.s 0x28
0x49c03  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x49c08  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x49c0d  ldarg.0
0x49c0e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_helpLabel
0x49c13  ldc.i4.s 0xA
0x49c15  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x49c1a  ldarg.0
0x49c1b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileLabel
0x49c20  ldc.i4.s 0xD
0x49c22  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x49c27  ldarg.0
0x49c28  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileLabel
0x49c2d  ldc.i4.s 0xC
0x49c2f  ldc.i4.s 0x3C
0x49c31  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x49c36  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x49c3b  ldarg.0
0x49c3c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileLabel
0x49c41  ldstr    aDatafilelabel// "_dataFileLabel"
0x49c46  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x49c4b  ldarg.0
0x49c4c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileLabel
0x49c51  ldc.i4   0x19A
0x49c56  ldc.i4.s 0x10
0x49c58  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x49c5d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x49c62  ldarg.0
0x49c63  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileLabel
0x49c68  ldc.i4.s 0x14
0x49c6a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x49c6f  ldarg.0
0x49c70  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileTextBox
0x49c75  ldc.i4.s 0xD
0x49c77  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x49c7c  ldarg.0
0x49c7d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileTextBox
0x49c82  ldc.i4.s 0xC
0x49c84  ldc.i4.s 0x4E
0x49c86  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x49c8b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x49c90  ldarg.0
0x49c91  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileTextBox
0x49c96  ldstr    aDatafiletextbo// "_dataFileTextBox"
0x49c9b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x49ca0  ldarg.0
0x49ca1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileTextBox
0x49ca6  ldc.i4   0x1A9
0x49cab  ldc.i4.s 0x14
0x49cad  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x49cb2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x49cb7  ldarg.0
0x49cb8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_dataFileTextBox
0x49cbd  ldc.i4.s 0x1E
0x49cbf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x49cc4  ldarg.0
0x49cc5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseDataFileButton
0x49cca  ldc.i4.s 9
0x49ccc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x49cd1  ldarg.0
0x49cd2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseDataFileButton
0x49cd7  ldc.i4   0x1BC
0x49cdc  ldc.i4.s 0x4E
0x49cde  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x49ce3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x49ce8  ldarg.0
0x49ce9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseDataFileButton
0x49cee  ldstr    aChoosedatafile// "_chooseDataFileButton"
0x49cf3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x49cf8  ldarg.0
0x49cf9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseDataFileButton
0x49cfe  ldc.i4.s 0x4B
0x49d00  ldc.i4.s 0x17
0x49d02  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x49d07  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x49d0c  ldarg.0
0x49d0d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseDataFileButton
0x49d12  ldc.i4.s 0x28
0x49d14  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x49d19  ldarg.0
0x49d1a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseDataFileButton
0x49d1f  ldarg.0
0x49d20  ldftn    instance void System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::OnChooseDataFileButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x49d26  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x49d2b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x49d30  ldarg.0
0x49d31  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileLabel
0x49d36  ldc.i4.s 0xD
0x49d38  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x49d3d  ldarg.0
0x49d3e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileLabel
0x49d43  ldc.i4.s 0xC
0x49d45  ldc.i4.s 0x6E
0x49d47  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x49d4c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x49d51  ldarg.0
0x49d52  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileLabel
0x49d57  ldstr    aTransformfilel// "_transformFileLabel"
0x49d5c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x49d61  ldarg.0
0x49d62  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileLabel
0x49d67  ldc.i4   0x19A
0x49d6c  ldc.i4.s 0x10
0x49d6e  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x49d73  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x49d78  ldarg.0
0x49d79  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileLabel
0x49d7e  ldc.i4.s 0x50
0x49d80  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x49d85  ldarg.0
0x49d86  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileTextBox
0x49d8b  ldc.i4.s 0xD
0x49d8d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x49d92  ldarg.0
0x49d93  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileTextBox
0x49d98  ldc.i4.s 0xC
0x49d9a  ldc.i4   0x80
0x49d9f  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x49da4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x49da9  ldarg.0
0x49daa  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileTextBox
0x49daf  ldstr    aTransformfilet// "_transformFileTextBox"
0x49db4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x49db9  ldarg.0
0x49dba  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileTextBox
0x49dbf  ldc.i4   0x1A9
0x49dc4  ldc.i4.s 0x14
0x49dc6  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x49dcb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x49dd0  ldarg.0
0x49dd1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileTextBox
0x49dd6  ldc.i4.s 0x5A
0x49dd8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x49ddd  ldarg.0
0x49dde  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseTransformFileButton
0x49de3  ldc.i4.s 9
0x49de5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x49dea  ldarg.0
0x49deb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseTransformFileButton
0x49df0  ldc.i4   0x1BC
0x49df5  ldc.i4   0x80
0x49dfa  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x49dff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x49e04  ldarg.0
0x49e05  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseTransformFileButton
0x49e0a  ldstr    aChoosetransfor// "_chooseTransformFileButton"
0x49e0f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x49e14  ldarg.0
0x49e15  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseTransformFileButton
0x49e1a  ldc.i4.s 0x64
0x49e1c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x49e21  ldarg.0
0x49e22  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseTransformFileButton
0x49e27  ldc.i4.s 0x4B
0x49e29  ldc.i4.s 0x17
0x49e2b  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x49e30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x49e35  ldarg.0
0x49e36  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_chooseTransformFileButton
0x49e3b  ldarg.0
0x49e3c  ldftn    instance void System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::OnChooseTransformFileButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x49e42  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x49e47  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x49e4c  ldarg.0
0x49e4d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileHelpLabel
0x49e52  ldc.i4.s 0xD
0x49e54  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x49e59  ldarg.0
0x49e5a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileHelpLabel
0x49e5f  ldc.i4.s 0xC
0x49e61  ldc.i4   0x98
0x49e66  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x49e6b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x49e70  ldarg.0
0x49e71  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileHelpLabel
0x49e76  ldstr    aTransformfileh// "_transformFileHelpLabel"
0x49e7b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x49e80  ldarg.0
0x49e81  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileHelpLabel
0x49e86  ldc.i4   0x1F8
0x49e8b  ldc.i4.s 0x20
0x49e8d  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x49e92  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x49e97  ldarg.0
0x49e98  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_transformFileHelpLabel
0x49e9d  ldc.i4.s 0x69
0x49e9f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x49ea4  ldarg.0
0x49ea5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionLabel
0x49eaa  ldc.i4.s 0xD
0x49eac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x49eb1  ldarg.0
0x49eb2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionLabel
0x49eb7  ldc.i4.s 0xC
0x49eb9  ldc.i4   0xC2
0x49ebe  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x49ec3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x49ec8  ldarg.0
0x49ec9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionLabel
0x49ece  ldstr    aXpathexpressio// "_xpathExpressionLabel"
0x49ed3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x49ed8  ldarg.0
0x49ed9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionLabel
0x49ede  ldc.i4   0x19A
0x49ee3  ldc.i4.s 0x10
0x49ee5  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x49eea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x49eef  ldarg.0
0x49ef0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionLabel
0x49ef5  ldc.i4.s 0x6E
0x49ef7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x49efc  ldarg.0
0x49efd  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionTextBox
0x49f02  ldc.i4.s 0xD
0x49f04  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x49f09  ldarg.0
0x49f0a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionTextBox
0x49f0f  ldc.i4.s 0xC
0x49f11  ldc.i4   0xD4
0x49f16  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x49f1b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x49f20  ldarg.0
0x49f21  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionTextBox
0x49f26  ldstr    aXpathexpressio_0// "_xpathExpressionTextBox"
0x49f2b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x49f30  ldarg.0
0x49f31  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionTextBox
0x49f36  ldc.i4   0x1A9
0x49f3b  ldc.i4.s 0x14
0x49f3d  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x49f42  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x49f47  ldarg.0
0x49f48  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionTextBox
0x49f4d  ldc.i4.s 0x78
0x49f4f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x49f54  ldarg.0
0x49f55  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionHelpLabel
0x49f5a  ldc.i4.s 0xD
0x49f5c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x49f61  ldarg.0
0x49f62  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.XmlDataSourceConfigureDataSourceForm::_xpathExpressionHelpLabel
0x49f67  ldc.i4.s 0xC
  ... truncated ...
```
