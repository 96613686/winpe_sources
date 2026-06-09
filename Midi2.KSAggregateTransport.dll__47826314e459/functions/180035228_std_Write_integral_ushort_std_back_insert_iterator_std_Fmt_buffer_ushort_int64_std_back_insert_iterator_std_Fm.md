# `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,__int64,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)

- ea: `0x180035228`
- end: `0x1800353e6`
- name: `??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@_J@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@_JU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `446`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180030900`
- `0x1800319bc`

## callees

- `0x180030600`
- `0x180032130`
- `0x180032244`
- `0x180033a7c`
- `0x180035228`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180035311`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180035311`

## pseudocode

```c
__int64 __fastcall `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,__int64>'::`2'::_lambda_1_::operator()(
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
  v7 = (_QWORD *)std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
                   &v25,
                   a3,
                   v6,
                   **(_QWORD **)(a1 + 16) >> 63);
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
0x180035228  mov     r11, rsp
0x18003522b  mov     [r11+10h], rbx
0x18003522f  mov     [r11+18h], rbp
0x180035233  push    rsi
0x180035234  push    rdi
0x180035235  push    r14
0x180035237  sub     rsp, 60h
0x18003523b  mov     rax, r8
0x18003523e  mov     rbp, rdx
0x180035241  mov     rdi, rcx
0x180035244  mov     r8, [rcx+10h]
0x180035248  mov     r9, [r8]
0x18003524b  shr     r9, 3Fh
0x18003524f  mov     r8, [rcx+8]
0x180035253  mov     r8b, [r8+0Ah]
0x180035257  mov     rdx, rax
0x18003525a  lea     rcx, [r11+8]
0x18003525e  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Fmt_sign,bool)
0x180035263  mov     rcx, [rdi+18h]
0x180035267  mov     rdx, [rcx]
0x18003526a  mov     r8, [rcx+8]
0x18003526e  add     r8, rdx
0x180035271  mov     r9, [rax]
0x180035274  lea     rcx, [rsp+78h+arg_0]
0x18003527c  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x180035281  mov     rbx, [rax]
0x180035284  mov     rax, [rdi+20h]
0x180035288  cmp     byte ptr [rax], 0
0x18003528b  jz      short loc_1800352D9
0x18003528d  mov     rax, [rdi+8]
0x180035291  mov     ecx, [rax]
0x180035293  mov     rax, [rdi+28h]
0x180035297  cmp     [rax], ecx
0x180035299  jge     short loc_1800352D9
0x18003529b  sub     ecx, [rax]
0x18003529d  movsxd  rsi, ecx
0x1800352a0  test    ecx, ecx
0x1800352a2  jle     short loc_1800352D9
0x1800352a4  mov     rdx, [rbx+10h]
0x1800352a8  inc     rdx
0x1800352ab  cmp     rdx, [rbx+18h]
0x1800352af  jbe     short loc_1800352BF
0x1800352b1  mov     rax, [rbx]
0x1800352b4  mov     rcx, rbx
0x1800352b7  mov     rax, [rax]
0x1800352ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352bf  mov     rcx, [rbx+10h]
0x1800352c3  mov     rax, [rbx+8]
0x1800352c7  mov     word ptr [rax+rcx*2], 30h ; '0'
0x1800352cd  inc     qword ptr [rbx+10h]
0x1800352d1  dec     rsi
0x1800352d4  test    rsi, rsi
0x1800352d7  jg      short loc_1800352A4
0x1800352d9  mov     rax, [rdi+30h]
0x1800352dd  mov     r14d, [rax]
0x1800352e0  test    r14d, r14d
0x1800352e3  jle     loc_1800353B9
0x1800352e9  mov     rax, [rdi+48h]
0x1800352ed  mov     rsi, [rax]
0x1800352f0  test    rsi, rsi
0x1800352f3  jz      short loc_18003530F
0x1800352f5  mov     rsi, [rsi+8]
0x1800352f9  mov     [rsp+78h+var_30], rsi
0x1800352fe  mov     rax, [rsi]
0x180035301  mov     rcx, rsi
0x180035304  mov     rax, [rax+8]
0x180035308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003530d  jmp     short loc_18003531F
0x18003530f  mov     cl, 1
0x180035311  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180035317  mov     rsi, rax
0x18003531a  mov     [rsp+78h+var_30], rax
0x18003531f  lea     rcx, [rsp+78h+var_38]
0x180035324  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x180035329  mov     rdx, rax
0x18003532c  mov     rcx, [rax]
0x18003532f  mov     rax, [rcx+20h]
0x180035333  mov     rcx, rdx
0x180035336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003533b  movzx   r8d, ax
0x18003533f  mov     rax, [rdi+40h]
0x180035343  cmp     qword ptr [rax+18h], 0Fh
0x180035348  jbe     short loc_18003534F
0x18003534a  mov     rcx, [rax]
0x18003534d  jmp     short loc_180035352
0x18003534f  mov     rcx, rax
0x180035352  mov     [rsp+78h+var_28], rcx
0x180035357  mov     rax, [rax+10h]
0x18003535b  mov     [rsp+78h+var_20], rax
0x180035360  mov     rdx, [rdi+38h]
0x180035364  mov     [rsp+78h+var_48], rbx
0x180035369  mov     [rsp+78h+var_50], r14d
0x18003536e  mov     [rsp+78h+var_58], r8w
0x180035374  lea     r9, [rsp+78h+var_28]
0x180035379  mov     r8, [rdi]
0x18003537c  mov     rdx, [rdx]
0x18003537f  mov     rcx, rbp
0x180035382  call    ??$_Write_separated_integer@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@GHV10@@Z; std::_Write_separated_integer<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::string_view,ushort,int,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x180035387  nop
0x180035388  test    rsi, rsi
0x18003538b  jz      short loc_1800353CE
0x18003538d  mov     rax, [rsi]
0x180035390  mov     rcx, rsi
0x180035393  mov     rax, [rax+10h]
0x180035397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003539c  mov     r8, rax
0x18003539f  test    rax, rax
0x1800353a2  jz      short loc_1800353CE
0x1800353a4  mov     rcx, [rax]
0x1800353a7  mov     rax, [rcx]
0x1800353aa  mov     edx, 1
0x1800353af  mov     rcx, r8
0x1800353b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800353b7  jmp     short loc_1800353CE
0x1800353b9  mov     rdx, [rdi+38h]
0x1800353bd  mov     r9, rbx
0x1800353c0  mov     r8, [rdi]
0x1800353c3  mov     rdx, [rdx]
0x1800353c6  mov     rcx, rbp
0x1800353c9  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x1800353ce  mov     rax, rbp
0x1800353d1  lea     r11, [rsp+78h+var_18]
0x1800353d6  mov     rbx, [r11+28h]
0x1800353da  mov     rbp, [r11+30h]
0x1800353de  mov     rsp, r11
0x1800353e1  pop     r14
0x1800353e3  pop     rdi
0x1800353e4  pop     rsi
0x1800353e5  retn
```
