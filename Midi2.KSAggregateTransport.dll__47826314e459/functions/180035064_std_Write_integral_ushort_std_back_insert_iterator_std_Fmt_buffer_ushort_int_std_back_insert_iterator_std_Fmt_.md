# `std::_Write_integral<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,int,std::_Basic_format_specs<ushort>,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<ushort>>)

- ea: `0x180035064`
- end: `0x180035222`
- name: `??R_lambda_1_@?1???$_Write_integral@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@H@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@1@V21@HU?$_Basic_format_specs@G@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `446`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180030824`
- `0x18003124c`

## callees

- `0x180030600`
- `0x180032130`
- `0x180032244`
- `0x180033a7c`
- `0x180035064`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18003514d`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18003514d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall `std::_Write_integral<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,int>'::`2'::_lambda_1_::operator()(
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
                   **(_DWORD **)(a1 + 16) >> 31);
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
0x180035064  mov     r11, rsp
0x180035067  mov     [r11+10h], rbx
0x18003506b  mov     [r11+18h], rbp
0x18003506f  push    rsi
0x180035070  push    rdi
0x180035071  push    r14
0x180035073  sub     rsp, 60h
0x180035077  mov     rax, r8
0x18003507a  mov     rbp, rdx
0x18003507d  mov     rdi, rcx
0x180035080  mov     r8, [rcx+10h]
0x180035084  mov     r9d, [r8]
0x180035087  shr     r9d, 1Fh
0x18003508b  mov     r8, [rcx+8]
0x18003508f  mov     r8b, [r8+0Ah]
0x180035093  mov     rdx, rax
0x180035096  lea     rcx, [r11+8]
0x18003509a  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,std::_Fmt_sign,bool)
0x18003509f  mov     rcx, [rdi+18h]
0x1800350a3  mov     rdx, [rcx]
0x1800350a6  mov     r8, [rcx+8]
0x1800350aa  add     r8, rdx
0x1800350ad  mov     r9, [rax]
0x1800350b0  lea     rcx, [rsp+78h+arg_0]
0x1800350b8  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x1800350bd  mov     rbx, [rax]
0x1800350c0  mov     rax, [rdi+20h]
0x1800350c4  cmp     byte ptr [rax], 0
0x1800350c7  jz      short loc_180035115
0x1800350c9  mov     rax, [rdi+8]
0x1800350cd  mov     ecx, [rax]
0x1800350cf  mov     rax, [rdi+28h]
0x1800350d3  cmp     [rax], ecx
0x1800350d5  jge     short loc_180035115
0x1800350d7  sub     ecx, [rax]
0x1800350d9  movsxd  rsi, ecx
0x1800350dc  test    ecx, ecx
0x1800350de  jle     short loc_180035115
0x1800350e0  mov     rdx, [rbx+10h]
0x1800350e4  inc     rdx
0x1800350e7  cmp     rdx, [rbx+18h]
0x1800350eb  jbe     short loc_1800350FB
0x1800350ed  mov     rax, [rbx]
0x1800350f0  mov     rcx, rbx
0x1800350f3  mov     rax, [rax]
0x1800350f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350fb  mov     rcx, [rbx+10h]
0x1800350ff  mov     rax, [rbx+8]
0x180035103  mov     word ptr [rax+rcx*2], 30h ; '0'
0x180035109  inc     qword ptr [rbx+10h]
0x18003510d  dec     rsi
0x180035110  test    rsi, rsi
0x180035113  jg      short loc_1800350E0
0x180035115  mov     rax, [rdi+30h]
0x180035119  mov     r14d, [rax]
0x18003511c  test    r14d, r14d
0x18003511f  jle     loc_1800351F5
0x180035125  mov     rax, [rdi+48h]
0x180035129  mov     rsi, [rax]
0x18003512c  test    rsi, rsi
0x18003512f  jz      short loc_18003514B
0x180035131  mov     rsi, [rsi+8]
0x180035135  mov     [rsp+78h+var_30], rsi
0x18003513a  mov     rax, [rsi]
0x18003513d  mov     rcx, rsi
0x180035140  mov     rax, [rax+8]
0x180035144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035149  jmp     short loc_18003515B
0x18003514b  mov     cl, 1
0x18003514d  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180035153  mov     rsi, rax
0x180035156  mov     [rsp+78h+var_30], rax
0x18003515b  lea     rcx, [rsp+78h+var_38]
0x180035160  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x180035165  mov     rdx, rax
0x180035168  mov     rcx, [rax]
0x18003516b  mov     rax, [rcx+20h]
0x18003516f  mov     rcx, rdx
0x180035172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035177  movzx   r8d, ax
0x18003517b  mov     rax, [rdi+40h]
0x18003517f  cmp     qword ptr [rax+18h], 0Fh
0x180035184  jbe     short loc_18003518B
0x180035186  mov     rcx, [rax]
0x180035189  jmp     short loc_18003518E
0x18003518b  mov     rcx, rax
0x18003518e  mov     [rsp+78h+var_28], rcx
0x180035193  mov     rax, [rax+10h]
0x180035197  mov     [rsp+78h+var_20], rax
0x18003519c  mov     rdx, [rdi+38h]
0x1800351a0  mov     [rsp+78h+var_48], rbx
0x1800351a5  mov     [rsp+78h+var_50], r14d
0x1800351aa  mov     [rsp+78h+var_58], r8w
0x1800351b0  lea     r9, [rsp+78h+var_28]
0x1800351b5  mov     r8, [rdi]
0x1800351b8  mov     rdx, [rdx]
0x1800351bb  mov     rcx, rbp
0x1800351be  call    ??$_Write_separated_integer@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@GHV10@@Z; std::_Write_separated_integer<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::string_view,ushort,int,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x1800351c3  nop
0x1800351c4  test    rsi, rsi
0x1800351c7  jz      short loc_18003520A
0x1800351c9  mov     rax, [rsi]
0x1800351cc  mov     rcx, rsi
0x1800351cf  mov     rax, [rax+10h]
0x1800351d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351d8  mov     r8, rax
0x1800351db  test    rax, rax
0x1800351de  jz      short loc_18003520A
0x1800351e0  mov     rcx, [rax]
0x1800351e3  mov     rax, [rcx]
0x1800351e6  mov     edx, 1
0x1800351eb  mov     rcx, r8
0x1800351ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351f3  jmp     short loc_18003520A
0x1800351f5  mov     rdx, [rdi+38h]
0x1800351f9  mov     r9, rbx
0x1800351fc  mov     r8, [rdi]
0x1800351ff  mov     rdx, [rdx]
0x180035202  mov     rcx, rbp
0x180035205  call    ??$_Widen_and_copy@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<ushort>>)
0x18003520a  mov     rax, rbp
0x18003520d  lea     r11, [rsp+78h+var_18]
0x180035212  mov     rbx, [r11+28h]
0x180035216  mov     rbp, [r11+30h]
0x18003521a  mov     rsp, r11
0x18003521d  pop     r14
0x18003521f  pop     rdi
0x180035220  pop     rsi
0x180035221  retn
```
