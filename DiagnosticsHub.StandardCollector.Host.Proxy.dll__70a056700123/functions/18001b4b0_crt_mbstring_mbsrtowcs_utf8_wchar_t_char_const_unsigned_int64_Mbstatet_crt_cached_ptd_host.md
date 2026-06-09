# __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x18001b4b0`
- end: `0x18001b665`
- name: `?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `437`
- prototype: `unsigned __int64(__crt_mbstring *__hidden this, wchar_t *, const char **, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180014ab0`
- `0x18001b8a0`
- `0x180021c20`
- `0x18004b184`
- `0x18004b780`
- `0x18004bdb8`
- `0x18004c3b4`
- `0x18004c92c`
- `0x18004ceb8`
- `0x1800549d0`
- `0x180054c60`
- `0x180054ef0`
- `0x180055180`
- `0x1800553b4`
- `0x1800555e8`

## callees

- `0x18001b4b0`
- `0x180020d00`

## pseudocode

```c
__int64 __fastcall __crt_mbstring::__mbsrtowcs_utf8(
        __crt_mbstring *this,
        wchar_t *a2,
        const char **a3,
        unsigned __int64 a4,
        struct _Mbstatet *a5)
{
  __int64 v5; // rdi
  const char **v7; // rsi
  __crt_mbstring *v10; // rbx
  struct _Mbstatet *v11; // r15
  __int64 v12; // r8
  unsigned __int64 v13; // rax
  __int16 v14; // cx
  unsigned int v15; // ecx
  __int64 i; // rbx
  struct _Mbstatet *v18; // rsi
  __int64 v19; // r8
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  struct __crt_cached_ptd_host *v22; // [rsp+28h] [rbp-30h]
  unsigned int v23; // [rsp+60h] [rbp+8h] BYREF

  v5 = *(_QWORD *)a2;
  v7 = a3;
  if ( !this )
  {
    v18 = a5;
    for ( i = 0; ; i = v21 + 1 )
    {
      if ( *(_BYTE *)v5 )
        v19 = *(_BYTE *)(v5 + 1) ? (*(_BYTE *)(v5 + 2) != 0) + 3LL : 2LL;
      else
        v19 = 1;
      v20 = __crt_mbstring::__mbrtoc32_utf8(0, (char32_t *)v5, (const char *)v19, a4, v18, v22);
      if ( v20 == -1 )
        break;
      if ( !v20 )
        return i;
      v21 = i + 1;
      v5 += v20;
      if ( v20 != 4 )
        v21 = i;
    }
    LOBYTE(v18[6]._Wchar) = 1;
    *(_DWORD *)&v18[5]._Byte = 42;
    return -1;
  }
  v10 = this;
  if ( a3 )
  {
    v11 = a5;
    while ( 1 )
    {
      if ( *(_BYTE *)v5 )
        v12 = *(_BYTE *)(v5 + 1) ? (*(_BYTE *)(v5 + 2) != 0) + 3LL : 2LL;
      else
        v12 = 1;
      v23 = 0;
      v13 = __crt_mbstring::__mbrtoc32_utf8((__crt_mbstring *)&v23, (char32_t *)v5, (const char *)v12, a4, v11, v22);
      if ( v13 == -1 )
        break;
      if ( !v13 )
      {
        v5 = 0;
        *(_WORD *)v10 = 0;
        goto LABEL_15;
      }
      v14 = v23;
      if ( v23 > 0xFFFF )
      {
        if ( (unsigned __int64)v7 <= 1 )
          goto LABEL_15;
        v15 = v23 - 0x10000;
        v23 = v15;
        v7 = (const char **)((char *)v7 - 1);
        *(_WORD *)v10 = (v15 >> 10) | 0xD800;
        v10 = (__crt_mbstring *)((char *)v10 + 2);
        v14 = v15 & 0x3FF | 0xDC00;
      }
      *(_WORD *)v10 = v14;
      v5 += v13;
      v10 = (__crt_mbstring *)((char *)v10 + 2);
      v7 = (const char **)((char *)v7 - 1);
      if ( !v7 )
        goto LABEL_15;
    }
    *(_QWORD *)a2 = v5;
    LOBYTE(v11[6]._Wchar) = 1;
    *(_DWORD *)&v11[5]._Byte = 42;
    return -1;
  }
LABEL_15:
  *(_QWORD *)a2 = v5;
  return (v10 - this) >> 1;
}

```

## disassembly

```asm
0x18001b4b0  mov     [rsp+arg_8], rbx
0x18001b4b5  mov     [rsp+arg_10], rbp
0x18001b4ba  mov     [rsp+arg_18], rsi
0x18001b4bf  push    rdi
0x18001b4c0  push    r12
0x18001b4c2  push    r13
0x18001b4c4  push    r14
0x18001b4c6  push    r15
0x18001b4c8  sub     rsp, 30h
0x18001b4cc  mov     rdi, [rdx]
0x18001b4cf  xor     r13d, r13d
0x18001b4d2  mov     r12, r9
0x18001b4d5  mov     rsi, r8
0x18001b4d8  mov     r14, rdx
0x18001b4db  mov     rbp, rcx
0x18001b4de  test    rcx, rcx
0x18001b4e1  jz      loc_18001B5D2
0x18001b4e7  mov     rbx, rcx
0x18001b4ea  test    r8, r8
0x18001b4ed  jz      loc_18001B5A6
0x18001b4f3  mov     r15, [rsp+58h+arg_20]
0x18001b4fb  cmp     [rdi], r13b
0x18001b4fe  jnz     short loc_18001B508
0x18001b500  mov     r8d, 1
0x18001b506  jmp     short loc_18001B525
0x18001b508  cmp     [rdi+1], r13b
0x18001b50c  jnz     short loc_18001B516
0x18001b50e  mov     r8d, 2
0x18001b514  jmp     short loc_18001B525
0x18001b516  mov     al, [rdi+2]
0x18001b519  neg     al
0x18001b51b  sbb     r8, r8
0x18001b51e  neg     r8
0x18001b521  add     r8, 3; char *
0x18001b525  mov     r9, r12; unsigned __int64
0x18001b528  mov     [rsp+58h+arg_0], r13d
0x18001b52d  mov     rdx, rdi; char32_t *
0x18001b530  mov     [rsp+58h+var_38], r15; struct _Mbstatet *
0x18001b535  lea     rcx, [rsp+58h+arg_0]; this
0x18001b53a  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001b53f  mov     rdx, rax
0x18001b542  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b546  jz      short loc_18001B5C0
0x18001b548  test    rax, rax
0x18001b54b  jz      short loc_18001B5B7
0x18001b54d  mov     ecx, [rsp+58h+arg_0]
0x18001b551  cmp     ecx, 0FFFFh
0x18001b557  jbe     short loc_18001B592
0x18001b559  cmp     rsi, 1
0x18001b55d  jbe     short loc_18001B5A6
0x18001b55f  add     ecx, 0FFFF0000h
0x18001b565  mov     r8d, 0D800h
0x18001b56b  mov     eax, ecx
0x18001b56d  mov     [rsp+58h+arg_0], ecx
0x18001b571  shr     eax, 0Ah
0x18001b574  dec     rsi
0x18001b577  or      ax, r8w
0x18001b57b  mov     [rbx], ax
0x18001b57e  mov     eax, 3FFh
0x18001b583  and     cx, ax
0x18001b586  add     rbx, 2
0x18001b58a  mov     eax, 0DC00h
0x18001b58f  or      cx, ax
0x18001b592  mov     [rbx], cx
0x18001b595  add     rdi, rdx
0x18001b598  add     rbx, 2
0x18001b59c  sub     rsi, 1
0x18001b5a0  jnz     loc_18001B4FB
0x18001b5a6  sub     rbx, rbp
0x18001b5a9  mov     [r14], rdi
0x18001b5ac  sar     rbx, 1
0x18001b5af  mov     rax, rbx
0x18001b5b2  jmp     loc_18001B648
0x18001b5b7  mov     rdi, r13
0x18001b5ba  mov     [rbx], r13w
0x18001b5be  jmp     short loc_18001B5A6
0x18001b5c0  mov     [r14], rdi
0x18001b5c3  mov     byte ptr [r15+30h], 1
0x18001b5c8  mov     dword ptr [r15+2Ch], 2Ah ; '*'
0x18001b5d0  jmp     short loc_18001B644
0x18001b5d2  mov     rsi, [rsp+58h+arg_20]
0x18001b5da  mov     rbx, r13
0x18001b5dd  cmp     [rdi], r13b
0x18001b5e0  jnz     short loc_18001B5EA
0x18001b5e2  mov     r8d, 1
0x18001b5e8  jmp     short loc_18001B607
0x18001b5ea  cmp     [rdi+1], r13b
0x18001b5ee  jnz     short loc_18001B5F8
0x18001b5f0  mov     r8d, 2
0x18001b5f6  jmp     short loc_18001B607
0x18001b5f8  mov     al, [rdi+2]
0x18001b5fb  neg     al
0x18001b5fd  sbb     r8, r8
0x18001b600  neg     r8
0x18001b603  add     r8, 3; char *
0x18001b607  mov     r9, r12; unsigned __int64
0x18001b60a  mov     [rsp+58h+var_38], rsi; struct _Mbstatet *
0x18001b60f  mov     rdx, rdi; char32_t *
0x18001b612  xor     ecx, ecx; this
0x18001b614  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001b619  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b61d  jz      short loc_18001B639
0x18001b61f  test    rax, rax
0x18001b622  jz      short loc_18001B5AF
0x18001b624  lea     rcx, [rbx+1]
0x18001b628  add     rdi, rax
0x18001b62b  cmp     rax, 4
0x18001b62f  cmovnz  rcx, rbx
0x18001b633  lea     rbx, [rcx+1]
0x18001b637  jmp     short loc_18001B5DD
0x18001b639  mov     byte ptr [rsi+30h], 1
0x18001b63d  mov     dword ptr [rsi+2Ch], 2Ah ; '*'
0x18001b644  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b648  mov     rbx, [rsp+58h+arg_8]
0x18001b64d  mov     rbp, [rsp+58h+arg_10]
0x18001b652  mov     rsi, [rsp+58h+arg_18]
0x18001b657  add     rsp, 30h
0x18001b65b  pop     r15
0x18001b65d  pop     r14
0x18001b65f  pop     r13
0x18001b661  pop     r12
0x18001b663  pop     rdi
0x18001b664  retn
```
