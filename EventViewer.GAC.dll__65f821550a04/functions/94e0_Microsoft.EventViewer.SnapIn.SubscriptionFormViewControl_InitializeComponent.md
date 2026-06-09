# Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::InitializeComponent

- ea: `0x94e0`
- end: `0x9513`
- name: `Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::InitializeComponent`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x9520`

## pseudocode

```c

```

## disassembly

```asm
0x94e0  ldarg.0
0x94e1  newobj   instance void [System]System.ComponentModel.Container::.ctor()
0x94e6  stfld    class [System]System.ComponentModel.IContainer Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::components
0x94eb  ldarg.0
0x94ec  ldc.i4.2
0x94ed  call     instance void [System.Windows.Forms]System.Windows.Forms.UserControl::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x94f2  ldarg.0
0x94f3  ldstr    aFolderviewer// "FolderViewer"
0x94f8  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x94fd  ldarg.0
0x94fe  ldc.i4   0x36C
0x9503  ldc.i4   0x253
0x9508  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x950d  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x9512  ret
```
