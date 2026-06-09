# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x180037154`
- end: `0x1800372f3`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_JU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `415`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180032d64`
- `0x180033b50`

## callees

- `0x180032838`
- `0x1800342b4`
- `0x1800343c4`
- `0x180035ca4`
- `0x180037154`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18003722e`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18003722e`

## pseudocode

```c
_QWORD *__fastcall `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>'::`2'::_lambda_1_::operator()(
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
                    **(_QWORD **)(a1 + 16) >> 63);
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
0x180037154  mov     r11, rsp
0x180037157  push    rbx
0x180037158  push    rbp
0x180037159  push    rsi
0x18003715a  push    rdi
0x18003715b  sub     rsp, 68h
0x18003715f  mov     rax, r8
0x180037162  mov     rbp, rdx
0x180037165  mov     rdi, rcx
0x180037168  mov     r8, [rcx+10h]
0x18003716c  mov     r9, [r8]
0x18003716f  shr     r9, 3Fh
0x180037173  mov     r8, [rcx+8]
0x180037177  mov     r8b, [r8+0Ah]
0x18003717b  mov     rdx, rax
0x18003717e  lea     rcx, [r11+8]
0x180037182  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x180037187  mov     rcx, [rdi+18h]
0x18003718b  mov     rdx, [rcx]
0x18003718e  mov     r8, [rcx+8]
0x180037192  add     r8, rdx
0x180037195  mov     r9, [rax]
0x180037198  lea     rcx, [rsp+88h+arg_0]
0x1800371a0  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x1800371a5  mov     rbx, [rax]
0x1800371a8  mov     rax, [rdi+20h]
0x1800371ac  cmp     byte ptr [rax], 0
0x1800371af  jz      short loc_1800371FB
0x1800371b1  mov     rax, [rdi+8]
0x1800371b5  mov     ecx, [rax]
0x1800371b7  mov     rax, [rdi+28h]
0x1800371bb  cmp     [rax], ecx
0x1800371bd  jge     short loc_1800371FB
0x1800371bf  sub     ecx, [rax]
0x1800371c1  movsxd  rsi, ecx
0x1800371c4  test    ecx, ecx
0x1800371c6  jle     short loc_1800371FB
0x1800371c8  mov     rdx, [rbx+10h]
0x1800371cc  inc     rdx
0x1800371cf  cmp     rdx, [rbx+18h]
0x1800371d3  jbe     short loc_1800371E3
0x1800371d5  mov     rax, [rbx]
0x1800371d8  mov     rcx, rbx
0x1800371db  mov     rax, [rax]
0x1800371de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371e3  mov     rcx, [rbx+10h]
0x1800371e7  mov     rax, [rbx+8]
0x1800371eb  mov     byte ptr [rcx+rax], 30h ; '0'
0x1800371ef  inc     qword ptr [rbx+10h]
0x1800371f3  dec     rsi
0x1800371f6  test    rsi, rsi
0x1800371f9  jg      short loc_1800371C8
0x1800371fb  mov     rax, [rdi+30h]
0x1800371ff  mov     esi, [rax]
0x180037201  test    esi, esi
0x180037203  jle     loc_1800372D2
0x180037209  mov     rax, [rdi+48h]
0x18003720d  mov     rcx, [rax]
0x180037210  test    rcx, rcx
0x180037213  jz      short loc_18003722C
0x180037215  mov     rcx, [rcx+8]
0x180037219  mov     [rsp+88h+var_40], rcx
0x18003721e  mov     rax, [rcx]
0x180037221  mov     rax, [rax+8]
0x180037225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003722a  jmp     short loc_180037239
0x18003722c  mov     cl, 1
0x18003722e  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180037234  mov     [rsp+88h+var_40], rax
0x180037239  lea     rcx, [rsp+88h+var_48]
0x18003723e  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180037243  mov     rdx, rax
0x180037246  mov     rcx, [rax]
0x180037249  mov     rax, [rcx+20h]
0x18003724d  mov     rcx, rdx
0x180037250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037255  mov     r8b, al
0x180037258  mov     rax, [rdi+40h]
0x18003725c  cmp     qword ptr [rax+18h], 0Fh
0x180037261  jbe     short loc_180037268
0x180037263  mov     rcx, [rax]
0x180037266  jmp     short loc_18003726B
0x180037268  mov     rcx, rax
0x18003726b  mov     [rsp+88h+var_38], rcx
0x180037270  mov     rax, [rax+10h]
0x180037274  mov     [rsp+88h+var_30], rax
0x180037279  mov     rdx, [rdi+38h]
0x18003727d  mov     [rsp+88h+var_58], rbx
0x180037282  mov     [rsp+88h+var_60], esi
0x180037286  mov     [rsp+88h+var_68], r8b
0x18003728b  lea     r9, [rsp+88h+var_38]
0x180037290  mov     r8, [rdi]
0x180037293  mov     rdx, [rdx]
0x180037296  mov     rcx, rbp
0x180037299  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18003729e  nop
0x18003729f  mov     rcx, [rsp+88h+var_40]
0x1800372a4  test    rcx, rcx
0x1800372a7  jz      short loc_1800372E7
0x1800372a9  mov     rax, [rcx]
0x1800372ac  mov     rax, [rax+10h]
0x1800372b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372b5  mov     r8, rax
0x1800372b8  test    rax, rax
0x1800372bb  jz      short loc_1800372E7
0x1800372bd  mov     rcx, [rax]
0x1800372c0  mov     rax, [rcx]
0x1800372c3  mov     edx, 1
0x1800372c8  mov     rcx, r8
0x1800372cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372d0  jmp     short loc_1800372E7
0x1800372d2  mov     rdx, [rdi+38h]
0x1800372d6  mov     r9, rbx
0x1800372d9  mov     r8, [rdi]
0x1800372dc  mov     rdx, [rdx]
0x1800372df  mov     rcx, rbp
0x1800372e2  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x1800372e7  mov     rax, rbp
0x1800372ea  add     rsp, 68h
0x1800372ee  pop     rdi
0x1800372ef  pop     rsi
0x1800372f0  pop     rbp
0x1800372f1  pop     rbx
0x1800372f2  retn
```
