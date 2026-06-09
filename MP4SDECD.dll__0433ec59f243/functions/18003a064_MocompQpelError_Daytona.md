# MocompQpelError_Daytona

- ea: `0x18003a064`
- end: `0x18003a2b0`
- name: `MocompQpelError_Daytona`
- size: `588`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180039c50`
- `0x180039cb0`
- `0x180039db0`
- `0x180039e10`
- `0x180039f10`
- `0x180039f70`

## callees

- `0x1800259ac`
- `0x18003a064`

## import_xrefs

- `mfperfhelper!__imp_ippiCopy8x8QP_MPEG4_8u_C1R` at `0x18003a207`
- `mfperfhelper!__imp_ippiCopy8x8QP_MPEG4_8u_C1R` at `0x18003a207`
- `mfperfhelper!__imp_ippiCopy16x8QP_MPEG4_8u_C1R` at `0x18003a199`
- `mfperfhelper!__imp_ippiCopy16x8QP_MPEG4_8u_C1R` at `0x18003a199`
- `mfperfhelper!__imp_ippiCopy16x16QP_MPEG4_8u_C1R` at `0x18003a238`
- `mfperfhelper!__imp_ippiCopy16x16QP_MPEG4_8u_C1R` at `0x18003a238`
- `mfperfhelper!__imp_ippiAdd8x8_16s8u_C1IRS` at `0x18003a1af`
- `mfperfhelper!__imp_ippiAdd8x8_16s8u_C1IRS` at `0x18003a24c`
- `mfperfhelper!__imp_ippiAdd8x8_16s8u_C1IRS` at `0x18003a26a`
- `mfperfhelper!__imp_ippiAdd8x8_16s8u_C1IRS` at `0x18003a286`
- `mfperfhelper!__imp_ippiAdd8x8_16s8u_C1IRS` at `0x18003a299`
- `mfperfhelper!__imp_ippiAdd8x8_16s8u_C1IRS` at `0x18003a1af`
- `mfperfhelper!__imp_ippiAdd8x8_16s8u_C1IRS` at `0x18003a24c`
- `mfperfhelper!__imp_ippiAdd8x8_16s8u_C1IRS` at `0x18003a26a`
- `mfperfhelper!__imp_ippiAdd8x8_16s8u_C1IRS` at `0x18003a286`
- `mfperfhelper!__imp_ippiAdd8x8_16s8u_C1IRS` at `0x18003a299`

## pseudocode

```c
__int64 __fastcall MocompQpelError_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        unsigned int a8,
        int a9,
        int a10,
        unsigned __int8 a11)
{
  unsigned int v11; // ebx
  __int64 result; // rax
  int v15; // r8d
  __int64 v16; // r15
  __int64 v17; // r12
  __int64 v18; // r13
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // [rsp+40h] [rbp-18h] BYREF
  int v24[5]; // [rsp+44h] [rbp-14h] BYREF

  v11 = a8;
  if ( a8 )
  {
    result = a8 + a5 * (a8 - 1) - 1;
    if ( (unsigned int)result >= a2 )
      return result;
    if ( a2 < a8 )
      return result;
    result = a8 - 8;
    if ( (result & 0xFFFFFFF7) != 0 )
      return result;
  }
  else
  {
    result = 14 * a5 + 15;
    if ( (unsigned int)result >= a2 || a2 < 0x10 )
      return result;
  }
  v15 = a8;
  v24[0] = 0;
  v23 = 0;
  a7 = 0;
  a8 = 0;
  CalculateQPel(a9, a10, v15, v24, &v23, &a7, (int *)&a8);
  if ( v11 == 16 || (v16 = 0, !v11) )
    v16 = a4 + 256;
  v17 = a4 + 768;
  if ( v11 != 16 )
    v17 = 0;
  v18 = a4 + 512;
  if ( v11 != 16 )
    v18 = 0;
  if ( !v11 )
  {
    ippiCopy16x8QP_MPEG4_8u_C1R(a3 + (int)(2 * a6 * v23) + v24[0], 2 * a6, a1, 2 * a5, a7 | (4 * a8), a11);
    ippiAdd8x8_16s8u_C1IRS(a4, 16, a1, 2 * a5);
    v19 = a1 + 8;
    v20 = 2 * a5;
    v21 = v16;
    return ippiAdd8x8_16s8u_C1IRS(v21, 16, v19, v20);
  }
  v22 = a3 + (int)(a6 * v23);
  if ( v11 == 8 )
  {
    ippiCopy8x8QP_MPEG4_8u_C1R(v22 + v24[0], a6, a1, a5, a7 | (4 * a8), a11);
  }
  else if ( v11 == 16 )
  {
    ippiCopy16x16QP_MPEG4_8u_C1R(v22 + v24[0], a6, a1, a5, a7 | (4 * a8), a11);
  }
  result = ippiAdd8x8_16s8u_C1IRS(a4, 16, a1, a5);
  if ( v11 == 16 )
  {
    ippiAdd8x8_16s8u_C1IRS(v16, 16, a1 + 8, a5);
    ippiAdd8x8_16s8u_C1IRS(v18, 16, a1 + 8 * a5, a5);
    v19 = a1 + 8 * a5 + 8;
    v20 = a5;
    v21 = v17;
    return ippiAdd8x8_16s8u_C1IRS(v21, 16, v19, v20);
  }
  return result;
}

```

## disassembly

```asm
0x18003a064  mov     [rsp-40h+arg_10], r8
0x18003a069  push    rbp
0x18003a06a  push    rbx
0x18003a06b  push    rsi
0x18003a06c  push    rdi
0x18003a06d  push    r12
0x18003a06f  push    r13
0x18003a071  push    r14
0x18003a073  push    r15
0x18003a075  mov     rbp, rsp
0x18003a078  sub     rsp, 58h
0x18003a07c  mov     ebx, [rbp+arg_38]
0x18003a082  xor     r13d, r13d
0x18003a085  mov     edi, [rbp+arg_20]
0x18003a088  mov     r14, r9
0x18003a08b  mov     rsi, rcx
0x18003a08e  test    ebx, ebx
0x18003a090  jnz     short loc_18003A0AA
0x18003a092  imul    eax, edi, 0Eh
0x18003a095  add     eax, 0Fh
0x18003a098  cmp     eax, edx
0x18003a09a  jnb     loc_18003A29F
0x18003a0a0  cmp     edx, 10h
0x18003a0a3  jnb     short loc_18003A0D2
0x18003a0a5  jmp     loc_18003A29F
0x18003a0aa  lea     eax, [rbx-1]
0x18003a0ad  imul    eax, edi
0x18003a0b0  dec     eax
0x18003a0b2  add     eax, ebx
0x18003a0b4  cmp     eax, edx
0x18003a0b6  jnb     loc_18003A29F
0x18003a0bc  cmp     edx, ebx
0x18003a0be  jb      loc_18003A29F
0x18003a0c4  lea     eax, [rbx-8]
0x18003a0c7  test    eax, 0FFFFFFF7h
0x18003a0cc  jnz     loc_18003A29F
0x18003a0d2  mov     edx, [rbp+arg_48]; int
0x18003a0d8  lea     rax, [rbp+arg_38]
0x18003a0df  mov     ecx, [rbp+arg_40]; int
0x18003a0e5  lea     r9, [rbp+var_14]; int *
0x18003a0e9  mov     [rsp+58h+var_28], rax; int *
0x18003a0ee  mov     r8d, ebx; int
0x18003a0f1  lea     rax, [rbp+arg_30]
0x18003a0f5  mov     [rbp+var_14], r13d
0x18003a0f9  mov     [rsp+58h+var_30], rax; int *
0x18003a0fe  lea     rax, [rbp+var_18]
0x18003a102  mov     [rsp+58h+var_38], rax; int *
0x18003a107  mov     [rbp+var_18], r13d
0x18003a10b  mov     [rbp+arg_30], r13d
0x18003a10f  mov     [rbp+arg_38], r13d
0x18003a116  call    ?CalculateQPel@@YAXJJJAEAJ000@Z; CalculateQPel(long,long,long,long &,long &,long &,long &)
0x18003a11b  cmp     ebx, 10h
0x18003a11e  jz      short loc_18003A127
0x18003a120  mov     r15, r13
0x18003a123  test    ebx, ebx
0x18003a125  jnz     short loc_18003A12E
0x18003a127  lea     r15, [r14+100h]
0x18003a12e  cmp     ebx, 10h
0x18003a131  lea     r12, [r14+300h]
0x18003a138  cmovnz  r12, r13
0x18003a13c  xor     eax, eax
0x18003a13e  cmp     ebx, 10h
0x18003a141  lea     r13, [r14+200h]
0x18003a148  cmovnz  r13, rax
0x18003a14c  test    ebx, ebx
0x18003a14e  jnz     short loc_18003A1C6
0x18003a150  mov     eax, [rbp+arg_38]
0x18003a156  lea     ebx, [rdi+rdi]
0x18003a159  mov     ecx, [rbp+var_18]
0x18003a15c  mov     r9d, ebx
0x18003a15f  movzx   r10d, [rbp+arg_50]
0x18003a167  mov     dword ptr [rsp+58h+var_30], r10d
0x18003a16c  lea     r8d, ds:0[rax*4]
0x18003a174  mov     eax, [rbp+arg_28]
0x18003a177  or      r8d, [rbp+arg_30]
0x18003a17b  imul    ecx, eax
0x18003a17e  mov     dword ptr [rsp+58h+var_38], r8d
0x18003a183  mov     r8, rsi
0x18003a186  lea     edx, [rax+rax]
0x18003a189  lea     eax, [rcx+rcx]
0x18003a18c  movsxd  rcx, [rbp+var_14]
0x18003a190  cdqe
0x18003a192  add     rax, [rbp+arg_10]
0x18003a196  add     rcx, rax
0x18003a199  call    cs:__imp_ippiCopy16x8QP_MPEG4_8u_C1R
0x18003a19f  mov     edi, 10h
0x18003a1a4  mov     r9d, ebx
0x18003a1a7  mov     edx, edi
0x18003a1a9  mov     r8, rsi
0x18003a1ac  mov     rcx, r14
0x18003a1af  call    cs:__imp_ippiAdd8x8_16s8u_C1IRS
0x18003a1b5  lea     r8, [rsi+8]
0x18003a1b9  mov     r9d, ebx
0x18003a1bc  mov     edx, edi
0x18003a1be  mov     rcx, r15
0x18003a1c1  jmp     loc_18003A299
0x18003a1c6  mov     eax, [rbp+var_18]
0x18003a1c9  mov     edx, [rbp+arg_28]
0x18003a1cc  movsxd  r10, [rbp+var_14]
0x18003a1d0  imul    eax, edx
0x18003a1d3  cdqe
0x18003a1d5  add     rax, [rbp+arg_10]
0x18003a1d9  add     r10, rax
0x18003a1dc  cmp     ebx, 8
0x18003a1df  jnz     short loc_18003A20F
0x18003a1e1  mov     eax, [rbp+arg_38]
0x18003a1e7  mov     r9d, edi
0x18003a1ea  movzx   r8d, [rbp+arg_50]
0x18003a1f2  mov     rcx, r10
0x18003a1f5  mov     dword ptr [rsp+58h+var_30], r8d
0x18003a1fa  mov     r8, rsi
0x18003a1fd  shl     eax, 2
0x18003a200  or      eax, [rbp+arg_30]
0x18003a203  mov     dword ptr [rsp+58h+var_38], eax
0x18003a207  call    cs:__imp_ippiCopy8x8QP_MPEG4_8u_C1R
0x18003a20d  jmp     short loc_18003A23E
0x18003a20f  cmp     ebx, 10h
0x18003a212  jnz     short loc_18003A23E
0x18003a214  mov     eax, [rbp+arg_38]
0x18003a21a  mov     r9d, edi
0x18003a21d  movzx   ecx, [rbp+arg_50]
0x18003a224  mov     r8, rsi
0x18003a227  mov     dword ptr [rsp+58h+var_30], ecx
0x18003a22b  mov     rcx, r10
0x18003a22e  shl     eax, 2
0x18003a231  or      eax, [rbp+arg_30]
0x18003a234  mov     dword ptr [rsp+58h+var_38], eax
0x18003a238  call    cs:__imp_ippiCopy16x16QP_MPEG4_8u_C1R
0x18003a23e  mov     r9d, edi
0x18003a241  mov     r8, rsi
0x18003a244  mov     edx, 10h
0x18003a249  mov     rcx, r14
0x18003a24c  call    cs:__imp_ippiAdd8x8_16s8u_C1IRS
0x18003a252  mov     r14d, 10h
0x18003a258  cmp     ebx, r14d
0x18003a25b  jnz     short loc_18003A29F
0x18003a25d  lea     r8, [rsi+8]
0x18003a261  mov     r9d, edi
0x18003a264  mov     edx, r14d
0x18003a267  mov     rcx, r15
0x18003a26a  call    cs:__imp_ippiAdd8x8_16s8u_C1IRS
0x18003a270  lea     ebx, ds:0[rdi*8]
0x18003a277  mov     r9d, edi
0x18003a27a  add     rbx, rsi
0x18003a27d  mov     edx, r14d
0x18003a280  mov     r8, rbx
0x18003a283  mov     rcx, r13
0x18003a286  call    cs:__imp_ippiAdd8x8_16s8u_C1IRS
0x18003a28c  lea     r8, [rbx+8]
0x18003a290  mov     r9d, edi
0x18003a293  mov     edx, r14d
0x18003a296  mov     rcx, r12
0x18003a299  call    cs:__imp_ippiAdd8x8_16s8u_C1IRS
0x18003a29f  add     rsp, 58h
0x18003a2a3  pop     r15
0x18003a2a5  pop     r14
0x18003a2a7  pop     r13
0x18003a2a9  pop     r12
0x18003a2ab  pop     rdi
0x18003a2ac  pop     rsi
0x18003a2ad  pop     rbx
0x18003a2ae  pop     rbp
0x18003a2af  retn
```
