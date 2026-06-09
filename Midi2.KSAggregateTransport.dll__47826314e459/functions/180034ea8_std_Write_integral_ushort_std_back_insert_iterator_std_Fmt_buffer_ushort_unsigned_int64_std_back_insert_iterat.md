# `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,unsigned __int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)

- ea: `0x180034ea8`
- end: `0x18003505e`
- name: `??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_KU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `438`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180030748`
- `0x180030ac4`
- `0x180030e60`
- `0x180031608`
- `0x180031d7c`

## callees

- `0x180030600`
- `0x180032130`
- `0x180032244`
- `0x180033a7c`
- `0x180034ea8`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180034f89`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180034f89`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,unsigned __int64>'::`2'::_lambda_1_::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r8
  _QWORD *v7; // rax
  __int64 v8; // rbx
  int v9; // ecx
  _DWORD *v10; // rax
  int v11; // ecx
  __int64 i; // rsi
  int v13; // r14d
  __int64 v14; // rsi
  struct std::locale::_Locimp *v15; // rsi
  __int64 v16; // rax
  __int16 v17; // r8
  __int64 *v18; // rax
  __int64 v19; // rcx
  void (__fastcall ***v20)(_QWORD, __int64); // rax
  _BYTE v22[8]; // [rsp+40h] [rbp-38h] BYREF
  struct std::locale::_Locimp *v23; // [rsp+48h] [rbp-30h]
  _QWORD v24[2]; // [rsp+50h] [rbp-28h] BYREF
  char v25; // [rsp+80h] [rbp+8h] BYREF

  v6 = *(_QWORD *)(a1 + 8);
  LOBYTE(v6) = *(_BYTE *)(v6 + 10);
  v7 = (_QWORD *)std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(&v25, a3, v6, 0);
  v8 = *(_QWORD *)std::_Widen_and_copy<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
                    &v25,
                    **(_QWORD **)(a1 + 24),
                    **(_QWORD **)(a1 + 24) + *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
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
        *(_WORD *)(*(_QWORD *)(v8 + 8) + 2LL * (*(_QWORD *)(v8 + 16))++) = 48;
      }
    }
  }
  v13 = **(_DWORD **)(a1 + 48);
  if ( v13 <= 0 )
  {
    std::_Widen_and_copy<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
      a2,
      **(_QWORD **)(a1 + 56),
      *(_QWORD *)a1,
      v8);
  }
  else
  {
    v14 = **(_QWORD **)(a1 + 72);
    if ( v14 )
    {
      v15 = *(struct std::locale::_Locimp **)(v14 + 8);
      v23 = v15;
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v15 + 8LL))(v15);
    }
    else
    {
      v15 = std::locale::_Init(1);
      v23 = v15;
    }
    v16 = std::use_facet<std::numpunct<unsigned short>>(v22);
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
    v18 = *(__int64 **)(a1 + 64);
    if ( (unsigned __int64)v18[3] <= 0xF )
      v19 = *(_QWORD *)(a1 + 64);
    else
      v19 = *v18;
    v24[0] = v19;
    v24[1] = v18[2];
    std::_Write_separated_integer<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
      a2,
      **(_QWORD **)(a1 + 56),
      *(_QWORD *)a1,
      (unsigned int)v24,
      v17,
      v13,
      v8);
    if ( v15 )
    {
      v20 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v20 )
        (**v20)(v20, 1);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180034ea8  mov     r11, rsp
0x180034eab  mov     [r11+10h], rbx
0x180034eaf  mov     [r11+18h], rbp
0x180034eb3  push    rsi
0x180034eb4  push    rdi
0x180034eb5  push    r14
0x180034eb7  sub     rsp, 60h
0x180034ebb  mov     rax, r8
0x180034ebe  mov     rbp, rdx
0x180034ec1  mov     rdi, rcx
0x180034ec4  mov     r8, [rcx+8]
0x180034ec8  xor     r9d, r9d
0x180034ecb  mov     r8b, [r8+0Ah]
0x180034ecf  mov     rdx, rax
0x180034ed2  lea     rcx, [r11+8]
0x180034ed6  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Fmt_sign,bool)
0x180034edb  mov     r8, [rdi+18h]
0x180034edf  mov     rdx, [r8]
0x180034ee2  mov     r8, [r8+8]
0x180034ee6  add     r8, rdx
0x180034ee9  mov     r9, [rax]
0x180034eec  lea     rcx, [rsp+78h+arg_0]
0x180034ef4  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x180034ef9  mov     rbx, [rax]
0x180034efc  mov     rax, [rdi+20h]
0x180034f00  cmp     byte ptr [rax], 0
0x180034f03  jz      short loc_180034F51
0x180034f05  mov     rax, [rdi+8]
0x180034f09  mov     ecx, [rax]
0x180034f0b  mov     rax, [rdi+28h]
0x180034f0f  cmp     [rax], ecx
0x180034f11  jge     short loc_180034F51
0x180034f13  sub     ecx, [rax]
0x180034f15  movsxd  rsi, ecx
0x180034f18  test    ecx, ecx
0x180034f1a  jle     short loc_180034F51
0x180034f1c  mov     rdx, [rbx+10h]
0x180034f20  inc     rdx
0x180034f23  cmp     rdx, [rbx+18h]
0x180034f27  jbe     short loc_180034F37
0x180034f29  mov     rax, [rbx]
0x180034f2c  mov     rcx, rbx
0x180034f2f  mov     rax, [rax]
0x180034f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f37  mov     rcx, [rbx+10h]
0x180034f3b  mov     rax, [rbx+8]
0x180034f3f  mov     word ptr [rax+rcx*2], 30h ; '0'
0x180034f45  inc     qword ptr [rbx+10h]
0x180034f49  dec     rsi
0x180034f4c  test    rsi, rsi
0x180034f4f  jg      short loc_180034F1C
0x180034f51  mov     rax, [rdi+30h]
0x180034f55  mov     r14d, [rax]
0x180034f58  test    r14d, r14d
0x180034f5b  jle     loc_180035031
0x180034f61  mov     rax, [rdi+48h]
0x180034f65  mov     rsi, [rax]
0x180034f68  test    rsi, rsi
0x180034f6b  jz      short loc_180034F87
0x180034f6d  mov     rsi, [rsi+8]
0x180034f71  mov     [rsp+78h+var_30], rsi
0x180034f76  mov     rax, [rsi]
0x180034f79  mov     rcx, rsi
0x180034f7c  mov     rax, [rax+8]
0x180034f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f85  jmp     short loc_180034F97
0x180034f87  mov     cl, 1
0x180034f89  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180034f8f  mov     rsi, rax
0x180034f92  mov     [rsp+78h+var_30], rax
0x180034f97  lea     rcx, [rsp+78h+var_38]
0x180034f9c  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x180034fa1  mov     rdx, rax
0x180034fa4  mov     rcx, [rax]
0x180034fa7  mov     rax, [rcx+20h]
0x180034fab  mov     rcx, rdx
0x180034fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fb3  movzx   r8d, ax
0x180034fb7  mov     rax, [rdi+40h]
0x180034fbb  cmp     qword ptr [rax+18h], 0Fh
0x180034fc0  jbe     short loc_180034FC7
0x180034fc2  mov     rcx, [rax]
0x180034fc5  jmp     short loc_180034FCA
0x180034fc7  mov     rcx, rax
0x180034fca  mov     [rsp+78h+var_28], rcx
0x180034fcf  mov     rax, [rax+10h]
0x180034fd3  mov     [rsp+78h+var_20], rax
0x180034fd8  mov     rdx, [rdi+38h]
0x180034fdc  mov     [rsp+78h+var_48], rbx
0x180034fe1  mov     [rsp+78h+var_50], r14d
0x180034fe6  mov     [rsp+78h+var_58], r8w
0x180034fec  lea     r9, [rsp+78h+var_28]
0x180034ff1  mov     r8, [rdi]
0x180034ff4  mov     rdx, [rdx]
0x180034ff7  mov     rcx, rbp
0x180034ffa  call    ??$_Write_separated_integer@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@GHV10@@Z; std::_Write_separated_integer<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::string_view,ushort,int,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x180034fff  nop
0x180035000  test    rsi, rsi
0x180035003  jz      short loc_180035046
0x180035005  mov     rax, [rsi]
0x180035008  mov     rcx, rsi
0x18003500b  mov     rax, [rax+10h]
0x18003500f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035014  mov     r8, rax
0x180035017  test    rax, rax
0x18003501a  jz      short loc_180035046
0x18003501c  mov     rcx, [rax]
0x18003501f  mov     rax, [rcx]
0x180035022  mov     edx, 1
0x180035027  mov     rcx, r8
0x18003502a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003502f  jmp     short loc_180035046
0x180035031  mov     rdx, [rdi+38h]
0x180035035  mov     r9, rbx
0x180035038  mov     r8, [rdi]
0x18003503b  mov     rdx, [rdx]
0x18003503e  mov     rcx, rbp
0x180035041  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x180035046  mov     rax, rbp
0x180035049  lea     r11, [rsp+78h+var_18]
0x18003504e  mov     rbx, [r11+28h]
0x180035052  mov     rbp, [r11+30h]
0x180035056  mov     rsp, r11
0x180035059  pop     r14
0x18003505b  pop     rdi
0x18003505c  pop     rsi
0x18003505d  retn
```
