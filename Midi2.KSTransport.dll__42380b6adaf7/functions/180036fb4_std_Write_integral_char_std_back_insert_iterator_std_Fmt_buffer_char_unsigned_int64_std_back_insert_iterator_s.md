# `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>(std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64,std::_Basic_format_specs<char>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x180036fb4`
- end: `0x18003714b`
- name: `??R_lambda_1_@?1???$_Write_integral@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@_K@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@_KU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `407`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180032c34`
- `0x1800337ac`
- `0x180033f10`

## callees

- `0x180032838`
- `0x1800342b4`
- `0x1800343c4`
- `0x180035ca4`
- `0x180036fb4`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180037086`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180037086`

## pseudocode

```c
__int64 __fastcall `std::_Write_integral<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,unsigned __int64>'::`2'::_lambda_1_::operator()(
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
  char v24; // [rsp+90h] [rbp+8h] BYREF

  v6 = *(_QWORD *)(a1 + 8);
  LOBYTE(v6) = *(_BYTE *)(v6 + 10);
  v7 = (_QWORD *)std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(&v24, a3, v6, 0);
  v8 = *(_QWORD *)std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
                    &v24,
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
        *(_BYTE *)(*(_QWORD *)(v8 + 8) + (*(_QWORD *)(v8 + 16))++) = 48;
      }
    }
  }
  v13 = **(_DWORD **)(a1 + 48);
  if ( v13 <= 0 )
  {
    std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
      a2,
      **(_QWORD **)(a1 + 56),
      *(_QWORD *)a1,
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
      a2,
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
0x180036fb4  mov     r11, rsp
0x180036fb7  push    rbx
0x180036fb8  push    rbp
0x180036fb9  push    rsi
0x180036fba  push    rdi
0x180036fbb  sub     rsp, 68h
0x180036fbf  mov     rax, r8
0x180036fc2  mov     rbp, rdx
0x180036fc5  mov     rdi, rcx
0x180036fc8  mov     r8, [rcx+8]
0x180036fcc  xor     r9d, r9d
0x180036fcf  mov     r8b, [r8+0Ah]
0x180036fd3  mov     rdx, rax
0x180036fd6  lea     rcx, [r11+8]
0x180036fda  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x180036fdf  mov     r8, [rdi+18h]
0x180036fe3  mov     rdx, [r8]
0x180036fe6  mov     r8, [r8+8]
0x180036fea  add     r8, rdx
0x180036fed  mov     r9, [rax]
0x180036ff0  lea     rcx, [rsp+88h+arg_0]
0x180036ff8  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x180036ffd  mov     rbx, [rax]
0x180037000  mov     rax, [rdi+20h]
0x180037004  cmp     byte ptr [rax], 0
0x180037007  jz      short loc_180037053
0x180037009  mov     rax, [rdi+8]
0x18003700d  mov     ecx, [rax]
0x18003700f  mov     rax, [rdi+28h]
0x180037013  cmp     [rax], ecx
0x180037015  jge     short loc_180037053
0x180037017  sub     ecx, [rax]
0x180037019  movsxd  rsi, ecx
0x18003701c  test    ecx, ecx
0x18003701e  jle     short loc_180037053
0x180037020  mov     rdx, [rbx+10h]
0x180037024  inc     rdx
0x180037027  cmp     rdx, [rbx+18h]
0x18003702b  jbe     short loc_18003703B
0x18003702d  mov     rax, [rbx]
0x180037030  mov     rcx, rbx
0x180037033  mov     rax, [rax]
0x180037036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003703b  mov     rcx, [rbx+8]
0x18003703f  mov     rax, [rbx+10h]
0x180037043  mov     byte ptr [rcx+rax], 30h ; '0'
0x180037047  inc     qword ptr [rbx+10h]
0x18003704b  dec     rsi
0x18003704e  test    rsi, rsi
0x180037051  jg      short loc_180037020
0x180037053  mov     rax, [rdi+30h]
0x180037057  mov     esi, [rax]
0x180037059  test    esi, esi
0x18003705b  jle     loc_18003712A
0x180037061  mov     rax, [rdi+48h]
0x180037065  mov     rcx, [rax]
0x180037068  test    rcx, rcx
0x18003706b  jz      short loc_180037084
0x18003706d  mov     rcx, [rcx+8]
0x180037071  mov     [rsp+88h+var_40], rcx
0x180037076  mov     rax, [rcx]
0x180037079  mov     rax, [rax+8]
0x18003707d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037082  jmp     short loc_180037091
0x180037084  mov     cl, 1
0x180037086  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18003708c  mov     [rsp+88h+var_40], rax
0x180037091  lea     rcx, [rsp+88h+var_48]
0x180037096  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18003709b  mov     rdx, rax
0x18003709e  mov     rcx, [rax]
0x1800370a1  mov     rax, [rcx+20h]
0x1800370a5  mov     rcx, rdx
0x1800370a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370ad  mov     r8b, al
0x1800370b0  mov     rax, [rdi+40h]
0x1800370b4  cmp     qword ptr [rax+18h], 0Fh
0x1800370b9  jbe     short loc_1800370C0
0x1800370bb  mov     rcx, [rax]
0x1800370be  jmp     short loc_1800370C3
0x1800370c0  mov     rcx, rax
0x1800370c3  mov     [rsp+88h+var_38], rcx
0x1800370c8  mov     rax, [rax+10h]
0x1800370cc  mov     [rsp+88h+var_30], rax
0x1800370d1  mov     rdx, [rdi+38h]
0x1800370d5  mov     [rsp+88h+var_58], rbx
0x1800370da  mov     [rsp+88h+var_60], esi
0x1800370de  mov     [rsp+88h+var_68], r8b
0x1800370e3  lea     r9, [rsp+88h+var_38]
0x1800370e8  mov     r8, [rdi]
0x1800370eb  mov     rdx, [rdx]
0x1800370ee  mov     rcx, rbp
0x1800370f1  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x1800370f6  nop
0x1800370f7  mov     rcx, [rsp+88h+var_40]
0x1800370fc  test    rcx, rcx
0x1800370ff  jz      short loc_18003713F
0x180037101  mov     rax, [rcx]
0x180037104  mov     rax, [rax+10h]
0x180037108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003710d  mov     r8, rax
0x180037110  test    rax, rax
0x180037113  jz      short loc_18003713F
0x180037115  mov     rcx, [rax]
0x180037118  mov     rax, [rcx]
0x18003711b  mov     edx, 1
0x180037120  mov     rcx, r8
0x180037123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037128  jmp     short loc_18003713F
0x18003712a  mov     rdx, [rdi+38h]
0x18003712e  mov     r9, rbx
0x180037131  mov     r8, [rdi]
0x180037134  mov     rdx, [rdx]
0x180037137  mov     rcx, rbp
0x18003713a  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18003713f  mov     rax, rbp
0x180037142  add     rsp, 68h
0x180037146  pop     rdi
0x180037147  pop     rsi
0x180037148  pop     rbp
0x180037149  pop     rbx
0x18003714a  retn
```
