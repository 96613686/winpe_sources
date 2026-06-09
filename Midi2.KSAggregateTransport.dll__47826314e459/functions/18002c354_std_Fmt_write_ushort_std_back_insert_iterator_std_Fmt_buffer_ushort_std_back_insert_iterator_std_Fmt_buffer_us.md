# std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,bool,std::_Basic_format_specs<ushort>,std::_Lazy_locale)

- ea: `0x18002c354`
- end: `0x18002c54b`
- name: `??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@_NU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002ff18`

## callees

- `0x180005020`
- `0x18000d430`
- `0x18002c298`
- `0x18002c354`
- `0x180030ac4`
- `0x180033a7c`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002c3f8`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002c3f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        __int64 a4,
        __int64 a5)
{
  char v9; // al
  struct std::locale::_Locimp *v10; // rdi
  void (__fastcall ***v11)(_QWORD, __int64); // r8
  __int64 *v12; // r12
  void (__fastcall ***v13)(_QWORD, __int64); // rax
  __int64 v14; // rax
  int v15; // edi
  _QWORD *v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // rax
  const wchar_t *v19; // rcx
  __int64 v20; // rax
  __int128 v22; // [rsp+30h] [rbp-51h] BYREF
  int v23; // [rsp+40h] [rbp-41h]
  int v24; // [rsp+50h] [rbp-31h]
  _QWORD v25[4]; // [rsp+58h] [rbp-29h] BYREF
  _QWORD v26[4]; // [rsp+78h] [rbp-9h] BYREF

  v24 = 0;
  v9 = *(_BYTE *)(a4 + 8);
  if ( !v9 || v9 == 115 )
  {
    if ( *(_BYTE *)(a4 + 12) )
    {
      *(_BYTE *)(a4 + 12) = 0;
      if ( a5 )
      {
        v10 = *(struct std::locale::_Locimp **)(a5 + 8);
        *((_QWORD *)&v22 + 1) = v10;
        (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v10 + 8LL))(v10);
      }
      else
      {
        v10 = std::locale::_Init(1);
        *((_QWORD *)&v22 + 1) = v10;
      }
      v12 = (__int64 *)std::use_facet<std::numpunct<unsigned short>>(&v22);
      if ( v10 )
      {
        v13 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v10 + 16LL))(v10);
        v11 = v13;
        if ( v13 )
          (**v13)(v13, 1);
      }
      v14 = *v12;
      if ( a3 )
      {
        (*(void (__fastcall **)(__int64 *, _QWORD *, void (__fastcall ***)(_QWORD, __int64)))(v14 + 56))(v12, v26, v11);
        v15 = 5;
        v16 = v26;
        if ( v26[3] > 7u )
          v16 = (_QWORD *)v26[0];
        *(_QWORD *)&v22 = v16;
        v17 = v26[2];
      }
      else
      {
        (*(void (__fastcall **)(__int64 *, _QWORD *, void (__fastcall ***)(_QWORD, __int64)))(v14 + 48))(v12, v25, v11);
        v15 = 10;
        v18 = v25;
        if ( v25[3] > 7u )
          v18 = (_QWORD *)v25[0];
        *(_QWORD *)&v22 = v18;
        v17 = v25[2];
      }
      *((_QWORD *)&v22 + 1) = v17;
      v24 = v15;
      std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(a1, a2, &v22, a4);
      if ( (v15 & 2) != 0 )
      {
        LOBYTE(v15) = v15 & 0xFD;
        std::wstring::~wstring(v25);
      }
      if ( (v15 & 1) != 0 )
        std::wstring::~wstring(v26);
    }
    else
    {
      v19 = L"true";
      if ( !a3 )
        v19 = L"false";
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      *(_QWORD *)&v22 = v19;
      *((_QWORD *)&v22 + 1) = v20;
      std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(a1, a2, &v22, a4);
    }
  }
  else
  {
    v22 = *(_OWORD *)a4;
    v23 = *(_DWORD *)(a4 + 16);
    std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned char>(
      a1,
      a2,
      a3,
      &v22,
      a5);
  }
  return a1;
}

```

## disassembly

```asm
0x18002c354  mov     [rsp-8+arg_8], rbx
0x18002c359  push    rbp
0x18002c35a  push    rsi
0x18002c35b  push    rdi
0x18002c35c  push    r12
0x18002c35e  push    r13
0x18002c360  push    r14
0x18002c362  push    r15
0x18002c364  lea     rbp, [rsp-1Fh]
0x18002c369  sub     rsp, 0A0h
0x18002c370  mov     rax, cs:__security_cookie
0x18002c377  xor     rax, rsp
0x18002c37a  mov     [rbp+4Fh+var_38], rax
0x18002c37e  mov     rsi, r9
0x18002c381  mov     r15b, r8b
0x18002c384  mov     rbx, rdx
0x18002c387  mov     r14, rcx
0x18002c38a  xor     r13d, r13d
0x18002c38d  mov     [rbp+4Fh+var_80], r13d
0x18002c391  mov     al, [r9+8]
0x18002c395  test    al, al
0x18002c397  jz      short loc_18002C3C6
0x18002c399  cmp     al, 73h ; 's'
0x18002c39b  jz      short loc_18002C3C6
0x18002c39d  movaps  xmm0, xmmword ptr [r9]
0x18002c3a1  movaps  [rbp+4Fh+var_A0], xmm0
0x18002c3a5  mov     ecx, [r9+10h]
0x18002c3a9  mov     [rbp+4Fh+var_90], ecx
0x18002c3ac  mov     rcx, [rbp+4Fh+arg_20]
0x18002c3b0  mov     [rsp+0D0h+var_B0], rcx
0x18002c3b5  lea     r9, [rbp+4Fh+var_A0]
0x18002c3b9  mov     rcx, r14
0x18002c3bc  call    ??$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@EU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,uchar,std::_Basic_format_specs<ushort>,std::_Lazy_locale)
0x18002c3c1  jmp     loc_18002C521
0x18002c3c6  cmp     [r9+0Ch], r13b
0x18002c3ca  jz      loc_18002C4EA
0x18002c3d0  mov     [r9+0Ch], r13b
0x18002c3d4  mov     rax, [rbp+4Fh+arg_20]
0x18002c3d8  test    rax, rax
0x18002c3db  jz      short loc_18002C3F6
0x18002c3dd  mov     rdi, [rax+8]
0x18002c3e1  mov     qword ptr [rbp+4Fh+var_A0+8], rdi
0x18002c3e5  mov     rax, [rdi]
0x18002c3e8  mov     rcx, rdi
0x18002c3eb  mov     rax, [rax+8]
0x18002c3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3f4  jmp     short loc_18002C405
0x18002c3f6  mov     cl, 1
0x18002c3f8  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002c3fe  mov     rdi, rax
0x18002c401  mov     qword ptr [rbp+4Fh+var_A0+8], rax
0x18002c405  lea     rcx, [rbp+4Fh+var_A0]
0x18002c409  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x18002c40e  mov     r12, rax
0x18002c411  test    rdi, rdi
0x18002c414  jz      short loc_18002C440
0x18002c416  mov     rcx, [rdi]
0x18002c419  mov     rax, [rcx+10h]
0x18002c41d  mov     rcx, rdi
0x18002c420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c425  mov     r8, rax
0x18002c428  test    rax, rax
0x18002c42b  jz      short loc_18002C440
0x18002c42d  mov     rcx, [rax]
0x18002c430  mov     rax, [rcx]
0x18002c433  mov     edx, 1
0x18002c438  mov     rcx, r8
0x18002c43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c440  mov     rax, [r12]
0x18002c444  mov     rcx, r12
0x18002c447  test    r15b, r15b
0x18002c44a  jz      short loc_18002C477
0x18002c44c  lea     rdx, [rbp+4Fh+var_58]
0x18002c450  mov     rax, [rax+38h]
0x18002c454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c459  nop
0x18002c45a  mov     edi, 5
0x18002c45f  lea     rax, [rbp+4Fh+var_58]
0x18002c463  cmp     [rbp+4Fh+var_40], 7
0x18002c468  cmova   rax, [rbp+4Fh+var_58]
0x18002c46d  mov     qword ptr [rbp+4Fh+var_A0], rax
0x18002c471  mov     rax, [rbp+4Fh+var_48]
0x18002c475  jmp     short loc_18002C4A0
0x18002c477  lea     rdx, [rbp+4Fh+var_78]
0x18002c47b  mov     rax, [rax+30h]
0x18002c47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c484  nop
0x18002c485  mov     edi, 0Ah
0x18002c48a  lea     rax, [rbp+4Fh+var_78]
0x18002c48e  cmp     [rbp+4Fh+var_60], 7
0x18002c493  cmova   rax, [rbp+4Fh+var_78]
0x18002c498  mov     qword ptr [rbp+4Fh+var_A0], rax
0x18002c49c  mov     rax, [rbp+4Fh+var_68]
0x18002c4a0  mov     qword ptr [rbp+4Fh+var_A0+8], rax
0x18002c4a4  lea     rax, [rbp+4Fh+var_A0]
0x18002c4a8  mov     [rbp+4Fh+var_80], edi
0x18002c4ab  movups  xmm0, xmmword ptr [rax]
0x18002c4ae  movdqu  [rbp+4Fh+var_A0], xmm0
0x18002c4b3  mov     r9, rsi
0x18002c4b6  lea     r8, [rbp+4Fh+var_A0]
0x18002c4ba  mov     rdx, rbx
0x18002c4bd  mov     rcx, r14
0x18002c4c0  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@V?$basic_string_view@GU?$char_traits@G@std@@@0@AEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::basic_string_view<ushort>,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)
0x18002c4c5  nop
0x18002c4c6  test    dil, 2
0x18002c4ca  jz      short loc_18002C4D9
0x18002c4cc  and     edi, 0FFFFFFFDh
0x18002c4cf  lea     rcx, [rbp+4Fh+var_78]; void *
0x18002c4d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c4d8  nop
0x18002c4d9  test    dil, 1
0x18002c4dd  jz      short loc_18002C521
0x18002c4df  lea     rcx, [rbp+4Fh+var_58]; void *
0x18002c4e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c4e8  jmp     short loc_18002C521
0x18002c4ea  lea     rax, aFalse_0; "false"
0x18002c4f1  lea     rcx, aTrue; "true"
0x18002c4f8  test    r15b, r15b
0x18002c4fb  cmovz   rcx, rax
0x18002c4ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c503  inc     rax
0x18002c506  cmp     [rcx+rax*2], r13w
0x18002c50b  jnz     short loc_18002C503
0x18002c50d  mov     qword ptr [rbp+4Fh+var_A0], rcx
0x18002c511  mov     qword ptr [rbp+4Fh+var_A0+8], rax
0x18002c515  lea     r8, [rbp+4Fh+var_A0]
0x18002c519  mov     rcx, r14
0x18002c51c  call    ??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@V?$basic_string_view@GU?$char_traits@G@std@@@0@AEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z; std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::basic_string_view<ushort>,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)
0x18002c521  mov     rax, r14
0x18002c524  mov     rcx, [rbp+4Fh+var_38]
0x18002c528  xor     rcx, rsp; StackCookie
0x18002c52b  call    __security_check_cookie
0x18002c530  mov     rbx, [rsp+0D0h+arg_8]
0x18002c538  add     rsp, 0A0h
0x18002c53f  pop     r15
0x18002c541  pop     r14
0x18002c543  pop     r13
0x18002c545  pop     r12
0x18002c547  pop     rdi
0x18002c548  pop     rsi
0x18002c549  pop     rbp
0x18002c54a  retn
```
