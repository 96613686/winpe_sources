# Em_AmrNB_Dec_gPow2

- ea: `0x180004d24`
- end: `0x180004d7e`
- name: `Em_AmrNB_Dec_gPow2`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800051e0`
- `0x180007138`

## callees

- `0x180006764`
- `0x180006844`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gPow2(__int64 a1, __int16 a2)
{
  unsigned int v2; // eax
  unsigned __int16 v3; // r10

  v2 = Em_AmrNB_Dec_L_msu(
         *((__int16 *)Em_AmrNB_Dec_Pow2Table + (a2 >> 10)) << 16,
         *((_WORD *)Em_AmrNB_Dec_Pow2Table + (a2 >> 10)) - *((_WORD *)Em_AmrNB_Dec_Pow2Table + (a2 >> 10) + 1),
         (a2 << 6 >> 1) & 0x7FFF);
  return Em_AmrNB_Dec_L_shr_r(v2, v3);
}

```

## disassembly

```asm
0x180004d24  sub     rsp, 28h
0x180004d28  movsx   r8d, dx
0x180004d2c  lea     r11, Em_AmrNB_Dec_Pow2Table
0x180004d33  shl     r8d, 6
0x180004d37  mov     r10d, 1Eh
0x180004d3d  mov     eax, r8d
0x180004d40  sub     r10w, cx
0x180004d44  sar     eax, 10h
0x180004d47  movsx   r9, ax
0x180004d4b  mov     eax, 7FFFh
0x180004d50  sar     r8d, 1
0x180004d53  and     r8w, ax
0x180004d57  movzx   edx, word ptr [r11+r9*2]
0x180004d5c  movsx   ecx, word ptr [r11+r9*2]
0x180004d61  sub     dx, [r11+r9*2+2]
0x180004d67  shl     ecx, 10h
0x180004d6a  call    Em_AmrNB_Dec_L_msu
0x180004d6f  mov     ecx, eax
0x180004d71  movzx   edx, r10w
0x180004d75  add     rsp, 28h
0x180004d79  jmp     Em_AmrNB_Dec_L_shr_r
```
