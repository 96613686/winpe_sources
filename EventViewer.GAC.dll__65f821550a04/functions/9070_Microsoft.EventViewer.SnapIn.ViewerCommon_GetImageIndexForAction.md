# Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndexForAction

- ea: `0x9070`
- end: `0x9115`
- name: `Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndexForAction`
- size: `165`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2470`
- `0x4c40`
- `0x5d60`
- `0x8120`
- `0x8680`
- `0x99a0`

## callees

- `0x9070`

## pseudocode

```c

```

## disassembly

```asm
0x9070  ldc.i4.0
0x9071  stloc.0
0x9072  ldarg.0
0x9073  switch   loc_90DB, loc_90E0, loc_9107, loc_9113, loc_90E5, loc_90EA, loc_90EF, loc_9113, loc_90EF, loc_9113, loc_90F9, loc_9113, loc_90FE, loc_9113, loc_90F4, loc_9113, loc_9113, loc_9113, loc_9113, loc_9111, loc_9111, loc_9111, loc_9103
0x90d4  ldarg.0
0x90d5  ldc.i4.s 0x20
0x90d7  beq.s    loc_910C
0x90d9  br.s     loc_9113
0x90db  ldc.i4.s 0x18
0x90dd  stloc.0
0x90de  br.s     loc_9113
0x90e0  ldc.i4.s 0x17
0x90e2  stloc.0
0x90e3  br.s     loc_9113
0x90e5  ldc.i4.s 0x12
0x90e7  stloc.0
0x90e8  br.s     loc_9113
0x90ea  ldc.i4.s 0x15
0x90ec  stloc.0
0x90ed  br.s     loc_9113
0x90ef  ldc.i4.s 0x13
0x90f1  stloc.0
0x90f2  br.s     loc_9113
0x90f4  ldc.i4.s 0x27
0x90f6  stloc.0
0x90f7  br.s     loc_9113
0x90f9  ldc.i4.s 0x14
0x90fb  stloc.0
0x90fc  br.s     loc_9113
0x90fe  ldc.i4.s 0x15
0x9100  stloc.0
0x9101  br.s     loc_9113
0x9103  ldc.i4.0
0x9104  stloc.0
0x9105  br.s     loc_9113
0x9107  ldc.i4.s 0x26
0x9109  stloc.0
0x910a  br.s     loc_9113
0x910c  ldc.i4.s 0x16
0x910e  stloc.0
0x910f  br.s     loc_9113
0x9111  ldc.i4.1
0x9112  stloc.0
0x9113  ldloc.0
0x9114  ret
```
