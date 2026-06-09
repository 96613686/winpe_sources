# System.Web.UI.Design.XmlFileEditor::EditValue

- ea: `0x137c0`
- end: `0x1384d`
- name: `System.Web.UI.Design.XmlFileEditor::EditValue`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x137c0`
- `0x8ef40`

## string_xrefs

- `0x137f8`: `XMLFilePicker_Caption`
- `0x1380d`: `XMLFilePicker_Filter`

## pseudocode

```c

```

## disassembly

```asm
0x137c0  ldarg.2
0x137c1  brfalse  loc_1384B
0x137c6  ldarg.2
0x137c7  ldtoken  [System.Windows.Forms]System.Windows.Forms.Design.IWindowsFormsEditorService
0x137cc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x137d1  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x137d6  castclass [System.Windows.Forms]System.Windows.Forms.Design.IWindowsFormsEditorService
0x137db  stloc.0
0x137dc  ldloc.0
0x137dd  brfalse.s loc_1384B
0x137df  ldarg.0
0x137e0  ldfld    class [System.Windows.Forms]System.Windows.Forms.FileDialog System.Web.UI.Design.XmlFileEditor::fileDialog
0x137e5  brtrue.s loc_1381C
0x137e7  ldarg.0
0x137e8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.OpenFileDialog::.ctor()
0x137ed  stfld    class [System.Windows.Forms]System.Windows.Forms.FileDialog System.Web.UI.Design.XmlFileEditor::fileDialog
0x137f2  ldarg.0
0x137f3  ldfld    class [System.Windows.Forms]System.Windows.Forms.FileDialog System.Web.UI.Design.XmlFileEditor::fileDialog
0x137f8  ldstr    aXmlfilepickerC// "XMLFilePicker_Caption"
0x137fd  call     string System.Design.SR::GetString(string name)
0x13802  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Title(string)
0x13807  ldarg.0
0x13808  ldfld    class [System.Windows.Forms]System.Windows.Forms.FileDialog System.Web.UI.Design.XmlFileEditor::fileDialog
0x1380d  ldstr    aXmlfilepickerF// "XMLFilePicker_Filter"
0x13812  call     string System.Design.SR::GetString(string name)
0x13817  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Filter(string)
0x1381c  ldarg.3
0x1381d  brfalse.s loc_13830
0x1381f  ldarg.0
0x13820  ldfld    class [System.Windows.Forms]System.Windows.Forms.FileDialog System.Web.UI.Design.XmlFileEditor::fileDialog
0x13825  ldarg.3
0x13826  callvirt instance string [mscorlib]System.Object::ToString()
0x1382b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_FileName(string)
0x13830  ldarg.0
0x13831  ldfld    class [System.Windows.Forms]System.Windows.Forms.FileDialog System.Web.UI.Design.XmlFileEditor::fileDialog
0x13836  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.CommonDialog::ShowDialog()
0x1383b  ldc.i4.1
0x1383c  bne.un.s loc_1384B
0x1383e  ldarg.0
0x1383f  ldfld    class [System.Windows.Forms]System.Windows.Forms.FileDialog System.Web.UI.Design.XmlFileEditor::fileDialog
0x13844  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x13849  starg.s  3
0x1384b  ldarg.3
0x1384c  ret
```
