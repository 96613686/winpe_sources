# Microsoft.EventViewer.SnapIn.FormControlBase::.ctor

- ea: `0x8460`
- end: `0x8472`
- name: `Microsoft.EventViewer.SnapIn.FormControlBase::.ctor`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4b60`
- `0x50d0`
- `0x9520`

## pseudocode

```c

```

## disassembly

```asm
0x8460  ldarg.0
0x8461  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x8466  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.EventViewer.SnapIn.FormControlBase::actions
0x846b  ldarg.0
0x846c  call     instance void [System.Windows.Forms]System.Windows.Forms.UserControl::.ctor()
0x8471  ret
```
