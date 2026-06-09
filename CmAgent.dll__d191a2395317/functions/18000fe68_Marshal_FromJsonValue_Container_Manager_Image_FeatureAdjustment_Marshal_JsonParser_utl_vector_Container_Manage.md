# Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(Marshal::JsonParser &,utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x18000fe68`
- end: `0x18001017f`
- name: `??$FromJsonValue@UFeatureAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@utl@@@utl@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `791`
- prototype: `char __fastcall(Marshal::JsonParser *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180010bb0`

## callees

- `0x180002534`
- `0x180003ce4`
- `0x18000fc94`
- `0x18000fe68`
- `0x1800131b0`
- `0x1800150f8`
- `0x180021220`
- `0x18002163c`

## string_xrefs

- `0x18001015b`: `onecore\internal\vm\inc\marshaljsonutl.h`
- `0x18001016d`: `onecore\internal\vm\inc\marshaljsonutl.h`

## pseudocode

```c
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(
        Marshal::JsonParser *a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v6; // r9
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  _OWORD *v11; // rcx
  _OWORD *v12; // r9
  const char *v13; // r9
  char v14; // r14
  __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rbx
  void *v18; // rcx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rdx
  char v22; // al
  int i; // esi
  __int64 v24; // rbx
  __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  char v28; // al
  __int64 v29; // rcx
  _OWORD *v30; // rdx
  _OWORD *v31; // r8
  __int128 v33; // [rsp+20h] [rbp-20h] BYREF
  __int64 v34; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  v33 = 0;
  v6 = 0;
  v34 = 0;
  v7 = 0;
  v8 = *a2;
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((a2[1] - *a2) >> 3) )
  {
    v9 = *((_QWORD *)&v33 + 1);
    while ( 1 )
    {
      v10 = v8 + 40LL * v7;
      if ( v9 == v6 )
      {
        std::vector<Container::Manager::Image::FeatureAdjustment>::_Emplace_reallocate<Container::Manager::Image::FeatureAdjustment>(
          &v33,
          v9,
          (__int64 *)v10);
        v9 = *((_QWORD *)&v33 + 1);
      }
      else
      {
        v11 = (_OWORD *)(v10 + 16);
        v12 = (_OWORD *)(v9 + 16);
        if ( *(_QWORD *)v10 == v10 + 16 )
        {
          *(_QWORD *)v9 = v12;
          *(_QWORD *)(v9 + 8) = v9 + 2 * (((*(_QWORD *)(v10 + 8) - v10 - 16) >> 1) + 8);
          *v12 = *v11;
        }
        else
        {
          *(_QWORD *)v9 = *(_QWORD *)v10;
          *(_QWORD *)(v9 + 8) = *(_QWORD *)(v10 + 8);
          *(_QWORD *)v12 = *(_QWORD *)v11;
        }
        *(_QWORD *)v10 = v11;
        *(_QWORD *)(v10 + 8) = v11;
        *(_WORD *)v11 = 0;
        *(_DWORD *)(v9 + 32) = *(_DWORD *)(v10 + 32);
        v9 = *((_QWORD *)&v33 + 1) + 40LL;
        *((_QWORD *)&v33 + 1) += 40LL;
      }
      ++v7;
      v8 = *a2;
      if ( v7 >= 0xCCCCCCCCCCCCCCCDuLL * ((a2[1] - *a2) >> 3) )
        break;
      v6 = v34;
    }
  }
  v14 = Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(a1, (__int64 *)&v33, a3);
  if ( v14 )
  {
    v15 = *a2;
    v16 = a2[1];
    a2[1] = *a2;
    v17 = (v16 - v15) / 40;
    while ( v17 )
    {
      --v17;
      v18 = *(void **)(v15 + 40 * v17);
      if ( v18 != (void *)(v15 + 8 * (5 * v17 + 2)) )
        operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
    }
    v19 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v33 + 1) - v33) >> 3);
    v20 = 0xCCCCCCCCCCCCCCCDuLL * ((a2[2] - *a2) >> 3);
    if ( v19 <= v20 )
      goto LABEL_24;
    v21 = 7 * (v20 >> 2) + 8;
    if ( v21 < v19 )
      v21 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v33 + 1) - v33) >> 3);
    if ( v21 > 0x333333333333333LL )
      v21 = 0x333333333333333LL;
    if ( v19 <= v21
      && (unsigned __int8)utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>::_SetCapacity(a2) )
    {
LABEL_24:
      v22 = 0;
    }
    else
    {
      v22 = 1;
    }
    if ( v22 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
        (const char *)0x8007000ELL,
        v33);
    for ( i = 0; i < 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v33 + 1) - v33) >> 3); ++i )
    {
      v24 = v33 + 40LL * i;
      v25 = a2[2];
      if ( a2[1] != v25 )
        goto LABEL_33;
      v26 = 0xCCCCCCCCCCCCCCCDuLL * ((v25 - *a2) >> 3);
      v27 = 7 * (v26 >> 2) + 8;
      if ( v27 > 0x333333333333333LL )
        v27 = 0x333333333333333LL;
      if ( v26 < v27
        && (unsigned __int8)utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>::_SetCapacity(a2) )
      {
LABEL_33:
        v29 = a2[1];
        v30 = (_OWORD *)(v24 + 16);
        v31 = (_OWORD *)(v29 + 16);
        if ( *(_QWORD *)v24 == v24 + 16 )
        {
          *(_QWORD *)v29 = v31;
          *(_QWORD *)(v29 + 8) = v29 + 2 * (((*(_QWORD *)(v24 + 8) - v24 - 16) >> 1) + 8);
          *v31 = *v30;
        }
        else
        {
          *(_QWORD *)v29 = *(_QWORD *)v24;
          *(_QWORD *)(v29 + 8) = *(_QWORD *)(v24 + 8);
          *(_QWORD *)v31 = *(_QWORD *)v30;
        }
        *(_QWORD *)v24 = v30;
        *(_QWORD *)(v24 + 8) = v30;
        *(_WORD *)v30 = 0;
        *(_DWORD *)(v29 + 32) = *(_DWORD *)(v24 + 32);
        a2[1] += 40;
        v28 = 0;
      }
      else
      {
        v28 = 1;
      }
      if ( v28 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x7F,
          (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
          v13);
    }
  }
  std::vector<Container::Manager::Image::PackageAdjustment>::~vector<Container::Manager::Image::PackageAdjustment>(&v33);
  return v14;
}

```

## disassembly

```asm
0x18000fe68  push    rbp
0x18000fe6a  push    rbx
0x18000fe6b  push    rsi
0x18000fe6c  push    rdi
0x18000fe6d  push    r12
0x18000fe6f  push    r14
0x18000fe71  push    r15
0x18000fe73  mov     rbp, rsp
0x18000fe76  sub     rsp, 40h
0x18000fe7a  mov     rsi, r8
0x18000fe7d  mov     rdi, rdx
0x18000fe80  mov     r14, rcx
0x18000fe83  xorps   xmm0, xmm0
0x18000fe86  movdqu  [rbp+var_20], xmm0
0x18000fe8b  xor     r9d, r9d
0x18000fe8e  mov     [rbp+var_10], r9
0x18000fe92  xor     ebx, ebx
0x18000fe94  mov     r8, [rdx]
0x18000fe97  mov     rax, [rdx+8]
0x18000fe9b  sub     rax, r8
0x18000fe9e  sar     rax, 3
0x18000fea2  mov     r15, 0CCCCCCCCCCCCCCCDh
0x18000feac  imul    rax, r15
0x18000feb0  test    rax, rax
0x18000feb3  jz      loc_18000FF68
0x18000feb9  mov     rdx, qword ptr [rbp+var_20+8]
0x18000febd  movsxd  rax, ebx
0x18000fec0  lea     rcx, [rax+rax*4]
0x18000fec4  lea     r8, [r8+rcx*8]
0x18000fec8  cmp     rdx, r9
0x18000fecb  jz      short loc_18000FF36
0x18000fecd  lea     rcx, [r8+10h]
0x18000fed1  mov     rax, [r8]
0x18000fed4  lea     r9, [rdx+10h]
0x18000fed8  cmp     rax, rcx
0x18000fedb  jnz     short loc_18000FF04
0x18000fedd  mov     [rdx], r9
0x18000fee0  mov     rax, [r8+8]
0x18000fee4  sub     rax, r8
0x18000fee7  sub     rax, 10h
0x18000feeb  sar     rax, 1
0x18000feee  add     rax, 8
0x18000fef2  lea     rax, [rdx+rax*2]
0x18000fef6  mov     [rdx+8], rax
0x18000fefa  movups  xmm0, xmmword ptr [rcx]
0x18000fefd  movdqu  xmmword ptr [r9], xmm0
0x18000ff02  jmp     short loc_18000FF15
0x18000ff04  mov     [rdx], rax
0x18000ff07  mov     rax, [r8+8]
0x18000ff0b  mov     [rdx+8], rax
0x18000ff0f  mov     rax, [rcx]
0x18000ff12  mov     [r9], rax
0x18000ff15  mov     [r8], rcx
0x18000ff18  mov     [r8+8], rcx
0x18000ff1c  xor     eax, eax
0x18000ff1e  mov     [rcx], ax
0x18000ff21  mov     eax, [r8+20h]
0x18000ff25  mov     [rdx+20h], eax
0x18000ff28  mov     rdx, qword ptr [rbp+var_20+8]
0x18000ff2c  add     rdx, 28h ; '('
0x18000ff30  mov     qword ptr [rbp+var_20+8], rdx
0x18000ff34  jmp     short loc_18000FF43
0x18000ff36  lea     rcx, [rbp+var_20]
0x18000ff3a  call    ??$_Emplace_reallocate@UFeatureAdjustment@Image@Manager@Container@@@?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAUFeatureAdjustment@Image@Manager@Container@@QEAU2345@$$QEAU2345@@Z; std::vector<Container::Manager::Image::FeatureAdjustment>::_Emplace_reallocate<Container::Manager::Image::FeatureAdjustment>(Container::Manager::Image::FeatureAdjustment * const,Container::Manager::Image::FeatureAdjustment &&)
0x18000ff3f  mov     rdx, qword ptr [rbp+var_20+8]
0x18000ff43  inc     ebx
0x18000ff45  mov     r8, [rdi]
0x18000ff48  mov     rcx, [rdi+8]
0x18000ff4c  sub     rcx, r8
0x18000ff4f  sar     rcx, 3
0x18000ff53  imul    rcx, r15
0x18000ff57  movsxd  rax, ebx
0x18000ff5a  cmp     rax, rcx
0x18000ff5d  jnb     short loc_18000FF68
0x18000ff5f  mov     r9, [rbp+var_10]
0x18000ff63  jmp     loc_18000FEBD
0x18000ff68  mov     r8, rsi
0x18000ff6b  lea     rdx, [rbp+var_20]
0x18000ff6f  mov     rcx, r14
0x18000ff72  call    ??$FromJsonValue@UFeatureAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::FeatureAdjustment> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)
0x18000ff77  mov     r14b, al
0x18000ff7a  test    al, al
0x18000ff7c  jz      loc_180010139
0x18000ff82  mov     rsi, [rdi]
0x18000ff85  mov     rcx, [rdi+8]
0x18000ff89  mov     [rdi+8], rsi
0x18000ff8d  sub     rcx, rsi
0x18000ff90  mov     rax, 6666666666666667h
0x18000ff9a  imul    rcx
0x18000ff9d  mov     rbx, rdx
0x18000ffa0  sar     rbx, 4
0x18000ffa4  mov     rcx, rbx
0x18000ffa7  shr     rcx, 3Fh
0x18000ffab  add     rbx, rcx
0x18000ffae  jz      short loc_18000FFD9
0x18000ffb0  dec     rbx
0x18000ffb3  lea     rax, [rbx+rbx*4]
0x18000ffb7  mov     rcx, [rsi+rax*8]; void *
0x18000ffbb  lea     rax, [rax+2]
0x18000ffbf  lea     rax, [rsi+rax*8]
0x18000ffc3  cmp     rcx, rax
0x18000ffc6  jz      short loc_18000FFD4
0x18000ffc8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ffcf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ffd4  test    rbx, rbx
0x18000ffd7  jnz     short loc_18000FFB0
0x18000ffd9  mov     rcx, qword ptr [rbp+var_20+8]
0x18000ffdd  sub     rcx, qword ptr [rbp+var_20]
0x18000ffe1  sar     rcx, 3
0x18000ffe5  imul    rcx, r15
0x18000ffe9  mov     rax, [rdi+10h]
0x18000ffed  sub     rax, [rdi]
0x18000fff0  sar     rax, 3
0x18000fff4  imul    rax, r15
0x18000fff8  mov     r12, 333333333333333h
0x180010002  cmp     rcx, rax
0x180010005  jbe     short loc_180010036
0x180010007  shr     rax, 2
0x18001000b  imul    rdx, rax, 7
0x18001000f  add     rdx, 8
0x180010013  cmp     rdx, rcx
0x180010016  cmovb   rdx, rcx
0x18001001a  cmp     rdx, r12
0x18001001d  cmova   rdx, r12
0x180010021  cmp     rcx, rdx
0x180010024  ja      short loc_180010032
0x180010026  mov     rcx, rdi
0x180010029  call    ?_SetCapacity@?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>::_SetCapacity(unsigned __int64)
0x18001002e  test    al, al
0x180010030  jnz     short loc_180010036
0x180010032  mov     al, 1
0x180010034  jmp     short loc_180010038
0x180010036  xor     al, al
0x180010038  mov     rcx, [rbp+38h]; this
0x18001003c  test    al, al
0x18001003e  jnz     loc_180010155
0x180010044  xor     esi, esi
0x180010046  mov     rax, qword ptr [rbp+var_20+8]
0x18001004a  sub     rax, qword ptr [rbp+var_20]
0x18001004e  sar     rax, 3
0x180010052  imul    rax, r15
0x180010056  test    rax, rax
0x180010059  jz      loc_180010139
0x18001005f  movsxd  rax, esi
0x180010062  lea     rcx, [rax+rax*4]
0x180010066  mov     rax, qword ptr [rbp+var_20]
0x18001006a  lea     rbx, [rax+rcx*8]
0x18001006e  mov     rcx, [rdi+10h]
0x180010072  cmp     [rdi+8], rcx
0x180010076  jnz     short loc_1800100AE
0x180010078  sub     rcx, [rdi]
0x18001007b  sar     rcx, 3
0x18001007f  imul    rcx, r15
0x180010083  mov     rax, rcx
0x180010086  shr     rax, 2
0x18001008a  imul    rdx, rax, 7
0x18001008e  add     rdx, 8
0x180010092  cmp     rdx, r12
0x180010095  cmova   rdx, r12
0x180010099  cmp     rcx, rdx
0x18001009c  jnb     short loc_1800100AA
0x18001009e  mov     rcx, rdi
0x1800100a1  call    ?_SetCapacity@?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>::_SetCapacity(unsigned __int64)
0x1800100a6  test    al, al
0x1800100a8  jnz     short loc_1800100AE
0x1800100aa  mov     al, 1
0x1800100ac  jmp     short loc_180010113
0x1800100ae  mov     rcx, [rdi+8]
0x1800100b2  lea     rdx, [rbx+10h]
0x1800100b6  mov     rax, [rbx]
0x1800100b9  lea     r8, [rcx+10h]
0x1800100bd  cmp     rax, rdx
0x1800100c0  jnz     short loc_1800100E9
0x1800100c2  mov     [rcx], r8
0x1800100c5  mov     rax, [rbx+8]
0x1800100c9  sub     rax, rbx
0x1800100cc  sub     rax, 10h
0x1800100d0  sar     rax, 1
0x1800100d3  add     rax, 8
0x1800100d7  lea     rax, [rcx+rax*2]
0x1800100db  mov     [rcx+8], rax
0x1800100df  movups  xmm0, xmmword ptr [rdx]
0x1800100e2  movdqu  xmmword ptr [r8], xmm0
0x1800100e7  jmp     short loc_1800100FA
0x1800100e9  mov     [rcx], rax
0x1800100ec  mov     rax, [rbx+8]
0x1800100f0  mov     [rcx+8], rax
0x1800100f4  mov     rax, [rdx]
0x1800100f7  mov     [r8], rax
0x1800100fa  mov     [rbx], rdx
0x1800100fd  mov     [rbx+8], rdx
0x180010101  xor     eax, eax
0x180010103  mov     [rdx], ax
0x180010106  mov     eax, [rbx+20h]
0x180010109  mov     [rcx+20h], eax
0x18001010c  add     qword ptr [rdi+8], 28h ; '('
0x180010111  xor     al, al
0x180010113  mov     rcx, [rbp+38h]; this
0x180010117  test    al, al
0x180010119  jnz     short loc_18001016D
0x18001011b  inc     esi
0x18001011d  mov     rcx, qword ptr [rbp+var_20+8]
0x180010121  sub     rcx, qword ptr [rbp+var_20]
0x180010125  sar     rcx, 3
0x180010129  imul    rcx, r15
0x18001012d  movsxd  rax, esi
0x180010130  cmp     rax, rcx
0x180010133  jb      loc_18001005F
0x180010139  lea     rcx, [rbp+var_20]
0x18001013d  call    ??1?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ; std::vector<Container::Manager::Image::PackageAdjustment>::~vector<Container::Manager::Image::PackageAdjustment>(void)
0x180010142  mov     al, r14b
0x180010145  add     rsp, 40h
0x180010149  pop     r15
0x18001014b  pop     r14
0x18001014d  pop     r12
0x18001014f  pop     rdi
0x180010150  pop     rsi
0x180010151  pop     rbx
0x180010152  pop     rbp
0x180010153  retn
0x180010155  mov     r9d, 8007000Eh; char *
0x18001015b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\vm\\inc\\marshaljson"...
0x180010162  mov     edx, 78h ; 'x'; void *
0x180010167  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001016d  lea     r8, aOnecoreInterna_3; "onecore\\internal\\vm\\inc\\marshaljson"...
0x180010174  mov     edx, 7Fh; void *
0x180010179  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
