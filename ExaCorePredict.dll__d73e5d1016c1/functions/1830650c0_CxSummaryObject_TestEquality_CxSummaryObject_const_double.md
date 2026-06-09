# CxSummaryObject::TestEquality(CxSummaryObject const &,double)

- ea: `0x1830650c0`
- end: `0x1830654ce`
- name: `?TestEquality@CxSummaryObject@@QEBA_NAEBV1@N@Z`
- size: `1038`
- prototype: `bool __fastcall(CxSummaryObject *__hidden this, const struct CxSummaryObject *, double)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1815c1d30`

## callees

- `0x1815cd850`
- `0x1830574d0`
- `0x1830ea7f0`
- `0x1830eae30`

## string_xrefs

- `0x1830651bd`: `m_wDescriptorDiffMatrix`
- `0x18306522f`: `m_ivPureContinuousCrossProdDescriptors`
- `0x183065259`: `m_ivNonContinuousCrossProdDescriptors`
- `0x183065283`: `m_ivDescriptiveStatDescriptors`
- `0x18306518f`: `rObj.m_wVarDescriptorVector`
- `0x183065199`: `m_wVarDescriptorVector`
- `0x1830651b6`: `rObj.m_wDescriptorDiffMatrix`
- `0x183065228`: `rObj.m_ivPureContinuousCrossProdDescriptors`
- `0x183065252`: `rObj.m_ivNonContinuousCrossProdDescriptors`
- `0x183065276`: `rObj.m_ivDescriptiveStatDescriptors`

## pseudocode

```c
bool __fastcall CxSummaryObject::TestEquality(CxSummaryObject *this, const struct CxSummaryObject *a2, double a3)
{
  __int64 v5; // rsi

  v5 = TestScalarEquality<__int64>(
         (char *)this + 24,
         (char *)a2 + 24,
         "m_llTotalValidObservations",
         "rObj.m_llTotalValidObservations")
     & 1;
  LOBYTE(v5) = TestScalarEquality<__int64>(
                 (char *)this + 32,
                 (char *)a2 + 32,
                 "m_llTotalMissingObservations",
                 "rObj.m_llTotalMissingObservations")
             & v5;
  LOBYTE(v5) = TestScalarEquality<__int64>(
                 (char *)this + 40,
                 (char *)a2 + 40,
                 "m_llCurrentValidObservations",
                 "rObj.m_llCurrentValidObservations")
             & v5;
  LOBYTE(v5) = TestScalarEquality<__int64>(
                 (char *)this + 48,
                 (char *)a2 + 48,
                 "m_llCurrentMissingObservations",
                 "rObj.m_llCurrentMissingObservations")
             & v5;
  LOBYTE(v5) = TestScalarEquality<CxWrapper<CxVarInfoArrays>>(
                 (char *)this + 56,
                 (char *)a2 + 56,
                 "m_wVarInfoArrays",
                 "rObj.m_wVarInfoArrays")
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 64),
                 (const struct CxSummaryObject *)((char *)a2 + 64),
                 "m_wVarDescriptorVector",
                 "rObj.m_wVarDescriptorVector",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 80),
                 (const struct CxSummaryObject *)((char *)a2 + 80),
                 "m_wDescriptorDiffMatrix",
                 "rObj.m_wDescriptorDiffMatrix",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestDSEquality(
                 (CxSummaryObject *)((char *)this + 112),
                 (const struct CxSummaryObject *)((char *)a2 + 112),
                 "m_wContinuousInteractions",
                 "rObj.m_wContinuousInteractions",
                 a3)
             & v5;
  LOBYTE(v5) = TestDSEquality(
                 (CxSummaryObject *)((char *)this + 120),
                 (const struct CxSummaryObject *)((char *)a2 + 120),
                 "m_wDiscreteInteractions",
                 "rObj.m_wDiscreteInteractions",
                 a3)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 128),
                 (const struct CxSummaryObject *)((char *)a2 + 128),
                 "m_ivPureContinuousCrossProdDescriptors",
                 "rObj.m_ivPureContinuousCrossProdDescriptors",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 136),
                 (const struct CxSummaryObject *)((char *)a2 + 136),
                 "m_ivNonContinuousCrossProdDescriptors",
                 "rObj.m_ivNonContinuousCrossProdDescriptors",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 144),
                 (const struct CxSummaryObject *)((char *)a2 + 144),
                 "m_ivDescriptiveStatDescriptors",
                 "rObj.m_ivDescriptiveStatDescriptors",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 152),
                 (const struct CxSummaryObject *)((char *)a2 + 152),
                 "m_wCrossProdMask",
                 "rObj.m_wCrossProdMask",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 160),
                 (const struct CxSummaryObject *)((char *)a2 + 160),
                 "m_wMixedCrossProdContinuousSummaries",
                 "rObj.m_wMixedCrossProdContinuousSummaries",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 168),
                 (const struct CxSummaryObject *)((char *)a2 + 168),
                 "m_wMixedCrossProdDiscreteSummaries",
                 "rObj.m_wMixedCrossProdDiscreteSummaries",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 176),
                 (const struct CxSummaryObject *)((char *)a2 + 176),
                 "m_wNonContCrossProdContinuousSummaries",
                 "rObj.m_wNonContCrossProdContinuousSummaries",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 184),
                 (const struct CxSummaryObject *)((char *)a2 + 184),
                 "m_wNonContCrossProdDiscreteSummaries",
                 "rObj.m_wNonContCrossProdDiscreteSummaries",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 192),
                 (const struct CxSummaryObject *)((char *)a2 + 192),
                 "m_w2ndOrderInteractionInstructions",
                 "rObj.m_w2ndOrderInteractionInstructions",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 200),
                 (const struct CxSummaryObject *)((char *)a2 + 200),
                 "m_wMixedFirstOrderInstructions",
                 "rObj.m_wMixedFirstOrderInstructions",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 208),
                 (const struct CxSummaryObject *)((char *)a2 + 208),
                 "m_wMixedCrossProdInstructions",
                 "rObj.m_wMixedCrossProdInstructions",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 216),
                 (const struct CxSummaryObject *)((char *)a2 + 216),
                 "m_wNonContCrossProdInstructions",
                 "rObj.m_wNonContCrossProdInstructions",
                 0.000001)
             & v5;
  LOBYTE(v5) = TestVarEquality(
                 (CxSummaryObject *)((char *)this + 232),
                 (const struct CxSummaryObject *)((char *)a2 + 232),
                 "m_mPureContinuousCrossProds",
                 "rObj.m_mPureContinuousCrossProds",
                 a3)
             & v5;
  LOBYTE(v5) = TestDSEquality(
                 (CxSummaryObject *)((char *)this + 240),
                 (const struct CxSummaryObject *)((char *)a2 + 240),
                 "m_wContDiscreteCrossProds",
                 "rObj.m_wContDiscreteCrossProds",
                 a3)
             & v5;
  LOBYTE(v5) = TestDSEquality(
                 (CxSummaryObject *)((char *)this + 248),
                 (const struct CxSummaryObject *)((char *)a2 + 248),
                 "m_dsExtraResults",
                 "rObj.m_dsExtraResults",
                 a3)
             & v5;
  return v5
       & TestVarEquality(
           (CxSummaryObject *)((char *)this + 224),
           (const struct CxSummaryObject *)((char *)a2 + 224),
           "m_wDescriptiveStatsVar",
           "rObj.m_wDescriptiveStatsVar",
           0.000001);
}

```

## disassembly

```asm
0x1830650c0  mov     [rsp+arg_0], rbx
0x1830650c5  mov     [rsp+arg_8], rsi
0x1830650ca  push    rdi
0x1830650cb  sub     rsp, 50h
0x1830650cf  mov     rbx, rdx
0x1830650d2  movaps  [rsp+58h+var_18], xmm6
0x1830650d7  mov     rdi, rcx
0x1830650da  movaps  [rsp+58h+var_28], xmm7
0x1830650df  add     rdx, 18h
0x1830650e3  lea     r9, aRobjMLltotalva; "rObj.m_llTotalValidObservations"
0x1830650ea  add     rcx, 18h
0x1830650ee  lea     r8, aMLltotalvalido; "m_llTotalValidObservations"
0x1830650f5  movaps  xmm7, xmm2
0x1830650f8  call    ??$TestScalarEquality@_J@@YA_NAEB_J0PEBD1@Z; TestScalarEquality<__int64>(__int64 const &,__int64 const &,char const *,char const *)
0x1830650fd  movzx   esi, al
0x183065100  lea     rdx, [rbx+20h]
0x183065104  lea     rcx, [rdi+20h]
0x183065108  and     sil, 1
0x18306510c  lea     r9, aRobjMLltotalmi; "rObj.m_llTotalMissingObservations"
0x183065113  lea     r8, aMLltotalmissin; "m_llTotalMissingObservations"
0x18306511a  call    ??$TestScalarEquality@_J@@YA_NAEB_J0PEBD1@Z; TestScalarEquality<__int64>(__int64 const &,__int64 const &,char const *,char const *)
0x18306511f  lea     rdx, [rbx+28h]
0x183065123  and     sil, al
0x183065126  lea     rcx, [rdi+28h]
0x18306512a  lea     r9, aRobjMLlcurrent; "rObj.m_llCurrentValidObservations"
0x183065131  lea     r8, aMLlcurrentvali; "m_llCurrentValidObservations"
0x183065138  call    ??$TestScalarEquality@_J@@YA_NAEB_J0PEBD1@Z; TestScalarEquality<__int64>(__int64 const &,__int64 const &,char const *,char const *)
0x18306513d  lea     rdx, [rbx+30h]
0x183065141  and     sil, al
0x183065144  lea     rcx, [rdi+30h]
0x183065148  lea     r9, aRobjMLlcurrent_0; "rObj.m_llCurrentMissingObservations"
0x18306514f  lea     r8, aMLlcurrentmiss; "m_llCurrentMissingObservations"
0x183065156  call    ??$TestScalarEquality@_J@@YA_NAEB_J0PEBD1@Z; TestScalarEquality<__int64>(__int64 const &,__int64 const &,char const *,char const *)
0x18306515b  lea     rdx, [rbx+38h]
0x18306515f  and     sil, al
0x183065162  lea     rcx, [rdi+38h]
0x183065166  lea     r9, aRobjMWvarinfoa; "rObj.m_wVarInfoArrays"
0x18306516d  lea     r8, aMWvarinfoarray; "m_wVarInfoArrays"
0x183065174  call    ??$TestScalarEquality@V?$CxWrapper@VCxVarInfoArrays@@@@@@YA_NAEBV?$CxWrapper@VCxVarInfoArrays@@@@0PEBD1@Z; TestScalarEquality<CxWrapper<CxVarInfoArrays>>(CxWrapper<CxVarInfoArrays> const &,CxWrapper<CxVarInfoArrays> const &,char const *,char const *)
0x183065179  movsd   xmm6, cs:__real@3eb0c6f7a0b5ed8d
0x183065181  lea     rdx, [rbx+40h]; struct Var *
0x183065185  lea     rcx, [rdi+40h]; struct Var *
0x183065189  movsd   [rsp+58h+var_38], xmm6; double
0x18306518f  lea     r9, aRobjMWvardescr; "rObj.m_wVarDescriptorVector"
0x183065196  and     sil, al
0x183065199  lea     r8, aMWvardescripto; "m_wVarDescriptorVector"
0x1830651a0  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1830651a5  lea     rdx, [rbx+50h]; struct Var *
0x1830651a9  movsd   [rsp+58h+var_38], xmm6; double
0x1830651af  lea     rcx, [rdi+50h]; struct Var *
0x1830651b3  and     sil, al
0x1830651b6  lea     r9, aRobjMWdescript_0; "rObj.m_wDescriptorDiffMatrix"
0x1830651bd  lea     r8, aMWdescriptordi; "m_wDescriptorDiffMatrix"
0x1830651c4  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1830651c9  lea     rdx, [rbx+70h]; struct DataSet *
0x1830651cd  movsd   [rsp+58h+var_38], xmm7; double
0x1830651d3  lea     rcx, [rdi+70h]; this
0x1830651d7  and     sil, al
0x1830651da  lea     r9, aRobjMWcontinuo; "rObj.m_wContinuousInteractions"
0x1830651e1  lea     r8, aMWcontinuousin; "m_wContinuousInteractions"
0x1830651e8  call    ?TestDSEquality@@YA_NAEBVDataSet@@0PEBD1N@Z; TestDSEquality(DataSet const &,DataSet const &,char const *,char const *,double)
0x1830651ed  lea     rdx, [rbx+78h]; struct DataSet *
0x1830651f1  movsd   [rsp+58h+var_38], xmm7; double
0x1830651f7  lea     rcx, [rdi+78h]; this
0x1830651fb  and     sil, al
0x1830651fe  lea     r9, aRobjMWdiscrete_2; "rObj.m_wDiscreteInteractions"
0x183065205  lea     r8, aMWdiscreteinte_0; "m_wDiscreteInteractions"
0x18306520c  call    ?TestDSEquality@@YA_NAEBVDataSet@@0PEBD1N@Z; TestDSEquality(DataSet const &,DataSet const &,char const *,char const *,double)
0x183065211  lea     rdx, [rbx+80h]; struct Var *
0x183065218  movsd   [rsp+58h+var_38], xmm6; double
0x18306521e  lea     rcx, [rdi+80h]; struct Var *
0x183065225  and     sil, al
0x183065228  lea     r9, aRobjMIvpurecon; "rObj.m_ivPureContinuousCrossProdDescrip"...
0x18306522f  lea     r8, aMIvpurecontinu; "m_ivPureContinuousCrossProdDescriptors"
0x183065236  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x18306523b  lea     rdx, [rbx+88h]; struct Var *
0x183065242  movsd   [rsp+58h+var_38], xmm6; double
0x183065248  lea     rcx, [rdi+88h]; struct Var *
0x18306524f  and     sil, al
0x183065252  lea     r9, aRobjMIvnoncont; "rObj.m_ivNonContinuousCrossProdDescript"...
0x183065259  lea     r8, aMIvnoncontinuo; "m_ivNonContinuousCrossProdDescriptors"
0x183065260  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x183065265  and     sil, al
0x183065268  lea     rdx, [rbx+90h]; struct Var *
0x18306526f  lea     rcx, [rdi+90h]; struct Var *
0x183065276  lea     r9, aRobjMIvdescrip; "rObj.m_ivDescriptiveStatDescriptors"
0x18306527d  movsd   [rsp+58h+var_38], xmm6; double
0x183065283  lea     r8, aMIvdescriptive; "m_ivDescriptiveStatDescriptors"
0x18306528a  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x18306528f  lea     rdx, [rbx+98h]; struct Var *
0x183065296  movsd   [rsp+58h+var_38], xmm6; double
0x18306529c  lea     rcx, [rdi+98h]; struct Var *
0x1830652a3  and     sil, al
0x1830652a6  lea     r9, aRobjMWcrosspro; "rObj.m_wCrossProdMask"
0x1830652ad  lea     r8, aMWcrossprodmas; "m_wCrossProdMask"
0x1830652b4  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1830652b9  lea     rdx, [rbx+0A0h]; struct Var *
0x1830652c0  movsd   [rsp+58h+var_38], xmm6; double
0x1830652c6  lea     rcx, [rdi+0A0h]; struct Var *
0x1830652cd  and     sil, al
0x1830652d0  lea     r9, aRobjMWmixedcro; "rObj.m_wMixedCrossProdContinuousSummari"...
0x1830652d7  lea     r8, aMWmixedcrosspr_1; "m_wMixedCrossProdContinuousSummaries"
0x1830652de  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1830652e3  lea     rdx, [rbx+0A8h]; struct Var *
0x1830652ea  movsd   [rsp+58h+var_38], xmm6; double
0x1830652f0  lea     rcx, [rdi+0A8h]; struct Var *
0x1830652f7  and     sil, al
0x1830652fa  lea     r9, aRobjMWmixedcro_1; "rObj.m_wMixedCrossProdDiscreteSummaries"
0x183065301  lea     r8, aMWmixedcrosspr; "m_wMixedCrossProdDiscreteSummaries"
0x183065308  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x18306530d  lea     rdx, [rbx+0B0h]; struct Var *
0x183065314  movsd   [rsp+58h+var_38], xmm6; double
0x18306531a  lea     rcx, [rdi+0B0h]; struct Var *
0x183065321  and     sil, al
0x183065324  lea     r9, aRobjMWnoncontc_0; "rObj.m_wNonContCrossProdContinuousSumma"...
0x18306532b  lea     r8, aMWnoncontcross_4; "m_wNonContCrossProdContinuousSummaries"
0x183065332  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x183065337  lea     rdx, [rbx+0B8h]; struct Var *
0x18306533e  movsd   [rsp+58h+var_38], xmm6; double
0x183065344  lea     rcx, [rdi+0B8h]; struct Var *
0x18306534b  and     sil, al
0x18306534e  lea     r9, aRobjMWnoncontc; "rObj.m_wNonContCrossProdDiscreteSummari"...
0x183065355  lea     r8, aMWnoncontcross_3; "m_wNonContCrossProdDiscreteSummaries"
0x18306535c  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x183065361  lea     rdx, [rbx+0C0h]; struct Var *
0x183065368  movsd   [rsp+58h+var_38], xmm6; double
0x18306536e  lea     rcx, [rdi+0C0h]; struct Var *
0x183065375  and     sil, al
0x183065378  lea     r9, aRobjMW2ndorder; "rObj.m_w2ndOrderInteractionInstructions"
0x18306537f  lea     r8, aMW2ndorderinte; "m_w2ndOrderInteractionInstructions"
0x183065386  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x18306538b  lea     rdx, [rbx+0C8h]; struct Var *
0x183065392  movsd   [rsp+58h+var_38], xmm6; double
0x183065398  lea     rcx, [rdi+0C8h]; struct Var *
0x18306539f  and     sil, al
0x1830653a2  lea     r9, aRobjMWmixedfir; "rObj.m_wMixedFirstOrderInstructions"
0x1830653a9  lea     r8, aMWmixedfirstor_0; "m_wMixedFirstOrderInstructions"
0x1830653b0  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1830653b5  lea     rdx, [rbx+0D0h]; struct Var *
0x1830653bc  movsd   [rsp+58h+var_38], xmm6; double
0x1830653c2  lea     rcx, [rdi+0D0h]; struct Var *
0x1830653c9  and     sil, al
0x1830653cc  lea     r9, aRobjMWmixedcro_0; "rObj.m_wMixedCrossProdInstructions"
0x1830653d3  lea     r8, aMWmixedcrosspr_0; "m_wMixedCrossProdInstructions"
0x1830653da  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1830653df  lea     rdx, [rbx+0D8h]; struct Var *
0x1830653e6  movsd   [rsp+58h+var_38], xmm6; double
0x1830653ec  lea     rcx, [rdi+0D8h]; struct Var *
0x1830653f3  and     sil, al
0x1830653f6  lea     r9, aRobjMWnoncontc_1; "rObj.m_wNonContCrossProdInstructions"
0x1830653fd  lea     r8, aMWnoncontcross_1; "m_wNonContCrossProdInstructions"
0x183065404  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x183065409  lea     rdx, [rbx+0E8h]; struct Var *
0x183065410  movsd   [rsp+58h+var_38], xmm7; double
0x183065416  lea     rcx, [rdi+0E8h]; struct Var *
0x18306541d  and     sil, al
0x183065420  lea     r9, aRobjMMpurecont; "rObj.m_mPureContinuousCrossProds"
0x183065427  lea     r8, aMMpurecontinuo; "m_mPureContinuousCrossProds"
0x18306542e  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x183065433  and     sil, al
0x183065436  movsd   [rsp+58h+var_38], xmm7; double
0x18306543c  lea     rdx, [rbx+0F0h]; struct DataSet *
0x183065443  lea     rcx, [rdi+0F0h]; this
0x18306544a  lea     r9, aRobjMWcontdisc; "rObj.m_wContDiscreteCrossProds"
0x183065451  lea     r8, aMWcontdiscrete; "m_wContDiscreteCrossProds"
0x183065458  call    ?TestDSEquality@@YA_NAEBVDataSet@@0PEBD1N@Z; TestDSEquality(DataSet const &,DataSet const &,char const *,char const *,double)
0x18306545d  lea     rdx, [rbx+0F8h]; struct DataSet *
0x183065464  movsd   [rsp+58h+var_38], xmm7; double
0x18306546a  lea     rcx, [rdi+0F8h]; this
0x183065471  and     sil, al
0x183065474  lea     r9, aRobjMDsextrare; "rObj.m_dsExtraResults"
0x18306547b  lea     r8, aMDsextraresult; "m_dsExtraResults"
0x183065482  call    ?TestDSEquality@@YA_NAEBVDataSet@@0PEBD1N@Z; TestDSEquality(DataSet const &,DataSet const &,char const *,char const *,double)
0x183065487  lea     rdx, [rbx+0E0h]; struct Var *
0x18306548e  movsd   [rsp+58h+var_38], xmm6; double
0x183065494  lea     rcx, [rdi+0E0h]; struct Var *
0x18306549b  and     sil, al
0x18306549e  lea     r9, aRobjMWdescript; "rObj.m_wDescriptiveStatsVar"
0x1830654a5  lea     r8, aMWdescriptives; "m_wDescriptiveStatsVar"
0x1830654ac  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1830654b1  mov     rbx, [rsp+58h+arg_0]
0x1830654b6  and     al, sil
0x1830654b9  mov     rsi, [rsp+58h+arg_8]
0x1830654be  movaps  xmm6, [rsp+58h+var_18]
0x1830654c3  movaps  xmm7, [rsp+58h+var_28]
0x1830654c8  add     rsp, 50h
0x1830654cc  pop     rdi
0x1830654cd  retn
```
