# `std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,long double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x1800369ac`
- end: `0x180036c65`
- name: `??R_lambda_1_@?1???$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@OAEBU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `697`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18002f348`
- `0x18002fa10`
- `0x1800300e0`

## callees

- `0x180032838`
- `0x1800342b4`
- `0x1800343c4`
- `0x180035ca4`
- `0x1800369ac`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180036a6a`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180036a6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall `std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>'::`2'::_lambda_1_::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _BYTE *v6; // r9
  _BYTE *v7; // r8
  __int64 v8; // rbx
  int v9; // ecx
  _DWORD *v10; // rax
  int v11; // ecx
  __int64 i; // rsi
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rsi
  void (__fastcall ***v16)(_QWORD, __int64); // r8
  void (__fastcall ***v17)(_QWORD, __int64); // rax
  int v18; // ebp
  char v19; // r9
  __int64 *v20; // rax
  __int64 v21; // rcx
  char v22; // si
  __int64 v23; // rbx
  __int64 v25; // [rsp+40h] [rbp-28h] BYREF
  struct std::locale::_Locimp *v26; // [rsp+48h] [rbp-20h]
  char v27; // [rsp+70h] [rbp+8h] BYREF

  v6 = *(_BYTE **)(a1 + 8);
  v7 = *(_BYTE **)a1;
  LOBYTE(v6) = *v6;
  LOBYTE(v7) = **(_BYTE **)a1;
  v8 = *(_QWORD *)std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(&v27, a3, v7, v6);
  if ( **(_BYTE **)(a1 + 16) )
  {
    v9 = **(_DWORD **)(a1 + 32);
    v10 = *(_DWORD **)(a1 + 24);
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
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 32) + 12LL) )
  {
    v13 = *(_QWORD *)(a1 + 40);
    if ( *(_QWORD *)v13 )
    {
      v26 = *(struct std::locale::_Locimp **)(*(_QWORD *)v13 + 8LL);
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v26 + 8LL))(v26);
    }
    else
    {
      v26 = std::locale::_Init(1);
    }
    v15 = std::use_facet<std::numpunct<char>>(&v25);
    if ( v26 )
    {
      v17 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v26 + 16LL))(v26);
      v16 = v17;
      if ( v17 )
        (**v17)(v17, 1);
    }
    v18 = **(_DWORD **)(a1 + 72);
    v19 = (*(__int64 (__fastcall **)(__int64, __int64, void (__fastcall ***)(_QWORD, __int64)))(*(_QWORD *)v15 + 32LL))(
            v15,
            v14,
            v16);
    v20 = *(__int64 **)(a1 + 64);
    if ( (unsigned __int64)v20[3] <= 0xF )
      v21 = *(_QWORD *)(a1 + 64);
    else
      v21 = *v20;
    v25 = v21;
    v26 = (struct std::locale::_Locimp *)v20[2];
    v8 = *(_QWORD *)std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
                      (unsigned int)&v27,
                      **(_QWORD **)(a1 + 48),
                      **(_QWORD **)(a1 + 56),
                      (unsigned int)&v25,
                      v19,
                      v18,
                      v8);
    if ( **(_QWORD **)(a1 + 80) != **(_QWORD **)(a1 + 88) || **(_BYTE **)(a1 + 96) )
    {
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 24LL))(v15);
      if ( (unsigned __int64)(*(_QWORD *)(v8 + 16) + 1LL) > *(_QWORD *)(v8 + 24) )
        (**(void (__fastcall ***)(__int64))v8)(v8);
      *(_BYTE *)(*(_QWORD *)(v8 + 8) + (*(_QWORD *)(v8 + 16))++) = v22;
      **(_BYTE **)(a1 + 96) = 0;
    }
    **(_QWORD **)(a1 + 48) = **(_QWORD **)(a1 + 56);
    if ( **(_QWORD **)(a1 + 80) != **(_QWORD **)(a1 + 88) )
      ++**(_QWORD **)(a1 + 48);
  }
  v23 = *(_QWORD *)std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
                     &v27,
                     **(_QWORD **)(a1 + 48),
                     **(_QWORD **)(a1 + 104),
                     v8);
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 32) + 11LL) && **(_BYTE **)(a1 + 96) )
  {
    if ( (unsigned __int64)(*(_QWORD *)(v23 + 16) + 1LL) > *(_QWORD *)(v23 + 24) )
      (**(void (__fastcall ***)(__int64))v23)(v23);
    *(_BYTE *)(*(_QWORD *)(v23 + 8) + (*(_QWORD *)(v23 + 16))++) = 46;
  }
  while ( **(int **)(a1 + 112) > 0 )
  {
    if ( (unsigned __int64)(*(_QWORD *)(v23 + 16) + 1LL) > *(_QWORD *)(v23 + 24) )
      (**(void (__fastcall ***)(__int64))v23)(v23);
    *(_BYTE *)(*(_QWORD *)(v23 + 16) + *(_QWORD *)(v23 + 8)) = 48;
    ++*(_QWORD *)(v23 + 16);
    --**(_DWORD **)(a1 + 112);
  }
  std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
    a2,
    **(_QWORD **)(a1 + 104),
    **(_QWORD **)(a1 + 88),
    v23);
  return a2;
}

```

## disassembly

```asm
0x1800369ac  mov     [rsp+arg_8], rbx
0x1800369b1  mov     [rsp+arg_10], rbp
0x1800369b6  push    rsi
0x1800369b7  push    rdi
0x1800369b8  push    r14
0x1800369ba  sub     rsp, 50h
0x1800369be  mov     rax, r8
0x1800369c1  mov     r14, rdx
0x1800369c4  mov     rdi, rcx
0x1800369c7  mov     r9, [rcx+8]
0x1800369cb  mov     r8, [rcx]
0x1800369ce  mov     r9b, [r9]
0x1800369d1  mov     r8b, [r8]
0x1800369d4  mov     rdx, rax
0x1800369d7  lea     rcx, [rsp+68h+arg_0]
0x1800369dc  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x1800369e1  mov     rbx, [rax]
0x1800369e4  mov     rax, [rdi+10h]
0x1800369e8  cmp     byte ptr [rax], 0
0x1800369eb  jz      short loc_180036A37
0x1800369ed  mov     rax, [rdi+20h]
0x1800369f1  mov     ecx, [rax]
0x1800369f3  mov     rax, [rdi+18h]
0x1800369f7  cmp     [rax], ecx
0x1800369f9  jge     short loc_180036A37
0x1800369fb  sub     ecx, [rax]
0x1800369fd  movsxd  rsi, ecx
0x180036a00  test    ecx, ecx
0x180036a02  jle     short loc_180036A37
0x180036a04  mov     rdx, [rbx+10h]
0x180036a08  inc     rdx
0x180036a0b  cmp     rdx, [rbx+18h]
0x180036a0f  jbe     short loc_180036A1F
0x180036a11  mov     rax, [rbx]
0x180036a14  mov     rcx, rbx
0x180036a17  mov     rax, [rax]
0x180036a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a1f  mov     rcx, [rbx+10h]
0x180036a23  mov     rax, [rbx+8]
0x180036a27  mov     byte ptr [rcx+rax], 30h ; '0'
0x180036a2b  inc     qword ptr [rbx+10h]
0x180036a2f  dec     rsi
0x180036a32  test    rsi, rsi
0x180036a35  jg      short loc_180036A04
0x180036a37  mov     rax, [rdi+20h]
0x180036a3b  cmp     byte ptr [rax+0Ch], 0
0x180036a3f  jz      loc_180036B9C
0x180036a45  mov     rax, [rdi+28h]
0x180036a49  mov     rcx, [rax]
0x180036a4c  test    rcx, rcx
0x180036a4f  jz      short loc_180036A68
0x180036a51  mov     rcx, [rcx+8]
0x180036a55  mov     [rsp+68h+var_20], rcx
0x180036a5a  mov     rax, [rcx]
0x180036a5d  mov     rax, [rax+8]
0x180036a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a66  jmp     short loc_180036A75
0x180036a68  mov     cl, 1
0x180036a6a  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180036a70  mov     [rsp+68h+var_20], rax
0x180036a75  lea     rcx, [rsp+68h+var_28]
0x180036a7a  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180036a7f  mov     rsi, rax
0x180036a82  mov     rcx, [rsp+68h+var_20]
0x180036a87  test    rcx, rcx
0x180036a8a  jz      short loc_180036AB3
0x180036a8c  mov     rdx, [rcx]
0x180036a8f  mov     rax, [rdx+10h]
0x180036a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a98  mov     r8, rax
0x180036a9b  test    rax, rax
0x180036a9e  jz      short loc_180036AB3
0x180036aa0  mov     rcx, [rax]
0x180036aa3  mov     rax, [rcx]
0x180036aa6  mov     edx, 1
0x180036aab  mov     rcx, r8
0x180036aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ab3  mov     rax, [rdi+48h]
0x180036ab7  mov     ebp, [rax]
0x180036ab9  mov     rax, [rsi]
0x180036abc  mov     rcx, rsi
0x180036abf  mov     rax, [rax+20h]
0x180036ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ac8  mov     r9b, al
0x180036acb  mov     rax, [rdi+40h]
0x180036acf  cmp     qword ptr [rax+18h], 0Fh
0x180036ad4  jbe     short loc_180036ADB
0x180036ad6  mov     rcx, [rax]
0x180036ad9  jmp     short loc_180036ADE
0x180036adb  mov     rcx, rax
0x180036ade  mov     [rsp+68h+var_28], rcx
0x180036ae3  mov     rax, [rax+10h]
0x180036ae7  mov     [rsp+68h+var_20], rax
0x180036aec  mov     r8, [rdi+38h]
0x180036af0  mov     rdx, [rdi+30h]
0x180036af4  mov     [rsp+68h+var_38], rbx
0x180036af9  mov     [rsp+68h+var_40], ebp
0x180036afd  mov     [rsp+68h+var_48], r9b
0x180036b02  lea     r9, [rsp+68h+var_28]
0x180036b07  mov     r8, [r8]
0x180036b0a  mov     rdx, [rdx]
0x180036b0d  lea     rcx, [rsp+68h+arg_0]
0x180036b12  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180036b17  mov     rbx, [rax]
0x180036b1a  mov     rdx, [rdi+50h]
0x180036b1e  mov     rax, [rdi+58h]
0x180036b22  mov     rcx, [rax]
0x180036b25  cmp     [rdx], rcx
0x180036b28  jnz     short loc_180036B33
0x180036b2a  mov     rax, [rdi+60h]
0x180036b2e  cmp     byte ptr [rax], 0
0x180036b31  jz      short loc_180036B77
0x180036b33  mov     rax, [rsi]
0x180036b36  mov     rcx, rsi
0x180036b39  mov     rax, [rax+18h]
0x180036b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b42  mov     sil, al
0x180036b45  mov     rdx, [rbx+10h]
0x180036b49  inc     rdx
0x180036b4c  cmp     rdx, [rbx+18h]
0x180036b50  jbe     short loc_180036B60
0x180036b52  mov     rcx, [rbx]
0x180036b55  mov     rax, [rcx]
0x180036b58  mov     rcx, rbx
0x180036b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b60  mov     rcx, [rbx+8]
0x180036b64  mov     rax, [rbx+10h]
0x180036b68  mov     [rcx+rax], sil
0x180036b6c  inc     qword ptr [rbx+10h]
0x180036b70  mov     rax, [rdi+60h]
0x180036b74  mov     byte ptr [rax], 0
0x180036b77  mov     rax, [rdi+38h]
0x180036b7b  mov     rcx, [rdi+30h]
0x180036b7f  mov     rax, [rax]
0x180036b82  mov     [rcx], rax
0x180036b85  mov     rdx, [rdi+50h]
0x180036b89  mov     rax, [rdi+58h]
0x180036b8d  mov     rcx, [rax]
0x180036b90  cmp     [rdx], rcx
0x180036b93  jz      short loc_180036B9C
0x180036b95  mov     rax, [rdi+30h]
0x180036b99  inc     qword ptr [rax]
0x180036b9c  mov     r8, [rdi+68h]
0x180036ba0  mov     rdx, [rdi+30h]
0x180036ba4  mov     r9, rbx
0x180036ba7  mov     r8, [r8]
0x180036baa  mov     rdx, [rdx]
0x180036bad  lea     rcx, [rsp+68h+arg_0]
0x180036bb2  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180036bb7  mov     rbx, [rax]
0x180036bba  mov     rax, [rdi+20h]
0x180036bbe  cmp     byte ptr [rax+0Bh], 0
0x180036bc2  jz      short loc_180036C2B
0x180036bc4  mov     rax, [rdi+60h]
0x180036bc8  cmp     byte ptr [rax], 0
0x180036bcb  jz      short loc_180036C2B
0x180036bcd  mov     rdx, [rbx+10h]
0x180036bd1  inc     rdx
0x180036bd4  cmp     rdx, [rbx+18h]
0x180036bd8  jbe     short loc_180036BE8
0x180036bda  mov     rax, [rbx]
0x180036bdd  mov     rcx, rbx
0x180036be0  mov     rax, [rax]
0x180036be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036be8  mov     rcx, [rbx+8]
0x180036bec  mov     rax, [rbx+10h]
0x180036bf0  mov     byte ptr [rcx+rax], 2Eh ; '.'
0x180036bf4  inc     qword ptr [rbx+10h]
0x180036bf8  jmp     short loc_180036C2B
0x180036bfa  mov     rdx, [rbx+10h]
0x180036bfe  inc     rdx
0x180036c01  cmp     rdx, [rbx+18h]
0x180036c05  jbe     short loc_180036C15
0x180036c07  mov     rax, [rbx]
0x180036c0a  mov     rcx, rbx
0x180036c0d  mov     rax, [rax]
0x180036c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c15  mov     rcx, [rbx+10h]
0x180036c19  mov     rax, [rbx+8]
0x180036c1d  mov     byte ptr [rcx+rax], 30h ; '0'
0x180036c21  inc     qword ptr [rbx+10h]
0x180036c25  mov     rax, [rdi+70h]
0x180036c29  dec     dword ptr [rax]
0x180036c2b  mov     rax, [rdi+70h]
0x180036c2f  cmp     dword ptr [rax], 0
0x180036c32  jg      short loc_180036BFA
0x180036c34  mov     r8, [rdi+58h]
0x180036c38  mov     rdx, [rdi+68h]
0x180036c3c  mov     r9, rbx
0x180036c3f  mov     r8, [r8]
0x180036c42  mov     rdx, [rdx]
0x180036c45  mov     rcx, r14
0x180036c48  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180036c4d  mov     rax, r14
0x180036c50  lea     r11, [rsp+68h+var_18]
0x180036c55  mov     rbx, [r11+28h]
0x180036c59  mov     rbp, [r11+30h]
0x180036c5d  mov     rsp, r11
0x180036c60  pop     r14
0x180036c62  pop     rdi
0x180036c63  pop     rsi
0x180036c64  retn
```
