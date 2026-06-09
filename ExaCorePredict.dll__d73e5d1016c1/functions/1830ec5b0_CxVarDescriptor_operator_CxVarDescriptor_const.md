# CxVarDescriptor::operator==(CxVarDescriptor const &)

- ea: `0x1830ec5b0`
- end: `0x1830ec747`
- name: `??8CxVarDescriptor@@QEBA_NAEBV0@@Z`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x183083cf0`

## callees

- `0x1815be180`
- `0x1815be3a0`
- `0x1815bea00`
- `0x1830eae30`
- `0x1830eb4e0`
- `0x1830eb720`

## string_xrefs

- `0x1830ec5ca`: `rObj.m_sDescriptorString`
- `0x1830ec5d5`: `m_sDescriptorString`
- `0x1830ec5f4`: `rObj.m_iDescriptorIndex`
- `0x1830ec5fb`: `m_iDescriptorIndex`
- `0x1830ec6d1`: `rObj.m_sDescriptorElementLabels`
- `0x1830ec6db`: `m_sDescriptorElementLabels`

## pseudocode

```c
char __fastcall CxVarDescriptor::operator==(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi

  v4 = TestScalarEquality<CxString>(a1 + 32, a2 + 32, "m_sDescriptorString", "rObj.m_sDescriptorString") & 1;
  LOBYTE(v4) = TestScalarEquality<unsigned int>(a1 + 40, a2 + 40, "m_iDescriptorIndex", "rObj.m_iDescriptorIndex") & v4;
  LOBYTE(v4) = TestScalarEquality<unsigned int>(
                 a1 + 56,
                 a2 + 56,
                 "m_iContinuousPartIndex",
                 "rObj.m_iContinuousPartIndex")
             & v4;
  LOBYTE(v4) = TestScalarEquality<unsigned int>(a1 + 60, a2 + 60, "m_iDiscretePartIndex", "rObj.m_iDiscretePartIndex")
             & v4;
  LOBYTE(v4) = TestScalarEquality<int>(a1 + 52, a2 + 52, "m_iTermID", "rObj.m_iTermID") & v4;
  LOBYTE(v4) = TestScalarEquality<unsigned int>(
                 a1 + 64,
                 a2 + 64,
                 "m_iDescriptiveStatsIndex",
                 "rObj.m_iDescriptiveStatsIndex")
             & v4;
  LOBYTE(v4) = TestScalarEquality<CxWrapper<CxInteractionSummary>>(
                 a1 + 16,
                 a2 + 16,
                 "m_wInteractionSummary",
                 "rObj.m_wInteractionSummary")
             & v4;
  LOBYTE(v4) = TestScalarEquality<CxWrapper<CxInteractionLongForm>>(
                 a1 + 24,
                 a2 + 24,
                 "m_wInteractionLongForm",
                 "rObj.m_wInteractionLongForm")
             & v4;
  LOBYTE(v4) = TestVarEquality(
                 (const struct Var *)(a1 + 96),
                 (const struct Var *)(a2 + 96),
                 "m_sDescriptorElementLabels",
                 "rObj.m_sDescriptorElementLabels",
                 0.000001)
             & v4;
  LOBYTE(v4) = TestVarEquality(
                 (const struct Var *)(a1 + 80),
                 (const struct Var *)(a2 + 80),
                 "m_svContinuousVarNames",
                 "rObj.m_svContinuousVarNames",
                 0.000001)
             & v4;
  return v4
       & TestVarEquality(
           (const struct Var *)(a1 + 88),
           (const struct Var *)(a2 + 88),
           "m_mdDiscreteVarArray",
           "rObj.m_mdDiscreteVarArray",
           0.000001);
}

```

## disassembly

```asm
0x1830ec5b0  mov     [rsp+arg_0], rbx
0x1830ec5b5  mov     [rsp+arg_8], rsi
0x1830ec5ba  push    rdi
0x1830ec5bb  sub     rsp, 40h
0x1830ec5bf  mov     rbx, rdx
0x1830ec5c2  movaps  [rsp+48h+var_18], xmm6
0x1830ec5c7  mov     rdi, rcx
0x1830ec5ca  lea     r9, aRobjMSdescript_1; "rObj.m_sDescriptorString"
0x1830ec5d1  add     rdx, 20h ; ' '
0x1830ec5d5  lea     r8, aMSdescriptorst; "m_sDescriptorString"
0x1830ec5dc  add     rcx, 20h ; ' '
0x1830ec5e0  call    ??$TestScalarEquality@VCxString@@@@YA_NAEBVCxString@@0PEBD1@Z; TestScalarEquality<CxString>(CxString const &,CxString const &,char const *,char const *)
0x1830ec5e5  movzx   esi, al
0x1830ec5e8  lea     rdx, [rbx+28h]
0x1830ec5ec  lea     rcx, [rdi+28h]
0x1830ec5f0  and     sil, 1
0x1830ec5f4  lea     r9, aRobjMIdescript; "rObj.m_iDescriptorIndex"
0x1830ec5fb  lea     r8, aMIdescriptorin_2; "m_iDescriptorIndex"
0x1830ec602  call    ??$TestScalarEquality@I@@YA_NAEBI0PEBD1@Z; TestScalarEquality<uint>(uint const &,uint const &,char const *,char const *)
0x1830ec607  lea     rdx, [rbx+38h]
0x1830ec60b  and     sil, al
0x1830ec60e  lea     rcx, [rdi+38h]
0x1830ec612  lea     r9, aRobjMIcontinuo; "rObj.m_iContinuousPartIndex"
0x1830ec619  lea     r8, aMIcontinuouspa; "m_iContinuousPartIndex"
0x1830ec620  call    ??$TestScalarEquality@I@@YA_NAEBI0PEBD1@Z; TestScalarEquality<uint>(uint const &,uint const &,char const *,char const *)
0x1830ec625  lea     rdx, [rbx+3Ch]
0x1830ec629  and     sil, al
0x1830ec62c  lea     rcx, [rdi+3Ch]
0x1830ec630  lea     r9, aRobjMIdiscrete_0; "rObj.m_iDiscretePartIndex"
0x1830ec637  lea     r8, aMIdiscretepart_0; "m_iDiscretePartIndex"
0x1830ec63e  call    ??$TestScalarEquality@I@@YA_NAEBI0PEBD1@Z; TestScalarEquality<uint>(uint const &,uint const &,char const *,char const *)
0x1830ec643  lea     rdx, [rbx+34h]
0x1830ec647  and     sil, al
0x1830ec64a  lea     rcx, [rdi+34h]
0x1830ec64e  lea     r9, aRobjMItermid; "rObj.m_iTermID"
0x1830ec655  lea     r8, aMItermid_0; "m_iTermID"
0x1830ec65c  call    ??$TestScalarEquality@H@@YA_NAEBH0PEBD1@Z; TestScalarEquality<int>(int const &,int const &,char const *,char const *)
0x1830ec661  lea     rdx, [rbx+40h]
0x1830ec665  and     sil, al
0x1830ec668  lea     rcx, [rdi+40h]
0x1830ec66c  lea     r9, aRobjMIdescript_3; "rObj.m_iDescriptiveStatsIndex"
0x1830ec673  lea     r8, aMIdescriptives_1; "m_iDescriptiveStatsIndex"
0x1830ec67a  call    ??$TestScalarEquality@I@@YA_NAEBI0PEBD1@Z; TestScalarEquality<uint>(uint const &,uint const &,char const *,char const *)
0x1830ec67f  lea     rdx, [rbx+10h]
0x1830ec683  and     sil, al
0x1830ec686  lea     rcx, [rdi+10h]
0x1830ec68a  lea     r9, aRobjMWinteract; "rObj.m_wInteractionSummary"
0x1830ec691  lea     r8, aMWinteractions; "m_wInteractionSummary"
0x1830ec698  call    ??$TestScalarEquality@V?$CxWrapper@VCxInteractionSummary@@@@@@YA_NAEBV?$CxWrapper@VCxInteractionSummary@@@@0PEBD1@Z; TestScalarEquality<CxWrapper<CxInteractionSummary>>(CxWrapper<CxInteractionSummary> const &,CxWrapper<CxInteractionSummary> const &,char const *,char const *)
0x1830ec69d  lea     rdx, [rbx+18h]
0x1830ec6a1  and     sil, al
0x1830ec6a4  lea     rcx, [rdi+18h]
0x1830ec6a8  lea     r9, aRobjMWinteract_0; "rObj.m_wInteractionLongForm"
0x1830ec6af  lea     r8, aMWinteractionl; "m_wInteractionLongForm"
0x1830ec6b6  call    ??$TestScalarEquality@V?$CxWrapper@VCxInteractionLongForm@@@@@@YA_NAEBV?$CxWrapper@VCxInteractionLongForm@@@@0PEBD1@Z; TestScalarEquality<CxWrapper<CxInteractionLongForm>>(CxWrapper<CxInteractionLongForm> const &,CxWrapper<CxInteractionLongForm> const &,char const *,char const *)
0x1830ec6bb  movsd   xmm6, cs:__real@3eb0c6f7a0b5ed8d
0x1830ec6c3  lea     rdx, [rbx+60h]; struct Var *
0x1830ec6c7  lea     rcx, [rdi+60h]; struct Var *
0x1830ec6cb  movsd   [rsp+48h+var_28], xmm6; double
0x1830ec6d1  lea     r9, aRobjMSdescript; "rObj.m_sDescriptorElementLabels"
0x1830ec6d8  and     sil, al
0x1830ec6db  lea     r8, aMSdescriptorel; "m_sDescriptorElementLabels"
0x1830ec6e2  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1830ec6e7  lea     rdx, [rbx+50h]; struct Var *
0x1830ec6eb  movsd   [rsp+48h+var_28], xmm6; double
0x1830ec6f1  lea     rcx, [rdi+50h]; struct Var *
0x1830ec6f5  and     sil, al
0x1830ec6f8  lea     r9, aRobjMSvcontinu; "rObj.m_svContinuousVarNames"
0x1830ec6ff  lea     r8, aMSvcontinuousv; "m_svContinuousVarNames"
0x1830ec706  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1830ec70b  lea     rdx, [rbx+58h]; struct Var *
0x1830ec70f  movsd   [rsp+48h+var_28], xmm6; double
0x1830ec715  lea     rcx, [rdi+58h]; struct Var *
0x1830ec719  and     sil, al
0x1830ec71c  lea     r9, aRobjMMddiscret; "rObj.m_mdDiscreteVarArray"
0x1830ec723  lea     r8, aMMddiscretevar; "m_mdDiscreteVarArray"
0x1830ec72a  call    ?TestVarEquality@@YA_NAEBVVar@@0PEBD1N@Z; TestVarEquality(Var const &,Var const &,char const *,char const *,double)
0x1830ec72f  mov     rbx, [rsp+48h+arg_0]
0x1830ec734  and     al, sil
0x1830ec737  mov     rsi, [rsp+48h+arg_8]
0x1830ec73c  movaps  xmm6, [rsp+48h+var_18]
0x1830ec741  add     rsp, 40h
0x1830ec745  pop     rdi
0x1830ec746  retn
```
