# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,bool,std::_Basic_format_specs<char>,std::_Lazy_locale)

- ea: `0x18004eab8`
- end: `0x18004eca2`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@_NU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180051498`

## callees

- `0x180005020`
- `0x1800342a8`
- `0x18004ea14`
- `0x18004eab8`
- `0x180052334`
- `0x180053d44`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18004eb57`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18004eb57`

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
0x18004eab8  mov     [rsp-8+arg_8], rbx
0x18004eabd  push    rbp
0x18004eabe  push    rsi
0x18004eabf  push    rdi
0x18004eac0  push    r14
0x18004eac2  push    r15
0x18004eac4  lea     rbp, [rsp-2Fh]
0x18004eac9  sub     rsp, 0A0h
0x18004ead0  mov     rax, cs:__security_cookie
0x18004ead7  xor     rax, rsp
0x18004eada  mov     [rbp+4Fh+var_28], rax
0x18004eade  mov     rsi, r9
0x18004eae1  mov     dil, r8b
0x18004eae4  mov     rbx, rdx
0x18004eae7  mov     r14, rcx
0x18004eaea  mov     [rbp+4Fh+var_70], 0
0x18004eaf1  mov     al, [r9+8]
0x18004eaf5  test    al, al
0x18004eaf7  jz      short loc_18004EB26
0x18004eaf9  cmp     al, 73h ; 's'
0x18004eafb  jz      short loc_18004EB26
0x18004eafd  movaps  xmm0, xmmword ptr [r9]
0x18004eb01  movaps  [rbp+4Fh+var_90], xmm0
0x18004eb05  mov     ecx, [r9+10h]
0x18004eb09  mov     [rbp+4Fh+var_80], ecx
0x18004eb0c  mov     rcx, [rbp+4Fh+arg_20]
0x18004eb10  mov     [rsp+0C0h+var_A0], rcx
0x18004eb15  lea     r9, [rbp+4Fh+var_90]
0x18004eb19  mov     rcx, r14
0x18004eb1c  call    ??$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@EU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)
0x18004eb21  jmp     loc_18004EC7C
0x18004eb26  cmp     byte ptr [r9+0Ch], 0
0x18004eb2b  jz      loc_18004EC46
0x18004eb31  mov     byte ptr [r9+0Ch], 0
0x18004eb36  mov     rax, [rbp+4Fh+arg_20]
0x18004eb3a  test    rax, rax
0x18004eb3d  jz      short loc_18004EB55
0x18004eb3f  mov     rcx, [rax+8]
0x18004eb43  mov     qword ptr [rbp+4Fh+var_90+8], rcx
0x18004eb47  mov     rax, [rcx]
0x18004eb4a  mov     rax, [rax+8]
0x18004eb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb53  jmp     short loc_18004EB61
0x18004eb55  mov     cl, 1
0x18004eb57  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18004eb5d  mov     qword ptr [rbp+4Fh+var_90+8], rax
0x18004eb61  lea     rcx, [rbp+4Fh+var_90]
0x18004eb65  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18004eb6a  mov     r15, rax
0x18004eb6d  mov     rcx, qword ptr [rbp+4Fh+var_90+8]
0x18004eb71  test    rcx, rcx
0x18004eb74  jz      short loc_18004EB9D
0x18004eb76  mov     rdx, [rcx]
0x18004eb79  mov     rax, [rdx+10h]
0x18004eb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb82  mov     r8, rax
0x18004eb85  test    rax, rax
0x18004eb88  jz      short loc_18004EB9D
0x18004eb8a  mov     rcx, [rax]
0x18004eb8d  mov     rax, [rcx]
0x18004eb90  mov     edx, 1
0x18004eb95  mov     rcx, r8
0x18004eb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb9d  mov     rax, [r15]
0x18004eba0  mov     rcx, r15
0x18004eba3  test    dil, dil
0x18004eba6  jz      short loc_18004EBD3
0x18004eba8  lea     rdx, [rbp+4Fh+var_48]
0x18004ebac  mov     rax, [rax+38h]
0x18004ebb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ebb5  nop
0x18004ebb6  mov     edi, 5
0x18004ebbb  lea     rax, [rbp+4Fh+var_48]
0x18004ebbf  cmp     [rbp+4Fh+var_30], 0Fh
0x18004ebc4  cmova   rax, [rbp+4Fh+var_48]
0x18004ebc9  mov     qword ptr [rbp+4Fh+var_90], rax
0x18004ebcd  mov     rax, [rbp+4Fh+var_38]
0x18004ebd1  jmp     short loc_18004EBFC
0x18004ebd3  lea     rdx, [rbp+4Fh+var_68]
0x18004ebd7  mov     rax, [rax+30h]
0x18004ebdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ebe0  nop
0x18004ebe1  mov     edi, 0Ah
0x18004ebe6  lea     rax, [rbp+4Fh+var_68]
0x18004ebea  cmp     [rbp+4Fh+var_50], 0Fh
0x18004ebef  cmova   rax, [rbp+4Fh+var_68]
0x18004ebf4  mov     qword ptr [rbp+4Fh+var_90], rax
0x18004ebf8  mov     rax, [rbp+4Fh+var_58]
0x18004ebfc  mov     qword ptr [rbp+4Fh+var_90+8], rax
0x18004ec00  lea     rax, [rbp+4Fh+var_90]
0x18004ec04  mov     [rbp+4Fh+var_70], edi
0x18004ec07  movups  xmm0, xmmword ptr [rax]
0x18004ec0a  movdqu  [rbp+4Fh+var_90], xmm0
0x18004ec0f  mov     r9, rsi
0x18004ec12  lea     r8, [rbp+4Fh+var_90]
0x18004ec16  mov     rdx, rbx
0x18004ec19  mov     rcx, r14
0x18004ec1c  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@V?$basic_string_view@DU?$char_traits@D@std@@@0@AEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::string_view,std::_Basic_format_specs<char> const &,std::_Lazy_locale)
0x18004ec21  nop
0x18004ec22  test    dil, 2
0x18004ec26  jz      short loc_18004EC35
0x18004ec28  and     edi, 0FFFFFFFDh
0x18004ec2b  lea     rcx, [rbp+4Fh+var_68]
0x18004ec2f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004ec34  nop
0x18004ec35  test    dil, 1
0x18004ec39  jz      short loc_18004EC7C
0x18004ec3b  lea     rcx, [rbp+4Fh+var_48]
0x18004ec3f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004ec44  jmp     short loc_18004EC7C
0x18004ec46  lea     rax, aFalse; "false"
0x18004ec4d  lea     rcx, aTrue_0; "true"
0x18004ec54  test    dil, dil
0x18004ec57  cmovz   rcx, rax
0x18004ec5b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ec5f  inc     rax
0x18004ec62  cmp     byte ptr [rcx+rax], 0
0x18004ec66  jnz     short loc_18004EC5F
0x18004ec68  mov     qword ptr [rbp+4Fh+var_90], rcx
0x18004ec6c  mov     qword ptr [rbp+4Fh+var_90+8], rax
0x18004ec70  lea     r8, [rbp+4Fh+var_90]
0x18004ec74  mov     rcx, r14
0x18004ec77  call    ??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@V?$basic_string_view@DU?$char_traits@D@std@@@0@AEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z; std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::string_view,std::_Basic_format_specs<char> const &,std::_Lazy_locale)
0x18004ec7c  mov     rax, r14
0x18004ec7f  mov     rcx, [rbp+4Fh+var_28]
0x18004ec83  xor     rcx, rsp; StackCookie
0x18004ec86  call    __security_check_cookie
0x18004ec8b  mov     rbx, [rsp+0C0h+arg_8]
0x18004ec93  add     rsp, 0A0h
0x18004ec9a  pop     r15
0x18004ec9c  pop     r14
0x18004ec9e  pop     rdi
0x18004ec9f  pop     rsi
0x18004eca0  pop     rbp
0x18004eca1  retn
```
