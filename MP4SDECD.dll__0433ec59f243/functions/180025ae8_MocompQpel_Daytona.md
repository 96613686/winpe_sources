# MocompQpel_Daytona

- ea: `0x180025ae8`
- end: `0x180025c92`
- name: `MocompQpel_Daytona`
- size: `426`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180039d10`
- `0x180039d60`
- `0x180039e70`
- `0x180039ec0`
- `0x180039fd0`
- `0x18003a020`

## callees

- `0x180025ae8`

## import_xrefs

- `mfperfhelper!__imp_ippiCopy8x8QP_MPEG4_8u_C1R` at `0x180025c50`
- `mfperfhelper!__imp_ippiCopy8x8QP_MPEG4_8u_C1R` at `0x180025c50`
- `mfperfhelper!__imp_ippiCopy16x8QP_MPEG4_8u_C1R` at `0x180025c14`
- `mfperfhelper!__imp_ippiCopy16x8QP_MPEG4_8u_C1R` at `0x180025c14`
- `mfperfhelper!__imp_ippiCopy16x16QP_MPEG4_8u_C1R` at `0x180025c81`
- `mfperfhelper!__imp_ippiCopy16x16QP_MPEG4_8u_C1R` at `0x180025c81`

## pseudocode

```c
__int64 __fastcall MocompQpel_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8,
        unsigned __int8 a9)
{
  __int64 result; // rax
  int v11; // r11d
  int v12; // r9d
  int v13; // ebx
  int v14; // r11d
  __int64 v15; // r11

  if ( a6 )
  {
    result = a6 + a4 * (a6 - 1) - 1;
    if ( (unsigned int)result >= a2 )
      return result;
    if ( a2 < a6 )
      return result;
    result = a6 - 8;
    if ( (result & 0xFFFFFFF7) != 0 )
      return result;
    v11 = a8 / 4;
    if ( a8 < 0 && a8 % 4 )
      --v11;
    v12 = a8 - 4 * v11;
  }
  else
  {
    result = 14 * a4 + 15;
    if ( (unsigned int)result >= a2 || a2 < 0x10 )
      return result;
    v11 = (a8 >> 1) / 4;
    if ( a8 >> 1 < 0 && (a8 >> 1) % 4 )
      --v11;
    v12 = (a8 >> 1) - 4 * v11;
  }
  result = (unsigned int)(a7 / 4);
  if ( a7 < 0 && a7 % 4 )
    result = (unsigned int)(result - 1);
  v13 = a7 - 4 * result;
  v14 = a5 * v11;
  if ( !a6 )
    return ippiCopy16x8QP_MPEG4_8u_C1R(
             a3 + (int)result + (__int64)(2 * v14),
             2 * a5,
             a1,
             2 * a4,
             v13 | (unsigned int)(4 * v12),
             a9);
  v15 = a3 + (int)result + (__int64)v14;
  if ( a6 == 8 )
    return ippiCopy8x8QP_MPEG4_8u_C1R(v15, a5, a1, a4, v13 | (unsigned int)(4 * v12), a9);
  if ( a6 == 16 )
    return ippiCopy16x16QP_MPEG4_8u_C1R(v15, a5, a1, a4, v13 | (unsigned int)(4 * v12), a9);
  return result;
}

```

## disassembly

```asm
0x180025ae8  push    rbx
0x180025aea  push    rbp
0x180025aeb  push    rsi
0x180025aec  push    rdi
0x180025aed  push    r14
0x180025aef  sub     rsp, 30h
0x180025af3  mov     r10d, [rsp+58h+arg_28]
0x180025afb  mov     edi, r9d
0x180025afe  mov     r14, r8
0x180025b01  mov     rbp, rcx
0x180025b04  test    r10d, r10d
0x180025b07  jnz     short loc_180025B52
0x180025b09  imul    eax, edi, 0Eh
0x180025b0c  add     eax, 0Fh
0x180025b0f  cmp     eax, edx
0x180025b11  jnb     loc_180025C87
0x180025b17  cmp     edx, 10h
0x180025b1a  jb      loc_180025C87
0x180025b20  mov     r9d, [rsp+58h+arg_38]
0x180025b28  lea     r8d, [r10+4]
0x180025b2c  sar     r9d, 1
0x180025b2f  mov     eax, r9d
0x180025b32  cdq
0x180025b33  idiv    r8d
0x180025b36  mov     r11d, eax
0x180025b39  test    r9d, r9d
0x180025b3c  jns     short loc_180025B45
0x180025b3e  test    edx, edx
0x180025b40  jz      short loc_180025B45
0x180025b42  dec     r11d
0x180025b45  lea     ecx, ds:0[r11*4]
0x180025b4d  sub     r9d, ecx
0x180025b50  jmp     short loc_180025BAD
0x180025b52  lea     eax, [r10-1]
0x180025b56  imul    eax, edi
0x180025b59  dec     eax
0x180025b5b  add     eax, r10d
0x180025b5e  cmp     eax, edx
0x180025b60  jnb     loc_180025C87
0x180025b66  cmp     edx, r10d
0x180025b69  jb      loc_180025C87
0x180025b6f  lea     eax, [r10-8]
0x180025b73  test    eax, 0FFFFFFF7h
0x180025b78  jnz     loc_180025C87
0x180025b7e  mov     r9d, [rsp+58h+arg_38]
0x180025b86  mov     r8d, 4
0x180025b8c  mov     eax, r9d
0x180025b8f  cdq
0x180025b90  idiv    r8d
0x180025b93  mov     r11d, eax
0x180025b96  test    r9d, r9d
0x180025b99  jns     short loc_180025BA2
0x180025b9b  test    edx, edx
0x180025b9d  jz      short loc_180025BA2
0x180025b9f  dec     r11d
0x180025ba2  lea     eax, ds:0[r11*4]
0x180025baa  sub     r9d, eax
0x180025bad  mov     ebx, [rsp+58h+arg_30]
0x180025bb4  mov     eax, ebx
0x180025bb6  cdq
0x180025bb7  idiv    r8d
0x180025bba  test    ebx, ebx
0x180025bbc  jns     short loc_180025BC4
0x180025bbe  test    edx, edx
0x180025bc0  jz      short loc_180025BC4
0x180025bc2  dec     eax
0x180025bc4  mov     edx, [rsp+58h+arg_20]
0x180025bcb  lea     ecx, ds:0[rax*4]
0x180025bd2  sub     ebx, ecx
0x180025bd4  imul    r11d, edx
0x180025bd8  movsxd  rsi, eax
0x180025bdb  test    r10d, r10d
0x180025bde  jnz     short loc_180025C1C
0x180025be0  movzx   r8d, [rsp+58h+arg_40]
0x180025be9  lea     r10d, ds:0[r9*4]
0x180025bf1  mov     [rsp+58h+var_30], r8d
0x180025bf6  lea     eax, [r11+r11]
0x180025bfa  movsxd  rcx, eax
0x180025bfd  lea     r9d, [rdi+rdi]
0x180025c01  add     rcx, rsi
0x180025c04  or      r10d, ebx
0x180025c07  add     rcx, r14
0x180025c0a  mov     [rsp+58h+var_38], r10d
0x180025c0f  add     edx, edx
0x180025c11  mov     r8, rbp
0x180025c14  call    cs:__imp_ippiCopy16x8QP_MPEG4_8u_C1R
0x180025c1a  jmp     short loc_180025C87
0x180025c1c  movsxd  r11, r11d
0x180025c1f  add     r11, rsi
0x180025c22  add     r11, r14
0x180025c25  cmp     r10d, 8
0x180025c29  jnz     short loc_180025C58
0x180025c2b  movzx   eax, [rsp+58h+arg_40]
0x180025c33  lea     r8d, ds:0[r9*4]
0x180025c3b  or      r8d, ebx
0x180025c3e  mov     [rsp+58h+var_30], eax
0x180025c42  mov     [rsp+58h+var_38], r8d
0x180025c47  mov     r9d, edi
0x180025c4a  mov     r8, rbp
0x180025c4d  mov     rcx, r11
0x180025c50  call    cs:__imp_ippiCopy8x8QP_MPEG4_8u_C1R
0x180025c56  jmp     short loc_180025C87
0x180025c58  cmp     r10d, 10h
0x180025c5c  jnz     short loc_180025C87
0x180025c5e  movzx   eax, [rsp+58h+arg_40]
0x180025c66  lea     ecx, ds:0[r9*4]
0x180025c6e  or      ecx, ebx
0x180025c70  mov     [rsp+58h+var_30], eax
0x180025c74  mov     [rsp+58h+var_38], ecx
0x180025c78  mov     r9d, edi
0x180025c7b  mov     rcx, r11
0x180025c7e  mov     r8, rbp
0x180025c81  call    cs:__imp_ippiCopy16x16QP_MPEG4_8u_C1R
0x180025c87  add     rsp, 30h
0x180025c8b  pop     r14
0x180025c8d  pop     rdi
0x180025c8e  pop     rsi
0x180025c8f  pop     rbp
0x180025c90  pop     rbx
0x180025c91  retn
```
