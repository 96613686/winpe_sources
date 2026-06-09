# BthUsb_ScoStopUsbTraffic(_DEVICE_EXTENSION *)

- ea: `0x14000581c`
- end: `0x14000584f`
- name: `?BthUsb_ScoStopUsbTraffic@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `51`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400030e0`
- `0x140005180`
- `0x140018910`

## callees

- `0x14000465c`
- `0x14000581c`
- `0x140007f8c`
- `0x1400098bc`

## pseudocode

```c
void __fastcall BthUsb_ScoStopUsbTraffic(struct _DEVICE_EXTENSION *a1)
{
  __int16 v2; // dx
  struct _DEVICE_EXTENSION *v3; // rcx
  int v4; // r8d
  __int16 v5; // dx
  struct _DEVICE_EXTENSION *v6; // rcx
  int v7; // r8d

  if ( BthUsb_ScoAnyTransfer(a1, 1u) )
    BthUsb_ScoReadStopWait(v3, v2, v4);
  if ( BthUsb_ScoAnyTransfer(a1, 0) )
    BthUsb_ScoWriteStopWait(v6, v5, v7);
}

```

## disassembly

```asm
0x14000581c  push    rbx
0x14000581e  sub     rsp, 20h
0x140005822  mov     dl, 1; unsigned __int8
0x140005824  mov     rbx, rcx
0x140005827  call    ?BthUsb_ScoAnyTransfer@@YAEPEAU_DEVICE_EXTENSION@@E@Z; BthUsb_ScoAnyTransfer(_DEVICE_EXTENSION *,uchar)
0x14000582c  test    al, al
0x14000582e  jz      short loc_140005835
0x140005830  call    ?BthUsb_ScoReadStopWait@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoReadStopWait(_DEVICE_EXTENSION *)
0x140005835  xor     edx, edx; unsigned __int8
0x140005837  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14000583a  call    ?BthUsb_ScoAnyTransfer@@YAEPEAU_DEVICE_EXTENSION@@E@Z; BthUsb_ScoAnyTransfer(_DEVICE_EXTENSION *,uchar)
0x14000583f  test    al, al
0x140005841  jz      short loc_140005848
0x140005843  call    ?BthUsb_ScoWriteStopWait@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoWriteStopWait(_DEVICE_EXTENSION *)
0x140005848  add     rsp, 20h
0x14000584c  pop     rbx
0x14000584d  retn
```
