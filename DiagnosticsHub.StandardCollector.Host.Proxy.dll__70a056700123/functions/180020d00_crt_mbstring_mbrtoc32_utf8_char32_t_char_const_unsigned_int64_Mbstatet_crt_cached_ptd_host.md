# __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x180020d00`
- end: `0x180020ebd`
- name: `?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `445`
- prototype: `unsigned __int64(__crt_mbstring *__hidden this, char32_t *, const char *, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001b468`
- `0x18001b4b0`
- `0x180020ec0`

## callees

- `0x180020cc8`
- `0x180020d00`
- `0x180021adc`
- `0x180021ae4`
- `0x180032370`

## pseudocode

```c
unsigned __int64 __fastcall __crt_mbstring::__mbrtoc32_utf8(
        unsigned __int64 this,
        char32_t *a2,
        unsigned __int64 a3,
        __int64 *a4,
        struct _Mbstatet *a5)
{
  __int64 *v5; // rbx
  __crt_mbstring *v6; // rdi
  unsigned __int64 v8; // rbp
  _DWORD *v9; // r14
  int v11; // eax
  unsigned __int8 v12; // r9
  unsigned int v13; // edx
  unsigned __int64 v14; // r10
  char v15; // cl
  _DWORD v16[6]; // [rsp+18h] [rbp-60h]

  v5 = &qword_180079030;
  v6 = (__crt_mbstring *)&qword_180069970;
  if ( a4 )
    v5 = a4;
  v8 = 1;
  if ( a2 )
  {
    v8 = a3;
    v6 = (__crt_mbstring *)a2;
  }
  v9 = (_DWORD *)(this & -(__int64)(a2 != 0));
  if ( !v8 )
    return -2;
  if ( *((_WORD *)v5 + 3) )
  {
    LOBYTE(a3) = *((_BYTE *)v5 + 4);
    v13 = *(_DWORD *)v5;
    v12 = *((_BYTE *)v5 + 6);
    if ( (unsigned __int8)(a3 - 2) > 2u || !v12 || v12 >= (unsigned __int8)a3 )
      return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
    goto LABEL_17;
  }
  a3 = (int)__crt_mbstring::__mblen_utf8(v6, (const char *)a2);
  v11 = *(unsigned __int8 *)v6;
  v6 = (__crt_mbstring *)((char *)v6 + 1);
  if ( (unsigned int)a3 > 1 )
  {
    if ( (unsigned int)(a3 - 2) > 2 )
      return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
    v12 = a3;
    v13 = v11 & ((1 << (7 - a3)) - 1);
LABEL_17:
    v14 = v12;
    if ( v12 >= v8 )
      v14 = v8;
    while ( v6 - (__crt_mbstring *)a2 < v14 )
    {
      v15 = *(_BYTE *)v6;
      v6 = (__crt_mbstring *)((char *)v6 + 1);
      if ( (v15 & 0xC0) != 0x80 )
        return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
      v13 = (v13 << 6) | v15 & 0x3F;
    }
    if ( v14 < v12 )
    {
      *((_WORD *)v5 + 2) = (unsigned __int8)a3;
      *((_WORD *)v5 + 3) = (unsigned __int8)(v12 - v14);
      *(_DWORD *)v5 = v13;
      return -2;
    }
    if ( v13 - 55296 > 0x7FF && v13 < 0x110000 )
    {
      v16[2] = 128;
      v16[3] = 2048;
      v16[4] = 0x10000;
      if ( v13 >= v16[(unsigned __int8)a3] )
      {
        if ( v9 )
          *v9 = v13;
        return __crt_mbstring::reset_and_return(
                 (__crt_mbstring *)(v12 & (unsigned __int64)-(__int64)(v13 != 0)),
                 (unsigned __int64)v5,
                 (struct _Mbstatet *)a3);
      }
    }
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
  }
  if ( v9 )
    *v9 = v11;
  return a3;
}

```

## disassembly

```asm
0x180020d00  push    rbx
0x180020d02  push    rbp
0x180020d03  push    rsi
0x180020d04  push    rdi
0x180020d05  push    r12
0x180020d07  push    r14
0x180020d09  push    r15
0x180020d0b  sub     rsp, 40h
0x180020d0f  mov     rax, cs:__security_cookie
0x180020d16  xor     rax, rsp
0x180020d19  mov     [rsp+78h+var_48], rax
0x180020d1e  mov     rsi, [rsp+78h+arg_20]
0x180020d26  lea     rbx, qword_180079030
0x180020d2d  xor     r12d, r12d
0x180020d30  lea     rdi, qword_180069970
0x180020d37  test    r9, r9
0x180020d3a  mov     rax, rdx
0x180020d3d  mov     r15, rdx
0x180020d40  cmovnz  rbx, r9
0x180020d44  test    rdx, rdx
0x180020d47  lea     ebp, [r12+1]
0x180020d4c  cmovnz  rbp, r8
0x180020d50  cmovnz  rdi, rdx
0x180020d54  neg     rax
0x180020d57  sbb     r14, r14
0x180020d5a  and     r14, rcx
0x180020d5d  test    rbp, rbp
0x180020d60  jnz     short loc_180020D6E
0x180020d62  mov     rax, 0FFFFFFFFFFFFFFFEh
0x180020d69  jmp     loc_180020EA1
0x180020d6e  cmp     [rbx+6], r12w
0x180020d73  jnz     short loc_180020DC4
0x180020d75  mov     rcx, rdi; this
0x180020d78  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x180020d7d  movsxd  r8, eax; struct __crt_cached_ptd_host *
0x180020d80  movzx   eax, byte ptr [rdi]
0x180020d83  inc     rdi
0x180020d86  cmp     r8d, 1
0x180020d8a  jbe     short loc_180020DB4
0x180020d8c  lea     ecx, [r8-2]
0x180020d90  cmp     ecx, 2
0x180020d93  ja      loc_180020E96
0x180020d99  movzx   edx, r8b
0x180020d9d  mov     ecx, 7
0x180020da2  sub     ecx, edx
0x180020da4  mov     r9b, r8b
0x180020da7  mov     edx, 1
0x180020dac  shl     edx, cl
0x180020dae  dec     edx
0x180020db0  and     edx, eax
0x180020db2  jmp     short loc_180020DED
0x180020db4  test    r14, r14
0x180020db7  jz      short loc_180020DBC
0x180020db9  mov     [r14], eax
0x180020dbc  mov     rax, r8
0x180020dbf  jmp     loc_180020EA1
0x180020dc4  mov     r8b, [rbx+4]; struct _Mbstatet *
0x180020dc8  mov     edx, [rbx]
0x180020dca  mov     r9b, [rbx+6]
0x180020dce  lea     eax, [r8-2]
0x180020dd2  cmp     al, 2
0x180020dd4  ja      loc_180020E96
0x180020dda  cmp     r9b, 1
0x180020dde  jb      loc_180020E96
0x180020de4  cmp     r9b, r8b
0x180020de7  jnb     loc_180020E96
0x180020ded  movzx   r11d, r9b
0x180020df1  cmp     r11, rbp
0x180020df4  mov     r10d, r11d
0x180020df7  cmovnb  r10, rbp
0x180020dfb  jmp     short loc_180020E1B
0x180020dfd  movzx   ecx, byte ptr [rdi]
0x180020e00  inc     rdi
0x180020e03  mov     al, cl
0x180020e05  and     al, 0C0h
0x180020e07  cmp     al, 80h
0x180020e09  jnz     loc_180020E96
0x180020e0f  mov     eax, edx
0x180020e11  and     ecx, 3Fh
0x180020e14  shl     eax, 6
0x180020e17  mov     edx, ecx
0x180020e19  or      edx, eax
0x180020e1b  mov     rax, rdi
0x180020e1e  sub     rax, r15
0x180020e21  cmp     rax, r10
0x180020e24  jb      short loc_180020DFD
0x180020e26  cmp     r10, r11
0x180020e29  jnb     short loc_180020E45
0x180020e2b  movzx   eax, r8b
0x180020e2f  sub     r9b, r10b
0x180020e32  mov     [rbx+4], ax
0x180020e36  movzx   eax, r9b
0x180020e3a  mov     [rbx+6], ax
0x180020e3e  mov     [rbx], edx
0x180020e40  jmp     loc_180020D62
0x180020e45  lea     eax, [rdx-0D800h]
0x180020e4b  cmp     eax, 7FFh
0x180020e50  jbe     short loc_180020E96
0x180020e52  cmp     edx, 110000h
0x180020e58  jnb     short loc_180020E96
0x180020e5a  movzx   eax, r8b
0x180020e5e  mov     [rsp+78h+var_58], 80h
0x180020e66  mov     [rsp+78h+var_54], 800h
0x180020e6e  mov     [rsp+78h+var_50], 10000h
0x180020e76  cmp     edx, [rsp+rax*4+78h+var_60]
0x180020e7a  jb      short loc_180020E96
0x180020e7c  test    r14, r14
0x180020e7f  jz      short loc_180020E84
0x180020e81  mov     [r14], edx
0x180020e84  neg     edx
0x180020e86  mov     rdx, rbx; unsigned __int64
0x180020e89  sbb     rcx, rcx
0x180020e8c  and     rcx, r11; this
0x180020e8f  call    ?reset_and_return@__crt_mbstring@@YA_K_KPEAU_Mbstatet@@@Z; __crt_mbstring::reset_and_return(unsigned __int64,_Mbstatet *)
0x180020e94  jmp     short loc_180020EA1
0x180020e96  mov     rdx, rsi; struct _Mbstatet *
0x180020e99  mov     rcx, rbx; this
0x180020e9c  call    ?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::return_illegal_sequence(_Mbstatet *,__crt_cached_ptd_host &)
0x180020ea1  mov     rcx, [rsp+78h+var_48]
0x180020ea6  xor     rcx, rsp; StackCookie
0x180020ea9  call    __security_check_cookie
0x180020eae  add     rsp, 40h
0x180020eb2  pop     r15
0x180020eb4  pop     r14
0x180020eb6  pop     r12
0x180020eb8  pop     rdi
0x180020eb9  pop     rsi
0x180020eba  pop     rbp
0x180020ebb  pop     rbx
0x180020ebc  retn
```
