# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x18002b7fc`
- end: `0x18002b99b`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@HU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `415`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180027868`
- `0x180028158`

## callees

- `0x18002759c`
- `0x180029018`
- `0x180029128`
- `0x18002a6a0`
- `0x18002b7fc`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002b8d6`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002b8d6`

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
0x18002b7fc  mov     r11, rsp
0x18002b7ff  push    rbx
0x18002b800  push    rbp
0x18002b801  push    rsi
0x18002b802  push    rdi
0x18002b803  sub     rsp, 68h
0x18002b807  mov     rax, r8
0x18002b80a  mov     rbp, rdx
0x18002b80d  mov     rdi, rcx
0x18002b810  mov     r8, [rcx+10h]
0x18002b814  mov     r9d, [r8]
0x18002b817  shr     r9d, 1Fh
0x18002b81b  mov     r8, [rcx+8]
0x18002b81f  mov     r8b, [r8+0Ah]
0x18002b823  mov     rdx, rax
0x18002b826  lea     rcx, [r11+8]
0x18002b82a  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x18002b82f  mov     rcx, [rdi+18h]
0x18002b833  mov     rdx, [rcx]
0x18002b836  mov     r8, [rcx+8]
0x18002b83a  add     r8, rdx
0x18002b83d  mov     r9, [rax]
0x18002b840  lea     rcx, [rsp+88h+arg_0]
0x18002b848  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002b84d  mov     rbx, [rax]
0x18002b850  mov     rax, [rdi+20h]
0x18002b854  cmp     byte ptr [rax], 0
0x18002b857  jz      short loc_18002B8A3
0x18002b859  mov     rax, [rdi+8]
0x18002b85d  mov     ecx, [rax]
0x18002b85f  mov     rax, [rdi+28h]
0x18002b863  cmp     [rax], ecx
0x18002b865  jge     short loc_18002B8A3
0x18002b867  sub     ecx, [rax]
0x18002b869  movsxd  rsi, ecx
0x18002b86c  test    ecx, ecx
0x18002b86e  jle     short loc_18002B8A3
0x18002b870  mov     rdx, [rbx+10h]
0x18002b874  inc     rdx
0x18002b877  cmp     rdx, [rbx+18h]
0x18002b87b  jbe     short loc_18002B88B
0x18002b87d  mov     rax, [rbx]
0x18002b880  mov     rcx, rbx
0x18002b883  mov     rax, [rax]
0x18002b886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b88b  mov     rcx, [rbx+10h]
0x18002b88f  mov     rax, [rbx+8]
0x18002b893  mov     byte ptr [rcx+rax], 30h ; '0'
0x18002b897  inc     qword ptr [rbx+10h]
0x18002b89b  dec     rsi
0x18002b89e  test    rsi, rsi
0x18002b8a1  jg      short loc_18002B870
0x18002b8a3  mov     rax, [rdi+30h]
0x18002b8a7  mov     esi, [rax]
0x18002b8a9  test    esi, esi
0x18002b8ab  jle     loc_18002B97A
0x18002b8b1  mov     rax, [rdi+48h]
0x18002b8b5  mov     rcx, [rax]
0x18002b8b8  test    rcx, rcx
0x18002b8bb  jz      short loc_18002B8D4
0x18002b8bd  mov     rcx, [rcx+8]
0x18002b8c1  mov     [rsp+88h+var_40], rcx
0x18002b8c6  mov     rax, [rcx]
0x18002b8c9  mov     rax, [rax+8]
0x18002b8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8d2  jmp     short loc_18002B8E1
0x18002b8d4  mov     cl, 1
0x18002b8d6  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002b8dc  mov     [rsp+88h+var_40], rax
0x18002b8e1  lea     rcx, [rsp+88h+var_48]
0x18002b8e6  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002b8eb  mov     rdx, rax
0x18002b8ee  mov     rcx, [rax]
0x18002b8f1  mov     rax, [rcx+20h]
0x18002b8f5  mov     rcx, rdx
0x18002b8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8fd  mov     r8b, al
0x18002b900  mov     rax, [rdi+40h]
0x18002b904  cmp     qword ptr [rax+18h], 0Fh
0x18002b909  jbe     short loc_18002B910
0x18002b90b  mov     rcx, [rax]
0x18002b90e  jmp     short loc_18002B913
0x18002b910  mov     rcx, rax
0x18002b913  mov     [rsp+88h+var_38], rcx
0x18002b918  mov     rax, [rax+10h]
0x18002b91c  mov     [rsp+88h+var_30], rax
0x18002b921  mov     rdx, [rdi+38h]
0x18002b925  mov     [rsp+88h+var_58], rbx
0x18002b92a  mov     [rsp+88h+var_60], esi
0x18002b92e  mov     [rsp+88h+var_68], r8b
0x18002b933  lea     r9, [rsp+88h+var_38]
0x18002b938  mov     r8, [rdi]
0x18002b93b  mov     rdx, [rdx]
0x18002b93e  mov     rcx, rbp
0x18002b941  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002b946  nop
0x18002b947  mov     rcx, [rsp+88h+var_40]
0x18002b94c  test    rcx, rcx
0x18002b94f  jz      short loc_18002B98F
0x18002b951  mov     rax, [rcx]
0x18002b954  mov     rax, [rax+10h]
0x18002b958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b95d  mov     r8, rax
0x18002b960  test    rax, rax
0x18002b963  jz      short loc_18002B98F
0x18002b965  mov     rcx, [rax]
0x18002b968  mov     rax, [rcx]
0x18002b96b  mov     edx, 1
0x18002b970  mov     rcx, r8
0x18002b973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b978  jmp     short loc_18002B98F
0x18002b97a  mov     rdx, [rdi+38h]
0x18002b97e  mov     r9, rbx
0x18002b981  mov     r8, [rdi]
0x18002b984  mov     rdx, [rdx]
0x18002b987  mov     rcx, rbp
0x18002b98a  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002b98f  mov     rax, rbp
0x18002b992  add     rsp, 68h
0x18002b996  pop     rdi
0x18002b997  pop     rsi
0x18002b998  pop     rbp
0x18002b999  pop     rbx
0x18002b99a  retn
```
