# __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x180021460`
- end: `0x18002161d`
- name: `?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `445`
- prototype: `unsigned __int64(__crt_mbstring *__hidden this, char32_t *, const char *, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001bbc8`
- `0x18001bc10`
- `0x180021620`

## callees

- `0x180002810`
- `0x180021428`
- `0x180021460`
- `0x18002223c`
- `0x180022244`

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

  v5 = &qword_18007CAE0;
  v6 = (__crt_mbstring *)&qword_18006D050;
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
0x180021460  push    rbx
0x180021462  push    rbp
0x180021463  push    rsi
0x180021464  push    rdi
0x180021465  push    r12
0x180021467  push    r14
0x180021469  push    r15
0x18002146b  sub     rsp, 40h
0x18002146f  mov     rax, cs:__security_cookie
0x180021476  xor     rax, rsp
0x180021479  mov     [rsp+78h+var_48], rax
0x18002147e  mov     rsi, [rsp+78h+arg_20]
0x180021486  lea     rbx, qword_18007CAE0
0x18002148d  xor     r12d, r12d
0x180021490  lea     rdi, qword_18006D050
0x180021497  test    r9, r9
0x18002149a  mov     rax, rdx
0x18002149d  mov     r15, rdx
0x1800214a0  cmovnz  rbx, r9
0x1800214a4  test    rdx, rdx
0x1800214a7  lea     ebp, [r12+1]
0x1800214ac  cmovnz  rbp, r8
0x1800214b0  cmovnz  rdi, rdx
0x1800214b4  neg     rax
0x1800214b7  sbb     r14, r14
0x1800214ba  and     r14, rcx
0x1800214bd  test    rbp, rbp
0x1800214c0  jnz     short loc_1800214CE
0x1800214c2  mov     rax, 0FFFFFFFFFFFFFFFEh
0x1800214c9  jmp     loc_180021601
0x1800214ce  cmp     [rbx+6], r12w
0x1800214d3  jnz     short loc_180021524
0x1800214d5  mov     rcx, rdi; this
0x1800214d8  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x1800214dd  movsxd  r8, eax; struct __crt_cached_ptd_host *
0x1800214e0  movzx   eax, byte ptr [rdi]
0x1800214e3  inc     rdi
0x1800214e6  cmp     r8d, 1
0x1800214ea  jbe     short loc_180021514
0x1800214ec  lea     ecx, [r8-2]
0x1800214f0  cmp     ecx, 2
0x1800214f3  ja      loc_1800215F6
0x1800214f9  movzx   edx, r8b
0x1800214fd  mov     ecx, 7
0x180021502  sub     ecx, edx
0x180021504  mov     r9b, r8b
0x180021507  mov     edx, 1
0x18002150c  shl     edx, cl
0x18002150e  dec     edx
0x180021510  and     edx, eax
0x180021512  jmp     short loc_18002154D
0x180021514  test    r14, r14
0x180021517  jz      short loc_18002151C
0x180021519  mov     [r14], eax
0x18002151c  mov     rax, r8
0x18002151f  jmp     loc_180021601
0x180021524  mov     r8b, [rbx+4]; struct _Mbstatet *
0x180021528  mov     edx, [rbx]
0x18002152a  mov     r9b, [rbx+6]
0x18002152e  lea     eax, [r8-2]
0x180021532  cmp     al, 2
0x180021534  ja      loc_1800215F6
0x18002153a  cmp     r9b, 1
0x18002153e  jb      loc_1800215F6
0x180021544  cmp     r9b, r8b
0x180021547  jnb     loc_1800215F6
0x18002154d  movzx   r11d, r9b
0x180021551  cmp     r11, rbp
0x180021554  mov     r10d, r11d
0x180021557  cmovnb  r10, rbp
0x18002155b  jmp     short loc_18002157B
0x18002155d  movzx   ecx, byte ptr [rdi]
0x180021560  inc     rdi
0x180021563  mov     al, cl
0x180021565  and     al, 0C0h
0x180021567  cmp     al, 80h
0x180021569  jnz     loc_1800215F6
0x18002156f  mov     eax, edx
0x180021571  and     ecx, 3Fh
0x180021574  shl     eax, 6
0x180021577  mov     edx, ecx
0x180021579  or      edx, eax
0x18002157b  mov     rax, rdi
0x18002157e  sub     rax, r15
0x180021581  cmp     rax, r10
0x180021584  jb      short loc_18002155D
0x180021586  cmp     r10, r11
0x180021589  jnb     short loc_1800215A5
0x18002158b  movzx   eax, r8b
0x18002158f  sub     r9b, r10b
0x180021592  mov     [rbx+4], ax
0x180021596  movzx   eax, r9b
0x18002159a  mov     [rbx+6], ax
0x18002159e  mov     [rbx], edx
0x1800215a0  jmp     loc_1800214C2
0x1800215a5  lea     eax, [rdx-0D800h]
0x1800215ab  cmp     eax, 7FFh
0x1800215b0  jbe     short loc_1800215F6
0x1800215b2  cmp     edx, 110000h
0x1800215b8  jnb     short loc_1800215F6
0x1800215ba  movzx   eax, r8b
0x1800215be  mov     [rsp+78h+var_58], 80h
0x1800215c6  mov     [rsp+78h+var_54], 800h
0x1800215ce  mov     [rsp+78h+var_50], 10000h
0x1800215d6  cmp     edx, [rsp+rax*4+78h+var_60]
0x1800215da  jb      short loc_1800215F6
0x1800215dc  test    r14, r14
0x1800215df  jz      short loc_1800215E4
0x1800215e1  mov     [r14], edx
0x1800215e4  neg     edx
0x1800215e6  mov     rdx, rbx; unsigned __int64
0x1800215e9  sbb     rcx, rcx
0x1800215ec  and     rcx, r11; this
0x1800215ef  call    ?reset_and_return@__crt_mbstring@@YA_K_KPEAU_Mbstatet@@@Z; __crt_mbstring::reset_and_return(unsigned __int64,_Mbstatet *)
0x1800215f4  jmp     short loc_180021601
0x1800215f6  mov     rdx, rsi; struct _Mbstatet *
0x1800215f9  mov     rcx, rbx; this
0x1800215fc  call    ?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::return_illegal_sequence(_Mbstatet *,__crt_cached_ptd_host &)
0x180021601  mov     rcx, [rsp+78h+var_48]
0x180021606  xor     rcx, rsp; StackCookie
0x180021609  call    __security_check_cookie
0x18002160e  add     rsp, 40h
0x180021612  pop     r15
0x180021614  pop     r14
0x180021616  pop     r12
0x180021618  pop     rdi
0x180021619  pop     rsi
0x18002161a  pop     rbp
0x18002161b  pop     rbx
0x18002161c  retn
```
