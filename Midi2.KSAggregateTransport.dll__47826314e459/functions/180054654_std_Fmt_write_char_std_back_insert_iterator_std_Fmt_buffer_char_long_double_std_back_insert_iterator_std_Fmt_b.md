# `std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,long double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)'::`2'::_lambda_1_::operator()(std::back_insert_iterator<std::_Fmt_buffer<char>>)

- ea: `0x180054654`
- end: `0x18005490d`
- name: `??R_lambda_1_@?1???$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@1@V21@OAEBU?$_Basic_format_specs@D@1@V_Lazy_locale@1@@Z@QEBA@0@Z`
- size: `697`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18004eca8`
- `0x18004f370`
- `0x18004fa40`

## callees

- `0x180051b6c`
- `0x1800535e8`
- `0x1800536f8`
- `0x180053d44`
- `0x180054654`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180054712`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180054712`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall `std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>'::`2'::_lambda_1_::operator()(
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
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rsi
  void (__fastcall ***v16)(_QWORD, __int64); // r8
  void (__fastcall ***v17)(_QWORD, __int64); // rax
  int v18; // ebp
  char v19; // r9
  __int64 *v20; // rax
  __int64 v21; // rcx
  char v22; // si
  __int64 v23; // rbx
  __int64 v25; // [rsp+40h] [rbp-28h] BYREF
  struct std::locale::_Locimp *v26; // [rsp+48h] [rbp-20h]
  char v27; // [rsp+70h] [rbp+8h] BYREF

  v6 = *(_BYTE **)(a1 + 8);
  v7 = *(_BYTE **)a1;
  LOBYTE(v6) = *v6;
  LOBYTE(v7) = **(_BYTE **)a1;
  v8 = *(_QWORD *)std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(&v27, a3, v7, v6);
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
        *(_BYTE *)(*(_QWORD *)(v8 + 16) + *(_QWORD *)(v8 + 8)) = 48;
        ++*(_QWORD *)(v8 + 16);
      }
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 32) + 12LL) )
  {
    v13 = *(_QWORD *)(a1 + 40);
    if ( *(_QWORD *)v13 )
    {
      v26 = *(struct std::locale::_Locimp **)(*(_QWORD *)v13 + 8LL);
      (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v26 + 8LL))(v26);
    }
    else
    {
      v26 = std::locale::_Init(1);
    }
    v15 = std::use_facet<std::numpunct<char>>(&v25);
    if ( v26 )
    {
      v17 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v26 + 16LL))(v26);
      v16 = v17;
      if ( v17 )
        (**v17)(v17, 1);
    }
    v18 = **(_DWORD **)(a1 + 72);
    v19 = (*(__int64 (__fastcall **)(__int64, __int64, void (__fastcall ***)(_QWORD, __int64)))(*(_QWORD *)v15 + 32LL))(
            v15,
            v14,
            v16);
    v20 = *(__int64 **)(a1 + 64);
    if ( (unsigned __int64)v20[3] <= 0xF )
      v21 = *(_QWORD *)(a1 + 64);
    else
      v21 = *v20;
    v25 = v21;
    v26 = (struct std::locale::_Locimp *)v20[2];
    v8 = *(_QWORD *)std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
                      (unsigned int)&v27,
                      **(_QWORD **)(a1 + 48),
                      **(_QWORD **)(a1 + 56),
                      (unsigned int)&v25,
                      v19,
                      v18,
                      v8);
    if ( **(_QWORD **)(a1 + 80) != **(_QWORD **)(a1 + 88) || **(_BYTE **)(a1 + 96) )
    {
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 24LL))(v15);
      if ( (unsigned __int64)(*(_QWORD *)(v8 + 16) + 1LL) > *(_QWORD *)(v8 + 24) )
        (**(void (__fastcall ***)(__int64))v8)(v8);
      *(_BYTE *)(*(_QWORD *)(v8 + 8) + (*(_QWORD *)(v8 + 16))++) = v22;
      **(_BYTE **)(a1 + 96) = 0;
    }
    **(_QWORD **)(a1 + 48) = **(_QWORD **)(a1 + 56);
    if ( **(_QWORD **)(a1 + 80) != **(_QWORD **)(a1 + 88) )
      ++**(_QWORD **)(a1 + 48);
  }
  v23 = *(_QWORD *)std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
                     &v27,
                     **(_QWORD **)(a1 + 48),
                     **(_QWORD **)(a1 + 104),
                     v8);
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 32) + 11LL) && **(_BYTE **)(a1 + 96) )
  {
    if ( (unsigned __int64)(*(_QWORD *)(v23 + 16) + 1LL) > *(_QWORD *)(v23 + 24) )
      (**(void (__fastcall ***)(__int64))v23)(v23);
    *(_BYTE *)(*(_QWORD *)(v23 + 8) + (*(_QWORD *)(v23 + 16))++) = 46;
  }
  while ( **(int **)(a1 + 112) > 0 )
  {
    if ( (unsigned __int64)(*(_QWORD *)(v23 + 16) + 1LL) > *(_QWORD *)(v23 + 24) )
      (**(void (__fastcall ***)(__int64))v23)(v23);
    *(_BYTE *)(*(_QWORD *)(v23 + 16) + *(_QWORD *)(v23 + 8)) = 48;
    ++*(_QWORD *)(v23 + 16);
    --**(_DWORD **)(a1 + 112);
  }
  std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(
    a2,
    **(_QWORD **)(a1 + 104),
    **(_QWORD **)(a1 + 88),
    v23);
  return a2;
}

```

## disassembly

```asm
0x180054654  mov     [rsp+arg_8], rbx
0x180054659  mov     [rsp+arg_10], rbp
0x18005465e  push    rsi
0x18005465f  push    rdi
0x180054660  push    r14
0x180054662  sub     rsp, 50h
0x180054666  mov     rax, r8
0x180054669  mov     r14, rdx
0x18005466c  mov     rdi, rcx
0x18005466f  mov     r9, [rcx+8]
0x180054673  mov     r8, [rcx]
0x180054676  mov     r9b, [r9]
0x180054679  mov     r8b, [r8]
0x18005467c  mov     rdx, rax
0x18005467f  lea     rcx, [rsp+68h+arg_0]
0x180054684  call    ??$_Write_sign@V?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@W4_Fmt_sign@0@_N@Z; std::_Write_sign<std::back_insert_iterator<std::_Fmt_buffer<char>>>(std::back_insert_iterator<std::_Fmt_buffer<char>>,std::_Fmt_sign,bool)
0x180054689  mov     rbx, [rax]
0x18005468c  mov     rax, [rdi+10h]
0x180054690  cmp     byte ptr [rax], 0
0x180054693  jz      short loc_1800546DF
0x180054695  mov     rax, [rdi+20h]
0x180054699  mov     ecx, [rax]
0x18005469b  mov     rax, [rdi+18h]
0x18005469f  cmp     [rax], ecx
0x1800546a1  jge     short loc_1800546DF
0x1800546a3  sub     ecx, [rax]
0x1800546a5  movsxd  rsi, ecx
0x1800546a8  test    ecx, ecx
0x1800546aa  jle     short loc_1800546DF
0x1800546ac  mov     rdx, [rbx+10h]
0x1800546b0  inc     rdx
0x1800546b3  cmp     rdx, [rbx+18h]
0x1800546b7  jbe     short loc_1800546C7
0x1800546b9  mov     rax, [rbx]
0x1800546bc  mov     rcx, rbx
0x1800546bf  mov     rax, [rax]
0x1800546c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546c7  mov     rcx, [rbx+10h]
0x1800546cb  mov     rax, [rbx+8]
0x1800546cf  mov     byte ptr [rcx+rax], 30h ; '0'
0x1800546d3  inc     qword ptr [rbx+10h]
0x1800546d7  dec     rsi
0x1800546da  test    rsi, rsi
0x1800546dd  jg      short loc_1800546AC
0x1800546df  mov     rax, [rdi+20h]
0x1800546e3  cmp     byte ptr [rax+0Ch], 0
0x1800546e7  jz      loc_180054844
0x1800546ed  mov     rax, [rdi+28h]
0x1800546f1  mov     rcx, [rax]
0x1800546f4  test    rcx, rcx
0x1800546f7  jz      short loc_180054710
0x1800546f9  mov     rcx, [rcx+8]
0x1800546fd  mov     [rsp+68h+var_20], rcx
0x180054702  mov     rax, [rcx]
0x180054705  mov     rax, [rax+8]
0x180054709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005470e  jmp     short loc_18005471D
0x180054710  mov     cl, 1
0x180054712  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180054718  mov     [rsp+68h+var_20], rax
0x18005471d  lea     rcx, [rsp+68h+var_28]
0x180054722  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180054727  mov     rsi, rax
0x18005472a  mov     rcx, [rsp+68h+var_20]
0x18005472f  test    rcx, rcx
0x180054732  jz      short loc_18005475B
0x180054734  mov     rdx, [rcx]
0x180054737  mov     rax, [rdx+10h]
0x18005473b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054740  mov     r8, rax
0x180054743  test    rax, rax
0x180054746  jz      short loc_18005475B
0x180054748  mov     rcx, [rax]
0x18005474b  mov     rax, [rcx]
0x18005474e  mov     edx, 1
0x180054753  mov     rcx, r8
0x180054756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005475b  mov     rax, [rdi+48h]
0x18005475f  mov     ebp, [rax]
0x180054761  mov     rax, [rsi]
0x180054764  mov     rcx, rsi
0x180054767  mov     rax, [rax+20h]
0x18005476b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054770  mov     r9b, al
0x180054773  mov     rax, [rdi+40h]
0x180054777  cmp     qword ptr [rax+18h], 0Fh
0x18005477c  jbe     short loc_180054783
0x18005477e  mov     rcx, [rax]
0x180054781  jmp     short loc_180054786
0x180054783  mov     rcx, rax
0x180054786  mov     [rsp+68h+var_28], rcx
0x18005478b  mov     rax, [rax+10h]
0x18005478f  mov     [rsp+68h+var_20], rax
0x180054794  mov     r8, [rdi+38h]
0x180054798  mov     rdx, [rdi+30h]
0x18005479c  mov     [rsp+68h+var_38], rbx
0x1800547a1  mov     [rsp+68h+var_40], ebp
0x1800547a5  mov     [rsp+68h+var_48], r9b
0x1800547aa  lea     r9, [rsp+68h+var_28]
0x1800547af  mov     r8, [r8]
0x1800547b2  mov     rdx, [rdx]
0x1800547b5  lea     rcx, [rsp+68h+arg_0]
0x1800547ba  call    ??$_Write_separated_integer@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV?$basic_string_view@DU?$char_traits@D@std@@@0@DHV10@@Z; std::_Write_separated_integer<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::string_view,char,int,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x1800547bf  mov     rbx, [rax]
0x1800547c2  mov     rdx, [rdi+50h]
0x1800547c6  mov     rax, [rdi+58h]
0x1800547ca  mov     rcx, [rax]
0x1800547cd  cmp     [rdx], rcx
0x1800547d0  jnz     short loc_1800547DB
0x1800547d2  mov     rax, [rdi+60h]
0x1800547d6  cmp     byte ptr [rax], 0
0x1800547d9  jz      short loc_18005481F
0x1800547db  mov     rax, [rsi]
0x1800547de  mov     rcx, rsi
0x1800547e1  mov     rax, [rax+18h]
0x1800547e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547ea  mov     sil, al
0x1800547ed  mov     rdx, [rbx+10h]
0x1800547f1  inc     rdx
0x1800547f4  cmp     rdx, [rbx+18h]
0x1800547f8  jbe     short loc_180054808
0x1800547fa  mov     rcx, [rbx]
0x1800547fd  mov     rax, [rcx]
0x180054800  mov     rcx, rbx
0x180054803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054808  mov     rcx, [rbx+8]
0x18005480c  mov     rax, [rbx+10h]
0x180054810  mov     [rcx+rax], sil
0x180054814  inc     qword ptr [rbx+10h]
0x180054818  mov     rax, [rdi+60h]
0x18005481c  mov     byte ptr [rax], 0
0x18005481f  mov     rax, [rdi+38h]
0x180054823  mov     rcx, [rdi+30h]
0x180054827  mov     rax, [rax]
0x18005482a  mov     [rcx], rax
0x18005482d  mov     rdx, [rdi+50h]
0x180054831  mov     rax, [rdi+58h]
0x180054835  mov     rcx, [rax]
0x180054838  cmp     [rdx], rcx
0x18005483b  jz      short loc_180054844
0x18005483d  mov     rax, [rdi+30h]
0x180054841  inc     qword ptr [rax]
0x180054844  mov     r8, [rdi+68h]
0x180054848  mov     rdx, [rdi+30h]
0x18005484c  mov     r9, rbx
0x18005484f  mov     r8, [r8]
0x180054852  mov     rdx, [rdx]
0x180054855  lea     rcx, [rsp+68h+arg_0]
0x18005485a  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x18005485f  mov     rbx, [rax]
0x180054862  mov     rax, [rdi+20h]
0x180054866  cmp     byte ptr [rax+0Bh], 0
0x18005486a  jz      short loc_1800548D3
0x18005486c  mov     rax, [rdi+60h]
0x180054870  cmp     byte ptr [rax], 0
0x180054873  jz      short loc_1800548D3
0x180054875  mov     rdx, [rbx+10h]
0x180054879  inc     rdx
0x18005487c  cmp     rdx, [rbx+18h]
0x180054880  jbe     short loc_180054890
0x180054882  mov     rax, [rbx]
0x180054885  mov     rcx, rbx
0x180054888  mov     rax, [rax]
0x18005488b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054890  mov     rcx, [rbx+8]
0x180054894  mov     rax, [rbx+10h]
0x180054898  mov     byte ptr [rcx+rax], 2Eh ; '.'
0x18005489c  inc     qword ptr [rbx+10h]
0x1800548a0  jmp     short loc_1800548D3
0x1800548a2  mov     rdx, [rbx+10h]
0x1800548a6  inc     rdx
0x1800548a9  cmp     rdx, [rbx+18h]
0x1800548ad  jbe     short loc_1800548BD
0x1800548af  mov     rax, [rbx]
0x1800548b2  mov     rcx, rbx
0x1800548b5  mov     rax, [rax]
0x1800548b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548bd  mov     rcx, [rbx+10h]
0x1800548c1  mov     rax, [rbx+8]
0x1800548c5  mov     byte ptr [rcx+rax], 30h ; '0'
0x1800548c9  inc     qword ptr [rbx+10h]
0x1800548cd  mov     rax, [rdi+70h]
0x1800548d1  dec     dword ptr [rax]
0x1800548d3  mov     rax, [rdi+70h]
0x1800548d7  cmp     dword ptr [rax], 0
0x1800548da  jg      short loc_1800548A2
0x1800548dc  mov     r8, [rdi+58h]
0x1800548e0  mov     rdx, [rdi+68h]
0x1800548e4  mov     r9, rbx
0x1800548e7  mov     r8, [r8]
0x1800548ea  mov     rdx, [rdx]
0x1800548ed  mov     rcx, r14
0x1800548f0  call    ??$_Widen_and_copy@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@PEBDQEBDV10@@Z; std::_Widen_and_copy<char,std::back_insert_iterator<std::_Fmt_buffer<char>>>(char const *,char const * const,std::back_insert_iterator<std::_Fmt_buffer<char>>)
0x1800548f5  mov     rax, r14
0x1800548f8  lea     r11, [rsp+68h+var_18]
0x1800548fd  mov     rbx, [r11+28h]
0x180054901  mov     rbp, [r11+30h]
0x180054905  mov     rsp, r11
0x180054908  pop     r14
0x18005490a  pop     rdi
0x18005490b  pop     rsi
0x18005490c  retn
```
