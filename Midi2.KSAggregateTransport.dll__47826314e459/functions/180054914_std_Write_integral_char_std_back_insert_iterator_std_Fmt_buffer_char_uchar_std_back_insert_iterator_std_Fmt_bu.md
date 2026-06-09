# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x180054914`
- end: `0x180054aab`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@EU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `407`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180051d08`
- `0x180052334`

## callees

- `0x180051b6c`
- `0x1800535e8`
- `0x1800536f8`
- `0x180053d44`
- `0x180054914`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1800549e6`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1800549e6`

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
0x180054914  mov     r11, rsp
0x180054917  push    rbx
0x180054918  push    rbp
0x180054919  push    rsi
0x18005491a  push    rdi
0x18005491b  sub     rsp, 68h
0x18005491f  mov     rax, r8
0x180054922  mov     rbp, rdx
0x180054925  mov     rdi, rcx
0x180054928  mov     r8, [rcx+8]
0x18005492c  xor     r9d, r9d
0x18005492f  mov     r8b, [r8+0Ah]
0x180054933  mov     rdx, rax
0x180054936  lea     rcx, [r11+8]
0x18005493a  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x18005493f  mov     r8, [rdi+18h]
0x180054943  mov     rdx, [r8]
0x180054946  mov     r8, [r8+8]
0x18005494a  add     r8, rdx
0x18005494d  mov     r9, [rax]
0x180054950  lea     rcx, [rsp+88h+arg_0]
0x180054958  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18005495d  mov     rbx, [rax]
0x180054960  mov     rax, [rdi+20h]
0x180054964  cmp     byte ptr [rax], 0
0x180054967  jz      short loc_1800549B3
0x180054969  mov     rax, [rdi+8]
0x18005496d  mov     ecx, [rax]
0x18005496f  mov     rax, [rdi+28h]
0x180054973  cmp     [rax], ecx
0x180054975  jge     short loc_1800549B3
0x180054977  sub     ecx, [rax]
0x180054979  movsxd  rsi, ecx
0x18005497c  test    ecx, ecx
0x18005497e  jle     short loc_1800549B3
0x180054980  mov     rdx, [rbx+10h]
0x180054984  inc     rdx
0x180054987  cmp     rdx, [rbx+18h]
0x18005498b  jbe     short loc_18005499B
0x18005498d  mov     rax, [rbx]
0x180054990  mov     rcx, rbx
0x180054993  mov     rax, [rax]
0x180054996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005499b  mov     rcx, [rbx+10h]
0x18005499f  mov     rax, [rbx+8]
0x1800549a3  mov     byte ptr [rcx+rax], 30h ; '0'
0x1800549a7  inc     qword ptr [rbx+10h]
0x1800549ab  dec     rsi
0x1800549ae  test    rsi, rsi
0x1800549b1  jg      short loc_180054980
0x1800549b3  mov     rax, [rdi+30h]
0x1800549b7  mov     esi, [rax]
0x1800549b9  test    esi, esi
0x1800549bb  jle     loc_180054A8A
0x1800549c1  mov     rax, [rdi+48h]
0x1800549c5  mov     rcx, [rax]
0x1800549c8  test    rcx, rcx
0x1800549cb  jz      short loc_1800549E4
0x1800549cd  mov     rcx, [rcx+8]
0x1800549d1  mov     [rsp+88h+var_40], rcx
0x1800549d6  mov     rax, [rcx]
0x1800549d9  mov     rax, [rax+8]
0x1800549dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549e2  jmp     short loc_1800549F1
0x1800549e4  mov     cl, 1
0x1800549e6  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x1800549ec  mov     [rsp+88h+var_40], rax
0x1800549f1  lea     rcx, [rsp+88h+var_48]
0x1800549f6  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x1800549fb  mov     rdx, rax
0x1800549fe  mov     rcx, [rax]
0x180054a01  mov     rax, [rcx+20h]
0x180054a05  mov     rcx, rdx
0x180054a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a0d  mov     r8b, al
0x180054a10  mov     rax, [rdi+40h]
0x180054a14  cmp     qword ptr [rax+18h], 0Fh
0x180054a19  jbe     short loc_180054A20
0x180054a1b  mov     rcx, [rax]
0x180054a1e  jmp     short loc_180054A23
0x180054a20  mov     rcx, rax
0x180054a23  mov     [rsp+88h+var_38], rcx
0x180054a28  mov     rax, [rax+10h]
0x180054a2c  mov     [rsp+88h+var_30], rax
0x180054a31  mov     rdx, [rdi+38h]
0x180054a35  mov     [rsp+88h+var_58], rbx
0x180054a3a  mov     [rsp+88h+var_60], esi
0x180054a3e  mov     [rsp+88h+var_68], r8b
0x180054a43  lea     r9, [rsp+88h+var_38]
0x180054a48  mov     r8, [rdi]
0x180054a4b  mov     rdx, [rdx]
0x180054a4e  mov     rcx, rbp
0x180054a51  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180054a56  nop
0x180054a57  mov     rcx, [rsp+88h+var_40]
0x180054a5c  test    rcx, rcx
0x180054a5f  jz      short loc_180054A9F
0x180054a61  mov     rax, [rcx]
0x180054a64  mov     rax, [rax+10h]
0x180054a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a6d  mov     r8, rax
0x180054a70  test    rax, rax
0x180054a73  jz      short loc_180054A9F
0x180054a75  mov     rcx, [rax]
0x180054a78  mov     rax, [rcx]
0x180054a7b  mov     edx, 1
0x180054a80  mov     rcx, r8
0x180054a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a88  jmp     short loc_180054A9F
0x180054a8a  mov     rdx, [rdi+38h]
0x180054a8e  mov     r9, rbx
0x180054a91  mov     r8, [rdi]
0x180054a94  mov     rdx, [rdx]
0x180054a97  mov     rcx, rbp
0x180054a9a  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180054a9f  mov     rax, rbp
0x180054aa2  add     rsp, 68h
0x180054aa6  pop     rdi
0x180054aa7  pop     rsi
0x180054aa8  pop     rbp
0x180054aa9  pop     rbx
0x180054aaa  retn
```
