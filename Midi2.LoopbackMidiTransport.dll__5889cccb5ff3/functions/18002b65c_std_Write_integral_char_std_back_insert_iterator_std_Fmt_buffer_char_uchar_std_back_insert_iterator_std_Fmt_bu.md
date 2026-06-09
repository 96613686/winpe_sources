# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar>(std::back_insert_iterator<std::_Fmt_buffer<char>>,uchar,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x18002b65c`
- end: `0x18002b7f3`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@E@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@EU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `407`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180027738`
- `0x180027d64`

## callees

- `0x18002759c`
- `0x180029018`
- `0x180029128`
- `0x18002a6a0`
- `0x18002b65c`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002b72e`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002b72e`

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
0x18002b65c  mov     r11, rsp
0x18002b65f  push    rbx
0x18002b660  push    rbp
0x18002b661  push    rsi
0x18002b662  push    rdi
0x18002b663  sub     rsp, 68h
0x18002b667  mov     rax, r8
0x18002b66a  mov     rbp, rdx
0x18002b66d  mov     rdi, rcx
0x18002b670  mov     r8, [rcx+8]
0x18002b674  xor     r9d, r9d
0x18002b677  mov     r8b, [r8+0Ah]
0x18002b67b  mov     rdx, rax
0x18002b67e  lea     rcx, [r11+8]
0x18002b682  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x18002b687  mov     r8, [rdi+18h]
0x18002b68b  mov     rdx, [r8]
0x18002b68e  mov     r8, [r8+8]
0x18002b692  add     r8, rdx
0x18002b695  mov     r9, [rax]
0x18002b698  lea     rcx, [rsp+88h+arg_0]
0x18002b6a0  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002b6a5  mov     rbx, [rax]
0x18002b6a8  mov     rax, [rdi+20h]
0x18002b6ac  cmp     byte ptr [rax], 0
0x18002b6af  jz      short loc_18002B6FB
0x18002b6b1  mov     rax, [rdi+8]
0x18002b6b5  mov     ecx, [rax]
0x18002b6b7  mov     rax, [rdi+28h]
0x18002b6bb  cmp     [rax], ecx
0x18002b6bd  jge     short loc_18002B6FB
0x18002b6bf  sub     ecx, [rax]
0x18002b6c1  movsxd  rsi, ecx
0x18002b6c4  test    ecx, ecx
0x18002b6c6  jle     short loc_18002B6FB
0x18002b6c8  mov     rdx, [rbx+10h]
0x18002b6cc  inc     rdx
0x18002b6cf  cmp     rdx, [rbx+18h]
0x18002b6d3  jbe     short loc_18002B6E3
0x18002b6d5  mov     rax, [rbx]
0x18002b6d8  mov     rcx, rbx
0x18002b6db  mov     rax, [rax]
0x18002b6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6e3  mov     rcx, [rbx+10h]
0x18002b6e7  mov     rax, [rbx+8]
0x18002b6eb  mov     byte ptr [rcx+rax], 30h ; '0'
0x18002b6ef  inc     qword ptr [rbx+10h]
0x18002b6f3  dec     rsi
0x18002b6f6  test    rsi, rsi
0x18002b6f9  jg      short loc_18002B6C8
0x18002b6fb  mov     rax, [rdi+30h]
0x18002b6ff  mov     esi, [rax]
0x18002b701  test    esi, esi
0x18002b703  jle     loc_18002B7D2
0x18002b709  mov     rax, [rdi+48h]
0x18002b70d  mov     rcx, [rax]
0x18002b710  test    rcx, rcx
0x18002b713  jz      short loc_18002B72C
0x18002b715  mov     rcx, [rcx+8]
0x18002b719  mov     [rsp+88h+var_40], rcx
0x18002b71e  mov     rax, [rcx]
0x18002b721  mov     rax, [rax+8]
0x18002b725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b72a  jmp     short loc_18002B739
0x18002b72c  mov     cl, 1
0x18002b72e  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002b734  mov     [rsp+88h+var_40], rax
0x18002b739  lea     rcx, [rsp+88h+var_48]
0x18002b73e  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002b743  mov     rdx, rax
0x18002b746  mov     rcx, [rax]
0x18002b749  mov     rax, [rcx+20h]
0x18002b74d  mov     rcx, rdx
0x18002b750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b755  mov     r8b, al
0x18002b758  mov     rax, [rdi+40h]
0x18002b75c  cmp     qword ptr [rax+18h], 0Fh
0x18002b761  jbe     short loc_18002B768
0x18002b763  mov     rcx, [rax]
0x18002b766  jmp     short loc_18002B76B
0x18002b768  mov     rcx, rax
0x18002b76b  mov     [rsp+88h+var_38], rcx
0x18002b770  mov     rax, [rax+10h]
0x18002b774  mov     [rsp+88h+var_30], rax
0x18002b779  mov     rdx, [rdi+38h]
0x18002b77d  mov     [rsp+88h+var_58], rbx
0x18002b782  mov     [rsp+88h+var_60], esi
0x18002b786  mov     [rsp+88h+var_68], r8b
0x18002b78b  lea     r9, [rsp+88h+var_38]
0x18002b790  mov     r8, [rdi]
0x18002b793  mov     rdx, [rdx]
0x18002b796  mov     rcx, rbp
0x18002b799  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002b79e  nop
0x18002b79f  mov     rcx, [rsp+88h+var_40]
0x18002b7a4  test    rcx, rcx
0x18002b7a7  jz      short loc_18002B7E7
0x18002b7a9  mov     rax, [rcx]
0x18002b7ac  mov     rax, [rax+10h]
0x18002b7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7b5  mov     r8, rax
0x18002b7b8  test    rax, rax
0x18002b7bb  jz      short loc_18002B7E7
0x18002b7bd  mov     rcx, [rax]
0x18002b7c0  mov     rax, [rcx]
0x18002b7c3  mov     edx, 1
0x18002b7c8  mov     rcx, r8
0x18002b7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7d0  jmp     short loc_18002B7E7
0x18002b7d2  mov     rdx, [rdi+38h]
0x18002b7d6  mov     r9, rbx
0x18002b7d9  mov     r8, [rdi]
0x18002b7dc  mov     rdx, [rdx]
0x18002b7df  mov     rcx, rbp
0x18002b7e2  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002b7e7  mov     rax, rbp
0x18002b7ea  add     rsp, 68h
0x18002b7ee  pop     rdi
0x18002b7ef  pop     rsi
0x18002b7f0  pop     rbp
0x18002b7f1  pop     rbx
0x18002b7f2  retn
```
