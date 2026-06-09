# Em_AmrNB_Dec_Mpy_32_16

- ea: `0x180004afc`
- end: `0x180004b53`
- name: `Em_AmrNB_Dec_Mpy_32_16`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007138`
- `0x1800079f0`
- `0x180007d60`

## callees

- `0x180004afc`
- `0x18000671c`
- `0x18000694c`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_Mpy_32_16(int a1, __int16 a2)
{
  __int16 v2; // ax
  int v3; // r9d
  __int16 v4; // r10

  v2 = Em_AmrNB_Dec_mult((a1 >> 1) & 0x7FFF, a2);
  return Em_AmrNB_Dec_L_mac(v3, v2, v4);
}

```

## disassembly

```asm
0x180004afc  sub     rsp, 28h
0x180004b00  mov     r8d, ecx
0x180004b03  mov     eax, 7FFFh
0x180004b08  sar     r8d, 1
0x180004b0b  sar     ecx, 10h
0x180004b0e  and     r8w, ax
0x180004b12  movsx   eax, dx
0x180004b15  movsx   r9d, cx
0x180004b19  imul    r9d, eax
0x180004b1d  cmp     r9d, 40000000h
0x180004b24  jz      short loc_180004B2B
0x180004b26  add     r9d, r9d
0x180004b29  jmp     short loc_180004B31
0x180004b2b  mov     r9d, 7FFFFFFFh
0x180004b31  movzx   ecx, r8w
0x180004b35  mov     r10d, 1
0x180004b3b  call    Em_AmrNB_Dec_mult
0x180004b40  movzx   edx, ax
0x180004b43  movzx   r8d, r10w
0x180004b47  mov     ecx, r9d
0x180004b4a  add     rsp, 28h
0x180004b4e  jmp     Em_AmrNB_Dec_L_mac
```
