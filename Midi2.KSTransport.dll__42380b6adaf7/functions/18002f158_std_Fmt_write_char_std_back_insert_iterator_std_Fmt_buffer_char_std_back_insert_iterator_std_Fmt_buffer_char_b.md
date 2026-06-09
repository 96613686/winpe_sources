# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,bool,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x18002f158`
- end: `0x18002f342`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@_NU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180032164`

## callees

- `0x180004410`
- `0x18002f0b4`
- `0x18002f158`
- `0x180033000`
- `0x180035ca4`
- `0x1800361c4`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002f1f7`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002f1f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        __int64 a4,
        __int64 a5)
{
  char v9; // al
  void (__fastcall ***v10)(_QWORD, __int64); // r8
  __int64 *v11; // r15
  void (__fastcall ***v12)(_QWORD, __int64); // rax
  __int64 v13; // rax
  int v14; // edi
  _QWORD *v15; // rax
  __int64 v16; // rax
  _QWORD *v17; // rax
  const char *v18; // rcx
  __int64 v19; // rax
  __int128 v21; // [rsp+30h] [rbp-41h] BYREF
  int v22; // [rsp+40h] [rbp-31h]
  int v23; // [rsp+50h] [rbp-21h]
  _QWORD v24[4]; // [rsp+58h] [rbp-19h] BYREF
  _QWORD v25[4]; // [rsp+78h] [rbp+7h] BYREF

  v23 = 0;
  v9 = *(_BYTE *)(a4 + 8);
  if ( !v9 || v9 == 115 )
  {
    if ( *(_BYTE *)(a4 + 12) )
    {
      *(_BYTE *)(a4 + 12) = 0;
      if ( a5 )
      {
        *((_QWORD *)&v21 + 1) = *(_QWORD *)(a5 + 8);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v21 + 1) + 8LL))(*((_QWORD *)&v21 + 1));
      }
      else
      {
        *((_QWORD *)&v21 + 1) = std::locale::_Init(1);
      }
      v11 = (__int64 *)std::use_facet<std::numpunct<char>>(&v21);
      if ( *((_QWORD *)&v21 + 1) )
      {
        v12 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v21 + 1) + 16LL))(*((_QWORD *)&v21 + 1));
        v10 = v12;
        if ( v12 )
          (**v12)(v12, 1);
      }
      v13 = *v11;
      if ( a3 )
      {
        (*(void (__fastcall **)(__int64 *, _QWORD *, void (__fastcall ***)(_QWORD, __int64)))(v13 + 56))(v11, v25, v10);
        v14 = 5;
        v15 = v25;
        if ( v25[3] > 0xFu )
          v15 = (_QWORD *)v25[0];
        *(_QWORD *)&v21 = v15;
        v16 = v25[2];
      }
      else
      {
        (*(void (__fastcall **)(__int64 *, _QWORD *, void (__fastcall ***)(_QWORD, __int64)))(v13 + 48))(v11, v24, v10);
        v14 = 10;
        v17 = v24;
        if ( v24[3] > 0xFu )
          v17 = (_QWORD *)v24[0];
        *(_QWORD *)&v21 = v17;
        v16 = v24[2];
      }
      *((_QWORD *)&v21 + 1) = v16;
      v23 = v14;
      std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(a1, a2, &v21, a4);
      if ( (v14 & 2) != 0 )
      {
        LOBYTE(v14) = v14 & 0xFD;
        std::string::~string(v24);
      }
      if ( (v14 & 1) != 0 )
        std::string::~string(v25);
    }
    else
    {
      v18 = "true";
      if ( !a3 )
        v18 = "false";
      v19 = -1;
      do
        ++v19;
      while ( v18[v19] );
      *(_QWORD *)&v21 = v18;
      *((_QWORD *)&v21 + 1) = v19;
      std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(a1, a2, &v21, a4);
    }
  }
  else
  {
    v21 = *(_OWORD *)a4;
    v22 = *(_DWORD *)(a4 + 16);
    std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned char>(a1, a2, a3, &v21, a5);
  }
  return a1;
}

```

## disassembly

```asm
0x18002f158  mov     [rsp-8+arg_8], rbx
0x18002f15d  push    rbp
0x18002f15e  push    rsi
0x18002f15f  push    rdi
0x18002f160  push    r14
0x18002f162  push    r15
0x18002f164  lea     rbp, [rsp-2Fh]
0x18002f169  sub     rsp, 0A0h
0x18002f170  mov     rax, cs:__security_cookie
0x18002f177  xor     rax, rsp
0x18002f17a  mov     [rbp+4Fh+var_28], rax
0x18002f17e  mov     rsi, r9
0x18002f181  mov     dil, r8b
0x18002f184  mov     rbx, rdx
0x18002f187  mov     r14, rcx
0x18002f18a  mov     [rbp+4Fh+var_70], 0
0x18002f191  mov     al, [r9+8]
0x18002f195  test    al, al
0x18002f197  jz      short loc_18002F1C6
0x18002f199  cmp     al, 73h ; 's'
0x18002f19b  jz      short loc_18002F1C6
0x18002f19d  movaps  xmm0, xmmword ptr [r9]
0x18002f1a1  movaps  [rbp+4Fh+var_90], xmm0
0x18002f1a5  mov     ecx, [r9+10h]
0x18002f1a9  mov     [rbp+4Fh+var_80], ecx
0x18002f1ac  mov     rcx, [rbp+4Fh+arg_20]
0x18002f1b0  mov     [rsp+0C0h+var_A0], rcx
0x18002f1b5  lea     r9, [rbp+4Fh+var_90]
0x18002f1b9  mov     rcx, r14
0x18002f1bc  call    ??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x18002f1c1  jmp     loc_18002F31C
0x18002f1c6  cmp     byte ptr [r9+0Ch], 0
0x18002f1cb  jz      loc_18002F2E6
0x18002f1d1  mov     byte ptr [r9+0Ch], 0
0x18002f1d6  mov     rax, [rbp+4Fh+arg_20]
0x18002f1da  test    rax, rax
0x18002f1dd  jz      short loc_18002F1F5
0x18002f1df  mov     rcx, [rax+8]
0x18002f1e3  mov     qword ptr [rbp+4Fh+var_90+8], rcx
0x18002f1e7  mov     rax, [rcx]
0x18002f1ea  mov     rax, [rax+8]
0x18002f1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1f3  jmp     short loc_18002F201
0x18002f1f5  mov     cl, 1
0x18002f1f7  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002f1fd  mov     qword ptr [rbp+4Fh+var_90+8], rax
0x18002f201  lea     rcx, [rbp+4Fh+var_90]
0x18002f205  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002f20a  mov     r15, rax
0x18002f20d  mov     rcx, qword ptr [rbp+4Fh+var_90+8]
0x18002f211  test    rcx, rcx
0x18002f214  jz      short loc_18002F23D
0x18002f216  mov     rdx, [rcx]
0x18002f219  mov     rax, [rdx+10h]
0x18002f21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f222  mov     r8, rax
0x18002f225  test    rax, rax
0x18002f228  jz      short loc_18002F23D
0x18002f22a  mov     rcx, [rax]
0x18002f22d  mov     rax, [rcx]
0x18002f230  mov     edx, 1
0x18002f235  mov     rcx, r8
0x18002f238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f23d  mov     rax, [r15]
0x18002f240  mov     rcx, r15
0x18002f243  test    dil, dil
0x18002f246  jz      short loc_18002F273
0x18002f248  lea     rdx, [rbp+4Fh+var_48]
0x18002f24c  mov     rax, [rax+38h]
0x18002f250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f255  nop
0x18002f256  mov     edi, 5
0x18002f25b  lea     rax, [rbp+4Fh+var_48]
0x18002f25f  cmp     [rbp+4Fh+var_30], 0Fh
0x18002f264  cmova   rax, [rbp+4Fh+var_48]
0x18002f269  mov     qword ptr [rbp+4Fh+var_90], rax
0x18002f26d  mov     rax, [rbp+4Fh+var_38]
0x18002f271  jmp     short loc_18002F29C
0x18002f273  lea     rdx, [rbp+4Fh+var_68]
0x18002f277  mov     rax, [rax+30h]
0x18002f27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f280  nop
0x18002f281  mov     edi, 0Ah
0x18002f286  lea     rax, [rbp+4Fh+var_68]
0x18002f28a  cmp     [rbp+4Fh+var_50], 0Fh
0x18002f28f  cmova   rax, [rbp+4Fh+var_68]
0x18002f294  mov     qword ptr [rbp+4Fh+var_90], rax
0x18002f298  mov     rax, [rbp+4Fh+var_58]
0x18002f29c  mov     qword ptr [rbp+4Fh+var_90+8], rax
0x18002f2a0  lea     rax, [rbp+4Fh+var_90]
0x18002f2a4  mov     [rbp+4Fh+var_70], edi
0x18002f2a7  movups  xmm0, xmmword ptr [rax]
0x18002f2aa  movdqu  [rbp+4Fh+var_90], xmm0
0x18002f2af  mov     r9, rsi
0x18002f2b2  lea     r8, [rbp+4Fh+var_90]
0x18002f2b6  mov     rdx, rbx
0x18002f2b9  mov     rcx, r14
0x18002f2bc  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@V?$basic_string_view@DU?$char_traits@D@std@@@0@AEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::string_view,std::_Basic_format_specs<char> const &,std::_Lazy_locale)
0x18002f2c1  nop
0x18002f2c2  test    dil, 2
0x18002f2c6  jz      short loc_18002F2D5
0x18002f2c8  and     edi, 0FFFFFFFDh
0x18002f2cb  lea     rcx, [rbp+4Fh+var_68]
0x18002f2cf  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002f2d4  nop
0x18002f2d5  test    dil, 1
0x18002f2d9  jz      short loc_18002F31C
0x18002f2db  lea     rcx, [rbp+4Fh+var_48]
0x18002f2df  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002f2e4  jmp     short loc_18002F31C
0x18002f2e6  lea     rax, aFalse; "false"
0x18002f2ed  lea     rcx, aTrue; "true"
0x18002f2f4  test    dil, dil
0x18002f2f7  cmovz   rcx, rax
0x18002f2fb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f2ff  inc     rax
0x18002f302  cmp     byte ptr [rcx+rax], 0
0x18002f306  jnz     short loc_18002F2FF
0x18002f308  mov     qword ptr [rbp+4Fh+var_90], rcx
0x18002f30c  mov     qword ptr [rbp+4Fh+var_90+8], rax
0x18002f310  lea     r8, [rbp+4Fh+var_90]
0x18002f314  mov     rcx, r14
0x18002f317  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@V?$basic_string_view@DU?$char_traits@D@std@@@0@AEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::string_view,std::_Basic_format_specs<char> const &,std::_Lazy_locale)
0x18002f31c  mov     rax, r14
0x18002f31f  mov     rcx, [rbp+4Fh+var_28]
0x18002f323  xor     rcx, rsp; StackCookie
0x18002f326  call    __security_check_cookie
0x18002f32b  mov     rbx, [rsp+0C0h+arg_8]
0x18002f333  add     rsp, 0A0h
0x18002f33a  pop     r15
0x18002f33c  pop     r14
0x18002f33e  pop     rdi
0x18002f33f  pop     rsi
0x18002f340  pop     rbp
0x18002f341  retn
```
