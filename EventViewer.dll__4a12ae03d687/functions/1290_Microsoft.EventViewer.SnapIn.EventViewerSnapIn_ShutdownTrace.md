# Microsoft.EventViewer.SnapIn.EventViewerSnapIn::ShutdownTrace

- ea: `0x1290`
- end: `0x12b3`
- name: `Microsoft.EventViewer.SnapIn.EventViewerSnapIn::ShutdownTrace`
- size: `35`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x430`
- `0x540`
- `0x1340`
- `0x1580`

## callees

- `0x1290`

## pseudocode

```c

```

## disassembly

```asm
0x1290  ldsfld   int32 Microsoft.EventViewer.SnapIn.EventViewerSnapIn::numberOfviewers
0x1295  ldc.i4.1
0x1296  sub
0x1297  stsfld   int32 Microsoft.EventViewer.SnapIn.EventViewerSnapIn::numberOfviewers
0x129c  ldsfld   int32 Microsoft.EventViewer.SnapIn.EventViewerSnapIn::numberOfviewers
0x12a1  brtrue.s loc_12B2
0x12a3  ldstr    aShutdowntrace// "ShutdownTrace"
0x12a8  call     void [System]System.Diagnostics.Trace::WriteLine(string)
0x12ad  call     void [System]System.Diagnostics.Trace::Close()
0x12b2  ret
```
