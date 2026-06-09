# BthUsb_ScoAnyTransfer(_DEVICE_EXTENSION *,uchar)

- ea: `0x14000465c`
- end: `0x1400046ab`
- name: `?BthUsb_ScoAnyTransfer@@YAEPEAU_DEVICE_EXTENSION@@E@Z`
- size: `79`
- prototype: `unsigned __int8 __fastcall(struct _DEVICE_EXTENSION *, unsigned __int8)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400057ac`
- `0x14000581c`

## callees

- `0x14000465c`

## pseudocode

```c
char __fastcall BthUsb_ScoAnyTransfer(struct _DEVICE_EXTENSION *a1, char a2)
{
  unsigned __int16 v2; // r9
  char v3; // r8
  __int64 v4; // r10

  v2 = 0;
  v3 = 1;
  while ( 1 )
  {
    v4 = v2;
    if ( a1->Sco.Channel[v4].ConnectionHandle != 0xFFFF
      && !(a2 ? a1->Sco.Channel[v4].RxBandwidth == 0 : a1->Sco.Channel[v4].TxBandwidth == 0) )
    {
      break;
    }
    if ( ++v2 >= 3u )
      return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x14000465c  xor     r9d, r9d
0x14000465f  mov     r8w, 1
0x140004664  movzx   eax, r9w
0x140004668  imul    r10, rax, 98h
0x14000466f  mov     eax, 0FFFFh
0x140004674  cmp     [r10+rcx+2B0h], ax
0x14000467d  jz      short loc_140004699
0x14000467f  test    dl, dl
0x140004681  jz      short loc_14000468E
0x140004683  cmp     dword ptr [r10+rcx+2C8h], 0
0x14000468c  jmp     short loc_140004697
0x14000468e  cmp     dword ptr [r10+rcx+2C4h], 0
0x140004697  jnz     short loc_1400046A7
0x140004699  add     r9w, r8w
0x14000469d  cmp     r9w, 3
0x1400046a2  jb      short loc_140004664
0x1400046a4  xor     r8b, r8b
0x1400046a7  mov     al, r8b
0x1400046aa  retn
```
