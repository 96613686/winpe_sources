# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x18002bb44`
- end: `0x18002bce3`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_JU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `415`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180027ac8`
- `0x1800288b4`

## callees

- `0x18002759c`
- `0x180029018`
- `0x180029128`
- `0x18002a6a0`
- `0x18002bb44`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002bc1e`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002bc1e`

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
0x18002bb44  mov     r11, rsp
0x18002bb47  push    rbx
0x18002bb48  push    rbp
0x18002bb49  push    rsi
0x18002bb4a  push    rdi
0x18002bb4b  sub     rsp, 68h
0x18002bb4f  mov     rax, r8
0x18002bb52  mov     rbp, rdx
0x18002bb55  mov     rdi, rcx
0x18002bb58  mov     r8, [rcx+10h]
0x18002bb5c  mov     r9, [r8]
0x18002bb5f  shr     r9, 3Fh
0x18002bb63  mov     r8, [rcx+8]
0x18002bb67  mov     r8b, [r8+0Ah]
0x18002bb6b  mov     rdx, rax
0x18002bb6e  lea     rcx, [r11+8]
0x18002bb72  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x18002bb77  mov     rcx, [rdi+18h]
0x18002bb7b  mov     rdx, [rcx]
0x18002bb7e  mov     r8, [rcx+8]
0x18002bb82  add     r8, rdx
0x18002bb85  mov     r9, [rax]
0x18002bb88  lea     rcx, [rsp+88h+arg_0]
0x18002bb90  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002bb95  mov     rbx, [rax]
0x18002bb98  mov     rax, [rdi+20h]
0x18002bb9c  cmp     byte ptr [rax], 0
0x18002bb9f  jz      short loc_18002BBEB
0x18002bba1  mov     rax, [rdi+8]
0x18002bba5  mov     ecx, [rax]
0x18002bba7  mov     rax, [rdi+28h]
0x18002bbab  cmp     [rax], ecx
0x18002bbad  jge     short loc_18002BBEB
0x18002bbaf  sub     ecx, [rax]
0x18002bbb1  movsxd  rsi, ecx
0x18002bbb4  test    ecx, ecx
0x18002bbb6  jle     short loc_18002BBEB
0x18002bbb8  mov     rdx, [rbx+10h]
0x18002bbbc  inc     rdx
0x18002bbbf  cmp     rdx, [rbx+18h]
0x18002bbc3  jbe     short loc_18002BBD3
0x18002bbc5  mov     rax, [rbx]
0x18002bbc8  mov     rcx, rbx
0x18002bbcb  mov     rax, [rax]
0x18002bbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbd3  mov     rcx, [rbx+10h]
0x18002bbd7  mov     rax, [rbx+8]
0x18002bbdb  mov     byte ptr [rcx+rax], 30h ; '0'
0x18002bbdf  inc     qword ptr [rbx+10h]
0x18002bbe3  dec     rsi
0x18002bbe6  test    rsi, rsi
0x18002bbe9  jg      short loc_18002BBB8
0x18002bbeb  mov     rax, [rdi+30h]
0x18002bbef  mov     esi, [rax]
0x18002bbf1  test    esi, esi
0x18002bbf3  jle     loc_18002BCC2
0x18002bbf9  mov     rax, [rdi+48h]
0x18002bbfd  mov     rcx, [rax]
0x18002bc00  test    rcx, rcx
0x18002bc03  jz      short loc_18002BC1C
0x18002bc05  mov     rcx, [rcx+8]
0x18002bc09  mov     [rsp+88h+var_40], rcx
0x18002bc0e  mov     rax, [rcx]
0x18002bc11  mov     rax, [rax+8]
0x18002bc15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc1a  jmp     short loc_18002BC29
0x18002bc1c  mov     cl, 1
0x18002bc1e  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002bc24  mov     [rsp+88h+var_40], rax
0x18002bc29  lea     rcx, [rsp+88h+var_48]
0x18002bc2e  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002bc33  mov     rdx, rax
0x18002bc36  mov     rcx, [rax]
0x18002bc39  mov     rax, [rcx+20h]
0x18002bc3d  mov     rcx, rdx
0x18002bc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc45  mov     r8b, al
0x18002bc48  mov     rax, [rdi+40h]
0x18002bc4c  cmp     qword ptr [rax+18h], 0Fh
0x18002bc51  jbe     short loc_18002BC58
0x18002bc53  mov     rcx, [rax]
0x18002bc56  jmp     short loc_18002BC5B
0x18002bc58  mov     rcx, rax
0x18002bc5b  mov     [rsp+88h+var_38], rcx
0x18002bc60  mov     rax, [rax+10h]
0x18002bc64  mov     [rsp+88h+var_30], rax
0x18002bc69  mov     rdx, [rdi+38h]
0x18002bc6d  mov     [rsp+88h+var_58], rbx
0x18002bc72  mov     [rsp+88h+var_60], esi
0x18002bc76  mov     [rsp+88h+var_68], r8b
0x18002bc7b  lea     r9, [rsp+88h+var_38]
0x18002bc80  mov     r8, [rdi]
0x18002bc83  mov     rdx, [rdx]
0x18002bc86  mov     rcx, rbp
0x18002bc89  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002bc8e  nop
0x18002bc8f  mov     rcx, [rsp+88h+var_40]
0x18002bc94  test    rcx, rcx
0x18002bc97  jz      short loc_18002BCD7
0x18002bc99  mov     rax, [rcx]
0x18002bc9c  mov     rax, [rax+10h]
0x18002bca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bca5  mov     r8, rax
0x18002bca8  test    rax, rax
0x18002bcab  jz      short loc_18002BCD7
0x18002bcad  mov     rcx, [rax]
0x18002bcb0  mov     rax, [rcx]
0x18002bcb3  mov     edx, 1
0x18002bcb8  mov     rcx, r8
0x18002bcbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcc0  jmp     short loc_18002BCD7
0x18002bcc2  mov     rdx, [rdi+38h]
0x18002bcc6  mov     r9, rbx
0x18002bcc9  mov     r8, [rdi]
0x18002bccc  mov     rdx, [rdx]
0x18002bccf  mov     rcx, rbp
0x18002bcd2  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18002bcd7  mov     rax, rbp
0x18002bcda  add     rsp, 68h
0x18002bcde  pop     rdi
0x18002bcdf  pop     rsi
0x18002bce0  pop     rbp
0x18002bce1  pop     rbx
0x18002bce2  retn
```
