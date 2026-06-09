# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x180036c6c`
- end: `0x180036e03`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@EU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `407`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800329d4`
- `0x180033000`

## callees

- `0x180032838`
- `0x1800342b4`
- `0x1800343c4`
- `0x180035ca4`
- `0x180036c6c`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180036d3e`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180036d3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned char>'::`2'::_lambda_1_::operator()(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v6; // r8
  __int64 *v7; // rax
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
  __int64 v24; // [rsp+90h] [rbp+8h] BYREF

  v6 = *(_QWORD *)(a1 + 8);
  LOBYTE(v6) = *(_BYTE *)(v6 + 10);
  v7 = (__int64 *)std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(&v24, a3, v6, 0);
  v8 = *std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
          &v24,
          **(char ***)(a1 + 24),
          (char *)(**(_QWORD **)(a1 + 24) + *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL)),
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
        *(_BYTE *)(*(_QWORD *)(v8 + 16) + *(_QWORD *)(v8 + 8)) = 48;
        ++*(_QWORD *)(v8 + 16);
      }
    }
  }
  v13 = **(_DWORD **)(a1 + 48);
  if ( v13 <= 0 )
  {
    std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
      a2,
      **(char ***)(a1 + 56),
      *(char **)a1,
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
      (_DWORD)a2,
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
0x180036c6c  mov     r11, rsp
0x180036c6f  push    rbx
0x180036c70  push    rbp
0x180036c71  push    rsi
0x180036c72  push    rdi
0x180036c73  sub     rsp, 68h
0x180036c77  mov     rax, r8
0x180036c7a  mov     rbp, rdx
0x180036c7d  mov     rdi, rcx
0x180036c80  mov     r8, [rcx+8]
0x180036c84  xor     r9d, r9d
0x180036c87  mov     r8b, [r8+0Ah]
0x180036c8b  mov     rdx, rax
0x180036c8e  lea     rcx, [r11+8]
0x180036c92  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x180036c97  mov     r8, [rdi+18h]
0x180036c9b  mov     rdx, [r8]
0x180036c9e  mov     r8, [r8+8]
0x180036ca2  add     r8, rdx
0x180036ca5  mov     r9, [rax]
0x180036ca8  lea     rcx, [rsp+88h+arg_0]
0x180036cb0  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180036cb5  mov     rbx, [rax]
0x180036cb8  mov     rax, [rdi+20h]
0x180036cbc  cmp     byte ptr [rax], 0
0x180036cbf  jz      short loc_180036D0B
0x180036cc1  mov     rax, [rdi+8]
0x180036cc5  mov     ecx, [rax]
0x180036cc7  mov     rax, [rdi+28h]
0x180036ccb  cmp     [rax], ecx
0x180036ccd  jge     short loc_180036D0B
0x180036ccf  sub     ecx, [rax]
0x180036cd1  movsxd  rsi, ecx
0x180036cd4  test    ecx, ecx
0x180036cd6  jle     short loc_180036D0B
0x180036cd8  mov     rdx, [rbx+10h]
0x180036cdc  inc     rdx
0x180036cdf  cmp     rdx, [rbx+18h]
0x180036ce3  jbe     short loc_180036CF3
0x180036ce5  mov     rax, [rbx]
0x180036ce8  mov     rcx, rbx
0x180036ceb  mov     rax, [rax]
0x180036cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cf3  mov     rcx, [rbx+10h]
0x180036cf7  mov     rax, [rbx+8]
0x180036cfb  mov     byte ptr [rcx+rax], 30h ; '0'
0x180036cff  inc     qword ptr [rbx+10h]
0x180036d03  dec     rsi
0x180036d06  test    rsi, rsi
0x180036d09  jg      short loc_180036CD8
0x180036d0b  mov     rax, [rdi+30h]
0x180036d0f  mov     esi, [rax]
0x180036d11  test    esi, esi
0x180036d13  jle     loc_180036DE2
0x180036d19  mov     rax, [rdi+48h]
0x180036d1d  mov     rcx, [rax]
0x180036d20  test    rcx, rcx
0x180036d23  jz      short loc_180036D3C
0x180036d25  mov     rcx, [rcx+8]
0x180036d29  mov     [rsp+88h+var_40], rcx
0x180036d2e  mov     rax, [rcx]
0x180036d31  mov     rax, [rax+8]
0x180036d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d3a  jmp     short loc_180036D49
0x180036d3c  mov     cl, 1
0x180036d3e  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180036d44  mov     [rsp+88h+var_40], rax
0x180036d49  lea     rcx, [rsp+88h+var_48]
0x180036d4e  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180036d53  mov     rdx, rax
0x180036d56  mov     rcx, [rax]
0x180036d59  mov     rax, [rcx+20h]
0x180036d5d  mov     rcx, rdx
0x180036d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d65  mov     r8b, al
0x180036d68  mov     rax, [rdi+40h]
0x180036d6c  cmp     qword ptr [rax+18h], 0Fh
0x180036d71  jbe     short loc_180036D78
0x180036d73  mov     rcx, [rax]
0x180036d76  jmp     short loc_180036D7B
0x180036d78  mov     rcx, rax
0x180036d7b  mov     [rsp+88h+var_38], rcx
0x180036d80  mov     rax, [rax+10h]
0x180036d84  mov     [rsp+88h+var_30], rax
0x180036d89  mov     rdx, [rdi+38h]
0x180036d8d  mov     [rsp+88h+var_58], rbx
0x180036d92  mov     [rsp+88h+var_60], esi
0x180036d96  mov     [rsp+88h+var_68], r8b
0x180036d9b  lea     r9, [rsp+88h+var_38]
0x180036da0  mov     r8, [rdi]
0x180036da3  mov     rdx, [rdx]
0x180036da6  mov     rcx, rbp
0x180036da9  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180036dae  nop
0x180036daf  mov     rcx, [rsp+88h+var_40]
0x180036db4  test    rcx, rcx
0x180036db7  jz      short loc_180036DF7
0x180036db9  mov     rax, [rcx]
0x180036dbc  mov     rax, [rax+10h]
0x180036dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036dc5  mov     r8, rax
0x180036dc8  test    rax, rax
0x180036dcb  jz      short loc_180036DF7
0x180036dcd  mov     rcx, [rax]
0x180036dd0  mov     rax, [rcx]
0x180036dd3  mov     edx, 1
0x180036dd8  mov     rcx, r8
0x180036ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036de0  jmp     short loc_180036DF7
0x180036de2  mov     rdx, [rdi+38h]
0x180036de6  mov     r9, rbx
0x180036de9  mov     r8, [rdi]
0x180036dec  mov     rdx, [rdx]
0x180036def  mov     rcx, rbp
0x180036df2  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180036df7  mov     rax, rbp
0x180036dfa  add     rsp, 68h
0x180036dfe  pop     rdi
0x180036dff  pop     rsi
0x180036e00  pop     rbp
0x180036e01  pop     rbx
0x180036e02  retn
```
