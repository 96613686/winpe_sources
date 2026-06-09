# Common::StringBuffer::SetValueFromString(ushort const *)

- ea: `0x1800059f0`
- end: `0x180005da9`
- name: `?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z`
- size: `953`
- prototype: `__int64 __fastcall(Common::StringBuffer *__hidden this, const unsigned __int16 *)`
- caller_count: `27`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005830`
- `0x18000b454`
- `0x180044a38`
- `0x18005cd3c`
- `0x180061a04`
- `0x180069360`
- `0x180070b90`
- `0x18007122c`
- `0x18007a59c`
- `0x180092c64`
- `0x1800937dc`
- `0x180093ba0`
- `0x180094044`
- `0x180094280`
- `0x1800944f0`
- `0x180097f6c`
- `0x18009814c`
- `0x1800ac638`
- `0x1800ac824`
- `0x1800acd68`
- `0x1800b5298`
- `0x1800b7f58`
- `0x1800bd240`
- `0x1800d2928`
- `0x1800e6888`
- `0x1800ea0bc`
- `0x1800fc774`

## callees

- `0x1800059f0`
- `0x180005db0`
- `0x1800133fc`
- `0x180029dc0`
- `0x18002a224`
- `0x180071f50`
- `0x1800992c4`
- `0x180099dd8`
- `0x180099e38`
- `0x18009d3d0`
- `0x18009d729`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005c80`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005d62`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005c80`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005d62`

## string_xrefs

- `0x180005bd4`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180005c1a`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180005c3d`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180005c51`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180005cb0`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180005ce8`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180005d01`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180005d8e`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuffer::SetValueFromString(Common::StringBuffer *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rbp
  Common::StringBuffer *v3; // r14
  __int64 v4; // rcx
  const unsigned __int16 *v5; // rax
  unsigned int v6; // edi
  __int64 v7; // r13
  unsigned int v8; // ecx
  __int64 v9; // rsi
  unsigned int i; // ebx
  unsigned int v11; // ebp
  _WORD *v12; // r14
  unsigned __int64 v13; // rax
  _WORD *v14; // rax
  unsigned __int64 v15; // rdx
  _WORD *v16; // r15
  size_t v17; // rsi
  size_t v18; // r12
  unsigned int v19; // eax
  int v20; // edx
  unsigned int v21; // ecx
  __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  int *v27; // rax
  int v28; // ebx
  int v29; // eax
  void *v30; // rcx
  int v31; // [rsp+20h] [rbp-48h]
  int v32; // [rsp+20h] [rbp-48h]
  int v33; // [rsp+20h] [rbp-48h]
  char *v34; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = a2;
  v3 = this;
  if ( !a2 )
  {
    Common::StringBuffer::Clear(this);
    return 0;
  }
  v4 = 1073741822;
  v5 = a2;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = -2147024809;
  if ( !v4 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070057LL,
      v31);
    return 2147942487LL;
  }
  v7 = (unsigned int)(1073741822 - v4);
  if ( (unsigned int)v7 <= 0x7FFFFFFF )
  {
    v8 = 0;
    v9 = *((unsigned int *)v3 + 4);
    if ( (_DWORD)v9 )
      v8 = v9 - 1;
    if ( (unsigned int)v7 <= v8 && v8 <= 0x20 )
      goto LABEL_29;
    if ( (unsigned int)v7 <= 0x20 )
    {
      for ( i = 8; i < (unsigned int)v7; i *= 2 )
        ;
    }
    else
    {
      i = v7;
    }
    if ( i > 0x3FFFFFFF )
    {
      v6 = -2147023613;
      v23 = 425;
      goto LABEL_47;
    }
    if ( !i )
    {
      v30 = (void *)*((_QWORD *)v3 + 1);
      if ( v30 )
      {
        operator delete(v30, (unsigned __int64)a2);
        *((_QWORD *)v3 + 1) = 0;
        *(_DWORD *)v3 = 0;
      }
      *((_DWORD *)v3 + 4) = 0;
      goto LABEL_29;
    }
    v11 = i + 1;
    if ( i + 1 == (_DWORD)v9 )
    {
LABEL_28:
      v2 = a2;
LABEL_29:
      v20 = *((_DWORD *)v3 + 4);
      v21 = 0;
      if ( v20 )
        v21 = v20 - 1;
      if ( (unsigned int)v7 <= v21 || (v29 = Common::StringBuffer::SetCapacity(v3, v7), v6 = v29, v29 >= 0) )
      {
        *(_DWORD *)v3 = v7;
        if ( (_DWORD)v7 )
          *(_WORD *)(*((_QWORD *)v3 + 1) + 2 * v7) = 0;
        memcpy_0(*((void **)v3 + 1), v2, (unsigned int)(2 * v7));
        return 0;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x20C,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)(unsigned int)v29,
          v31);
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x235,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)v6,
          v33);
      }
      return v6;
    }
    v12 = (_WORD *)*((_QWORD *)v3 + 1);
    if ( v11 <= (unsigned int)v9 )
    {
      v16 = v12;
LABEL_24:
      v3 = this;
      v19 = *(_DWORD *)this;
      *((_DWORD *)this + 4) = v11;
      *((_QWORD *)this + 1) = v16;
      if ( v19 > i )
      {
        *(_DWORD *)this = i;
        v16[i] = 0;
      }
      else if ( v19 < i && !v19 )
      {
        *v16 = 0;
      }
      goto LABEL_28;
    }
    v13 = 2LL * v11;
    if ( !is_mul_ok(v11, 2u) )
      v13 = -1;
    v14 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
    v16 = v14;
    if ( !v14 )
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x8007000ELL,
        v31);
LABEL_46:
      v23 = 452;
LABEL_47:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)v6,
        v31);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x232,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)v6,
        v32);
      return v6;
    }
    v17 = 2 * v9;
    if ( !v17 )
    {
LABEL_23:
      operator delete(v12, v15);
      goto LABEL_24;
    }
    v18 = 2LL * v11;
    if ( v12 && v18 >= v17 )
    {
      memcpy_0(v14, v12, v17);
      goto LABEL_23;
    }
    memset_0(v14, 0, v18);
    if ( v12 )
    {
      if ( v18 >= v17 )
      {
        v28 = 22;
        goto LABEL_51;
      }
      v27 = (int *)_o__errno(v25, v24, v26);
      v28 = 34;
    }
    else
    {
      v27 = (int *)_o__errno(v25, v24, v26);
      v28 = 22;
    }
    *v27 = v28;
    invalid_parameter_noinfo();
LABEL_51:
    operator delete(v16, v24);
    LODWORD(v34) = v28;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070057LL,
      (int)"0x%08lx",
      v34);
    goto LABEL_46;
  }
  v6 = -2147024362;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x22F,
    (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
    (const char *)0x80070216LL,
    v31);
  return v6;
}

```

## disassembly

```asm
0x1800059f0  mov     rax, rsp
0x1800059f3  mov     [rax+10h], rdx
0x1800059f7  mov     [rax+8], rcx
0x1800059fb  push    rbp
0x1800059fc  push    r14
0x1800059fe  sub     rsp, 58h
0x180005a02  mov     rbp, rdx
0x180005a05  mov     r14, rcx
0x180005a08  test    rdx, rdx
0x180005a0b  jz      loc_180005BFD
0x180005a11  mov     [rax+18h], rbx
0x180005a15  mov     [rax-20h], rdi
0x180005a19  mov     [rax-30h], r13
0x180005a1d  mov     r13d, 3FFFFFFEh
0x180005a23  mov     ecx, r13d
0x180005a26  mov     rax, rdx
0x180005a29  nop     dword ptr [rax+00000000h]
0x180005a30  cmp     word ptr [rax], 0
0x180005a34  jz      short loc_180005A40
0x180005a36  add     rax, 2
0x180005a3a  sub     rcx, 1
0x180005a3e  jnz     short loc_180005A30
0x180005a40  xor     eax, eax
0x180005a42  mov     edi, 80070057h
0x180005a47  test    rcx, rcx
0x180005a4a  mov     ebx, edi
0x180005a4c  cmovnz  ebx, eax
0x180005a4f  jz      loc_180005D89
0x180005a55  sub     r13d, ecx
0x180005a58  cmp     r13d, 7FFFFFFFh
0x180005a5f  ja      loc_180005BCF
0x180005a65  mov     [rsp+68h+var_18], rsi
0x180005a6a  xor     ecx, ecx
0x180005a6c  mov     esi, [r14+10h]
0x180005a70  test    esi, esi
0x180005a72  mov     [rsp+68h+var_28], r12
0x180005a77  mov     [rsp+68h+var_38], r15
0x180005a7c  lea     eax, [rsi-1]
0x180005a7f  cmovnz  ecx, eax
0x180005a82  cmp     r13d, ecx
0x180005a85  jbe     loc_180005BEF
0x180005a8b  cmp     r13d, 20h ; ' '
0x180005a8f  jbe     loc_180005BB5
0x180005a95  mov     ebx, r13d
0x180005a98  cmp     ebx, 3FFFFFFFh
0x180005a9e  ja      loc_180005D1A
0x180005aa4  test    ebx, ebx
0x180005aa6  jz      loc_180005D29
0x180005aac  lea     ebp, [rbx+1]
0x180005aaf  cmp     ebp, esi
0x180005ab1  jz      loc_180005B44
0x180005ab7  mov     r14, [r14+8]
0x180005abb  jbe     loc_180005C0D
0x180005ac1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005ac8  mov     r12d, ebp
0x180005acb  mov     eax, 2
0x180005ad0  mul     r12
0x180005ad3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005ada  cmovb   rax, rcx
0x180005ade  mov     rcx, rax; unsigned __int64
0x180005ae1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005ae6  mov     r15, rax
0x180005ae9  test    rax, rax
0x180005aec  jz      loc_180005C15
0x180005af2  add     rsi, rsi
0x180005af5  jz      short loc_180005B1A
0x180005af7  add     r12, r12
0x180005afa  test    r14, r14
0x180005afd  jz      loc_180005C6A
0x180005b03  cmp     r12, rsi
0x180005b06  jb      loc_180005C6A
0x180005b0c  mov     r8, rsi; Size
0x180005b0f  mov     rdx, r14; Src
0x180005b12  mov     rcx, rax; void *
0x180005b15  call    memcpy_0
0x180005b1a  mov     rcx, r14; void *
0x180005b1d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005b22  mov     r14, [rsp+68h+arg_0]
0x180005b27  mov     eax, [r14]
0x180005b2a  mov     [r14+10h], ebp
0x180005b2e  mov     [r14+8], r15
0x180005b32  cmp     eax, ebx
0x180005b34  ja      loc_180005D78
0x180005b3a  jnb     short loc_180005B44
0x180005b3c  test    eax, eax
0x180005b3e  jnz     short loc_180005B44
0x180005b40  mov     [r15], ax
0x180005b44  mov     rbp, [rsp+68h+Src]
0x180005b49  mov     edx, [r14+10h]
0x180005b4d  xor     ecx, ecx
0x180005b4f  test    edx, edx
0x180005b51  lea     eax, [rdx-1]
0x180005b54  cmovnz  ecx, eax
0x180005b57  cmp     r13d, ecx
0x180005b5a  ja      loc_180005CCE
0x180005b60  mov     [r14], r13d
0x180005b63  test    r13d, r13d
0x180005b66  jz      short loc_180005B73
0x180005b68  mov     rcx, [r14+8]
0x180005b6c  xor     eax, eax
0x180005b6e  mov     [rcx+r13*2], ax
0x180005b73  mov     rcx, [r14+8]; void *
0x180005b77  lea     r8d, ds:0[r13*2]; Size
0x180005b7f  mov     rdx, rbp; Src
0x180005b82  call    memcpy_0
0x180005b87  xor     edi, edi
0x180005b89  mov     rsi, [rsp+68h+var_18]
0x180005b8e  mov     r12, [rsp+68h+var_28]
0x180005b93  mov     r15, [rsp+68h+var_38]
0x180005b98  mov     eax, edi
0x180005b9a  mov     rdi, [rsp+68h+var_20]
0x180005b9f  mov     rbx, [rsp+68h+arg_10]
0x180005ba7  mov     r13, [rsp+68h+var_30]
0x180005bac  add     rsp, 58h
0x180005bb0  pop     r14
0x180005bb2  pop     rbp
0x180005bb3  retn
0x180005bb5  mov     ebx, 8
0x180005bba  cmp     r13d, ebx
0x180005bbd  jbe     loc_180005A98
0x180005bc3  add     ebx, ebx
0x180005bc5  cmp     ebx, r13d
0x180005bc8  jb      short loc_180005BC3
0x180005bca  jmp     loc_180005A98
0x180005bcf  mov     rcx, [rsp+68h]; this
0x180005bd4  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\widest"...
0x180005bdb  mov     edi, 80070216h
0x180005be0  mov     edx, 22Fh; void *
0x180005be5  mov     r9d, edi; char *
0x180005be8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005bed  jmp     short loc_180005B98
0x180005bef  cmp     ecx, 20h ; ' '
0x180005bf2  jbe     loc_180005B49
0x180005bf8  jmp     loc_180005A8B
0x180005bfd  call    ?Clear@StringBuffer@Common@@QEAAXXZ; Common::StringBuffer::Clear(void)
0x180005c02  xor     eax, eax
0x180005c04  add     rsp, 58h
0x180005c08  pop     r14
0x180005c0a  pop     rbp
0x180005c0b  retn
0x180005c0d  mov     r15, r14
0x180005c10  jmp     loc_180005B22
0x180005c15  mov     rcx, [rsp+68h]; this
0x180005c1a  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\widest"...
0x180005c21  mov     edi, 8007000Eh
0x180005c26  mov     edx, 193h; void *
0x180005c2b  mov     r9d, edi; char *
0x180005c2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c33  mov     edx, 1C4h; void *
0x180005c38  mov     rcx, [rsp+68h]; this
0x180005c3d  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\widest"...
0x180005c44  mov     r9d, edi; char *
0x180005c47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c4c  mov     rcx, [rsp+68h]; this
0x180005c51  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\widest"...
0x180005c58  mov     r9d, edi; char *
0x180005c5b  mov     edx, 232h; void *
0x180005c60  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005c65  jmp     loc_180005B89
0x180005c6a  mov     r8, r12; Size
0x180005c6d  xor     edx, edx; Val
0x180005c6f  mov     rcx, r15; void *
0x180005c72  call    memset_0
0x180005c77  test    r14, r14
0x180005c7a  jnz     loc_180005D53
0x180005c80  call    cs:__imp__o__errno
0x180005c87  nop     dword ptr [rax+rax+00h]
0x180005c8c  mov     ebx, 16h
0x180005c91  mov     [rax], ebx
0x180005c93  call    _invalid_parameter_noinfo
0x180005c98  mov     rcx, r15; void *
0x180005c9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005ca0  mov     rcx, [rsp+68h]; this
0x180005ca5  lea     rax, a0x08lx; "0x%08lx"
0x180005cac  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x180005cb0  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\widest"...
0x180005cb7  mov     r9d, edi; char *
0x180005cba  mov     qword ptr [rsp+68h+var_48], rax; int
0x180005cbf  mov     edx, 198h; void *
0x180005cc4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180005cc9  jmp     loc_180005C33
0x180005cce  mov     edx, r13d; unsigned int
0x180005cd1  mov     rcx, r14; this
0x180005cd4  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x180005cd9  mov     edi, eax
0x180005cdb  test    eax, eax
0x180005cdd  jns     loc_180005B60
0x180005ce3  mov     rcx, [rsp+68h]; this
0x180005ce8  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\widest"...
0x180005cef  mov     r9d, eax; char *
0x180005cf2  mov     edx, 20Ch; void *
0x180005cf7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005cfc  mov     rcx, [rsp+68h]; this
0x180005d01  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\widest"...
0x180005d08  mov     r9d, edi; char *
0x180005d0b  mov     edx, 235h; void *
0x180005d10  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005d15  jmp     loc_180005B89
0x180005d1a  mov     edi, 80070503h
0x180005d1f  mov     edx, 1A9h; unsigned __int64
0x180005d24  jmp     loc_180005C38
0x180005d29  mov     rcx, [r14+8]; void *
0x180005d2d  test    rcx, rcx
0x180005d30  jz      short loc_180005D46
0x180005d32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005d37  mov     qword ptr [r14+8], 0
0x180005d3f  mov     dword ptr [r14], 0
0x180005d46  mov     dword ptr [r14+10h], 0
0x180005d4e  jmp     loc_180005B49
0x180005d53  cmp     r12, rsi
0x180005d56  jb      short loc_180005D62
0x180005d58  mov     ebx, 16h
0x180005d5d  jmp     loc_180005C98
0x180005d62  call    cs:__imp__o__errno
0x180005d69  nop     dword ptr [rax+rax+00h]
0x180005d6e  mov     ebx, 22h ; '"'
0x180005d73  jmp     loc_180005C91
0x180005d78  mov     ecx, ebx
0x180005d7a  xor     eax, eax
0x180005d7c  mov     [r14], ebx
0x180005d7f  mov     [r15+rcx*2], ax
0x180005d84  jmp     loc_180005B44
0x180005d89  mov     rcx, [rsp+68h]; this
0x180005d8e  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\widest"...
0x180005d95  mov     r9d, ebx; char *
0x180005d98  mov     edx, 249h; void *
0x180005d9d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005da2  mov     eax, ebx
0x180005da4  jmp     loc_180005B9A
```
