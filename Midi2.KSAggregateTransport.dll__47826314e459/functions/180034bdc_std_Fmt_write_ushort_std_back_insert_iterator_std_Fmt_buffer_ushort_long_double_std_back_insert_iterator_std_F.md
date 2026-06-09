# `std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,long double,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)

- ea: `0x180034bdc`
- end: `0x180034e9f`
- name: `??R_lambda_1_@?1???$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@OAEBU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `707`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18002c554`
- `0x18002cbd0`
- `0x18002d25c`

## callees

- `0x180030600`
- `0x180032130`
- `0x180032244`
- `0x180033a7c`
- `0x180034bdc`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180034ca0`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180034ca0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall `std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>'::`2'::_lambda_1_::operator()(
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
  __int64 v13; // rsi
  struct std::locale::_Locimp *v14; // rsi
  __int64 v15; // rdx
  void (__fastcall ***v16)(_QWORD, __int64); // r8
  __int64 v17; // r14
  void (__fastcall ***v18)(_QWORD, __int64); // rax
  int v19; // esi
  __int16 v20; // r9
  __int64 *v21; // rax
  __int64 v22; // rcx
  __int16 v23; // si
  __int64 v24; // rbx
  __int64 v26; // [rsp+40h] [rbp-48h] BYREF
  struct std::locale::_Locimp *v27; // [rsp+48h] [rbp-40h]
  char v28; // [rsp+90h] [rbp+8h] BYREF

  v6 = *(_BYTE **)(a1 + 8);
  v7 = *(_BYTE **)a1;
  LOBYTE(v6) = *v6;
  LOBYTE(v7) = **(_BYTE **)a1;
  v8 = *(_QWORD *)std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(&v28, a3, v7, v6);
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
        *(_WORD *)(*(_QWORD *)(v8 + 8) + 2LL * (*(_QWORD *)(v8 + 16))++) = 48;
      }
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 32) + 12LL) )
  {
    v13 = **(_QWORD **)(a1 + 40);
    if ( v13 )
    {
      v14 = *(struct std::locale::_Locimp **)(v13 + 8);
      v27 = v14;
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v14 + 8LL))(v14);
    }
    else
    {
      v14 = std::locale::_Init(1);
      v27 = v14;
    }
    v17 = std::use_facet<std::numpunct<unsigned short>>(&v26);
    if ( v14 )
    {
      v18 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v14 + 16LL))(v14);
      v16 = v18;
      if ( v18 )
        (**v18)(v18, 1);
    }
    v19 = **(_DWORD **)(a1 + 72);
    v20 = (*(__int64 (__fastcall **)(__int64, __int64, void (__fastcall ***)(_QWORD, __int64)))(*(_QWORD *)v17 + 32LL))(
            v17,
            v15,
            v16);
    v21 = *(__int64 **)(a1 + 64);
    if ( (unsigned __int64)v21[3] <= 0xF )
      v22 = *(_QWORD *)(a1 + 64);
    else
      v22 = *v21;
    v26 = v22;
    v27 = (struct std::locale::_Locimp *)v21[2];
    v8 = *(_QWORD *)std::_Write_separated_integer<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
                      (unsigned int)&v28,
                      **(_QWORD **)(a1 + 48),
                      **(_QWORD **)(a1 + 56),
                      (unsigned int)&v26,
                      v20,
                      v19,
                      v8);
    if ( **(_QWORD **)(a1 + 80) != **(_QWORD **)(a1 + 88) || **(_BYTE **)(a1 + 96) )
    {
      v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
      if ( (unsigned __int64)(*(_QWORD *)(v8 + 16) + 1LL) > *(_QWORD *)(v8 + 24) )
        (**(void (__fastcall ***)(__int64))v8)(v8);
      *(_WORD *)(*(_QWORD *)(v8 + 8) + 2LL * (*(_QWORD *)(v8 + 16))++) = v23;
      **(_BYTE **)(a1 + 96) = 0;
    }
    **(_QWORD **)(a1 + 48) = **(_QWORD **)(a1 + 56);
    if ( **(_QWORD **)(a1 + 80) != **(_QWORD **)(a1 + 88) )
      ++**(_QWORD **)(a1 + 48);
  }
  v24 = *(_QWORD *)std::_Widen_and_copy<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
                     &v28,
                     **(_QWORD **)(a1 + 48),
                     **(_QWORD **)(a1 + 104),
                     v8);
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 32) + 11LL) && **(_BYTE **)(a1 + 96) )
  {
    if ( (unsigned __int64)(*(_QWORD *)(v24 + 16) + 1LL) > *(_QWORD *)(v24 + 24) )
      (**(void (__fastcall ***)(__int64))v24)(v24);
    *(_WORD *)(*(_QWORD *)(v24 + 8) + 2LL * (*(_QWORD *)(v24 + 16))++) = 46;
  }
  while ( **(int **)(a1 + 112) > 0 )
  {
    if ( (unsigned __int64)(*(_QWORD *)(v24 + 16) + 1LL) > *(_QWORD *)(v24 + 24) )
      (**(void (__fastcall ***)(__int64))v24)(v24);
    *(_WORD *)(*(_QWORD *)(v24 + 8) + 2LL * (*(_QWORD *)(v24 + 16))++) = 48;
    --**(_DWORD **)(a1 + 112);
  }
  std::_Widen_and_copy<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
    a2,
    **(_QWORD **)(a1 + 104),
    **(_QWORD **)(a1 + 88),
    v24);
  return a2;
}

```

## disassembly

```asm
0x180034bdc  mov     r11, rsp
0x180034bdf  push    rbx
0x180034be0  push    rbp
0x180034be1  push    rsi
0x180034be2  push    rdi
0x180034be3  push    r12
0x180034be5  push    r14
0x180034be7  sub     rsp, 58h
0x180034beb  mov     rax, r8
0x180034bee  mov     rbp, rdx
0x180034bf1  mov     rdi, rcx
0x180034bf4  mov     r9, [rcx+8]
0x180034bf8  mov     r8, [rcx]
0x180034bfb  mov     r9b, [r9]
0x180034bfe  mov     r8b, [r8]
0x180034c01  mov     rdx, rax
0x180034c04  lea     rcx, [r11+8]
0x180034c08  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Fmt_sign,bool)
0x180034c0d  mov     rbx, [rax]
0x180034c10  mov     rax, [rdi+10h]
0x180034c14  mov     r12d, 30h ; '0'
0x180034c1a  cmp     byte ptr [rax], 0
0x180034c1d  jz      short loc_180034C6A
0x180034c1f  mov     rax, [rdi+20h]
0x180034c23  mov     ecx, [rax]
0x180034c25  mov     rax, [rdi+18h]
0x180034c29  cmp     [rax], ecx
0x180034c2b  jge     short loc_180034C6A
0x180034c2d  sub     ecx, [rax]
0x180034c2f  movsxd  rsi, ecx
0x180034c32  test    ecx, ecx
0x180034c34  jle     short loc_180034C6A
0x180034c36  mov     rdx, [rbx+10h]
0x180034c3a  inc     rdx
0x180034c3d  cmp     rdx, [rbx+18h]
0x180034c41  jbe     short loc_180034C51
0x180034c43  mov     rax, [rbx]
0x180034c46  mov     rcx, rbx
0x180034c49  mov     rax, [rax]
0x180034c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c51  mov     rcx, [rbx+10h]
0x180034c55  mov     rax, [rbx+8]
0x180034c59  mov     [rax+rcx*2], r12w
0x180034c5e  inc     qword ptr [rbx+10h]
0x180034c62  dec     rsi
0x180034c65  test    rsi, rsi
0x180034c68  jg      short loc_180034C36
0x180034c6a  mov     rax, [rdi+20h]
0x180034c6e  cmp     byte ptr [rax+0Ch], 0
0x180034c72  jz      loc_180034DD8
0x180034c78  mov     rax, [rdi+28h]
0x180034c7c  mov     rsi, [rax]
0x180034c7f  test    rsi, rsi
0x180034c82  jz      short loc_180034C9E
0x180034c84  mov     rsi, [rsi+8]
0x180034c88  mov     [rsp+88h+var_40], rsi
0x180034c8d  mov     rax, [rsi]
0x180034c90  mov     rcx, rsi
0x180034c93  mov     rax, [rax+8]
0x180034c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c9c  jmp     short loc_180034CAE
0x180034c9e  mov     cl, 1
0x180034ca0  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180034ca6  mov     rsi, rax
0x180034ca9  mov     [rsp+88h+var_40], rax
0x180034cae  lea     rcx, [rsp+88h+var_48]
0x180034cb3  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x180034cb8  mov     r14, rax
0x180034cbb  test    rsi, rsi
0x180034cbe  jz      short loc_180034CEA
0x180034cc0  mov     rcx, [rsi]
0x180034cc3  mov     rax, [rcx+10h]
0x180034cc7  mov     rcx, rsi
0x180034cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ccf  mov     r8, rax
0x180034cd2  test    rax, rax
0x180034cd5  jz      short loc_180034CEA
0x180034cd7  mov     rcx, [rax]
0x180034cda  mov     rax, [rcx]
0x180034cdd  mov     edx, 1
0x180034ce2  mov     rcx, r8
0x180034ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034cea  mov     rax, [rdi+48h]
0x180034cee  mov     esi, [rax]
0x180034cf0  mov     rax, [r14]
0x180034cf3  mov     rcx, r14
0x180034cf6  mov     rax, [rax+20h]
0x180034cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034cff  movzx   r9d, ax
0x180034d03  mov     rax, [rdi+40h]
0x180034d07  cmp     qword ptr [rax+18h], 0Fh
0x180034d0c  jbe     short loc_180034D13
0x180034d0e  mov     rcx, [rax]
0x180034d11  jmp     short loc_180034D16
0x180034d13  mov     rcx, rax
0x180034d16  mov     [rsp+88h+var_48], rcx
0x180034d1b  mov     rax, [rax+10h]
0x180034d1f  mov     [rsp+88h+var_40], rax
0x180034d24  mov     r8, [rdi+38h]
0x180034d28  mov     rdx, [rdi+30h]
0x180034d2c  mov     [rsp+88h+var_58], rbx
0x180034d31  mov     [rsp+88h+var_60], esi
0x180034d35  mov     [rsp+88h+var_68], r9w
0x180034d3b  lea     r9, [rsp+88h+var_48]
0x180034d40  mov     r8, [r8]
0x180034d43  mov     rdx, [rdx]
0x180034d46  lea     rcx, [rsp+88h+arg_0]
0x180034d4e  call    ??$_Write_separated_integer@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@GHV10@@Z; std::_Write_separated_integer<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::string_view,ushort,int,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x180034d53  mov     rbx, [rax]
0x180034d56  mov     rax, [rdi+58h]
0x180034d5a  mov     rcx, [rdi+50h]
0x180034d5e  mov     rax, [rax]
0x180034d61  cmp     [rcx], rax
0x180034d64  jnz     short loc_180034D6F
0x180034d66  mov     rax, [rdi+60h]
0x180034d6a  cmp     byte ptr [rax], 0
0x180034d6d  jz      short loc_180034DB3
0x180034d6f  mov     rax, [r14]
0x180034d72  mov     rcx, r14
0x180034d75  mov     rax, [rax+18h]
0x180034d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d7e  movzx   esi, ax
0x180034d81  mov     rdx, [rbx+10h]
0x180034d85  inc     rdx
0x180034d88  cmp     rdx, [rbx+18h]
0x180034d8c  jbe     short loc_180034D9C
0x180034d8e  mov     rcx, [rbx]
0x180034d91  mov     rax, [rcx]
0x180034d94  mov     rcx, rbx
0x180034d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d9c  mov     rcx, [rbx+10h]
0x180034da0  mov     rax, [rbx+8]
0x180034da4  mov     [rax+rcx*2], si
0x180034da8  inc     qword ptr [rbx+10h]
0x180034dac  mov     rax, [rdi+60h]
0x180034db0  mov     byte ptr [rax], 0
0x180034db3  mov     rax, [rdi+38h]
0x180034db7  mov     rcx, [rdi+30h]
0x180034dbb  mov     rax, [rax]
0x180034dbe  mov     [rcx], rax
0x180034dc1  mov     rax, [rdi+58h]
0x180034dc5  mov     rcx, [rdi+50h]
0x180034dc9  mov     rax, [rax]
0x180034dcc  cmp     [rcx], rax
0x180034dcf  jz      short loc_180034DD8
0x180034dd1  mov     rax, [rdi+30h]
0x180034dd5  inc     qword ptr [rax]
0x180034dd8  mov     r8, [rdi+68h]
0x180034ddc  mov     rdx, [rdi+30h]
0x180034de0  mov     r9, rbx
0x180034de3  mov     r8, [r8]
0x180034de6  mov     rdx, [rdx]
0x180034de9  lea     rcx, [rsp+88h+arg_0]
0x180034df1  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x180034df6  mov     rbx, [rax]
0x180034df9  mov     rax, [rdi+20h]
0x180034dfd  cmp     byte ptr [rax+0Bh], 0
0x180034e01  jz      short loc_180034E6D
0x180034e03  mov     rax, [rdi+60h]
0x180034e07  cmp     byte ptr [rax], 0
0x180034e0a  jz      short loc_180034E6D
0x180034e0c  mov     rdx, [rbx+10h]
0x180034e10  inc     rdx
0x180034e13  cmp     rdx, [rbx+18h]
0x180034e17  jbe     short loc_180034E27
0x180034e19  mov     rax, [rbx]
0x180034e1c  mov     rcx, rbx
0x180034e1f  mov     rax, [rax]
0x180034e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e27  mov     rcx, [rbx+10h]
0x180034e2b  mov     rax, [rbx+8]
0x180034e2f  mov     word ptr [rax+rcx*2], 2Eh ; '.'
0x180034e35  inc     qword ptr [rbx+10h]
0x180034e39  jmp     short loc_180034E6D
0x180034e3b  mov     rdx, [rbx+10h]
0x180034e3f  inc     rdx
0x180034e42  cmp     rdx, [rbx+18h]
0x180034e46  jbe     short loc_180034E56
0x180034e48  mov     rax, [rbx]
0x180034e4b  mov     rcx, rbx
0x180034e4e  mov     rax, [rax]
0x180034e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e56  mov     rcx, [rbx+10h]
0x180034e5a  mov     rax, [rbx+8]
0x180034e5e  mov     [rax+rcx*2], r12w
0x180034e63  inc     qword ptr [rbx+10h]
0x180034e67  mov     rax, [rdi+70h]
0x180034e6b  dec     dword ptr [rax]
0x180034e6d  mov     rax, [rdi+70h]
0x180034e71  cmp     dword ptr [rax], 0
0x180034e74  jg      short loc_180034E3B
0x180034e76  mov     r8, [rdi+58h]
0x180034e7a  mov     rdx, [rdi+68h]
0x180034e7e  mov     r9, rbx
0x180034e81  mov     r8, [r8]
0x180034e84  mov     rdx, [rdx]
0x180034e87  mov     rcx, rbp
0x180034e8a  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x180034e8f  mov     rax, rbp
0x180034e92  add     rsp, 58h
0x180034e96  pop     r14
0x180034e98  pop     r12
0x180034e9a  pop     rdi
0x180034e9b  pop     rsi
0x180034e9c  pop     rbp
0x180034e9d  pop     rbx
0x180034e9e  retn
```
