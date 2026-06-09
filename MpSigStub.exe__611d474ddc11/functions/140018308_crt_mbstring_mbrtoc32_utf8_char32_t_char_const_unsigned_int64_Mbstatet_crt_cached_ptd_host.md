# __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x140018308`
- end: `0x1400184e1`
- name: `?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `473`
- prototype: `unsigned __int64 __fastcall(unsigned __int64 this, char32_t *, unsigned __int64, __int64 *, struct _Mbstatet *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001511c`
- `0x140015164`

## callees

- `0x140018308`
- `0x1400184e4`
- `0x1400184ec`
- `0x14001bf00`

## pseudocode

```c
unsigned __int64 __fastcall __crt_mbstring::__mbrtoc32_utf8(
        unsigned __int64 this,
        char32_t *a2,
        unsigned __int64 a3,
        __int64 *a4,
        struct _Mbstatet *a5)
{
  __int64 *v5; // r10
  __int64 v6; // r11
  char *v7; // rdi
  unsigned __int64 v9; // r15
  _DWORD *v10; // r14
  int v12; // r9d
  unsigned __int8 v13; // bl
  unsigned int v14; // edx
  unsigned __int64 v15; // r9
  char v16; // cl
  _DWORD v17[6]; // [rsp+18h] [rbp-60h]

  v5 = &qword_1400D7268;
  v6 = 0;
  v7 = byte_1400BC14D;
  if ( a4 )
    v5 = a4;
  if ( a2 )
    v7 = (char *)a2;
  v9 = 1;
  if ( a2 )
    v9 = a3;
  v10 = (_DWORD *)(this & -(__int64)(a2 != 0));
  if ( !v9 )
    return -2;
  if ( !*((_WORD *)v5 + 3) )
  {
    v12 = (unsigned __int8)*v7++;
    if ( (v12 & 0x80u) == 0 )
    {
      if ( v10 )
        *v10 = v12;
      LOBYTE(v6) = (_BYTE)v12 != 0;
      return v6;
    }
    if ( (v12 & 0xE0) == 0xC0 )
    {
      LOBYTE(a3) = 2;
LABEL_20:
      v13 = a3;
      v14 = v12 & ((1 << (7 - a3)) - 1);
      goto LABEL_24;
    }
    if ( (v12 & 0xF0) == 0xE0 )
    {
      LOBYTE(a3) = 3;
      goto LABEL_20;
    }
    if ( (v12 & 0xF8) == 0xF0 )
    {
      LOBYTE(a3) = 4;
      goto LABEL_20;
    }
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
  }
  LOBYTE(a3) = *((_BYTE *)v5 + 4);
  v14 = *(_DWORD *)v5;
  v13 = *((_BYTE *)v5 + 6);
  if ( (unsigned __int8)(a3 - 2) > 2u || !v13 || v13 >= (unsigned __int8)a3 )
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
LABEL_24:
  v15 = v13;
  if ( v13 >= v9 )
    v15 = v9;
  while ( v7 - (char *)a2 < v15 )
  {
    v16 = *v7++;
    if ( (v16 & 0xC0) != 0x80 )
      return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
    v14 = (v14 << 6) | v16 & 0x3F;
  }
  if ( v15 < v13 )
  {
    *((_WORD *)v5 + 2) = (unsigned __int8)a3;
    *((_WORD *)v5 + 3) = (unsigned __int8)(v13 - v15);
    *(_DWORD *)v5 = v14;
    return -2;
  }
  if ( v14 - 55296 <= 0x7FF )
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
  if ( v14 >= 0x110000 )
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
  v17[2] = 128;
  v17[3] = 2048;
  v17[4] = 0x10000;
  if ( v14 < v17[(unsigned __int8)a3] )
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, (struct __crt_cached_ptd_host *)a3);
  if ( v10 )
    *v10 = v14;
  return __crt_mbstring::reset_and_return(
           (__crt_mbstring *)(v13 & (unsigned __int64)-(__int64)(v14 != 0)),
           (unsigned __int64)v5,
           (struct _Mbstatet *)a3);
}

```

## disassembly

```asm
0x140018308  push    rbx
0x14001830a  push    rbp
0x14001830b  push    rsi
0x14001830c  push    rdi
0x14001830d  push    r12
0x14001830f  push    r14
0x140018311  push    r15
0x140018313  sub     rsp, 40h
0x140018317  mov     rax, cs:__security_cookie
0x14001831e  xor     rax, rsp
0x140018321  mov     [rsp+78h+var_48], rax
0x140018326  mov     rsi, [rsp+78h+arg_20]
0x14001832e  lea     r10, qword_1400D7268
0x140018335  xor     r11d, r11d
0x140018338  lea     rdi, byte_1400BC14D
0x14001833f  test    r9, r9
0x140018342  mov     rax, rdx
0x140018345  mov     r12, rdx
0x140018348  cmovnz  r10, r9
0x14001834c  test    rdx, rdx
0x14001834f  lea     ebp, [r11+1]
0x140018353  cmovnz  rdi, rdx
0x140018357  mov     r15d, ebp
0x14001835a  cmovnz  r15, r8
0x14001835e  neg     rax
0x140018361  sbb     r14, r14
0x140018364  and     r14, rcx
0x140018367  test    r15, r15
0x14001836a  jnz     short loc_140018378
0x14001836c  mov     rax, 0FFFFFFFFFFFFFFFEh
0x140018373  jmp     loc_1400184C5
0x140018378  cmp     [r10+6], r11w
0x14001837d  jnz     short loc_1400183E7
0x14001837f  movzx   r9d, byte ptr [rdi]
0x140018383  inc     rdi
0x140018386  test    r9b, r9b
0x140018389  js      short loc_1400183A2
0x14001838b  test    r14, r14
0x14001838e  jz      short loc_140018393
0x140018390  mov     [r14], r9d
0x140018393  test    r9b, r9b
0x140018396  setnz   r11b
0x14001839a  mov     rax, r11
0x14001839d  jmp     loc_1400184C5
0x1400183a2  mov     al, r9b
0x1400183a5  and     al, 0E0h
0x1400183a7  cmp     al, 0C0h
0x1400183a9  jnz     short loc_1400183B0
0x1400183ab  mov     r8b, 2
0x1400183ae  jmp     short loc_1400183CE
0x1400183b0  mov     al, r9b
0x1400183b3  and     al, 0F0h
0x1400183b5  cmp     al, 0E0h
0x1400183b7  jnz     short loc_1400183BE
0x1400183b9  mov     r8b, 3
0x1400183bc  jmp     short loc_1400183CE
0x1400183be  mov     al, r9b
0x1400183c1  and     al, 0F8h
0x1400183c3  cmp     al, 0F0h
0x1400183c5  jnz     loc_1400184BA
0x1400183cb  mov     r8b, 4
0x1400183ce  movzx   eax, r8b
0x1400183d2  mov     ecx, 7
0x1400183d7  sub     ecx, eax
0x1400183d9  mov     edx, ebp
0x1400183db  shl     edx, cl
0x1400183dd  mov     bl, r8b
0x1400183e0  sub     edx, ebp
0x1400183e2  and     edx, r9d
0x1400183e5  jmp     short loc_140018410
0x1400183e7  mov     r8b, [r10+4]; struct _Mbstatet *
0x1400183eb  mov     edx, [r10]
0x1400183ee  mov     bl, [r10+6]
0x1400183f2  lea     eax, [r8-2]
0x1400183f6  cmp     al, 2
0x1400183f8  ja      loc_1400184BA
0x1400183fe  cmp     bl, bpl
0x140018401  jb      loc_1400184BA
0x140018407  cmp     bl, r8b
0x14001840a  jnb     loc_1400184BA
0x140018410  movzx   ebp, bl
0x140018413  cmp     rbp, r15
0x140018416  mov     r9d, ebp
0x140018419  cmovnb  r9, r15
0x14001841d  jmp     short loc_14001843D
0x14001841f  movzx   ecx, byte ptr [rdi]
0x140018422  inc     rdi
0x140018425  mov     al, cl
0x140018427  and     al, 0C0h
0x140018429  cmp     al, 80h
0x14001842b  jnz     loc_1400184BA
0x140018431  mov     eax, edx
0x140018433  and     ecx, 3Fh
0x140018436  shl     eax, 6
0x140018439  mov     edx, ecx
0x14001843b  or      edx, eax
0x14001843d  mov     rax, rdi
0x140018440  sub     rax, r12
0x140018443  cmp     rax, r9
0x140018446  jb      short loc_14001841F
0x140018448  cmp     r9, rbp
0x14001844b  jnb     short loc_140018469
0x14001844d  movzx   eax, r8b
0x140018451  sub     bl, r9b
0x140018454  mov     [r10+4], ax
0x140018459  movzx   eax, bl
0x14001845c  mov     [r10+6], ax
0x140018461  mov     [r10], edx
0x140018464  jmp     loc_14001836C
0x140018469  lea     eax, [rdx-0D800h]
0x14001846f  cmp     eax, 7FFh
0x140018474  jbe     short loc_1400184BA
0x140018476  cmp     edx, 110000h
0x14001847c  jnb     short loc_1400184BA
0x14001847e  movzx   eax, r8b
0x140018482  mov     [rsp+78h+var_58], 80h
0x14001848a  mov     [rsp+78h+var_54], 800h
0x140018492  mov     [rsp+78h+var_50], 10000h
0x14001849a  cmp     edx, [rsp+rax*4+78h+var_60]
0x14001849e  jb      short loc_1400184BA
0x1400184a0  test    r14, r14
0x1400184a3  jz      short loc_1400184A8
0x1400184a5  mov     [r14], edx
0x1400184a8  neg     edx
0x1400184aa  mov     rdx, r10; unsigned __int64
0x1400184ad  sbb     rcx, rcx
0x1400184b0  and     rcx, rbp; this
0x1400184b3  call    ?reset_and_return@__crt_mbstring@@YA_K_KPEAU_Mbstatet@@@Z
0x1400184b8  jmp     short loc_1400184C5
0x1400184ba  mov     rdx, rsi; struct _Mbstatet *
0x1400184bd  mov     rcx, r10; this
0x1400184c0  call    ?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z
0x1400184c5  mov     rcx, [rsp+78h+var_48]
0x1400184ca  xor     rcx, rsp; StackCookie
0x1400184cd  call    __security_check_cookie
0x1400184d2  add     rsp, 40h
0x1400184d6  pop     r15
0x1400184d8  pop     r14
0x1400184da  pop     r12
0x1400184dc  pop     rdi
0x1400184dd  pop     rsi
0x1400184de  pop     rbp
0x1400184df  pop     rbx
0x1400184e0  retn
```
