# Microsoft.EventViewer.SnapIn.MMCEventsResultView::InitializeComponent

- ea: `0x67b0`
- end: `0x67e4`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsResultView::InitializeComponent`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x50d0`

## callees

- `0x5100`

## pseudocode

```c

```

## disassembly

```asm
0x67b0  ldarg.0
0x67b1  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x67b6  ldarg.0
0x67b7  call     instance void Microsoft.EventViewer.SnapIn.MMCEventsResultView::AddSharedDetailControl()
0x67bc  ldarg.0
0x67bd  ldstr    aMmceventsresul// "MMCEventsResultView"
0x67c2  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x67c7  ldarg.0
0x67c8  ldc.i4   0x264
0x67cd  ldc.i4   0x2BC
0x67d2  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x67d7  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x67dc  ldarg.0
0x67dd  ldc.i4.0
0x67de  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x67e3  ret
```
