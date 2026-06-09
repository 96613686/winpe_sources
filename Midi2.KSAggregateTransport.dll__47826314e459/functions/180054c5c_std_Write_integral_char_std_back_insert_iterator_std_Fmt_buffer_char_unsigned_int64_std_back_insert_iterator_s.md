# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x180054c5c`
- end: `0x180054df3`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_KU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `407`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180051f68`
- `0x180052ae0`
- `0x180053244`

## callees

- `0x180051b6c`
- `0x1800535e8`
- `0x1800536f8`
- `0x180053d44`
- `0x180054c5c`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180054d2e`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180054d2e`

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
0x180054c5c  mov     r11, rsp
0x180054c5f  push    rbx
0x180054c60  push    rbp
0x180054c61  push    rsi
0x180054c62  push    rdi
0x180054c63  sub     rsp, 68h
0x180054c67  mov     rax, r8
0x180054c6a  mov     rbp, rdx
0x180054c6d  mov     rdi, rcx
0x180054c70  mov     r8, [rcx+8]
0x180054c74  xor     r9d, r9d
0x180054c77  mov     r8b, [r8+0Ah]
0x180054c7b  mov     rdx, rax
0x180054c7e  lea     rcx, [r11+8]
0x180054c82  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x180054c87  mov     r8, [rdi+18h]
0x180054c8b  mov     rdx, [r8]
0x180054c8e  mov     r8, [r8+8]
0x180054c92  add     r8, rdx
0x180054c95  mov     r9, [rax]
0x180054c98  lea     rcx, [rsp+88h+arg_0]
0x180054ca0  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180054ca5  mov     rbx, [rax]
0x180054ca8  mov     rax, [rdi+20h]
0x180054cac  cmp     byte ptr [rax], 0
0x180054caf  jz      short loc_180054CFB
0x180054cb1  mov     rax, [rdi+8]
0x180054cb5  mov     ecx, [rax]
0x180054cb7  mov     rax, [rdi+28h]
0x180054cbb  cmp     [rax], ecx
0x180054cbd  jge     short loc_180054CFB
0x180054cbf  sub     ecx, [rax]
0x180054cc1  movsxd  rsi, ecx
0x180054cc4  test    ecx, ecx
0x180054cc6  jle     short loc_180054CFB
0x180054cc8  mov     rdx, [rbx+10h]
0x180054ccc  inc     rdx
0x180054ccf  cmp     rdx, [rbx+18h]
0x180054cd3  jbe     short loc_180054CE3
0x180054cd5  mov     rax, [rbx]
0x180054cd8  mov     rcx, rbx
0x180054cdb  mov     rax, [rax]
0x180054cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ce3  mov     rcx, [rbx+8]
0x180054ce7  mov     rax, [rbx+10h]
0x180054ceb  mov     byte ptr [rcx+rax], 30h ; '0'
0x180054cef  inc     qword ptr [rbx+10h]
0x180054cf3  dec     rsi
0x180054cf6  test    rsi, rsi
0x180054cf9  jg      short loc_180054CC8
0x180054cfb  mov     rax, [rdi+30h]
0x180054cff  mov     esi, [rax]
0x180054d01  test    esi, esi
0x180054d03  jle     loc_180054DD2
0x180054d09  mov     rax, [rdi+48h]
0x180054d0d  mov     rcx, [rax]
0x180054d10  test    rcx, rcx
0x180054d13  jz      short loc_180054D2C
0x180054d15  mov     rcx, [rcx+8]
0x180054d19  mov     [rsp+88h+var_40], rcx
0x180054d1e  mov     rax, [rcx]
0x180054d21  mov     rax, [rax+8]
0x180054d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d2a  jmp     short loc_180054D39
0x180054d2c  mov     cl, 1
0x180054d2e  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180054d34  mov     [rsp+88h+var_40], rax
0x180054d39  lea     rcx, [rsp+88h+var_48]
0x180054d3e  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180054d43  mov     rdx, rax
0x180054d46  mov     rcx, [rax]
0x180054d49  mov     rax, [rcx+20h]
0x180054d4d  mov     rcx, rdx
0x180054d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d55  mov     r8b, al
0x180054d58  mov     rax, [rdi+40h]
0x180054d5c  cmp     qword ptr [rax+18h], 0Fh
0x180054d61  jbe     short loc_180054D68
0x180054d63  mov     rcx, [rax]
0x180054d66  jmp     short loc_180054D6B
0x180054d68  mov     rcx, rax
0x180054d6b  mov     [rsp+88h+var_38], rcx
0x180054d70  mov     rax, [rax+10h]
0x180054d74  mov     [rsp+88h+var_30], rax
0x180054d79  mov     rdx, [rdi+38h]
0x180054d7d  mov     [rsp+88h+var_58], rbx
0x180054d82  mov     [rsp+88h+var_60], esi
0x180054d86  mov     [rsp+88h+var_68], r8b
0x180054d8b  lea     r9, [rsp+88h+var_38]
0x180054d90  mov     r8, [rdi]
0x180054d93  mov     rdx, [rdx]
0x180054d96  mov     rcx, rbp
0x180054d99  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180054d9e  nop
0x180054d9f  mov     rcx, [rsp+88h+var_40]
0x180054da4  test    rcx, rcx
0x180054da7  jz      short loc_180054DE7
0x180054da9  mov     rax, [rcx]
0x180054dac  mov     rax, [rax+10h]
0x180054db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054db5  mov     r8, rax
0x180054db8  test    rax, rax
0x180054dbb  jz      short loc_180054DE7
0x180054dbd  mov     rcx, [rax]
0x180054dc0  mov     rax, [rcx]
0x180054dc3  mov     edx, 1
0x180054dc8  mov     rcx, r8
0x180054dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054dd0  jmp     short loc_180054DE7
0x180054dd2  mov     rdx, [rdi+38h]
0x180054dd6  mov     r9, rbx
0x180054dd9  mov     r8, [rdi]
0x180054ddc  mov     rdx, [rdx]
0x180054ddf  mov     rcx, rbp
0x180054de2  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180054de7  mov     rax, rbp
0x180054dea  add     rsp, 68h
0x180054dee  pop     rdi
0x180054def  pop     rsi
0x180054df0  pop     rbp
0x180054df1  pop     rbx
0x180054df2  retn
```
