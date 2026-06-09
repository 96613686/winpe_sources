# std::operator+<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180002c80`
- end: `0x180002f0c`
- name: `??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@0@Z`
- size: `652`
- prototype: `__int64 __fastcall(void *Src, void *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002030`

## callees

- `0x180001440`
- `0x1800017a0`
- `0x1800017c0`
- `0x180002c80`
- `0x180004acc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::operator+<wchar_t>(_QWORD *Src, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v3; // rbp
  _QWORD *v4; // r15
  _WORD *v6; // rax
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // r8
  _QWORD *v11; // rax
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // rdi
  _WORD *v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rdi
  _WORD *v21; // rax
  _QWORD *v22; // rcx
  _QWORD *v23; // rax

  v3 = a3;
  v4 = a2;
  Src[3] = 7;
  Src[2] = 0;
  if ( Src[3] < 8u )
    v6 = Src;
  else
    v6 = (_WORD *)*Src;
  *v6 = 0;
  v7 = a2[2] + a3[2];
  v8 = Src[2];
  if ( v8 > v7 )
    goto LABEL_20;
  v9 = Src[3];
  if ( v9 == v7 )
    goto LABEL_20;
  if ( v7 > 0x7FFFFFFFFFFFFFFELL )
    std::string::_Xlen(Src, a2);
  if ( v9 < v7 )
  {
    std::wstring::_Copy(Src, v7, Src[2]);
    goto LABEL_15;
  }
  if ( v7 < 8 )
  {
    v10 = Src[2];
    if ( v7 < v8 )
      v10 = v7;
    LOBYTE(a2) = 1;
    std::wstring::_Tidy(Src, a2, v10);
LABEL_15:
    if ( !v7 )
      goto LABEL_20;
  }
  Src[2] = v8;
  if ( Src[3] < 8u )
    v11 = Src;
  else
    v11 = (_QWORD *)*Src;
  *((_WORD *)v11 + v8) = 0;
LABEL_20:
  v12 = -1;
  v13 = -1;
  if ( v4[2] != -1 )
    v13 = v4[2];
  v14 = Src[2];
  if ( ~v14 <= v13 )
    std::string::_Xlen(Src, a2);
  v15 = v13 + v14;
  if ( v13 )
  {
    if ( v15 > 0x7FFFFFFFFFFFFFFELL )
      std::string::_Xlen(Src, a2);
    if ( Src[3] >= v15 )
    {
      if ( !v15 )
      {
        Src[2] = 0;
        if ( Src[3] < 8u )
          v16 = Src;
        else
          v16 = (_WORD *)*Src;
        *v16 = 0;
        goto LABEL_44;
      }
    }
    else
    {
      std::wstring::_Copy(Src, v13 + v14, v14);
      if ( !v15 )
        goto LABEL_44;
    }
    if ( v4[3] >= 8u )
      v4 = (_QWORD *)*v4;
    if ( Src[3] < 8u )
      v17 = Src;
    else
      v17 = (_QWORD *)*Src;
    memcpy_0((char *)v17 + 2 * Src[2], v4, 2 * v13);
    Src[2] = v15;
    if ( Src[3] < 8u )
      v18 = Src;
    else
      v18 = (_QWORD *)*Src;
    *((_WORD *)v18 + v15) = 0;
  }
LABEL_44:
  if ( v3[2] != -1 )
    v12 = v3[2];
  v19 = Src[2];
  if ( ~v19 <= v12 )
    std::string::_Xlen(Src, a2);
  v20 = v12 + v19;
  if ( v12 )
  {
    if ( v20 > 0x7FFFFFFFFFFFFFFELL )
      std::string::_Xlen(Src, a2);
    if ( Src[3] >= v20 )
    {
      if ( !v20 )
      {
        Src[2] = 0;
        if ( Src[3] < 8u )
          v21 = Src;
        else
          v21 = (_WORD *)*Src;
        *v21 = 0;
        return Src;
      }
    }
    else
    {
      std::wstring::_Copy(Src, v12 + v19, v19);
      if ( !v20 )
        return Src;
    }
    if ( v3[3] >= 8u )
      v3 = (_QWORD *)*v3;
    if ( Src[3] < 8u )
      v22 = Src;
    else
      v22 = (_QWORD *)*Src;
    memcpy_0((char *)v22 + 2 * Src[2], v3, 2 * v12);
    Src[2] = v20;
    if ( Src[3] < 8u )
      v23 = Src;
    else
      v23 = (_QWORD *)*Src;
    *((_WORD *)v23 + v20) = 0;
  }
  return Src;
}

```

## disassembly

```asm
0x180002c80  mov     [rsp+arg_0], rcx
0x180002c85  push    rdi
0x180002c86  push    r12
0x180002c88  push    r13
0x180002c8a  push    r14
0x180002c8c  push    r15
0x180002c8e  sub     rsp, 30h
0x180002c92  mov     [rsp+58h+var_30], 0FFFFFFFFFFFFFFFEh
0x180002c9b  mov     [rsp+58h+arg_8], rbx
0x180002ca0  mov     [rsp+58h+arg_10], rbp
0x180002ca5  mov     [rsp+58h+arg_18], rsi
0x180002caa  mov     rbp, r8
0x180002cad  mov     r15, rdx
0x180002cb0  mov     rbx, rcx
0x180002cb3  xor     r12d, r12d
0x180002cb6  mov     [rsp+58h+var_38], r12d
0x180002cbb  mov     qword ptr [rcx+18h], 7
0x180002cc3  mov     [rcx+10h], r12
0x180002cc7  cmp     qword ptr [rcx+18h], 8
0x180002ccc  jb      short loc_180002CD3
0x180002cce  mov     rax, [rcx]
0x180002cd1  jmp     short loc_180002CD6
0x180002cd3  mov     rax, rbx
0x180002cd6  mov     [rax], r12w
0x180002cda  mov     [rsp+58h+var_38], 1
0x180002ce2  mov     rdi, [r8+10h]
0x180002ce6  add     rdi, [rdx+10h]
0x180002cea  mov     rsi, [rcx+10h]
0x180002cee  mov     r13, 7FFFFFFFFFFFFFFEh
0x180002cf8  cmp     rsi, rdi
0x180002cfb  ja      short loc_180002D76
0x180002cfd  mov     rax, [rcx+18h]
0x180002d01  cmp     rax, rdi
0x180002d04  jz      short loc_180002D76
0x180002d06  cmp     rdi, r13
0x180002d09  jbe     short loc_180002D11
0x180002d0b  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
0x180002d11  cmp     rax, rdi
0x180002d14  jnb     short loc_180002D23
0x180002d16  mov     r8, rsi
0x180002d19  mov     rdx, rdi
0x180002d1c  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180002d21  jmp     short loc_180002D59
0x180002d23  cmp     rdi, 8
0x180002d27  jnb     short loc_180002D3C
0x180002d29  mov     r8, rsi
0x180002d2c  cmp     rdi, rsi
0x180002d2f  cmovb   r8, rdi
0x180002d33  mov     dl, 1
0x180002d35  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180002d3a  jmp     short loc_180002D59
0x180002d3c  test    rdi, rdi
0x180002d3f  jnz     short loc_180002D5E
0x180002d41  mov     [rcx+10h], r12
0x180002d45  cmp     rax, 8
0x180002d49  jb      short loc_180002D50
0x180002d4b  mov     rax, [rcx]
0x180002d4e  jmp     short loc_180002D53
0x180002d50  mov     rax, rbx
0x180002d53  mov     [rax], r12w
0x180002d57  jmp     short loc_180002D76
0x180002d59  test    rdi, rdi
0x180002d5c  jz      short loc_180002D76
0x180002d5e  mov     [rbx+10h], rsi
0x180002d62  cmp     qword ptr [rbx+18h], 8
0x180002d67  jb      short loc_180002D6E
0x180002d69  mov     rax, [rbx]
0x180002d6c  jmp     short loc_180002D71
0x180002d6e  mov     rax, rbx
0x180002d71  mov     [rax+rsi*2], r12w
0x180002d76  or      r14, 0FFFFFFFFFFFFFFFFh
0x180002d7a  mov     rsi, r14
0x180002d7d  cmp     [r15+10h], r14
0x180002d81  cmovb   rsi, [r15+10h]
0x180002d86  mov     r8, [rbx+10h]
0x180002d8a  mov     rax, r8
0x180002d8d  not     rax
0x180002d90  cmp     rax, rsi
0x180002d93  ja      short loc_180002D9B
0x180002d95  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
0x180002d9b  lea     rdi, [rsi+r8]
0x180002d9f  test    rsi, rsi
0x180002da2  jz      loc_180002E33
0x180002da8  cmp     rdi, r13
0x180002dab  jbe     short loc_180002DB3
0x180002dad  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
0x180002db3  cmp     [rbx+18h], rdi
0x180002db7  jnb     short loc_180002DC6
0x180002db9  mov     rdx, rdi
0x180002dbc  mov     rcx, rbx; Src
0x180002dbf  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180002dc4  jmp     short loc_180002DE4
0x180002dc6  test    rdi, rdi
0x180002dc9  jnz     short loc_180002DE9
0x180002dcb  mov     [rbx+10h], r12
0x180002dcf  cmp     qword ptr [rbx+18h], 8
0x180002dd4  jb      short loc_180002DDB
0x180002dd6  mov     rax, [rbx]
0x180002dd9  jmp     short loc_180002DDE
0x180002ddb  mov     rax, rbx
0x180002dde  mov     [rax], r12w
0x180002de2  jmp     short loc_180002E33
0x180002de4  test    rdi, rdi
0x180002de7  jz      short loc_180002E33
0x180002de9  cmp     qword ptr [r15+18h], 8
0x180002dee  jb      short loc_180002DF3
0x180002df0  mov     r15, [r15]
0x180002df3  cmp     qword ptr [rbx+18h], 8
0x180002df8  jb      short loc_180002DFF
0x180002dfa  mov     rcx, [rbx]
0x180002dfd  jmp     short loc_180002E02
0x180002dff  mov     rcx, rbx
0x180002e02  test    rsi, rsi
0x180002e05  jz      short loc_180002E1B
0x180002e07  lea     r8, [rsi+rsi]; Size
0x180002e0b  mov     rax, [rbx+10h]
0x180002e0f  lea     rcx, [rcx+rax*2]; void *
0x180002e13  mov     rdx, r15; Src
0x180002e16  call    memcpy_0
0x180002e1b  mov     [rbx+10h], rdi
0x180002e1f  cmp     qword ptr [rbx+18h], 8
0x180002e24  jb      short loc_180002E2B
0x180002e26  mov     rax, [rbx]
0x180002e29  jmp     short loc_180002E2E
0x180002e2b  mov     rax, rbx
0x180002e2e  mov     [rax+rdi*2], r12w
0x180002e33  cmp     qword ptr [rbp+10h], 0FFFFFFFFFFFFFFFFh
0x180002e38  cmovb   r14, [rbp+10h]
0x180002e3d  mov     r8, [rbx+10h]
0x180002e41  mov     rax, r8
0x180002e44  not     rax
0x180002e47  cmp     rax, r14
0x180002e4a  ja      short loc_180002E52
0x180002e4c  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
0x180002e52  lea     rdi, [r14+r8]
0x180002e56  test    r14, r14
0x180002e59  jz      loc_180002EEB
0x180002e5f  cmp     rdi, r13
0x180002e62  jbe     short loc_180002E6A
0x180002e64  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
0x180002e6a  cmp     [rbx+18h], rdi
0x180002e6e  jnb     short loc_180002E7D
0x180002e70  mov     rdx, rdi
0x180002e73  mov     rcx, rbx; Src
0x180002e76  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180002e7b  jmp     short loc_180002E9B
0x180002e7d  test    rdi, rdi
0x180002e80  jnz     short loc_180002EA0
0x180002e82  mov     [rbx+10h], r12
0x180002e86  cmp     qword ptr [rbx+18h], 8
0x180002e8b  jb      short loc_180002E92
0x180002e8d  mov     rax, [rbx]
0x180002e90  jmp     short loc_180002E95
0x180002e92  mov     rax, rbx
0x180002e95  mov     [rax], r12w
0x180002e99  jmp     short loc_180002EEB
0x180002e9b  test    rdi, rdi
0x180002e9e  jz      short loc_180002EEB
0x180002ea0  cmp     qword ptr [rbp+18h], 8
0x180002ea5  jb      short loc_180002EAB
0x180002ea7  mov     rbp, [rbp+0]
0x180002eab  cmp     qword ptr [rbx+18h], 8
0x180002eb0  jb      short loc_180002EB7
0x180002eb2  mov     rcx, [rbx]
0x180002eb5  jmp     short loc_180002EBA
0x180002eb7  mov     rcx, rbx
0x180002eba  test    r14, r14
0x180002ebd  jz      short loc_180002ED3
0x180002ebf  lea     r8, [r14+r14]; Size
0x180002ec3  mov     rax, [rbx+10h]
0x180002ec7  lea     rcx, [rcx+rax*2]; void *
0x180002ecb  mov     rdx, rbp; Src
0x180002ece  call    memcpy_0
0x180002ed3  mov     [rbx+10h], rdi
0x180002ed7  cmp     qword ptr [rbx+18h], 8
0x180002edc  jb      short loc_180002EE3
0x180002ede  mov     rax, [rbx]
0x180002ee1  jmp     short loc_180002EE6
0x180002ee3  mov     rax, rbx
0x180002ee6  mov     [rax+rdi*2], r12w
0x180002eeb  mov     rax, rbx
0x180002eee  mov     rbx, [rsp+58h+arg_8]
0x180002ef3  mov     rbp, [rsp+58h+arg_10]
0x180002ef8  mov     rsi, [rsp+58h+arg_18]
0x180002efd  add     rsp, 30h
0x180002f01  pop     r15
0x180002f03  pop     r14
0x180002f05  pop     r13
0x180002f07  pop     r12
0x180002f09  pop     rdi
0x180002f0a  retn
```
