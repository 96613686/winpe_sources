# CxAnalysisItem::operator==(CxAnalysisItem const &)

- ea: `0x1815c2160`
- end: `0x1815c23d9`
- name: `??8CxAnalysisItem@@QEBA_NAEBV0@@Z`
- size: `633`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x1815b2110`
- `0x1815b2240`
- `0x1815c6350`
- `0x1830832a0`

## callees

- `0x1815be3a0`
- `0x1815be5c0`
- `0x1815be7e0`
- `0x1815bea00`
- `0x1815bee60`
- `0x1815bf330`
- `0x1815bf790`
- `0x1815c2160`
- `0x1830ea7f0`
- `0x1830eae30`

## string_xrefs

- `0x1815c2210`: `rObj.m_wDependentVarDescriptorIndex`
- `0x1815c2219`: `m_wDependentVarDescriptorIndex`
- `0x1815c2235`: `rObj.m_wIndependentVarDescriptorIndex`
- `0x1815c223c`: `m_wIndependentVarDescriptorIndex`
- `0x1815c2275`: `rObj.m_iNumDependentDescriptors`
- `0x1815c227c`: `m_iNumDependentDescriptors`
- `0x1815c2292`: `rObj.m_iNumIndependentDescriptors`
- `0x1815c2299`: `m_iNumIndependentDescriptors`
- `0x1815c2306`: `rObj.m_ixWeightVarDescriptorIndex`
- `0x1815c230d`: `m_ixWeightVarDescriptorIndex`
- `0x1815c2329`: `rObj.m_ixvCategoryWeightVarDescriptorIndexes`
- `0x1815c2330`: `m_ixvCategoryWeightVarDescriptorIndexes`

## pseudocode

```c
char __fastcall CxAnalysisItem::operator==(_DWORD *a1, __int64 a2)
{
  char v4; // bl
  int v6; // eax
  char v7; // bl
  char v8; // bl
  char v9; // bl
  char v10; // bl
  char v11; // bl
  char v12; // bl
  char v13; // bl
  char v14; // bl
  char v15; // bl
  char v16; // bl
  char v17; // bl
  char v18; // bl
  char v19; // bl
  char v20; // bl

  v4 = TestScalarEquality<enum CxAnalysisType>(a1 + 6, a2 + 24, "m_eAnalysisType", "rObj.m_eAnalysisType") & 1;
  if ( !v4 )
    return 0;
  v6 = a1[6];
  if ( v6 == 9 || (unsigned int)(v6 - 12) <= 1 )
  {
    v4 &= TestScalarEquality<CxString>(a1 + 36, a2 + 144, "m_sAnalysisString", "rObj.m_sAnalysisString");
    if ( !v4 )
      return 0;
  }
  v7 = TestScalarEquality<enum CxAnalysisType>(a1 + 7, a2 + 28, "m_ePredictionType", "rObj.m_ePredictionType") & v4;
  v8 = TestVarEquality(
         (const struct Var *)(a1 + 14),
         (const struct Var *)(a2 + 56),
         "m_wDependentVarDescriptorIndex",
         "rObj.m_wDependentVarDescriptorIndex",
         0.000001)
     & v7;
  v9 = TestVarEquality(
         (const struct Var *)(a1 + 16),
         (const struct Var *)(a2 + 64),
         "m_wIndependentVarDescriptorIndex",
         "rObj.m_wIndependentVarDescriptorIndex",
         0.000001)
     & v8;
  v10 = TestDSEquality(
          (const struct DataSet *)(a1 + 18),
          (const struct DataSet *)(a2 + 72),
          "m_dsDiscreteIndependentVarOrder",
          "rObj.m_dsDiscreteIndependentVarOrder",
          0.000001)
      & v9;
  v11 = TestScalarEquality<unsigned int>(
          a1 + 4,
          a2 + 16,
          "m_iNumDependentDescriptors",
          "rObj.m_iNumDependentDescriptors")
      & v10;
  v12 = TestScalarEquality<unsigned int>(
          a1 + 5,
          a2 + 20,
          "m_iNumIndependentDescriptors",
          "rObj.m_iNumIndependentDescriptors")
      & v11;
  v13 = TestScalarEquality<bool>(a1 + 8, a2 + 32, "m_bInitialized", "rObj.m_bInitialized") & v12;
  v14 = TestScalarEquality<enum CxWeightType>(a1 + 20, a2 + 80, "m_eWeightType", "rObj.m_eWeightType") & v13;
  v15 = TestScalarEquality<enum CxWeightType>(a1 + 24, a2 + 96, "m_eUserWeightType", "rObj.m_eUserWeightType") & v14;
  v16 = TestScalarEquality<unsigned int>(
          a1 + 28,
          a2 + 112,
          "m_ixWeightVarDescriptorIndex",
          "rObj.m_ixWeightVarDescriptorIndex")
      & v15;
  v17 = TestVarEquality(
          (const struct Var *)(a1 + 30),
          (const struct Var *)(a2 + 120),
          "m_ixvCategoryWeightVarDescriptorIndexes",
          "rObj.m_ixvCategoryWeightVarDescriptorIndexes",
          0.000001)
      & v16;
  v18 = TestScalarEquality<CxString>(a1 + 22, a2 + 88, "m_sWeightName", "rObj.m_sWeightName") & v17;
  v19 = TestScalarEquality<CxString>(a1 + 26, a2 + 104, "m_sUserWeightName", "rObj.m_sUserWeightName") & v18;
  v20 = TestScalarEquality<CxWrapper<CxResults>>(a1 + 32, a2 + 128, "m_wResults", "rObj.m_wResults") & v19;
  return v20 & TestScalarEquality<CxInfoFlag>(a1 + 42, a2 + 168, "m_iAnalysisItemInfo", "rObj.m_iAnalysisItemInfo");
}

```

## disassembly

```asm
0x1815c2160  mov     [rsp+arg_0], rbx
0x1815c2165  mov     [rsp+arg_8], rsi
0x1815c216a  mov     [rsp+arg_10], rdi
0x1815c216f  push    r14
0x1815c2171  sub     rsp, 40h
0x1815c2175  mov     rdi, rdx
0x1815c2178  lea     r9, aRobjMEanalysis; "rObj.m_eAnalysisType"
0x1815c217f  mov     rsi, rcx
0x1815c2182  lea     r8, aMEanalysistype; "m_eAnalysisType"
0x1815c2189  add     rdx, 18h
0x1815c218d  add     rcx, 18h
0x1815c2191  call    ??$TestScalarEquality@W4CxAnalysisType@@@@YA_NAEBW4CxAnalysisType@@0PEBD1@Z; TestScalarEquality<CxAnalysisType>(CxAnalysisType const &,CxAnalysisType const &,char const *,char const *)
0x1815c2196  movzx   ebx, al
0x1815c2199  and     bl, 1
0x1815c219c  jnz     short loc_1815C21A5
0x1815c219e  xor     al, al
0x1815c21a0  jmp     loc_1815C23C3
0x1815c21a5  mov     eax, [rsi+18h]
0x1815c21a8  cmp     eax, 9
0x1815c21ab  jz      short loc_1815C21B5
0x1815c21ad  add     eax, 0FFFFFFF4h
0x1815c21b0  cmp     eax, 1
0x1815c21b3  ja      short loc_1815C21DA
0x1815c21b5  lea     rdx, [rdi+90h]
0x1815c21bc  lea     rcx, [rsi+90h]
0x1815c21c3  lea     r9, aRobjMSanalysis; "rObj.m_sAnalysisString"
0x1815c21ca  lea     r8, aMSanalysisstri; "m_sAnalysisString"
0x1815c21d1  call    ??$TestScalarEquality@VCxString@@@@YA_NAEBVCxString@@0PEBD1@Z; TestScalarEquality<CxString>(CxString const &,CxString const &,char const *,char const *)
0x1815c21d6  and     bl, al
0x1815c21d8  jz      short loc_1815C219E
0x1815c21da  lea     rdx, [rdi+1Ch]
0x1815c21de  movaps  [rsp+48h+var_18], xmm6
0x1815c21e3  lea     rcx, [rsi+1Ch]
0x1815c21e7  lea     r9, aRobjMEpredicti; "rObj.m_ePredictionType"
0x1815c21ee  lea     r8, aMEpredictionty; "m_ePredictionType"
0x1815c21f5  call    ??$TestScalarEquality@W4CxAnalysisType@@@@YA_NAEBW4CxAnalysisType@@0PEBD1@Z; TestScalarEquality<CxAnalysisType>(CxAnalysisType const &,CxAnalysisType const &,char const *,char const *)
0x1815c21fa  movsd   xmm6, cs:__real@3eb0c6f7a0b5ed8d
0x1815c2202  lea     rdx, [rdi+38h]; struct Var *
0x1815c2206  lea     rcx, [rsi+38h]; struct Var *
0x1815c220a  movsd   [rsp+48h+var_28], xmm6; double
0x1815c2210  lea     r9, aRobjMWdependen; "rObj.m_wDependentVarDescriptorIndex"
0x1815c2217  and     bl, al
0x1815c2219  lea     r8, aMWdependentvar; "m_wDependentVarDescriptorIndex"
0x1815c2220  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1815c2225  lea     rdx, [rdi+40h]; struct Var *
0x1815c2229  movsd   [rsp+48h+var_28], xmm6; double
0x1815c222f  lea     rcx, [rsi+40h]; struct Var *
0x1815c2233  and     bl, al
0x1815c2235  lea     r9, aRobjMWindepend; "rObj.m_wIndependentVarDescriptorIndex"
0x1815c223c  lea     r8, aMWindependentv; "m_wIndependentVarDescriptorIndex"
0x1815c2243  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1815c2248  lea     rdx, [rdi+48h]; struct DataSet *
0x1815c224c  movsd   [rsp+48h+var_28], xmm6; double
0x1815c2252  lea     rcx, [rsi+48h]; this
0x1815c2256  and     bl, al
0x1815c2258  lea     r9, aRobjMDsdiscret; "rObj.m_dsDiscreteIndependentVarOrder"
0x1815c225f  lea     r8, aMDsdiscreteind; "m_dsDiscreteIndependentVarOrder"
0x1815c2266  call    ?TestDSEquality@@YA_NAEBVDataSet@@0PEBD1N@Z; TestDSEquality(DataSet const &,DataSet const &,char const *,char const *,double)
0x1815c226b  lea     rdx, [rdi+10h]
0x1815c226f  and     bl, al
0x1815c2271  lea     rcx, [rsi+10h]
0x1815c2275  lea     r9, aRobjMInumdepen; "rObj.m_iNumDependentDescriptors"
0x1815c227c  lea     r8, aMInumdependent; "m_iNumDependentDescriptors"
0x1815c2283  call    ??$TestScalarEquality@I@@YA_NAEBI0PEBD1@Z; TestScalarEquality<uint>(uint const &,uint const &,char const *,char const *)
0x1815c2288  lea     rdx, [rdi+14h]
0x1815c228c  and     bl, al
0x1815c228e  lea     rcx, [rsi+14h]
0x1815c2292  lea     r9, aRobjMInumindep; "rObj.m_iNumIndependentDescriptors"
0x1815c2299  lea     r8, aMInumindepende; "m_iNumIndependentDescriptors"
0x1815c22a0  call    ??$TestScalarEquality@I@@YA_NAEBI0PEBD1@Z; TestScalarEquality<uint>(uint const &,uint const &,char const *,char const *)
0x1815c22a5  lea     rdx, [rdi+20h]
0x1815c22a9  and     bl, al
0x1815c22ab  lea     rcx, [rsi+20h]
0x1815c22af  lea     r9, aRobjMBinitiali; "rObj.m_bInitialized"
0x1815c22b6  lea     r8, aMBinitialized; "m_bInitialized"
0x1815c22bd  call    ??$TestScalarEquality@_N@@YA_NAEB_N0PEBD1@Z; TestScalarEquality<bool>(bool const &,bool const &,char const *,char const *)
0x1815c22c2  lea     rdx, [rdi+50h]
0x1815c22c6  and     bl, al
0x1815c22c8  lea     rcx, [rsi+50h]
0x1815c22cc  lea     r9, aRobjMEweightty; "rObj.m_eWeightType"
0x1815c22d3  lea     r8, aMEweighttype; "m_eWeightType"
0x1815c22da  call    ??$TestScalarEquality@W4CxWeightType@@@@YA_NAEBW4CxWeightType@@0PEBD1@Z; TestScalarEquality<CxWeightType>(CxWeightType const &,CxWeightType const &,char const *,char const *)
0x1815c22df  lea     rdx, [rdi+60h]
0x1815c22e3  and     bl, al
0x1815c22e5  lea     rcx, [rsi+60h]
0x1815c22e9  lea     r9, aRobjMEuserweig; "rObj.m_eUserWeightType"
0x1815c22f0  lea     r8, aMEuserweightty; "m_eUserWeightType"
0x1815c22f7  call    ??$TestScalarEquality@W4CxWeightType@@@@YA_NAEBW4CxWeightType@@0PEBD1@Z; TestScalarEquality<CxWeightType>(CxWeightType const &,CxWeightType const &,char const *,char const *)
0x1815c22fc  lea     rdx, [rdi+70h]
0x1815c2300  and     bl, al
0x1815c2302  lea     rcx, [rsi+70h]
0x1815c2306  lea     r9, aRobjMIxweightv; "rObj.m_ixWeightVarDescriptorIndex"
0x1815c230d  lea     r8, aMIxweightvarde; "m_ixWeightVarDescriptorIndex"
0x1815c2314  call    ??$TestScalarEquality@I@@YA_NAEBI0PEBD1@Z; TestScalarEquality<uint>(uint const &,uint const &,char const *,char const *)
0x1815c2319  lea     rdx, [rdi+78h]; struct Var *
0x1815c231d  movsd   [rsp+48h+var_28], xmm6; double
0x1815c2323  lea     rcx, [rsi+78h]; struct Var *
0x1815c2327  and     bl, al
0x1815c2329  lea     r9, aRobjMIxvcatego; "rObj.m_ixvCategoryWeightVarDescriptorIn"...
0x1815c2330  lea     r8, aMIxvcategorywe; "m_ixvCategoryWeightVarDescriptorIndexes"
0x1815c2337  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1815c233c  lea     rdx, [rdi+58h]
0x1815c2340  and     bl, al
0x1815c2342  lea     rcx, [rsi+58h]
0x1815c2346  lea     r9, aRobjMSweightna; "rObj.m_sWeightName"
0x1815c234d  lea     r8, aMSweightname; "m_sWeightName"
0x1815c2354  call    ??$TestScalarEquality@VCxString@@@@YA_NAEBVCxString@@0PEBD1@Z; TestScalarEquality<CxString>(CxString const &,CxString const &,char const *,char const *)
0x1815c2359  and     bl, al
0x1815c235b  lea     rdx, [rdi+68h]
0x1815c235f  lea     rcx, [rsi+68h]
0x1815c2363  lea     r9, aRobjMSuserweig; "rObj.m_sUserWeightName"
0x1815c236a  lea     r8, aMSuserweightna; "m_sUserWeightName"
0x1815c2371  call    ??$TestScalarEquality@VCxString@@@@YA_NAEBVCxString@@0PEBD1@Z; TestScalarEquality<CxString>(CxString const &,CxString const &,char const *,char const *)
0x1815c2376  lea     rdx, [rdi+80h]
0x1815c237d  and     bl, al
0x1815c237f  lea     rcx, [rsi+80h]
0x1815c2386  lea     r9, aRobjMWresults; "rObj.m_wResults"
0x1815c238d  lea     r8, aMWresults_0; "m_wResults"
0x1815c2394  call    ??$TestScalarEquality@V?$CxWrapper@VCxResults@@@@@@YA_NAEBV?$CxWrapper@VCxResults@@@@0PEBD1@Z; TestScalarEquality<CxWrapper<CxResults>>(CxWrapper<CxResults> const &,CxWrapper<CxResults> const &,char const *,char const *)
0x1815c2399  lea     rdx, [rdi+0A8h]
0x1815c23a0  and     bl, al
0x1815c23a2  lea     rcx, [rsi+0A8h]
0x1815c23a9  lea     r9, aRobjMIanalysis; "rObj.m_iAnalysisItemInfo"
0x1815c23b0  lea     r8, aMIanalysisitem; "m_iAnalysisItemInfo"
0x1815c23b7  call    ??$TestScalarEquality@VCxInfoFlag@@@@YA_NAEBVCxInfoFlag@@0PEBD1@Z; TestScalarEquality<CxInfoFlag>(CxInfoFlag const &,CxInfoFlag const &,char const *,char const *)
0x1815c23bc  movaps  xmm6, [rsp+48h+var_18]
0x1815c23c1  and     al, bl
0x1815c23c3  mov     rbx, [rsp+48h+arg_0]
0x1815c23c8  mov     rsi, [rsp+48h+arg_8]
0x1815c23cd  mov     rdi, [rsp+48h+arg_10]
0x1815c23d2  add     rsp, 40h
0x1815c23d6  pop     r14
0x1815c23d8  retn
```
