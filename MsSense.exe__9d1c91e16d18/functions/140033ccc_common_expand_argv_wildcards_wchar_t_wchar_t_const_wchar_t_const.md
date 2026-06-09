# common_expand_argv_wildcards<wchar_t>(wchar_t * * const,wchar_t * * * const)

- ea: `0x140033ccc`
- end: `0x140033e76`
- name: `??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z`
- size: `426`
- prototype: `__int64 __fastcall(__int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140034cc0`

## callees

- `0x140018140`
- `0x140028ae8`
- `0x140033868`
- `0x140033ccc`
- `0x140035788`
- `0x140035ce4`
- `0x140037f20`
- `0x140051ba0`
- `0x140066a40`

## pseudocode

```c
__int64 __fastcall common_expand_argv_wildcards<wchar_t>(__int64 a1, unsigned __int16 a2)
{
  _OWORD *v4; // r14
  _QWORD *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rsi
  _QWORD *v8; // rdx
  _QWORD *v9; // rax
  unsigned __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  _BYTE v14[32]; // [rsp+28h] [rbp-58h] BYREF
  _QWORD v15[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v16; // [rsp+58h] [rbp-28h]
  unsigned __int64 v17; // [rsp+60h] [rbp-20h]
  _WORD v18[4]; // [rsp+68h] [rbp-18h] BYREF

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v4 = (_OWORD *)(a1 + 32);
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 7;
  *(_WORD *)(a1 + 32) = 0;
  v5 = (_QWORD *)(a1 + 64);
  *(_OWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 7;
  *(_WORD *)(a1 + 64) = 0;
  *(_BYTE *)(a1 + 96) = 0;
  *(_DWORD *)(a1 + 100) = 0;
  sub_140033868(a1 + 104);
  *(_BYTE *)(a1 + 368) = 0;
  v18[1] = 58;
  v18[2] = 0;
  v18[0] = a2;
  v6 = sub_140066A40(v18);
  sub_140028AE8(a1, v18, v6);
  v7 = sub_140035788(v14, a2);
  if ( v4 != (_OWORD *)v7 )
  {
    sub_140018140(v4);
    *v4 = *(_OWORD *)v7;
    v4[1] = *(_OWORD *)(v7 + 16);
    *(_QWORD *)(v7 + 16) = 0;
    *(_QWORD *)(v7 + 24) = 7;
    *(_WORD *)v7 = 0;
  }
  sub_140018140(v14);
  sub_140035CE4(v15, a2);
  if ( v5 != v15 )
  {
    v8 = v15;
    if ( v17 > 7 )
      v8 = (_QWORD *)v15[0];
    sub_140028AE8(v5, v8, v16);
  }
  v9 = v5;
  v10 = v5[3];
  if ( v10 > 7 )
    v9 = (_QWORD *)*v5;
  v11 = v5[2];
  if ( *((_WORD *)v9 + v11 - 1) == 92 )
  {
    v5[2] = v11 - 1;
    if ( v10 > 7 )
      v5 = (_QWORD *)*v5;
    *((_WORD *)v5 + v11 - 1) = 0;
  }
  v12 = v15;
  if ( !v16 )
    v12 = (_QWORD *)a1;
  sub_140037F20(a1, v12);
  sub_140018140(v15);
  return a1;
}

```

## disassembly

```asm
0x140033ccc  mov     [rsp-38h+arg_10], rbx
0x140033cd1  push    rbp
0x140033cd2  push    rsi
0x140033cd3  push    rdi
0x140033cd4  push    r12
0x140033cd6  push    r13
0x140033cd8  push    r14
0x140033cda  push    r15
0x140033cdc  mov     rbp, rsp
0x140033cdf  sub     rsp, 80h
0x140033ce6  mov     rax, cs:__security_cookie
0x140033ced  xor     rax, rsp
0x140033cf0  mov     [rbp+var_10], rax
0x140033cf4  movzx   r15d, dx
0x140033cf8  mov     rdi, rcx
0x140033cfb  mov     [rbp+var_60], rcx
0x140033cff  xorps   xmm0, xmm0
0x140033d02  movups  xmmword ptr [rcx], xmm0
0x140033d05  xor     r12d, r12d
0x140033d08  mov     [rcx+10h], r12
0x140033d0c  lea     r13d, [r12+7]
0x140033d11  mov     [rcx+18h], r13
0x140033d15  mov     [rcx], r12w
0x140033d19  lea     r14, [rcx+20h]
0x140033d1d  movups  xmmword ptr [r14], xmm0
0x140033d21  mov     [r14+10h], r12
0x140033d25  mov     [r14+18h], r13
0x140033d29  mov     [r14], r12w
0x140033d2d  lea     rbx, [rcx+40h]
0x140033d31  movups  xmmword ptr [rbx], xmm0
0x140033d34  mov     [rbx+10h], r12
0x140033d38  mov     [rbx+18h], r13
0x140033d3c  mov     [rbx], r12w
0x140033d40  mov     [rcx+60h], r12b
0x140033d44  mov     [rcx+64h], r12d
0x140033d48  add     rcx, 68h ; 'h'
0x140033d4c  call    sub_140033868
0x140033d51  nop
0x140033d52  mov     [rdi+170h], r12b
0x140033d59  mov     eax, cs:dword_140090108
0x140033d5f  mov     [rbp+var_18], eax
0x140033d62  movzx   eax, cs:word_14009010C
0x140033d69  mov     [rbp+var_14], ax
0x140033d6d  mov     word ptr [rbp+var_18], r15w
0x140033d72  lea     rcx, [rbp+var_18]
0x140033d76  call    sub_140066A40
0x140033d7b  mov     r8, rax
0x140033d7e  lea     rdx, [rbp+var_18]
0x140033d82  mov     rcx, rdi
0x140033d85  call    sub_140028AE8
0x140033d8a  movzx   edx, r15w
0x140033d8e  lea     rcx, [rbp+var_58]
0x140033d92  call    sub_140035788
0x140033d97  mov     rsi, rax
0x140033d9a  cmp     r14, rax
0x140033d9d  jz      short loc_140033DC3
0x140033d9f  mov     rcx, r14
0x140033da2  call    sub_140018140
0x140033da7  movups  xmm0, xmmword ptr [rsi]
0x140033daa  movups  xmmword ptr [r14], xmm0
0x140033dae  movups  xmm1, xmmword ptr [rsi+10h]
0x140033db2  movups  xmmword ptr [r14+10h], xmm1
0x140033db7  mov     [rsi+10h], r12
0x140033dbb  mov     [rsi+18h], r13
0x140033dbf  mov     [rsi], r12w
0x140033dc3  lea     rcx, [rbp+var_58]
0x140033dc7  call    sub_140018140
0x140033dcc  movzx   edx, r15w
0x140033dd0  lea     rcx, [rbp+var_38]
0x140033dd4  call    sub_140035CE4
0x140033dd9  nop
0x140033dda  lea     rax, [rbp+var_38]
0x140033dde  cmp     rbx, rax
0x140033de1  jz      short loc_140033DFC
0x140033de3  lea     rdx, [rbp+var_38]
0x140033de7  cmp     [rbp+var_20], r13
0x140033deb  cmova   rdx, [rbp+var_38]
0x140033df0  mov     r8, [rbp+var_28]
0x140033df4  mov     rcx, rbx
0x140033df7  call    sub_140028AE8
0x140033dfc  mov     rax, rbx
0x140033dff  mov     rdx, [rbx+18h]
0x140033e03  cmp     rdx, r13
0x140033e06  jbe     short loc_140033E0B
0x140033e08  mov     rax, [rbx]
0x140033e0b  mov     rcx, [rbx+10h]
0x140033e0f  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140033e15  jnz     short loc_140033E2C
0x140033e17  lea     rax, [rcx-1]
0x140033e1b  mov     [rbx+10h], rax
0x140033e1f  cmp     rdx, r13
0x140033e22  jbe     short loc_140033E27
0x140033e24  mov     rbx, [rbx]
0x140033e27  mov     [rbx+rax*2], r12w
0x140033e2c  mov     rcx, rdi
0x140033e2f  cmp     [rbp+var_28], r12
0x140033e33  lea     rdx, [rbp+var_38]
0x140033e37  jnz     short loc_140033E3C
0x140033e39  mov     rdx, rdi
0x140033e3c  call    sub_140037F20
0x140033e41  nop
0x140033e42  lea     rcx, [rbp+var_38]
0x140033e46  call    sub_140018140
0x140033e4b  nop
0x140033e4c  mov     rax, rdi
0x140033e4f  mov     rcx, [rbp+var_10]
0x140033e53  xor     rcx, rsp; StackCookie
0x140033e56  call    __security_check_cookie
0x140033e5b  mov     rbx, [rsp+80h+arg_10]
0x140033e63  add     rsp, 80h
0x140033e6a  pop     r15
0x140033e6c  pop     r14
0x140033e6e  pop     r13
0x140033e70  pop     r12
0x140033e72  pop     rdi
0x140033e73  pop     rsi
0x140033e74  pop     rbp
0x140033e75  retn
```
