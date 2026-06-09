# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,__int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x180054dfc`
- end: `0x180054f9b`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_JU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `415`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180052098`
- `0x180052e84`

## callees

- `0x180051b6c`
- `0x1800535e8`
- `0x1800536f8`
- `0x180053d44`
- `0x180054dfc`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180054ed6`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180054ed6`

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
0x180054dfc  mov     r11, rsp
0x180054dff  push    rbx
0x180054e00  push    rbp
0x180054e01  push    rsi
0x180054e02  push    rdi
0x180054e03  sub     rsp, 68h
0x180054e07  mov     rax, r8
0x180054e0a  mov     rbp, rdx
0x180054e0d  mov     rdi, rcx
0x180054e10  mov     r8, [rcx+10h]
0x180054e14  mov     r9, [r8]
0x180054e17  shr     r9, 3Fh
0x180054e1b  mov     r8, [rcx+8]
0x180054e1f  mov     r8b, [r8+0Ah]
0x180054e23  mov     rdx, rax
0x180054e26  lea     rcx, [r11+8]
0x180054e2a  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x180054e2f  mov     rcx, [rdi+18h]
0x180054e33  mov     rdx, [rcx]
0x180054e36  mov     r8, [rcx+8]
0x180054e3a  add     r8, rdx
0x180054e3d  mov     r9, [rax]
0x180054e40  lea     rcx, [rsp+88h+arg_0]
0x180054e48  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180054e4d  mov     rbx, [rax]
0x180054e50  mov     rax, [rdi+20h]
0x180054e54  cmp     byte ptr [rax], 0
0x180054e57  jz      short loc_180054EA3
0x180054e59  mov     rax, [rdi+8]
0x180054e5d  mov     ecx, [rax]
0x180054e5f  mov     rax, [rdi+28h]
0x180054e63  cmp     [rax], ecx
0x180054e65  jge     short loc_180054EA3
0x180054e67  sub     ecx, [rax]
0x180054e69  movsxd  rsi, ecx
0x180054e6c  test    ecx, ecx
0x180054e6e  jle     short loc_180054EA3
0x180054e70  mov     rdx, [rbx+10h]
0x180054e74  inc     rdx
0x180054e77  cmp     rdx, [rbx+18h]
0x180054e7b  jbe     short loc_180054E8B
0x180054e7d  mov     rax, [rbx]
0x180054e80  mov     rcx, rbx
0x180054e83  mov     rax, [rax]
0x180054e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e8b  mov     rcx, [rbx+10h]
0x180054e8f  mov     rax, [rbx+8]
0x180054e93  mov     byte ptr [rcx+rax], 30h ; '0'
0x180054e97  inc     qword ptr [rbx+10h]
0x180054e9b  dec     rsi
0x180054e9e  test    rsi, rsi
0x180054ea1  jg      short loc_180054E70
0x180054ea3  mov     rax, [rdi+30h]
0x180054ea7  mov     esi, [rax]
0x180054ea9  test    esi, esi
0x180054eab  jle     loc_180054F7A
0x180054eb1  mov     rax, [rdi+48h]
0x180054eb5  mov     rcx, [rax]
0x180054eb8  test    rcx, rcx
0x180054ebb  jz      short loc_180054ED4
0x180054ebd  mov     rcx, [rcx+8]
0x180054ec1  mov     [rsp+88h+var_40], rcx
0x180054ec6  mov     rax, [rcx]
0x180054ec9  mov     rax, [rax+8]
0x180054ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ed2  jmp     short loc_180054EE1
0x180054ed4  mov     cl, 1
0x180054ed6  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180054edc  mov     [rsp+88h+var_40], rax
0x180054ee1  lea     rcx, [rsp+88h+var_48]
0x180054ee6  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180054eeb  mov     rdx, rax
0x180054eee  mov     rcx, [rax]
0x180054ef1  mov     rax, [rcx+20h]
0x180054ef5  mov     rcx, rdx
0x180054ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054efd  mov     r8b, al
0x180054f00  mov     rax, [rdi+40h]
0x180054f04  cmp     qword ptr [rax+18h], 0Fh
0x180054f09  jbe     short loc_180054F10
0x180054f0b  mov     rcx, [rax]
0x180054f0e  jmp     short loc_180054F13
0x180054f10  mov     rcx, rax
0x180054f13  mov     [rsp+88h+var_38], rcx
0x180054f18  mov     rax, [rax+10h]
0x180054f1c  mov     [rsp+88h+var_30], rax
0x180054f21  mov     rdx, [rdi+38h]
0x180054f25  mov     [rsp+88h+var_58], rbx
0x180054f2a  mov     [rsp+88h+var_60], esi
0x180054f2e  mov     [rsp+88h+var_68], r8b
0x180054f33  lea     r9, [rsp+88h+var_38]
0x180054f38  mov     r8, [rdi]
0x180054f3b  mov     rdx, [rdx]
0x180054f3e  mov     rcx, rbp
0x180054f41  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180054f46  nop
0x180054f47  mov     rcx, [rsp+88h+var_40]
0x180054f4c  test    rcx, rcx
0x180054f4f  jz      short loc_180054F8F
0x180054f51  mov     rax, [rcx]
0x180054f54  mov     rax, [rax+10h]
0x180054f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f5d  mov     r8, rax
0x180054f60  test    rax, rax
0x180054f63  jz      short loc_180054F8F
0x180054f65  mov     rcx, [rax]
0x180054f68  mov     rax, [rcx]
0x180054f6b  mov     edx, 1
0x180054f70  mov     rcx, r8
0x180054f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f78  jmp     short loc_180054F8F
0x180054f7a  mov     rdx, [rdi+38h]
0x180054f7e  mov     r9, rbx
0x180054f81  mov     r8, [rdi]
0x180054f84  mov     rdx, [rdx]
0x180054f87  mov     rcx, rbp
0x180054f8a  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180054f8f  mov     rax, rbp
0x180054f92  add     rsp, 68h
0x180054f96  pop     rdi
0x180054f97  pop     rsi
0x180054f98  pop     rbp
0x180054f99  pop     rbx
0x180054f9a  retn
```
