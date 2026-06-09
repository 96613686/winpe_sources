# `std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,long double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x18002b39c`
- end: `0x18002b655`
- name: `??R_lambda_1_@?1???$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@OAEBU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `697`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180024284`
- `0x18002494c`
- `0x18002501c`

## callees

- `0x18002759c`
- `0x180029018`
- `0x180029128`
- `0x18002a6a0`
- `0x18002b39c`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002b45a`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002b45a`

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
0x18002b39c  mov     [rsp+arg_8], rbx
0x18002b3a1  mov     [rsp+arg_10], rbp
0x18002b3a6  push    rsi
0x18002b3a7  push    rdi
0x18002b3a8  push    r14
0x18002b3aa  sub     rsp, 50h
0x18002b3ae  mov     rax, r8
0x18002b3b1  mov     r14, rdx
0x18002b3b4  mov     rdi, rcx
0x18002b3b7  mov     r9, [rcx+8]
0x18002b3bb  mov     r8, [rcx]
0x18002b3be  mov     r9b, [r9]
0x18002b3c1  mov     r8b, [r8]
0x18002b3c4  mov     rdx, rax
0x18002b3c7  lea     rcx, [rsp+68h+arg_0]
0x18002b3cc  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x18002b3d1  mov     rbx, [rax]
0x18002b3d4  mov     rax, [rdi+10h]
0x18002b3d8  cmp     byte ptr [rax], 0
0x18002b3db  jz      short loc_18002B427
0x18002b3dd  mov     rax, [rdi+20h]
0x18002b3e1  mov     ecx, [rax]
0x18002b3e3  mov     rax, [rdi+18h]
0x18002b3e7  cmp     [rax], ecx
0x18002b3e9  jge     short loc_18002B427
0x18002b3eb  sub     ecx, [rax]
0x18002b3ed  movsxd  rsi, ecx
0x18002b3f0  test    ecx, ecx
0x18002b3f2  jle     short loc_18002B427
0x18002b3f4  mov     rdx, [rbx+10h]
0x18002b3f8  inc     rdx
0x18002b3fb  cmp     rdx, [rbx+18h]
0x18002b3ff  jbe     short loc_18002B40F
0x18002b401  mov     rax, [rbx]
0x18002b404  mov     rcx, rbx
0x18002b407  mov     rax, [rax]
0x18002b40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b40f  mov     rcx, [rbx+10h]
0x18002b413  mov     rax, [rbx+8]
0x18002b417  mov     byte ptr [rcx+rax], 30h ; '0'
0x18002b41b  inc     qword ptr [rbx+10h]
0x18002b41f  dec     rsi
0x18002b422  test    rsi, rsi
0x18002b425  jg      short loc_18002B3F4
0x18002b427  mov     rax, [rdi+20h]
0x18002b42b  cmp     byte ptr [rax+0Ch], 0
0x18002b42f  jz      loc_18002B58C
0x18002b435  mov     rax, [rdi+28h]
0x18002b439  mov     rcx, [rax]
0x18002b43c  test    rcx, rcx
0x18002b43f  jz      short loc_18002B458
0x18002b441  mov     rcx, [rcx+8]
0x18002b445  mov     [rsp+68h+var_20], rcx
0x18002b44a  mov     rax, [rcx]
0x18002b44d  mov     rax, [rax+8]
0x18002b451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b456  jmp     short loc_18002B465
0x18002b458  mov     cl, 1
0x18002b45a  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002b460  mov     [rsp+68h+var_20], rax
0x18002b465  lea     rcx, [rsp+68h+var_28]
0x18002b46a  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002b46f  mov     rsi, rax
0x18002b472  mov     rcx, [rsp+68h+var_20]
0x18002b477  test    rcx, rcx
0x18002b47a  jz      short loc_18002B4A3
0x18002b47c  mov     rdx, [rcx]
0x18002b47f  mov     rax, [rdx+10h]
0x18002b483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b488  mov     r8, rax
0x18002b48b  test    rax, rax
0x18002b48e  jz      short loc_18002B4A3
0x18002b490  mov     rcx, [rax]
0x18002b493  mov     rax, [rcx]
0x18002b496  mov     edx, 1
0x18002b49b  mov     rcx, r8
0x18002b49e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4a3  mov     rax, [rdi+48h]
0x18002b4a7  mov     ebp, [rax]
0x18002b4a9  mov     rax, [rsi]
0x18002b4ac  mov     rcx, rsi
0x18002b4af  mov     rax, [rax+20h]
0x18002b4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4b8  mov     r9b, al
0x18002b4bb  mov     rax, [rdi+40h]
0x18002b4bf  cmp     qword ptr [rax+18h], 0Fh
0x18002b4c4  jbe     short loc_18002B4CB
0x18002b4c6  mov     rcx, [rax]
0x18002b4c9  jmp     short loc_18002B4CE
0x18002b4cb  mov     rcx, rax
0x18002b4ce  mov     [rsp+68h+var_28], rcx
0x18002b4d3  mov     rax, [rax+10h]
0x18002b4d7  mov     [rsp+68h+var_20], rax
0x18002b4dc  mov     r8, [rdi+38h]
0x18002b4e0  mov     rdx, [rdi+30h]
0x18002b4e4  mov     [rsp+68h+var_38], rbx
0x18002b4e9  mov     [rsp+68h+var_40], ebp
0x18002b4ed  mov     [rsp+68h+var_48], r9b
0x18002b4f2  lea     r9, [rsp+68h+var_28]
0x18002b4f7  mov     r8, [r8]
0x18002b4fa  mov     rdx, [rdx]
0x18002b4fd  lea     rcx, [rsp+68h+arg_0]
0x18002b502  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002b507  mov     rbx, [rax]
0x18002b50a  mov     rdx, [rdi+50h]
0x18002b50e  mov     rax, [rdi+58h]
0x18002b512  mov     rcx, [rax]
0x18002b515  cmp     [rdx], rcx
0x18002b518  jnz     short loc_18002B523
0x18002b51a  mov     rax, [rdi+60h]
0x18002b51e  cmp     byte ptr [rax], 0
0x18002b521  jz      short loc_18002B567
0x18002b523  mov     rax, [rsi]
0x18002b526  mov     rcx, rsi
0x18002b529  mov     rax, [rax+18h]
0x18002b52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b532  mov     sil, al
0x18002b535  mov     rdx, [rbx+10h]
0x18002b539  inc     rdx
0x18002b53c  cmp     rdx, [rbx+18h]
0x18002b540  jbe     short loc_18002B550
0x18002b542  mov     rcx, [rbx]
0x18002b545  mov     rax, [rcx]
0x18002b548  mov     rcx, rbx
0x18002b54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b550  mov     rcx, [rbx+8]
0x18002b554  mov     rax, [rbx+10h]
0x18002b558  mov     [rcx+rax], sil
0x18002b55c  inc     qword ptr [rbx+10h]
0x18002b560  mov     rax, [rdi+60h]
0x18002b564  mov     byte ptr [rax], 0
0x18002b567  mov     rax, [rdi+38h]
0x18002b56b  mov     rcx, [rdi+30h]
0x18002b56f  mov     rax, [rax]
0x18002b572  mov     [rcx], rax
0x18002b575  mov     rdx, [rdi+50h]
0x18002b579  mov     rax, [rdi+58h]
0x18002b57d  mov     rcx, [rax]
0x18002b580  cmp     [rdx], rcx
0x18002b583  jz      short loc_18002B58C
0x18002b585  mov     rax, [rdi+30h]
0x18002b589  inc     qword ptr [rax]
0x18002b58c  mov     r8, [rdi+68h]
0x18002b590  mov     rdx, [rdi+30h]
0x18002b594  mov     r9, rbx
0x18002b597  mov     r8, [r8]
0x18002b59a  mov     rdx, [rdx]
0x18002b59d  lea     rcx, [rsp+68h+arg_0]
0x18002b5a2  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002b5a7  mov     rbx, [rax]
0x18002b5aa  mov     rax, [rdi+20h]
0x18002b5ae  cmp     byte ptr [rax+0Bh], 0
0x18002b5b2  jz      short loc_18002B61B
0x18002b5b4  mov     rax, [rdi+60h]
0x18002b5b8  cmp     byte ptr [rax], 0
0x18002b5bb  jz      short loc_18002B61B
0x18002b5bd  mov     rdx, [rbx+10h]
0x18002b5c1  inc     rdx
0x18002b5c4  cmp     rdx, [rbx+18h]
0x18002b5c8  jbe     short loc_18002B5D8
0x18002b5ca  mov     rax, [rbx]
0x18002b5cd  mov     rcx, rbx
0x18002b5d0  mov     rax, [rax]
0x18002b5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5d8  mov     rcx, [rbx+8]
0x18002b5dc  mov     rax, [rbx+10h]
0x18002b5e0  mov     byte ptr [rcx+rax], 2Eh ; '.'
0x18002b5e4  inc     qword ptr [rbx+10h]
0x18002b5e8  jmp     short loc_18002B61B
0x18002b5ea  mov     rdx, [rbx+10h]
0x18002b5ee  inc     rdx
0x18002b5f1  cmp     rdx, [rbx+18h]
0x18002b5f5  jbe     short loc_18002B605
0x18002b5f7  mov     rax, [rbx]
0x18002b5fa  mov     rcx, rbx
0x18002b5fd  mov     rax, [rax]
0x18002b600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b605  mov     rcx, [rbx+10h]
0x18002b609  mov     rax, [rbx+8]
0x18002b60d  mov     byte ptr [rcx+rax], 30h ; '0'
0x18002b611  inc     qword ptr [rbx+10h]
0x18002b615  mov     rax, [rdi+70h]
0x18002b619  dec     dword ptr [rax]
0x18002b61b  mov     rax, [rdi+70h]
0x18002b61f  cmp     dword ptr [rax], 0
0x18002b622  jg      short loc_18002B5EA
0x18002b624  mov     r8, [rdi+58h]
0x18002b628  mov     rdx, [rdi+68h]
0x18002b62c  mov     r9, rbx
0x18002b62f  mov     r8, [r8]
0x18002b632  mov     rdx, [rdx]
0x18002b635  mov     rcx, r14
0x18002b638  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002b63d  mov     rax, r14
0x18002b640  lea     r11, [rsp+68h+var_18]
0x18002b645  mov     rbx, [r11+28h]
0x18002b649  mov     rbp, [r11+30h]
0x18002b64d  mov     rsp, r11
0x18002b650  pop     r14
0x18002b652  pop     rdi
0x18002b653  pop     rsi
0x18002b654  retn
```
