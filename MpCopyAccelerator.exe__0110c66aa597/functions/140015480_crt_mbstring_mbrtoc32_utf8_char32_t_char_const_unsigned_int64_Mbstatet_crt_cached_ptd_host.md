# __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x140015480`
- end: `0x14001563d`
- name: `?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `445`
- prototype: `unsigned __int64(__crt_mbstring *__hidden this, char32_t *, const char *, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400156e4`
- `0x14001572c`

## callees

- `0x140005c20`
- `0x140015448`
- `0x140015480`
- `0x140019df4`
- `0x140019dfc`

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

  v5 = &qword_14003CF98;
  v6 = (__crt_mbstring *)byte_140035928;
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
0x140015480  push    rbx
0x140015482  push    rbp
0x140015483  push    rsi
0x140015484  push    rdi
0x140015485  push    r12
0x140015487  push    r14
0x140015489  push    r15
0x14001548b  sub     rsp, 40h
0x14001548f  mov     rax, cs:__security_cookie
0x140015496  xor     rax, rsp
0x140015499  mov     [rsp+78h+var_48], rax
0x14001549e  mov     rsi, [rsp+78h+arg_20]
0x1400154a6  lea     rbx, qword_14003CF98
0x1400154ad  xor     r12d, r12d
0x1400154b0  lea     rdi, byte_140035928
0x1400154b7  test    r9, r9
0x1400154ba  mov     rax, rdx
0x1400154bd  mov     r15, rdx
0x1400154c0  cmovnz  rbx, r9
0x1400154c4  test    rdx, rdx
0x1400154c7  lea     ebp, [r12+1]
0x1400154cc  cmovnz  rbp, r8
0x1400154d0  cmovnz  rdi, rdx
0x1400154d4  neg     rax
0x1400154d7  sbb     r14, r14
0x1400154da  and     r14, rcx
0x1400154dd  test    rbp, rbp
0x1400154e0  jnz     short loc_1400154EE
0x1400154e2  mov     rax, 0FFFFFFFFFFFFFFFEh
0x1400154e9  jmp     loc_140015621
0x1400154ee  cmp     [rbx+6], r12w
0x1400154f3  jnz     short loc_140015544
0x1400154f5  mov     rcx, rdi; this
0x1400154f8  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x1400154fd  movsxd  r8, eax; struct __crt_cached_ptd_host *
0x140015500  movzx   eax, byte ptr [rdi]
0x140015503  inc     rdi
0x140015506  cmp     r8d, 1
0x14001550a  jbe     short loc_140015534
0x14001550c  lea     ecx, [r8-2]
0x140015510  cmp     ecx, 2
0x140015513  ja      loc_140015616
0x140015519  movzx   edx, r8b
0x14001551d  mov     ecx, 7
0x140015522  sub     ecx, edx
0x140015524  mov     r9b, r8b
0x140015527  mov     edx, 1
0x14001552c  shl     edx, cl
0x14001552e  dec     edx
0x140015530  and     edx, eax
0x140015532  jmp     short loc_14001556D
0x140015534  test    r14, r14
0x140015537  jz      short loc_14001553C
0x140015539  mov     [r14], eax
0x14001553c  mov     rax, r8
0x14001553f  jmp     loc_140015621
0x140015544  mov     r8b, [rbx+4]; struct _Mbstatet *
0x140015548  mov     edx, [rbx]
0x14001554a  mov     r9b, [rbx+6]
0x14001554e  lea     eax, [r8-2]
0x140015552  cmp     al, 2
0x140015554  ja      loc_140015616
0x14001555a  cmp     r9b, 1
0x14001555e  jb      loc_140015616
0x140015564  cmp     r9b, r8b
0x140015567  jnb     loc_140015616
0x14001556d  movzx   r11d, r9b
0x140015571  cmp     r11, rbp
0x140015574  mov     r10d, r11d
0x140015577  cmovnb  r10, rbp
0x14001557b  jmp     short loc_14001559B
0x14001557d  movzx   ecx, byte ptr [rdi]
0x140015580  inc     rdi
0x140015583  mov     al, cl
0x140015585  and     al, 0C0h
0x140015587  cmp     al, 80h
0x140015589  jnz     loc_140015616
0x14001558f  mov     eax, edx
0x140015591  and     ecx, 3Fh
0x140015594  shl     eax, 6
0x140015597  mov     edx, ecx
0x140015599  or      edx, eax
0x14001559b  mov     rax, rdi
0x14001559e  sub     rax, r15
0x1400155a1  cmp     rax, r10
0x1400155a4  jb      short loc_14001557D
0x1400155a6  cmp     r10, r11
0x1400155a9  jnb     short loc_1400155C5
0x1400155ab  movzx   eax, r8b
0x1400155af  sub     r9b, r10b
0x1400155b2  mov     [rbx+4], ax
0x1400155b6  movzx   eax, r9b
0x1400155ba  mov     [rbx+6], ax
0x1400155be  mov     [rbx], edx
0x1400155c0  jmp     loc_1400154E2
0x1400155c5  lea     eax, [rdx-0D800h]
0x1400155cb  cmp     eax, 7FFh
0x1400155d0  jbe     short loc_140015616
0x1400155d2  cmp     edx, 110000h
0x1400155d8  jnb     short loc_140015616
0x1400155da  movzx   eax, r8b
0x1400155de  mov     [rsp+78h+var_58], 80h
0x1400155e6  mov     [rsp+78h+var_54], 800h
0x1400155ee  mov     [rsp+78h+var_50], 10000h
0x1400155f6  cmp     edx, [rsp+rax*4+78h+var_60]
0x1400155fa  jb      short loc_140015616
0x1400155fc  test    r14, r14
0x1400155ff  jz      short loc_140015604
0x140015601  mov     [r14], edx
0x140015604  neg     edx
0x140015606  mov     rdx, rbx; unsigned __int64
0x140015609  sbb     rcx, rcx
0x14001560c  and     rcx, r11; this
0x14001560f  call    ?reset_and_return@__crt_mbstring@@YA_K_KPEAU_Mbstatet@@@Z; __crt_mbstring::reset_and_return(unsigned __int64,_Mbstatet *)
0x140015614  jmp     short loc_140015621
0x140015616  mov     rdx, rsi; struct _Mbstatet *
0x140015619  mov     rcx, rbx; this
0x14001561c  call    ?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::return_illegal_sequence(_Mbstatet *,__crt_cached_ptd_host &)
0x140015621  mov     rcx, [rsp+78h+var_48]
0x140015626  xor     rcx, rsp; StackCookie
0x140015629  call    __security_check_cookie
0x14001562e  add     rsp, 40h
0x140015632  pop     r15
0x140015634  pop     r14
0x140015636  pop     r12
0x140015638  pop     rdi
0x140015639  pop     rsi
0x14001563a  pop     rbp
0x14001563b  pop     rbx
0x14001563c  retn
```
