# MbbNdisMultiCarrierDsCidListCompletionHandler(_MBB_REQUEST_CONTEXT *,int)

- ea: `0x140012890`
- end: `0x1400128a3`
- name: `?MbbNdisMultiCarrierDsCidListCompletionHandler@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z`
- size: `19`
- prototype: `void __fastcall(struct _MBB_REQUEST_CONTEXT *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140012890`
- `0x14002e9c4`

## pseudocode

```c
void __fastcall MbbNdisMultiCarrierDsCidListCompletionHandler(struct _MBB_REQUEST_CONTEXT *a1, int a2)
{
  if ( a2 )
    MbbNdisIndicateDeviceCaps(a1, a2);
}

```

## disassembly

```asm
0x140012890  sub     rsp, 28h
0x140012894  test    edx, edx
0x140012896  jz      short loc_14001289D
0x140012898  call    ?MbbNdisIndicateDeviceCaps@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; MbbNdisIndicateDeviceCaps(_MBB_REQUEST_CONTEXT *,int)
0x14001289d  add     rsp, 28h
0x1400128a1  retn
```
