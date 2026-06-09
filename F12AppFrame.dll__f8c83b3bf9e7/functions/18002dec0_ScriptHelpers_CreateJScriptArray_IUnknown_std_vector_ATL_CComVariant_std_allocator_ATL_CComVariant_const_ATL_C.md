# ScriptHelpers::CreateJScriptArray(IUnknown *,std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>> const &,ATL::CComVariant &)

- ea: `0x18002dec0`
- end: `0x18002e267`
- name: `?CreateJScriptArray@ScriptHelpers@@YAJPEAUIUnknown@@AEBV?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAVCComVariant@ATL@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(__int64, _QWORD *, VARIANTARG *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007f08`

## callees

- `0x18000193c`
- `0x180002d44`
- `0x180003338`
- `0x180003858`
- `0x180003880`
- `0x180003c38`
- `0x1800045b4`
- `0x180006fcc`
- `0x1800071b4`
- `0x180007248`
- `0x1800095c4`
- `0x1800097f4`
- `0x18002dec0`
- `0x18002e270`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002deee`
- `OLEAUT32!__imp_VariantInit` at `0x18002df99`
- `OLEAUT32!__imp_VariantInit` at `0x18002deee`
- `OLEAUT32!__imp_VariantInit` at `0x18002df99`
- `OLEAUT32!__imp_VariantClear` at `0x18002e0dd`
- `OLEAUT32!__imp_VariantClear` at `0x18002e1dd`
- `OLEAUT32!__imp_VariantClear` at `0x18002e1ff`
- `OLEAUT32!__imp_VariantClear` at `0x18002e0dd`
- `OLEAUT32!__imp_VariantClear` at `0x18002e1dd`
- `OLEAUT32!__imp_VariantClear` at `0x18002e1ff`
- `OLEAUT32!__imp_VariantCopy` at `0x18002dfc5`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e08a`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e1c3`
- `OLEAUT32!__imp_VariantCopy` at `0x18002dfc5`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e08a`
- `OLEAUT32!__imp_VariantCopy` at `0x18002e1c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ScriptHelpers::CreateJScriptArray(__int64 a1, _QWORD *a2, VARIANTARG *a3)
{
  _QWORD *v6; // rax
  unsigned __int64 i; // r12
  VARIANTARG *v8; // rdx
  HRESULT v9; // ecx
  _QWORD *v10; // rax
  __int128 v11; // xmm6
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  __int64 v15; // rcx
  unsigned __int16 v16; // dx
  int v17; // eax
  void *v18; // r14
  char *v19; // rdi
  HRESULT v20; // eax
  unsigned __int16 *v21; // rdx
  wchar_t *v22; // rdx
  int v23; // ebx
  HRESULT v24; // eax
  void *v26; // [rsp+28h] [rbp-69h] BYREF
  __int64 v27; // [rsp+30h] [rbp-61h]
  void **v28; // [rsp+38h] [rbp-59h] BYREF
  char *v29; // [rsp+40h] [rbp-51h]
  _OWORD v30[2]; // [rsp+48h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-29h] BYREF
  unsigned __int16 *v32; // [rsp+80h] [rbp-11h] BYREF
  VARIANTARG pvargDest; // [rsp+88h] [rbp-9h] BYREF
  wchar_t *v34; // [rsp+100h] [rbp+6Fh] BYREF
  wchar_t **v35; // [rsp+110h] [rbp+7Fh]

  VariantInit(&pvarg);
  v27 = 0;
  v6 = operator new(0x40u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  v26 = v6;
  for ( i = 0; i < 0xAAAAAAAAAAAAAAABuLL * ((__int64)(a2[1] - *a2) >> 3); ++i )
  {
    v34 = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v34,
      L"%Iu",
      i);
    v32 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    VariantInit(&pvargDest);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &v32,
      &v34);
    v8 = (VARIANTARG *)(*a2 + 24 * i);
    if ( &pvargDest != v8 )
    {
      v9 = VariantCopy(&pvargDest, v8);
      if ( v9 < 0 )
      {
        pvargDest.vt = 10;
        pvargDest.lVal = v9;
        ATL::AtlThrowImpl(v9);
      }
    }
    v10 = std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>::_Find_lower_bound<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(
            (__int64)&v26,
            v30,
            &v32);
    v11 = *(_OWORD *)v10;
    v12 = v10[2];
    if ( *(_BYTE *)(v12 + 25) )
      goto LABEL_12;
    v13 = *(_QWORD *)(v12 + 32);
    if ( !v13 )
      ATL::AtlThrowImpl(-2147467259);
    v14 = v32;
    v15 = v13 - (_QWORD)v32;
    while ( 1 )
    {
      v16 = *v14;
      if ( *v14 != *(unsigned __int16 *)((char *)v14 + v15) )
        break;
      ++v14;
      if ( !v16 )
      {
        v17 = 0;
        goto LABEL_11;
      }
    }
    v17 = v16 < *(unsigned __int16 *)((char *)v14 + v15) ? -1 : 1;
LABEL_11:
    if ( v17 < 0 )
    {
LABEL_12:
      if ( v27 == 0x3FFFFFFFFFFFFFFLL )
        std::_Throw_tree_length_error();
      v18 = v26;
      v28 = &v26;
      v29 = 0;
      v19 = (char *)operator new(0x40u);
      v29 = v19;
      v35 = (wchar_t **)(v19 + 32);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (_QWORD *)v19 + 4,
        (__int64 *)&v32);
      *((_WORD *)v19 + 20) = 0;
      v20 = VariantCopy((VARIANTARG *)(v19 + 40), &pvargDest);
      if ( v20 < 0 )
      {
        *((_WORD *)v19 + 20) = 10;
        *((_DWORD *)v19 + 12) = v20;
        ATL::AtlThrowImpl(v20);
      }
      *(_QWORD *)v19 = v18;
      *((_QWORD *)v19 + 1) = v18;
      *((_QWORD *)v19 + 2) = v18;
      *((_WORD *)v19 + 12) = 0;
      v29 = 0;
      std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>,void *>>>((__int64)&v28);
      v30[0] = v11;
      std::_Tree_val<std::_Tree_simple_types<std::pair<enum PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>>>::_Insert_node(
        &v26,
        (__int64)v30,
        (__int64)v19);
    }
    VariantClear(&pvargDest);
    v21 = v32 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v32 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 8LL))(*(_QWORD *)v21);
    v22 = v34 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v34 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v22 + 8LL))(*(_QWORD *)v22);
  }
  v35 = &v34;
  v34 = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          &v34,
          (__int64)L"Array") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v34, L"Array", 5);
  v23 = ScriptHelpers::CreateJScriptItem(a1, &v34, &v26, &pvarg);
  if ( v23 )
  {
    if ( v23 >= 0 )
      v23 = -2147467259;
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>(&v26);
    VariantClear(&pvarg);
    return (unsigned int)v23;
  }
  else
  {
    if ( a3 != &pvarg )
    {
      v24 = VariantCopy(a3, &pvarg);
      if ( v24 < 0 )
      {
        a3->vt = 10;
        a3->lVal = v24;
        ATL::AtlThrowImpl(v24);
      }
    }
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>(&v26);
    VariantClear(&pvarg);
    return 0;
  }
}

```

## disassembly

```asm
0x18002dec0  mov     rax, rsp
0x18002dec3  mov     [rax+8], rbx
0x18002dec7  push    rbp
0x18002dec8  push    rsi
0x18002dec9  push    rdi
0x18002deca  push    r12
0x18002decc  push    r13
0x18002dece  push    r14
0x18002ded0  push    r15
0x18002ded2  lea     rbp, [rax-5Fh]
0x18002ded6  sub     rsp, 0B0h
0x18002dedd  movaps  xmmword ptr [rax-48h], xmm6
0x18002dee1  mov     rsi, r8
0x18002dee4  mov     r15, rdx
0x18002dee7  mov     r13, rcx
0x18002deea  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002deee  call    cs:__imp_VariantInit
0x18002def4  nop
0x18002def5  xor     r14d, r14d
0x18002def8  mov     [rbp+57h+var_C0], r14
0x18002defc  mov     [rbp+57h+var_B8], r14
0x18002df00  lea     ecx, [r14+40h]; Size
0x18002df04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002df09  mov     [rax], rax
0x18002df0c  mov     [rax+8], rax
0x18002df10  mov     [rax+10h], rax
0x18002df14  mov     word ptr [rax+18h], 101h
0x18002df1a  mov     [rbp+57h+var_C0], rax
0x18002df1e  mov     r12d, r14d
0x18002df21  mov     rax, [r15+8]
0x18002df25  sub     rax, [r15]
0x18002df28  sar     rax, 3
0x18002df2c  mov     rbx, 0AAAAAAAAAAAAAAABh
0x18002df36  imul    rax, rbx
0x18002df3a  test    rax, rax
0x18002df3d  jz      loc_18002E147
0x18002df43  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002df4a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002df51  mov     rax, [rax+18h]
0x18002df55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df5a  add     rax, 18h
0x18002df5e  mov     [rbp+57h+arg_8], rax
0x18002df62  mov     r8, r12
0x18002df65  lea     rdx, aIu; "%Iu"
0x18002df6c  lea     rcx, [rbp+57h+arg_8]
0x18002df70  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18002df75  nop
0x18002df76  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002df7d  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002df84  mov     rax, [rax+18h]
0x18002df88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df8d  add     rax, 18h
0x18002df91  mov     [rbp+57h+var_68], rax
0x18002df95  lea     rcx, [rbp+57h+pvargDest]; pvarg
0x18002df99  call    cs:__imp_VariantInit
0x18002df9f  nop
0x18002dfa0  lea     rdx, [rbp+57h+arg_8]
0x18002dfa4  lea     rcx, [rbp+57h+var_68]
0x18002dfa8  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002dfad  lea     rcx, [r12+r12*2]
0x18002dfb1  mov     rax, [r15]
0x18002dfb4  lea     rdx, [rax+rcx*8]; pvargSrc
0x18002dfb8  lea     rax, [rbp+57h+pvargDest]
0x18002dfbc  cmp     rax, rdx
0x18002dfbf  jz      short loc_18002DFD5
0x18002dfc1  lea     rcx, [rbp+57h+pvargDest]; pvargDest
0x18002dfc5  call    cs:__imp_VariantCopy
0x18002dfcb  mov     ecx, eax; int
0x18002dfcd  test    eax, eax
0x18002dfcf  js      loc_18002E23B
0x18002dfd5  lea     r8, [rbp+57h+var_68]
0x18002dfd9  lea     rdx, [rbp+57h+var_A0]
0x18002dfdd  lea     rcx, [rbp+57h+var_C0]
0x18002dfe1  call    ??$_Find_lower_bound@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@PEAX@std@@@1@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>::_Find_lower_bound<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002dfe6  movups  xmm6, xmmword ptr [rax]
0x18002dfe9  mov     rcx, [rax+10h]
0x18002dfed  cmp     [rcx+19h], r14b
0x18002dff1  jnz     short loc_18002E02E
0x18002dff3  mov     rcx, [rcx+20h]
0x18002dff7  test    rcx, rcx
0x18002dffa  jz      loc_18002E24D
0x18002e000  mov     rax, [rbp+57h+var_68]
0x18002e004  sub     rcx, rax
0x18002e007  movzx   edx, word ptr [rax]
0x18002e00a  cmp     dx, [rax+rcx]
0x18002e00e  jnz     short loc_18002E01E
0x18002e010  add     rax, 2
0x18002e014  test    dx, dx
0x18002e017  jnz     short loc_18002E007
0x18002e019  mov     eax, r14d
0x18002e01c  jmp     short loc_18002E023
0x18002e01e  sbb     eax, eax
0x18002e020  or      eax, 1
0x18002e023  shr     eax, 1Fh
0x18002e026  test    al, al
0x18002e028  jz      loc_18002E0D9
0x18002e02e  mov     rax, 3FFFFFFFFFFFFFFh
0x18002e038  cmp     [rbp+57h+var_B8], rax
0x18002e03c  jz      loc_18002E227
0x18002e042  mov     r14, [rbp+57h+var_C0]
0x18002e046  lea     rax, [rbp+57h+var_C0]
0x18002e04a  mov     [rbp+57h+var_B0], rax
0x18002e04e  mov     [rbp+57h+var_A8], 0
0x18002e056  mov     ecx, 40h ; '@'; Size
0x18002e05b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e060  mov     rdi, rax
0x18002e063  mov     [rbp+57h+var_A8], rax
0x18002e067  lea     rbx, [rax+20h]
0x18002e06b  mov     [rbp+57h+arg_18], rbx
0x18002e06f  lea     rdx, [rbp+57h+var_68]
0x18002e073  mov     rcx, rbx
0x18002e076  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002e07b  nop
0x18002e07c  xor     ecx, ecx
0x18002e07e  mov     [rbx+8], cx
0x18002e082  lea     rdx, [rbp+57h+pvargDest]; pvargSrc
0x18002e086  lea     rcx, [rbx+8]; pvargDest
0x18002e08a  call    cs:__imp_VariantCopy
0x18002e090  mov     ecx, eax; int
0x18002e092  test    eax, eax
0x18002e094  js      loc_18002E258
0x18002e09a  mov     [rdi], r14
0x18002e09d  mov     [rdi+8], r14
0x18002e0a1  mov     [rdi+10h], r14
0x18002e0a5  xor     r14d, r14d
0x18002e0a8  mov     [rdi+18h], r14w
0x18002e0ad  mov     [rbp+57h+var_A8], r14
0x18002e0b1  lea     rcx, [rbp+57h+var_B0]
0x18002e0b5  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>,void *>>>(void)
0x18002e0ba  movdqu  [rbp+57h+var_A0], xmm6
0x18002e0bf  mov     r8, rdi
0x18002e0c2  lea     rdx, [rbp+57h+var_A0]
0x18002e0c6  lea     rcx, [rbp+57h+var_C0]
0x18002e0ca  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>,void *> *>,std::_Tree_node<std::pair<PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>,void *> * const)
0x18002e0cf  mov     rbx, 0AAAAAAAAAAAAAAABh
0x18002e0d9  lea     rcx, [rbp+57h+pvargDest]; pvarg
0x18002e0dd  call    cs:__imp_VariantClear
0x18002e0e3  mov     rdx, [rbp+57h+var_68]
0x18002e0e7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002e0eb  or      eax, 0FFFFFFFFh
0x18002e0ee  lock xadd [rdx+10h], eax
0x18002e0f3  sub     eax, 1
0x18002e0f6  jg      short loc_18002E108
0x18002e0f8  mov     rcx, [rdx]
0x18002e0fb  mov     rax, [rcx]
0x18002e0fe  mov     rax, [rax+8]
0x18002e102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e107  nop
0x18002e108  mov     rdx, [rbp+57h+arg_8]
0x18002e10c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002e110  or      eax, 0FFFFFFFFh
0x18002e113  lock xadd [rdx+10h], eax
0x18002e118  sub     eax, 1
0x18002e11b  jg      short loc_18002E12C
0x18002e11d  mov     rcx, [rdx]
0x18002e120  mov     rax, [rcx]
0x18002e123  mov     rax, [rax+8]
0x18002e127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e12c  inc     r12
0x18002e12f  mov     rax, [r15+8]
0x18002e133  sub     rax, [r15]
0x18002e136  sar     rax, 3
0x18002e13a  imul    rax, rbx
0x18002e13e  cmp     r12, rax
0x18002e141  jb      loc_18002DF43
0x18002e147  lea     rax, [rbp+57h+arg_8]
0x18002e14b  mov     [rbp+57h+arg_18], rax
0x18002e14f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002e156  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002e15d  mov     rax, [rax+18h]
0x18002e161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e166  add     rax, 18h
0x18002e16a  mov     [rbp+57h+arg_8], rax
0x18002e16e  lea     rdx, aArray; "Array"
0x18002e175  lea     rcx, [rbp+57h+arg_8]
0x18002e179  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x18002e17e  test    al, al
0x18002e180  jnz     short loc_18002E199
0x18002e182  mov     r8d, 5
0x18002e188  lea     rdx, aArray; "Array"
0x18002e18f  lea     rcx, [rbp+57h+arg_8]
0x18002e193  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002e198  nop
0x18002e199  lea     r9, [rbp+57h+pvarg]
0x18002e19d  lea     r8, [rbp+57h+var_C0]
0x18002e1a1  lea     rdx, [rbp+57h+arg_8]
0x18002e1a5  mov     rcx, r13
0x18002e1a8  call    ?CreateJScriptItem@ScriptHelpers@@YAJPEAUIUnknown@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@@std@@AEAVCComVariant@4@@Z; ScriptHelpers::CreateJScriptItem(IUnknown *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant> const &,ATL::CComVariant &)
0x18002e1ad  mov     ebx, eax
0x18002e1af  test    eax, eax
0x18002e1b1  jnz     short loc_18002E1E7
0x18002e1b3  lea     rax, [rbp+57h+pvarg]
0x18002e1b7  cmp     rsi, rax
0x18002e1ba  jz      short loc_18002E1CF
0x18002e1bc  lea     rdx, [rbp+57h+pvarg]; pvargSrc
0x18002e1c0  mov     rcx, rsi; pvargDest
0x18002e1c3  call    cs:__imp_VariantCopy
0x18002e1c9  mov     ecx, eax; int
0x18002e1cb  test    eax, eax
0x18002e1cd  js      short loc_18002E22D
0x18002e1cf  lea     rcx, [rbp+57h+var_C0]
0x18002e1d3  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>(void)
0x18002e1d8  nop
0x18002e1d9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002e1dd  call    cs:__imp_VariantClear
0x18002e1e3  xor     eax, eax
0x18002e1e5  jmp     short loc_18002E207
0x18002e1e7  mov     eax, 80004005h
0x18002e1ec  test    ebx, ebx
0x18002e1ee  cmovns  ebx, eax
0x18002e1f1  lea     rcx, [rbp+57h+var_C0]
0x18002e1f5  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>(void)
0x18002e1fa  nop
0x18002e1fb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002e1ff  call    cs:__imp_VariantClear
0x18002e205  mov     eax, ebx
0x18002e207  lea     r11, [rsp+0E0h+var_30]
0x18002e20f  mov     rbx, [r11+40h]
0x18002e213  movaps  xmm6, xmmword ptr [r11-10h]
0x18002e218  mov     rsp, r11
0x18002e21b  pop     r15
0x18002e21d  pop     r14
0x18002e21f  pop     r13
0x18002e221  pop     r12
0x18002e223  pop     rdi
0x18002e224  pop     rsi
0x18002e225  pop     rbp
0x18002e226  retn
0x18002e227  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x18002e22d  mov     word ptr [rsi], 0Ah
0x18002e232  mov     [rsi+8], ecx
0x18002e235  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002e23b  mov     eax, 0Ah
0x18002e240  mov     word ptr [rbp+57h+pvargDest], ax
0x18002e244  mov     dword ptr [rbp+57h+pvargDest+8], ecx
0x18002e247  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002e24d  mov     ecx, 80004005h; int
0x18002e252  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002e258  mov     word ptr [rbx+8], 0Ah
0x18002e25e  mov     [rbx+10h], ecx
0x18002e261  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
