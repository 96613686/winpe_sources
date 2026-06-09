# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x14000de94`
- end: `0x14000e124`
- name: `?replace@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K0PEB_W0@Z`
- size: `656`
- prototype: `char __fastcall(char **, __int64, unsigned __int64, __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14000cfc4`

## callees

- `0x1400023f4`
- `0x140007350`
- `0x14000db78`
- `0x14000de94`
- `0x14001130c`
- `0x140011318`

## pseudocode

```c
char __fastcall utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(
        char **a1,
        __int64 a2,
        unsigned __int64 a3,
        __int16 *a4,
        unsigned __int64 a5)
{
  char *v5; // r13
  unsigned __int64 v8; // r8
  unsigned __int64 v10; // r12
  char v11; // r15
  char *v13; // r10
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  char *v16; // r11
  _WORD *v17; // rdi
  unsigned __int64 v18; // rdx
  _WORD *v19; // rcx
  char v20; // al
  __int16 v21; // ax
  __int64 v22; // r12
  char *v23; // rdi
  void *v24; // r14
  void *v25[2]; // [rsp+20h] [rbp-30h] BYREF
  _WORD *v26; // [rsp+30h] [rbp-20h] BYREF
  _WORD *v27; // [rsp+38h] [rbp-18h]
  _WORD v28[8]; // [rsp+40h] [rbp-10h] BYREF
  char *v29; // [rsp+90h] [rbp+40h]
  char *Src; // [rsp+98h] [rbp+48h]

  v5 = *a1;
  v8 = (unsigned __int64)a1[1];
  if ( (__int64)(v8 - (_QWORD)*a1) >> 1 < a3 )
    a3 = (a1[1] - *a1) >> 1;
  v10 = v8 + 2 * (a5 - a3);
  if ( v10 < (unsigned __int64)v5 )
    return 0;
  v11 = 1;
  v13 = &v5[2 * a3];
  Src = v13;
  if ( v5 == (char *)(a1 + 2) )
    v14 = (unsigned __int64)a1 + 30;
  else
    v14 = (unsigned __int64)a1[2];
  if ( v10 <= v14 )
  {
    v15 = 2 * a5;
    v16 = (char *)&a4[a5];
    v29 = v16;
    if ( v16 <= v5 || v8 < (unsigned __int64)a4 )
    {
      memmove_0(&v5[2 * a5], &v5[2 * a3], 2 * ((__int64)(v8 - (_QWORD)v13) >> 1) + 2);
      memcpy_0(v5, a4, 2 * a5);
      goto LABEL_29;
    }
    if ( a5 <= a3 )
    {
      memmove_0(v5, a4, 2 * a5);
      memmove_0(&v5[2 * a5], Src, 2 * ((a1[1] - Src) >> 1) + 2);
LABEL_29:
      a1[1] = (char *)v10;
      return v11;
    }
    v17 = v28;
    v26 = v28;
    v18 = v15 >> 1;
    v19 = v28;
    v27 = v28;
    v28[0] = 0;
    if ( (unsigned __int64)(v15 >> 1) >= 8 )
    {
      if ( v18 <= 0xF )
      {
        v18 = 15;
      }
      else if ( v18 > 0x3FFFFFFFFFFFFFF7LL )
      {
LABEL_20:
        v11 = 0;
LABEL_26:
        if ( v17 != v28 )
          operator delete(v17, (const struct std::nothrow_t *)&std::nothrow);
        return v11;
      }
      v20 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo((__int64)&v26, v18);
      v17 = v26;
      if ( !v20 )
        goto LABEL_20;
      v19 = v27;
      v13 = Src;
      v16 = v29;
    }
    if ( a4 != (__int16 *)v16 )
    {
      do
      {
        v21 = *a4++;
        *v19 = v21;
        v19 = ++v27;
      }
      while ( a4 != (__int16 *)v16 );
      v17 = v26;
    }
    memmove_0(&v5[2 * a5], v13, 2 * ((a1[1] - v13) >> 1) + 2);
    memcpy_0(v5, v17, 2 * a5);
    a1[1] = (char *)v10;
    goto LABEL_26;
  }
  v22 = (__int64)(v10 - (_QWORD)v5) >> 1;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowAlloc(a1, v25);
  v23 = (char *)v25[0];
  if ( !v25[0] )
    return 0;
  memcpy_0(v25[0], a4, 2 * a5);
  memcpy_0(&v23[2 * a5], Src, 2 * ((a1[1] - Src) >> 1) + 2);
  v24 = v25[1];
  if ( *a1 != (char *)(a1 + 2) )
    operator delete(*a1, (const struct std::nothrow_t *)&std::nothrow);
  *a1 = v23;
  a1[1] = &v23[2 * v22];
  a1[2] = &v23[2 * ((__int64)v24 - 1)];
  return v11;
}

```

## disassembly

```asm
0x14000de94  mov     [rsp-38h+arg_18], rbx
0x14000de99  mov     [rsp-38h+Src], rdx
0x14000de9e  push    rbp
0x14000de9f  push    rsi
0x14000dea0  push    rdi
0x14000dea1  push    r12
0x14000dea3  push    r13
0x14000dea5  push    r14
0x14000dea7  push    r15
0x14000dea9  mov     rbp, rsp
0x14000deac  sub     rsp, 50h
0x14000deb0  mov     r13, [rcx]
0x14000deb3  mov     r14, r9
0x14000deb6  mov     rbx, [rbp+arg_20]
0x14000deba  mov     r9, r8
0x14000debd  mov     r8, [rcx+8]
0x14000dec1  mov     rsi, rcx
0x14000dec4  mov     rax, r8
0x14000dec7  sub     rax, r13
0x14000deca  sar     rax, 1
0x14000decd  cmp     rax, r9
0x14000ded0  cmovb   r9, rax
0x14000ded4  mov     rax, rbx
0x14000ded7  sub     rax, r9
0x14000deda  lea     r12, [r8+rax*2]
0x14000dede  cmp     r12, r13
0x14000dee1  jnb     short loc_14000DF03
0x14000dee3  xor     ebx, ebx
0x14000dee5  mov     r15b, bl
0x14000dee8  mov     rbx, [rsp+50h+arg_18]
0x14000def0  mov     al, r15b
0x14000def3  add     rsp, 50h
0x14000def7  pop     r15
0x14000def9  pop     r14
0x14000defb  pop     r13
0x14000defd  pop     r12
0x14000deff  pop     rdi
0x14000df00  pop     rsi
0x14000df01  pop     rbp
0x14000df02  retn
0x14000df03  lea     r10, ds:0[r9*2]
0x14000df0b  mov     r15b, 1
0x14000df0e  add     r10, r13
0x14000df11  lea     rax, [rcx+10h]
0x14000df15  mov     [rbp+Src], r10
0x14000df19  cmp     r13, rax
0x14000df1c  jnz     short loc_14000DF24
0x14000df1e  lea     rax, [rcx+1Eh]
0x14000df22  jmp     short loc_14000DF27
0x14000df24  mov     rax, [rax]
0x14000df27  cmp     r12, rax
0x14000df2a  ja      loc_14000E098
0x14000df30  lea     rax, [rbx+rbx]
0x14000df34  lea     r11, [rax+r14]
0x14000df38  mov     [rbp+arg_0], r11
0x14000df3c  lea     rdi, [rax+r13]
0x14000df40  mov     [rbp+arg_10], rdi
0x14000df44  cmp     r11, r13
0x14000df47  jbe     loc_14000E067
0x14000df4d  cmp     r8, r14
0x14000df50  jb      loc_14000E067
0x14000df56  cmp     rbx, r9
0x14000df59  ja      short loc_14000DF8C
0x14000df5b  mov     r8, rax; Size
0x14000df5e  mov     rdx, r14; Src
0x14000df61  mov     rcx, r13; void *
0x14000df64  call    memmove_0
0x14000df69  mov     r8, [rsi+8]
0x14000df6d  mov     rcx, rdi; void *
0x14000df70  mov     rdx, [rbp+Src]; Src
0x14000df74  sub     r8, rdx
0x14000df77  sar     r8, 1
0x14000df7a  lea     r8, ds:2[r8*2]; Size
0x14000df82  call    memmove_0
0x14000df87  jmp     loc_14000E08F
0x14000df8c  xor     ebx, ebx
0x14000df8e  lea     rdi, [rbp+var_10]
0x14000df92  mov     rdx, rax
0x14000df95  mov     [rbp+var_20], rdi
0x14000df99  sar     rdx, 1
0x14000df9c  lea     rcx, [rbp+var_10]
0x14000dfa0  mov     [rbp+var_18], rcx
0x14000dfa4  mov     [rbp+var_10], bx
0x14000dfa8  cmp     rdx, 8
0x14000dfac  jb      short loc_14000DFEC
0x14000dfae  cmp     rdx, 0Fh
0x14000dfb2  jbe     short loc_14000DFC5
0x14000dfb4  mov     rax, 3FFFFFFFFFFFFFF7h
0x14000dfbe  cmp     rdx, rax
0x14000dfc1  ja      short loc_14000DFDB
0x14000dfc3  jmp     short loc_14000DFCA
0x14000dfc5  mov     edx, 0Fh
0x14000dfca  lea     rcx, [rbp+var_20]
0x14000dfce  call    ?_GrowTo@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(unsigned __int64)
0x14000dfd3  mov     rdi, [rbp+var_20]
0x14000dfd7  test    al, al
0x14000dfd9  jnz     short loc_14000DFE0
0x14000dfdb  mov     r15b, bl
0x14000dfde  jmp     short loc_14000E046
0x14000dfe0  mov     rcx, [rbp+var_18]
0x14000dfe4  mov     r10, [rbp+Src]
0x14000dfe8  mov     r11, [rbp+arg_0]
0x14000dfec  cmp     r14, r11
0x14000dfef  jz      short loc_14000E011
0x14000dff1  movzx   eax, word ptr [r14]
0x14000dff5  add     r14, 2
0x14000dff9  mov     [rcx], ax
0x14000dffc  mov     rcx, [rbp+var_18]
0x14000e000  add     rcx, 2
0x14000e004  mov     [rbp+var_18], rcx
0x14000e008  cmp     r14, r11
0x14000e00b  jnz     short loc_14000DFF1
0x14000e00d  mov     rdi, [rbp+var_20]
0x14000e011  mov     r8, [rsi+8]
0x14000e015  mov     rdx, r10; Src
0x14000e018  mov     rcx, [rbp+arg_10]; void *
0x14000e01c  sub     r8, r10
0x14000e01f  sar     r8, 1
0x14000e022  lea     r8, ds:2[r8*2]; Size
0x14000e02a  call    memmove_0
0x14000e02f  mov     rbx, [rbp+arg_20]
0x14000e033  mov     rdx, rdi; Src
0x14000e036  mov     rcx, r13; void *
0x14000e039  lea     r8, [rbx+rbx]; Size
0x14000e03d  call    memcpy_0
0x14000e042  mov     [rsi+8], r12
0x14000e046  lea     rax, [rbp+var_10]
0x14000e04a  cmp     rdi, rax
0x14000e04d  jz      loc_14000DEE8
0x14000e053  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e05a  mov     rcx, rdi; void *
0x14000e05d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e062  jmp     loc_14000DEE8
0x14000e067  sub     r8, r10
0x14000e06a  mov     rdx, r10; Src
0x14000e06d  sar     r8, 1
0x14000e070  mov     rcx, rdi; void *
0x14000e073  lea     r8, ds:2[r8*2]; Size
0x14000e07b  call    memmove_0
0x14000e080  lea     r8, [rbx+rbx]; Size
0x14000e084  mov     rdx, r14; Src
0x14000e087  mov     rcx, r13; void *
0x14000e08a  call    memcpy_0
0x14000e08f  mov     [rsi+8], r12
0x14000e093  jmp     loc_14000DEE8
0x14000e098  sub     r12, r13
0x14000e09b  lea     rdx, [rbp+var_30]
0x14000e09f  sar     r12, 1
0x14000e0a2  mov     r8, r12
0x14000e0a5  call    ?_GrowAlloc@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA?AU?$pair@PEA_W_K@2@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowAlloc(unsigned __int64)
0x14000e0aa  mov     rdi, [rbp+var_30]
0x14000e0ae  xor     ebx, ebx
0x14000e0b0  test    rdi, rdi
0x14000e0b3  jz      loc_14000DEE5
0x14000e0b9  mov     rbx, [rbp+arg_20]
0x14000e0bd  mov     rdx, r14; Src
0x14000e0c0  add     rbx, rbx
0x14000e0c3  mov     rcx, rdi; void *
0x14000e0c6  mov     r8, rbx; Size
0x14000e0c9  call    memcpy_0
0x14000e0ce  mov     r8, [rsi+8]
0x14000e0d2  lea     rcx, [rbx+rdi]; void *
0x14000e0d6  mov     rdx, [rbp+Src]; Src
0x14000e0da  sub     r8, rdx
0x14000e0dd  sar     r8, 1
0x14000e0e0  lea     r8, ds:2[r8*2]; Size
0x14000e0e8  call    memcpy_0
0x14000e0ed  mov     r14, [rbp+var_28]
0x14000e0f1  lea     rbx, [rsi+10h]
0x14000e0f5  cmp     [rsi], rbx
0x14000e0f8  jz      short loc_14000E109
0x14000e0fa  mov     rcx, [rsi]; void *
0x14000e0fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e104  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e109  lea     rax, [rdi+r12*2]
0x14000e10d  mov     [rsi], rdi
0x14000e110  mov     [rsi+8], rax
0x14000e114  lea     rax, [r14-1]
0x14000e118  lea     rax, [rdi+rax*2]
0x14000e11c  mov     [rbx], rax
0x14000e11f  jmp     loc_14000DEE8
```
