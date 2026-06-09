# Em_AmrNB_Dec_gLog2

- ea: `0x180004bb4`
- end: `0x180004c46`
- name: `Em_AmrNB_Dec_gLog2`
- size: `146`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800051e0`
- `0x180005fa0`
- `0x180007138`

## callees

- `0x180004bb4`
- `0x18000698c`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gLog2(__int64 a1)
{
  __int16 v1; // ax
  int v2; // r9d
  int v3; // r8d
  int v4; // r8d
  int v6; // ecx
  int v7; // r8d
  __int16 v8; // ax
  int v9; // edx

  v1 = Em_AmrNB_Dec_norm_l(a1);
  v2 = v1;
  v4 = v3 << v1;
  if ( v4 <= 0 || v4 >> 25 < 32 )
    return 0;
  v6 = (v4 >> 25) - 32;
  v7 = v4 >> 10;
  if ( v6 <= 0x7FFF )
  {
    v8 = 0x8000;
    if ( v6 >= -32768 )
      v8 = v6;
  }
  else
  {
    v8 = 0x7FFF;
  }
  v9 = *((__int16 *)Em_AmrNB_Dec_Log2Table + v8);
  return (unsigned int)(2
                      * (((30 - v2) << 15)
                       + (__int16)(((v9 << 16)
                                  - 2 * (v7 & 0x7FFFu) * (v9 - *((__int16 *)Em_AmrNB_Dec_Log2Table + v8 + 1))) >> 16)));
}

```

## disassembly

```asm
0x180004bb4  sub     rsp, 28h
0x180004bb8  mov     r8d, ecx
0x180004bbb  call    Em_AmrNB_Dec_norm_l
0x180004bc0  movsx   r9d, ax
0x180004bc4  mov     ecx, r9d
0x180004bc7  shl     r8d, cl
0x180004bca  test    r8d, r8d
0x180004bcd  jg      short loc_180004BD3
0x180004bcf  xor     eax, eax
0x180004bd1  jmp     short loc_180004C41
0x180004bd3  mov     eax, r8d
0x180004bd6  sar     eax, 19h
0x180004bd9  cmp     ax, 20h ; ' '
0x180004bdd  jl      short loc_180004BCF
0x180004bdf  movsx   ecx, ax
0x180004be2  mov     r10d, 7FFFh
0x180004be8  add     ecx, 0FFFFFFE0h
0x180004beb  sar     r8d, 0Ah
0x180004bef  cmp     ecx, r10d
0x180004bf2  jle     short loc_180004BFA
0x180004bf4  movzx   eax, r10w
0x180004bf8  jmp     short loc_180004C06
0x180004bfa  mov     eax, 0FFFF8000h
0x180004bff  cmp     ecx, eax
0x180004c01  jl      short loc_180004C06
0x180004c03  movzx   eax, cx
0x180004c06  movsx   rax, ax
0x180004c0a  lea     rcx, Em_AmrNB_Dec_Log2Table
0x180004c11  and     r8d, r10d
0x180004c14  movsx   edx, word ptr [rcx+rax*2]
0x180004c18  movsx   eax, word ptr [rcx+rax*2+2]
0x180004c1d  mov     ecx, edx
0x180004c1f  sub     ecx, eax
0x180004c21  shl     edx, 10h
0x180004c24  imul    ecx, r8d
0x180004c28  add     ecx, ecx
0x180004c2a  sub     edx, ecx
0x180004c2c  mov     ecx, 1Eh
0x180004c31  sub     ecx, r9d
0x180004c34  sar     edx, 10h
0x180004c37  shl     ecx, 0Fh
0x180004c3a  movsx   eax, dx
0x180004c3d  add     eax, ecx
0x180004c3f  add     eax, eax
0x180004c41  add     rsp, 28h
0x180004c45  retn
```
