# System.Web.UI.Design.Util.TaskFormBase::InitializeComponent

- ea: `0x52730`
- end: `0x52a08`
- name: `System.Web.UI.Design.Util.TaskFormBase::InitializeComponent`
- size: `728`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x526d0`

## string_xrefs

- `0x527aa`: `_taskPanel`
- `0x529d2`: `TaskForm`

## pseudocode

```c

```

## disassembly

```asm
0x52730  ldarg.0
0x52731  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x52736  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_taskPanel
0x5273b  ldarg.0
0x5273c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x52741  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_bottomDividerLabel
0x52746  ldarg.0
0x52747  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x5274c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_captionLabel
0x52751  ldarg.0
0x52752  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x52757  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x5275c  ldarg.0
0x5275d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x52762  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Web.UI.Design.Util.TaskFormBase::_glyphPictureBox
0x52767  ldarg.0
0x52768  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x5276d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x52772  ldarg.0
0x52773  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Web.UI.Design.Util.TaskFormBase::_glyphPictureBox
0x52778  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x5277d  ldarg.0
0x5277e  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x52783  ldarg.0
0x52784  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_taskPanel
0x52789  ldc.i4.s 0xF
0x5278b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x52790  ldarg.0
0x52791  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_taskPanel
0x52796  ldc.i4.s 0xE
0x52798  ldc.i4.s 0x4E
0x5279a  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x5279f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x527a4  ldarg.0
0x527a5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_taskPanel
0x527aa  ldstr    aTaskpanel// "_taskPanel"
0x527af  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x527b4  ldarg.0
0x527b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_taskPanel
0x527ba  ldc.i4   0x220
0x527bf  ldc.i4   0x112
0x527c4  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x527c9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x527ce  ldarg.0
0x527cf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_taskPanel
0x527d4  ldc.i4.s 0x1E
0x527d6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x527db  ldarg.0
0x527dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_bottomDividerLabel
0x527e1  ldc.i4.s 0xE
0x527e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x527e8  ldarg.0
0x527e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_bottomDividerLabel
0x527ee  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0x527f3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x527f8  ldarg.0
0x527f9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_bottomDividerLabel
0x527fe  ldc.i4.0
0x527ff  ldc.i4   0x16E
0x52804  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x52809  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x5280e  ldarg.0
0x5280f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_bottomDividerLabel
0x52814  ldstr    aBottomdividerl// "_bottomDividerLabel"
0x52819  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x5281e  ldarg.0
0x5281f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_bottomDividerLabel
0x52824  ldc.i4   0x23C
0x52829  ldc.i4.1
0x5282a  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x5282f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x52834  ldarg.0
0x52835  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_bottomDividerLabel
0x5283a  ldc.i4.s 0x28
0x5283c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x52841  ldarg.0
0x52842  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x52847  ldc.i4.s 0xD
0x52849  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x5284e  ldarg.0
0x5284f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x52854  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0x52859  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x5285e  ldarg.0
0x5285f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x52864  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x52869  ldarg.0
0x5286a  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Web.UI.Design.Util.TaskFormBase::_glyphPictureBox
0x5286f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x52874  ldarg.0
0x52875  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x5287a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x5287f  ldarg.0
0x52880  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_captionLabel
0x52885  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x5288a  ldarg.0
0x5288b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x52890  ldc.i4.0
0x52891  ldc.i4.0
0x52892  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x52897  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x5289c  ldarg.0
0x5289d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x528a2  ldstr    aHeaderpanel// "_headerPanel"
0x528a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x528ac  ldarg.0
0x528ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x528b2  ldc.i4   0x23C
0x528b7  ldc.i4.s 0x40
0x528b9  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x528be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x528c3  ldarg.0
0x528c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x528c9  ldc.i4.s 0xA
0x528cb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x528d0  ldarg.0
0x528d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Web.UI.Design.Util.TaskFormBase::_glyphPictureBox
0x528d6  ldc.i4.0
0x528d7  ldc.i4.0
0x528d8  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x528dd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x528e2  ldarg.0
0x528e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Web.UI.Design.Util.TaskFormBase::_glyphPictureBox
0x528e8  ldstr    aGlyphpicturebo// "_glyphPictureBox"
0x528ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x528f2  ldarg.0
0x528f3  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Web.UI.Design.Util.TaskFormBase::_glyphPictureBox
0x528f8  ldc.i4.s 0x41
0x528fa  ldc.i4.s 0x40
0x528fc  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x52901  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x52906  ldarg.0
0x52907  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Web.UI.Design.Util.TaskFormBase::_glyphPictureBox
0x5290c  ldc.i4.s 0x14
0x5290e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabIndex(int32)
0x52913  ldarg.0
0x52914  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Web.UI.Design.Util.TaskFormBase::_glyphPictureBox
0x52919  ldc.i4.0
0x5291a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0x5291f  ldarg.0
0x52920  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_captionLabel
0x52925  ldc.i4.s 0xD
0x52927  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x5292c  ldarg.0
0x5292d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_captionLabel
0x52932  ldc.i4.s 0x47
0x52934  ldc.i4.s 0x11
0x52936  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x5293b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x52940  ldarg.0
0x52941  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_captionLabel
0x52946  ldstr    aCaptionlabel// "_captionLabel"
0x5294b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x52950  ldarg.0
0x52951  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_captionLabel
0x52956  ldc.i4   0x1E7
0x5295b  ldc.i4.s 0x2F
0x5295d  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x52962  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x52967  ldarg.0
0x52968  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_captionLabel
0x5296d  ldc.i4.s 0xA
0x5296f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x52974  ldarg.0
0x52975  ldc.i4   0x23C
0x5297a  ldc.i4   0x1A0
0x5297f  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x52984  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_ClientSize(valuetype [System.Drawing]System.Drawing.Size)
0x52989  ldarg.0
0x5298a  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x5298f  ldarg.0
0x52990  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x52995  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x5299a  ldarg.0
0x5299b  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x529a0  ldarg.0
0x529a1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::_bottomDividerLabel
0x529a6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x529ab  ldarg.0
0x529ac  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x529b1  ldarg.0
0x529b2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_taskPanel
0x529b7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x529bc  ldarg.0
0x529bd  ldc.i4   0x244
0x529c2  ldc.i4   0x1C2
0x529c7  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x529cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x529d1  ldarg.0
0x529d2  ldstr    aTaskform// "TaskForm"
0x529d7  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x529dc  ldarg.0
0x529dd  ldc.i4.1
0x529de  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_SizeGripStyle(valuetype [System.Windows.Forms]System.Windows.Forms.SizeGripStyle)
0x529e3  ldarg.0
0x529e4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.Util.TaskFormBase::_headerPanel
0x529e9  ldc.i4.0
0x529ea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x529ef  ldarg.0
0x529f0  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Web.UI.Design.Util.TaskFormBase::_glyphPictureBox
0x529f5  callvirt instance void [System]System.ComponentModel.ISupportInitialize::EndInit()
0x529fa  ldarg.0
0x529fb  ldc.i4.0
0x529fc  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x52a01  ldarg.0
0x52a02  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x52a07  ret
```
