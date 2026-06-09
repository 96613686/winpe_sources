# HampConnectionDestroy

- ea: `0x180003af0`
- end: `0x180003b48`
- name: `HampConnectionDestroy`
- size: `88`
- prototype: `BOOLEAN __fastcall(__int64)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180001e00`
- `0x1800030a0`
- `0x180003170`
- `0x180003270`
- `0x180004990`
- `0x180004aa0`
- `0x180010650`
- `0x180012170`
- `0x180019810`

## callees

- `0x180003af0`
- `0x180003b50`
- `0x180003c1c`
- `0x180004550`
- `0x1800049fc`

## pseudocode

```c
BOOLEAN __fastcall HampConnectionDestroy(__int64 a1)
{
  __int64 v3; // rcx

  if ( !*(_BYTE *)(a1 + 156) || *(_BYTE *)(a1 + 156) == 1 || *(_BYTE *)(a1 + 156) == 2 || *(_BYTE *)(a1 + 156) == 3 )
  {
    HamIpcChannelRundown(a1 + 24);
  }
  else if ( *(_BYTE *)(a1 + 156) == 6 )
  {
    v3 = *(_QWORD *)(a1 + 24);
    if ( v3 )
      RmpClientWnfDestroySubscription(v3);
  }
  HampConnectionCleanup(a1);
  return HamFreeBuffer((void *)a1);
}

```

## disassembly

```asm
0x180003af0  push    rbx
0x180003af2  sub     rsp, 20h
0x180003af6  movzx   edx, byte ptr [rcx+9Ch]
0x180003afd  mov     rbx, rcx
0x180003b00  test    edx, edx
0x180003b02  jz      short loc_180003B2D
0x180003b04  sub     edx, 1
0x180003b07  jz      short loc_180003B2D
0x180003b09  sub     edx, 1
0x180003b0c  jz      short loc_180003B2D
0x180003b0e  sub     edx, 1
0x180003b11  jz      short loc_180003B2D
0x180003b13  cmp     edx, 3
0x180003b16  jz      short loc_180003B38
0x180003b18  mov     rcx, rbx
0x180003b1b  call    HampConnectionCleanup
0x180003b20  mov     rcx, rbx
0x180003b23  add     rsp, 20h
0x180003b27  pop     rbx
0x180003b28  jmp     HamFreeBuffer
0x180003b2d  add     rcx, 18h
0x180003b31  call    HamIpcChannelRundown
0x180003b36  jmp     short loc_180003B18
0x180003b38  mov     rcx, [rcx+18h]
0x180003b3c  test    rcx, rcx
0x180003b3f  jz      short loc_180003B18
0x180003b41  call    RmpClientWnfDestroySubscription
0x180003b46  jmp     short loc_180003B18
```
