# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,bool,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x180024094`
- end: `0x18002427e`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@_NU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180026ec8`

## callees

- `0x180004180`
- `0x180023ff0`
- `0x180024094`
- `0x180027d64`
- `0x18002a6a0`
- `0x18002abe4`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180024133`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180024133`

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
0x180024094  mov     [rsp-8+arg_8], rbx
0x180024099  push    rbp
0x18002409a  push    rsi
0x18002409b  push    rdi
0x18002409c  push    r14
0x18002409e  push    r15
0x1800240a0  lea     rbp, [rsp-2Fh]
0x1800240a5  sub     rsp, 0A0h
0x1800240ac  mov     rax, cs:__security_cookie
0x1800240b3  xor     rax, rsp
0x1800240b6  mov     [rbp+4Fh+var_28], rax
0x1800240ba  mov     rsi, r9
0x1800240bd  mov     dil, r8b
0x1800240c0  mov     rbx, rdx
0x1800240c3  mov     r14, rcx
0x1800240c6  mov     [rbp+4Fh+var_70], 0
0x1800240cd  mov     al, [r9+8]
0x1800240d1  test    al, al
0x1800240d3  jz      short loc_180024102
0x1800240d5  cmp     al, 73h ; 's'
0x1800240d7  jz      short loc_180024102
0x1800240d9  movaps  xmm0, xmmword ptr [r9]
0x1800240dd  movaps  [rbp+4Fh+var_90], xmm0
0x1800240e1  mov     ecx, [r9+10h]
0x1800240e5  mov     [rbp+4Fh+var_80], ecx
0x1800240e8  mov     rcx, [rbp+4Fh+arg_20]
0x1800240ec  mov     [rsp+0C0h+var_A0], rcx
0x1800240f1  lea     r9, [rbp+4Fh+var_90]
0x1800240f5  mov     rcx, r14
0x1800240f8  call    ??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x1800240fd  jmp     loc_180024258
0x180024102  cmp     byte ptr [r9+0Ch], 0
0x180024107  jz      loc_180024222
0x18002410d  mov     byte ptr [r9+0Ch], 0
0x180024112  mov     rax, [rbp+4Fh+arg_20]
0x180024116  test    rax, rax
0x180024119  jz      short loc_180024131
0x18002411b  mov     rcx, [rax+8]
0x18002411f  mov     qword ptr [rbp+4Fh+var_90+8], rcx
0x180024123  mov     rax, [rcx]
0x180024126  mov     rax, [rax+8]
0x18002412a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002412f  jmp     short loc_18002413D
0x180024131  mov     cl, 1
0x180024133  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180024139  mov     qword ptr [rbp+4Fh+var_90+8], rax
0x18002413d  lea     rcx, [rbp+4Fh+var_90]
0x180024141  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180024146  mov     r15, rax
0x180024149  mov     rcx, qword ptr [rbp+4Fh+var_90+8]
0x18002414d  test    rcx, rcx
0x180024150  jz      short loc_180024179
0x180024152  mov     rdx, [rcx]
0x180024155  mov     rax, [rdx+10h]
0x180024159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002415e  mov     r8, rax
0x180024161  test    rax, rax
0x180024164  jz      short loc_180024179
0x180024166  mov     rcx, [rax]
0x180024169  mov     rax, [rcx]
0x18002416c  mov     edx, 1
0x180024171  mov     rcx, r8
0x180024174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024179  mov     rax, [r15]
0x18002417c  mov     rcx, r15
0x18002417f  test    dil, dil
0x180024182  jz      short loc_1800241AF
0x180024184  lea     rdx, [rbp+4Fh+var_48]
0x180024188  mov     rax, [rax+38h]
0x18002418c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024191  nop
0x180024192  mov     edi, 5
0x180024197  lea     rax, [rbp+4Fh+var_48]
0x18002419b  cmp     [rbp+4Fh+var_30], 0Fh
0x1800241a0  cmova   rax, [rbp+4Fh+var_48]
0x1800241a5  mov     qword ptr [rbp+4Fh+var_90], rax
0x1800241a9  mov     rax, [rbp+4Fh+var_38]
0x1800241ad  jmp     short loc_1800241D8
0x1800241af  lea     rdx, [rbp+4Fh+var_68]
0x1800241b3  mov     rax, [rax+30h]
0x1800241b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241bc  nop
0x1800241bd  mov     edi, 0Ah
0x1800241c2  lea     rax, [rbp+4Fh+var_68]
0x1800241c6  cmp     [rbp+4Fh+var_50], 0Fh
0x1800241cb  cmova   rax, [rbp+4Fh+var_68]
0x1800241d0  mov     qword ptr [rbp+4Fh+var_90], rax
0x1800241d4  mov     rax, [rbp+4Fh+var_58]
0x1800241d8  mov     qword ptr [rbp+4Fh+var_90+8], rax
0x1800241dc  lea     rax, [rbp+4Fh+var_90]
0x1800241e0  mov     [rbp+4Fh+var_70], edi
0x1800241e3  movups  xmm0, xmmword ptr [rax]
0x1800241e6  movdqu  [rbp+4Fh+var_90], xmm0
0x1800241eb  mov     r9, rsi
0x1800241ee  lea     r8, [rbp+4Fh+var_90]
0x1800241f2  mov     rdx, rbx
0x1800241f5  mov     rcx, r14
0x1800241f8  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@V?$basic_string_view@DU?$char_traits@D@std@@@0@AEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::string_view,std::_Basic_format_specs<char> const &,std::_Lazy_locale)
0x1800241fd  nop
0x1800241fe  test    dil, 2
0x180024202  jz      short loc_180024211
0x180024204  and     edi, 0FFFFFFFDh
0x180024207  lea     rcx, [rbp+4Fh+var_68]
0x18002420b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180024210  nop
0x180024211  test    dil, 1
0x180024215  jz      short loc_180024258
0x180024217  lea     rcx, [rbp+4Fh+var_48]
0x18002421b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180024220  jmp     short loc_180024258
0x180024222  lea     rax, aFalse; "false"
0x180024229  lea     rcx, aTrue; "true"
0x180024230  test    dil, dil
0x180024233  cmovz   rcx, rax
0x180024237  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002423b  inc     rax
0x18002423e  cmp     byte ptr [rcx+rax], 0
0x180024242  jnz     short loc_18002423B
0x180024244  mov     qword ptr [rbp+4Fh+var_90], rcx
0x180024248  mov     qword ptr [rbp+4Fh+var_90+8], rax
0x18002424c  lea     r8, [rbp+4Fh+var_90]
0x180024250  mov     rcx, r14
0x180024253  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@V?$basic_string_view@DU?$char_traits@D@std@@@0@AEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::string_view,std::_Basic_format_specs<char> const &,std::_Lazy_locale)
0x180024258  mov     rax, r14
0x18002425b  mov     rcx, [rbp+4Fh+var_28]
0x18002425f  xor     rcx, rsp; StackCookie
0x180024262  call    __security_check_cookie
0x180024267  mov     rbx, [rsp+0C0h+arg_8]
0x18002426f  add     rsp, 0A0h
0x180024276  pop     r15
0x180024278  pop     r14
0x18002427a  pop     rdi
0x18002427b  pop     rsi
0x18002427c  pop     rbp
0x18002427d  retn
```
