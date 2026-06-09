# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x180054ab4`
- end: `0x180054c53`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@HU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `415`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180051e38`
- `0x180052728`

## callees

- `0x180051b6c`
- `0x1800535e8`
- `0x1800536f8`
- `0x180053d44`
- `0x180054ab4`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180054b8e`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180054b8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>'::`2'::_lambda_1_::operator()(
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
  v7 = (__int64 *)std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(
                    &v24,
                    a3,
                    v6,
                    **(_DWORD **)(a1 + 16) >> 31);
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
0x180054ab4  mov     r11, rsp
0x180054ab7  push    rbx
0x180054ab8  push    rbp
0x180054ab9  push    rsi
0x180054aba  push    rdi
0x180054abb  sub     rsp, 68h
0x180054abf  mov     rax, r8
0x180054ac2  mov     rbp, rdx
0x180054ac5  mov     rdi, rcx
0x180054ac8  mov     r8, [rcx+10h]
0x180054acc  mov     r9d, [r8]
0x180054acf  shr     r9d, 1Fh
0x180054ad3  mov     r8, [rcx+8]
0x180054ad7  mov     r8b, [r8+0Ah]
0x180054adb  mov     rdx, rax
0x180054ade  lea     rcx, [r11+8]
0x180054ae2  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x180054ae7  mov     rcx, [rdi+18h]
0x180054aeb  mov     rdx, [rcx]
0x180054aee  mov     r8, [rcx+8]
0x180054af2  add     r8, rdx
0x180054af5  mov     r9, [rax]
0x180054af8  lea     rcx, [rsp+88h+arg_0]
0x180054b00  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180054b05  mov     rbx, [rax]
0x180054b08  mov     rax, [rdi+20h]
0x180054b0c  cmp     byte ptr [rax], 0
0x180054b0f  jz      short loc_180054B5B
0x180054b11  mov     rax, [rdi+8]
0x180054b15  mov     ecx, [rax]
0x180054b17  mov     rax, [rdi+28h]
0x180054b1b  cmp     [rax], ecx
0x180054b1d  jge     short loc_180054B5B
0x180054b1f  sub     ecx, [rax]
0x180054b21  movsxd  rsi, ecx
0x180054b24  test    ecx, ecx
0x180054b26  jle     short loc_180054B5B
0x180054b28  mov     rdx, [rbx+10h]
0x180054b2c  inc     rdx
0x180054b2f  cmp     rdx, [rbx+18h]
0x180054b33  jbe     short loc_180054B43
0x180054b35  mov     rax, [rbx]
0x180054b38  mov     rcx, rbx
0x180054b3b  mov     rax, [rax]
0x180054b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b43  mov     rcx, [rbx+10h]
0x180054b47  mov     rax, [rbx+8]
0x180054b4b  mov     byte ptr [rcx+rax], 30h ; '0'
0x180054b4f  inc     qword ptr [rbx+10h]
0x180054b53  dec     rsi
0x180054b56  test    rsi, rsi
0x180054b59  jg      short loc_180054B28
0x180054b5b  mov     rax, [rdi+30h]
0x180054b5f  mov     esi, [rax]
0x180054b61  test    esi, esi
0x180054b63  jle     loc_180054C32
0x180054b69  mov     rax, [rdi+48h]
0x180054b6d  mov     rcx, [rax]
0x180054b70  test    rcx, rcx
0x180054b73  jz      short loc_180054B8C
0x180054b75  mov     rcx, [rcx+8]
0x180054b79  mov     [rsp+88h+var_40], rcx
0x180054b7e  mov     rax, [rcx]
0x180054b81  mov     rax, [rax+8]
0x180054b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b8a  jmp     short loc_180054B99
0x180054b8c  mov     cl, 1
0x180054b8e  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180054b94  mov     [rsp+88h+var_40], rax
0x180054b99  lea     rcx, [rsp+88h+var_48]
0x180054b9e  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180054ba3  mov     rdx, rax
0x180054ba6  mov     rcx, [rax]
0x180054ba9  mov     rax, [rcx+20h]
0x180054bad  mov     rcx, rdx
0x180054bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bb5  mov     r8b, al
0x180054bb8  mov     rax, [rdi+40h]
0x180054bbc  cmp     qword ptr [rax+18h], 0Fh
0x180054bc1  jbe     short loc_180054BC8
0x180054bc3  mov     rcx, [rax]
0x180054bc6  jmp     short loc_180054BCB
0x180054bc8  mov     rcx, rax
0x180054bcb  mov     [rsp+88h+var_38], rcx
0x180054bd0  mov     rax, [rax+10h]
0x180054bd4  mov     [rsp+88h+var_30], rax
0x180054bd9  mov     rdx, [rdi+38h]
0x180054bdd  mov     [rsp+88h+var_58], rbx
0x180054be2  mov     [rsp+88h+var_60], esi
0x180054be6  mov     [rsp+88h+var_68], r8b
0x180054beb  lea     r9, [rsp+88h+var_38]
0x180054bf0  mov     r8, [rdi]
0x180054bf3  mov     rdx, [rdx]
0x180054bf6  mov     rcx, rbp
0x180054bf9  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180054bfe  nop
0x180054bff  mov     rcx, [rsp+88h+var_40]
0x180054c04  test    rcx, rcx
0x180054c07  jz      short loc_180054C47
0x180054c09  mov     rax, [rcx]
0x180054c0c  mov     rax, [rax+10h]
0x180054c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c15  mov     r8, rax
0x180054c18  test    rax, rax
0x180054c1b  jz      short loc_180054C47
0x180054c1d  mov     rcx, [rax]
0x180054c20  mov     rax, [rcx]
0x180054c23  mov     edx, 1
0x180054c28  mov     rcx, r8
0x180054c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c30  jmp     short loc_180054C47
0x180054c32  mov     rdx, [rdi+38h]
0x180054c36  mov     r9, rbx
0x180054c39  mov     r8, [rdi]
0x180054c3c  mov     rdx, [rdx]
0x180054c3f  mov     rcx, rbp
0x180054c42  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180054c47  mov     rax, rbp
0x180054c4a  add     rsp, 68h
0x180054c4e  pop     rdi
0x180054c4f  pop     rsi
0x180054c50  pop     rbp
0x180054c51  pop     rbx
0x180054c52  retn
```
