# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,int>(std::back_insert_iterator<std::_Fmt_buffer<char>>,int,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x180036e0c`
- end: `0x180036fab`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@HU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `415`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180032b04`
- `0x1800333f4`

## callees

- `0x180032838`
- `0x1800342b4`
- `0x1800343c4`
- `0x180035ca4`
- `0x180036e0c`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180036ee6`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180036ee6`

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
0x180036e0c  mov     r11, rsp
0x180036e0f  push    rbx
0x180036e10  push    rbp
0x180036e11  push    rsi
0x180036e12  push    rdi
0x180036e13  sub     rsp, 68h
0x180036e17  mov     rax, r8
0x180036e1a  mov     rbp, rdx
0x180036e1d  mov     rdi, rcx
0x180036e20  mov     r8, [rcx+10h]
0x180036e24  mov     r9d, [r8]
0x180036e27  shr     r9d, 1Fh
0x180036e2b  mov     r8, [rcx+8]
0x180036e2f  mov     r8b, [r8+0Ah]
0x180036e33  mov     rdx, rax
0x180036e36  lea     rcx, [r11+8]
0x180036e3a  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x180036e3f  mov     rcx, [rdi+18h]
0x180036e43  mov     rdx, [rcx]
0x180036e46  mov     r8, [rcx+8]
0x180036e4a  add     r8, rdx
0x180036e4d  mov     r9, [rax]
0x180036e50  lea     rcx, [rsp+88h+arg_0]
0x180036e58  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180036e5d  mov     rbx, [rax]
0x180036e60  mov     rax, [rdi+20h]
0x180036e64  cmp     byte ptr [rax], 0
0x180036e67  jz      short loc_180036EB3
0x180036e69  mov     rax, [rdi+8]
0x180036e6d  mov     ecx, [rax]
0x180036e6f  mov     rax, [rdi+28h]
0x180036e73  cmp     [rax], ecx
0x180036e75  jge     short loc_180036EB3
0x180036e77  sub     ecx, [rax]
0x180036e79  movsxd  rsi, ecx
0x180036e7c  test    ecx, ecx
0x180036e7e  jle     short loc_180036EB3
0x180036e80  mov     rdx, [rbx+10h]
0x180036e84  inc     rdx
0x180036e87  cmp     rdx, [rbx+18h]
0x180036e8b  jbe     short loc_180036E9B
0x180036e8d  mov     rax, [rbx]
0x180036e90  mov     rcx, rbx
0x180036e93  mov     rax, [rax]
0x180036e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e9b  mov     rcx, [rbx+10h]
0x180036e9f  mov     rax, [rbx+8]
0x180036ea3  mov     byte ptr [rcx+rax], 30h ; '0'
0x180036ea7  inc     qword ptr [rbx+10h]
0x180036eab  dec     rsi
0x180036eae  test    rsi, rsi
0x180036eb1  jg      short loc_180036E80
0x180036eb3  mov     rax, [rdi+30h]
0x180036eb7  mov     esi, [rax]
0x180036eb9  test    esi, esi
0x180036ebb  jle     loc_180036F8A
0x180036ec1  mov     rax, [rdi+48h]
0x180036ec5  mov     rcx, [rax]
0x180036ec8  test    rcx, rcx
0x180036ecb  jz      short loc_180036EE4
0x180036ecd  mov     rcx, [rcx+8]
0x180036ed1  mov     [rsp+88h+var_40], rcx
0x180036ed6  mov     rax, [rcx]
0x180036ed9  mov     rax, [rax+8]
0x180036edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ee2  jmp     short loc_180036EF1
0x180036ee4  mov     cl, 1
0x180036ee6  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180036eec  mov     [rsp+88h+var_40], rax
0x180036ef1  lea     rcx, [rsp+88h+var_48]
0x180036ef6  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180036efb  mov     rdx, rax
0x180036efe  mov     rcx, [rax]
0x180036f01  mov     rax, [rcx+20h]
0x180036f05  mov     rcx, rdx
0x180036f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f0d  mov     r8b, al
0x180036f10  mov     rax, [rdi+40h]
0x180036f14  cmp     qword ptr [rax+18h], 0Fh
0x180036f19  jbe     short loc_180036F20
0x180036f1b  mov     rcx, [rax]
0x180036f1e  jmp     short loc_180036F23
0x180036f20  mov     rcx, rax
0x180036f23  mov     [rsp+88h+var_38], rcx
0x180036f28  mov     rax, [rax+10h]
0x180036f2c  mov     [rsp+88h+var_30], rax
0x180036f31  mov     rdx, [rdi+38h]
0x180036f35  mov     [rsp+88h+var_58], rbx
0x180036f3a  mov     [rsp+88h+var_60], esi
0x180036f3e  mov     [rsp+88h+var_68], r8b
0x180036f43  lea     r9, [rsp+88h+var_38]
0x180036f48  mov     r8, [rdi]
0x180036f4b  mov     rdx, [rdx]
0x180036f4e  mov     rcx, rbp
0x180036f51  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180036f56  nop
0x180036f57  mov     rcx, [rsp+88h+var_40]
0x180036f5c  test    rcx, rcx
0x180036f5f  jz      short loc_180036F9F
0x180036f61  mov     rax, [rcx]
0x180036f64  mov     rax, [rax+10h]
0x180036f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f6d  mov     r8, rax
0x180036f70  test    rax, rax
0x180036f73  jz      short loc_180036F9F
0x180036f75  mov     rcx, [rax]
0x180036f78  mov     rax, [rcx]
0x180036f7b  mov     edx, 1
0x180036f80  mov     rcx, r8
0x180036f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f88  jmp     short loc_180036F9F
0x180036f8a  mov     rdx, [rdi+38h]
0x180036f8e  mov     r9, rbx
0x180036f91  mov     r8, [rdi]
0x180036f94  mov     rdx, [rdx]
0x180036f97  mov     rcx, rbp
0x180036f9a  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180036f9f  mov     rax, rbp
0x180036fa2  add     rsp, 68h
0x180036fa6  pop     rdi
0x180036fa7  pop     rsi
0x180036fa8  pop     rbp
0x180036fa9  pop     rbx
0x180036faa  retn
```
