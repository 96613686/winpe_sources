# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x18002b9a4`
- end: `0x18002bb3b`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_KU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `407`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180027998`
- `0x180028510`
- `0x180028c74`

## callees

- `0x18002759c`
- `0x180029018`
- `0x180029128`
- `0x18002a6a0`
- `0x18002b9a4`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002ba76`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002ba76`

## pseudocode

```c
__int64 __fastcall `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>'::`2'::_lambda_1_::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r8
  _QWORD *v7; // rax
  __int64 v8; // rbx
  int v9; // ecx
  _DWORD *v10; // rax
  int v11; // ecx
  __int64 i; // rsi
  int v13; // esi
  __int64 v14; // rax
  __int64 v15; // rax
  char v16; // r8
  __int64 *v17; // rax
  __int64 v18; // rcx
  void (__fastcall ***v19)(_QWORD, __int64); // rax
  _BYTE v21[8]; // [rsp+40h] [rbp-48h] BYREF
  struct std::locale::_Locimp *v22; // [rsp+48h] [rbp-40h]
  _QWORD v23[7]; // [rsp+50h] [rbp-38h] BYREF
  char v24; // [rsp+90h] [rbp+8h] BYREF

  v6 = *(_QWORD *)(a1 + 8);
  LOBYTE(v6) = *(_BYTE *)(v6 + 10);
  v7 = (_QWORD *)std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(&v24, a3, v6, 0);
  v8 = *(_QWORD *)std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
                    &v24,
                    **(_QWORD **)(a1 + 24),
                    **(_QWORD **)(a1 + 24) + *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
                    *v7);
  if ( **(_BYTE **)(a1 + 32) )
  {
    v9 = **(_DWORD **)(a1 + 8);
    v10 = *(_DWORD **)(a1 + 40);
    if ( *v10 < v9 )
    {
      v11 = v9 - *v10;
      for ( i = v11; i > 0; --i )
      {
        if ( (unsigned __int64)(*(_QWORD *)(v8 + 16) + 1LL) > *(_QWORD *)(v8 + 24) )
          (**(void (__fastcall ***)(__int64))v8)(v8);
        *(_BYTE *)(*(_QWORD *)(v8 + 8) + (*(_QWORD *)(v8 + 16))++) = 48;
      }
    }
  }
  v13 = **(_DWORD **)(a1 + 48);
  if ( v13 <= 0 )
  {
    std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
      a2,
      **(_QWORD **)(a1 + 56),
      *(_QWORD *)a1,
      v8);
  }
  else
  {
    v14 = *(_QWORD *)(a1 + 72);
    if ( *(_QWORD *)v14 )
    {
      v22 = *(struct std::locale::_Locimp **)(*(_QWORD *)v14 + 8LL);
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v22 + 8LL))(v22);
    }
    else
    {
      v22 = std::locale::_Init(1);
    }
    v15 = std::use_facet<std::numpunct<char>>(v21);
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 32LL))(v15);
    v17 = *(__int64 **)(a1 + 64);
    if ( (unsigned __int64)v17[3] <= 0xF )
      v18 = *(_QWORD *)(a1 + 64);
    else
      v18 = *v17;
    v23[0] = v18;
    v23[1] = v17[2];
    std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
      a2,
      **(_QWORD **)(a1 + 56),
      *(_QWORD *)a1,
      (unsigned int)v23,
      v16,
      v13,
      v8);
    if ( v22 )
    {
      v19 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v22 + 16LL))(v22);
      if ( v19 )
        (**v19)(v19, 1);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18002b9a4  mov     r11, rsp
0x18002b9a7  push    rbx
0x18002b9a8  push    rbp
0x18002b9a9  push    rsi
0x18002b9aa  push    rdi
0x18002b9ab  sub     rsp, 68h
0x18002b9af  mov     rax, r8
0x18002b9b2  mov     rbp, rdx
0x18002b9b5  mov     rdi, rcx
0x18002b9b8  mov     r8, [rcx+8]
0x18002b9bc  xor     r9d, r9d
0x18002b9bf  mov     r8b, [r8+0Ah]
0x18002b9c3  mov     rdx, rax
0x18002b9c6  lea     rcx, [r11+8]
0x18002b9ca  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x18002b9cf  mov     r8, [rdi+18h]
0x18002b9d3  mov     rdx, [r8]
0x18002b9d6  mov     r8, [r8+8]
0x18002b9da  add     r8, rdx
0x18002b9dd  mov     r9, [rax]
0x18002b9e0  lea     rcx, [rsp+88h+arg_0]
0x18002b9e8  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002b9ed  mov     rbx, [rax]
0x18002b9f0  mov     rax, [rdi+20h]
0x18002b9f4  cmp     byte ptr [rax], 0
0x18002b9f7  jz      short loc_18002BA43
0x18002b9f9  mov     rax, [rdi+8]
0x18002b9fd  mov     ecx, [rax]
0x18002b9ff  mov     rax, [rdi+28h]
0x18002ba03  cmp     [rax], ecx
0x18002ba05  jge     short loc_18002BA43
0x18002ba07  sub     ecx, [rax]
0x18002ba09  movsxd  rsi, ecx
0x18002ba0c  test    ecx, ecx
0x18002ba0e  jle     short loc_18002BA43
0x18002ba10  mov     rdx, [rbx+10h]
0x18002ba14  inc     rdx
0x18002ba17  cmp     rdx, [rbx+18h]
0x18002ba1b  jbe     short loc_18002BA2B
0x18002ba1d  mov     rax, [rbx]
0x18002ba20  mov     rcx, rbx
0x18002ba23  mov     rax, [rax]
0x18002ba26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba2b  mov     rcx, [rbx+8]
0x18002ba2f  mov     rax, [rbx+10h]
0x18002ba33  mov     byte ptr [rcx+rax], 30h ; '0'
0x18002ba37  inc     qword ptr [rbx+10h]
0x18002ba3b  dec     rsi
0x18002ba3e  test    rsi, rsi
0x18002ba41  jg      short loc_18002BA10
0x18002ba43  mov     rax, [rdi+30h]
0x18002ba47  mov     esi, [rax]
0x18002ba49  test    esi, esi
0x18002ba4b  jle     loc_18002BB1A
0x18002ba51  mov     rax, [rdi+48h]
0x18002ba55  mov     rcx, [rax]
0x18002ba58  test    rcx, rcx
0x18002ba5b  jz      short loc_18002BA74
0x18002ba5d  mov     rcx, [rcx+8]
0x18002ba61  mov     [rsp+88h+var_40], rcx
0x18002ba66  mov     rax, [rcx]
0x18002ba69  mov     rax, [rax+8]
0x18002ba6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba72  jmp     short loc_18002BA81
0x18002ba74  mov     cl, 1
0x18002ba76  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002ba7c  mov     [rsp+88h+var_40], rax
0x18002ba81  lea     rcx, [rsp+88h+var_48]
0x18002ba86  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002ba8b  mov     rdx, rax
0x18002ba8e  mov     rcx, [rax]
0x18002ba91  mov     rax, [rcx+20h]
0x18002ba95  mov     rcx, rdx
0x18002ba98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba9d  mov     r8b, al
0x18002baa0  mov     rax, [rdi+40h]
0x18002baa4  cmp     qword ptr [rax+18h], 0Fh
0x18002baa9  jbe     short loc_18002BAB0
0x18002baab  mov     rcx, [rax]
0x18002baae  jmp     short loc_18002BAB3
0x18002bab0  mov     rcx, rax
0x18002bab3  mov     [rsp+88h+var_38], rcx
0x18002bab8  mov     rax, [rax+10h]
0x18002babc  mov     [rsp+88h+var_30], rax
0x18002bac1  mov     rdx, [rdi+38h]
0x18002bac5  mov     [rsp+88h+var_58], rbx
0x18002baca  mov     [rsp+88h+var_60], esi
0x18002bace  mov     [rsp+88h+var_68], r8b
0x18002bad3  lea     r9, [rsp+88h+var_38]
0x18002bad8  mov     r8, [rdi]
0x18002badb  mov     rdx, [rdx]
0x18002bade  mov     rcx, rbp
0x18002bae1  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002bae6  nop
0x18002bae7  mov     rcx, [rsp+88h+var_40]
0x18002baec  test    rcx, rcx
0x18002baef  jz      short loc_18002BB2F
0x18002baf1  mov     rax, [rcx]
0x18002baf4  mov     rax, [rax+10h]
0x18002baf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bafd  mov     r8, rax
0x18002bb00  test    rax, rax
0x18002bb03  jz      short loc_18002BB2F
0x18002bb05  mov     rcx, [rax]
0x18002bb08  mov     rax, [rcx]
0x18002bb0b  mov     edx, 1
0x18002bb10  mov     rcx, r8
0x18002bb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb18  jmp     short loc_18002BB2F
0x18002bb1a  mov     rdx, [rdi+38h]
0x18002bb1e  mov     r9, rbx
0x18002bb21  mov     r8, [rdi]
0x18002bb24  mov     rdx, [rdx]
0x18002bb27  mov     rcx, rbp
0x18002bb2a  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002bb2f  mov     rax, rbp
0x18002bb32  add     rsp, 68h
0x18002bb36  pop     rdi
0x18002bb37  pop     rsi
0x18002bb38  pop     rbp
0x18002bb39  pop     rbx
0x18002bb3a  retn
```
