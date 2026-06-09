# ProcessedPipelineEffect::LoadPropertiesFromSourceEffect(IEffectHost *)

- ea: `0x1805011ac`
- end: `0x180501b81`
- name: `?LoadPropertiesFromSourceEffect@ProcessedPipelineEffect@@AEAAXPEAUIEffectHost@@@Z`
- size: `2517`
- prototype: `void __fastcall(ProcessedPipelineEffect *__hidden this, struct IEffectHost *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180500da0`
- `0x180500ee0`

## callees

- `0x1804c6944`
- `0x1804fc524`
- `0x1805010e0`
- `0x1805011ac`
- `0x180503030`
- `0x180507c50`
- `0x1805129ec`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1805011eb`
- `OLEAUT32!__imp_VariantInit` at `0x180501214`
- `OLEAUT32!__imp_VariantInit` at `0x180501237`
- `OLEAUT32!__imp_VariantInit` at `0x18050137f`
- `OLEAUT32!__imp_VariantInit` at `0x18050144e`
- `OLEAUT32!__imp_VariantInit` at `0x18050196e`
- `OLEAUT32!__imp_VariantInit` at `0x1805011eb`
- `OLEAUT32!__imp_VariantInit` at `0x180501214`
- `OLEAUT32!__imp_VariantInit` at `0x180501237`
- `OLEAUT32!__imp_VariantInit` at `0x18050137f`
- `OLEAUT32!__imp_VariantInit` at `0x18050144e`
- `OLEAUT32!__imp_VariantInit` at `0x18050196e`
- `OLEAUT32!__imp_VariantClear` at `0x18050181f`
- `OLEAUT32!__imp_VariantClear` at `0x1805019c8`
- `OLEAUT32!__imp_VariantClear` at `0x1805019d2`
- `OLEAUT32!__imp_VariantClear` at `0x1805019df`
- `OLEAUT32!__imp_VariantClear` at `0x180501a00`
- `OLEAUT32!__imp_VariantClear` at `0x180501a0a`
- `OLEAUT32!__imp_VariantClear` at `0x180501a14`
- `OLEAUT32!__imp_VariantClear` at `0x180501a1e`
- `OLEAUT32!__imp_VariantClear` at `0x180501a28`
- `OLEAUT32!__imp_VariantClear` at `0x180501a32`
- `OLEAUT32!__imp_VariantClear` at `0x180501a3c`
- `OLEAUT32!__imp_VariantClear` at `0x18050181f`
- `OLEAUT32!__imp_VariantClear` at `0x1805019c8`
- `OLEAUT32!__imp_VariantClear` at `0x1805019d2`
- `OLEAUT32!__imp_VariantClear` at `0x1805019df`
- `OLEAUT32!__imp_VariantClear` at `0x180501a00`
- `OLEAUT32!__imp_VariantClear` at `0x180501a0a`
- `OLEAUT32!__imp_VariantClear` at `0x180501a14`
- `OLEAUT32!__imp_VariantClear` at `0x180501a1e`
- `OLEAUT32!__imp_VariantClear` at `0x180501a28`
- `OLEAUT32!__imp_VariantClear` at `0x180501a32`
- `OLEAUT32!__imp_VariantClear` at `0x180501a3c`
- `OLEAUT32!__imp_VariantCopy` at `0x180501316`
- `OLEAUT32!__imp_VariantCopy` at `0x180501316`
- `OLEAUT32!__imp_VariantChangeType` at `0x180501537`
- `OLEAUT32!__imp_VariantChangeType` at `0x180501537`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18050159d`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18050159d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1805019f5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1805019f5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180501612`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180501683`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805016ef`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180501612`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180501683`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805016ef`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805015e4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180501656`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805016bf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805015e4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180501656`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805016bf`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1805015ba`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1805015ba`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1805019e8`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1805019e8`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180501766`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180501766`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18050177a`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18050177a`

## string_xrefs

- `0x180501338`: `ExposureCompensation`
- `0x1805018ee`: `Temperature`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ProcessedPipelineEffect::LoadPropertiesFromSourceEffect(
        ProcessedPipelineEffect *this,
        struct IEffectHost *a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int vt; // r12d
  HRESULT v10; // eax
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  __int64 *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  __int64 *v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  HRESULT v23; // eax
  __int64 *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  SAFEARRAY *v27; // rax
  SAFEARRAY *v28; // rbx
  HRESULT v29; // eax
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  double *v32; // r15
  HRESULT v33; // eax
  HRESULT v34; // eax
  double *v35; // r14
  HRESULT v36; // eax
  LONG v37; // esi
  HRESULT v38; // eax
  double v39; // xmm6_8
  __int64 v40; // rsi
  __int64 (__fastcall *v41)(__int64, const WCHAR *, ULONG *); // r14
  HRESULT v42; // eax
  HRESULT Vartype; // ecx
  SHORT iVal; // dx
  SHORT v45; // dx
  int v46; // esi
  __int64 v47; // rax
  int v48; // eax
  __int64 *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  __int64 *v52; // rcx
  __int64 v53; // rax
  int v54; // eax
  int v55; // eax
  VARIANTARG pvargDest; // [rsp+40h] [rbp-C8h] BYREF
  IRecordInfo *pRecInfo; // [rsp+58h] [rbp-B0h]
  LONG plLbound; // [rsp+68h] [rbp-A0h] BYREF
  struct tagVARIANT v59; // [rsp+70h] [rbp-98h] BYREF
  IRecordInfo *v60; // [rsp+88h] [rbp-80h]
  int v61; // [rsp+98h] [rbp-70h] BYREF
  double v62; // [rsp+A0h] [rbp-68h] BYREF
  LONGLONG v63; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG v64; // [rsp+B0h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarSrc; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG v67; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG v68; // [rsp+110h] [rbp+8h] BYREF
  VARIANTARG v69; // [rsp+128h] [rbp+20h] BYREF
  VARIANTARG v70; // [rsp+140h] [rbp+38h] BYREF
  VARIANTARG v71; // [rsp+158h] [rbp+50h] BYREF
  VARIANTARG v72; // [rsp+170h] [rbp+68h] BYREF
  VARIANTARG v73; // [rsp+188h] [rbp+80h] BYREF
  SAFEARRAY *v74; // [rsp+1A0h] [rbp+98h]
  SAFEARRAYBOUND rgsabound; // [rsp+218h] [rbp+110h] BYREF
  LONG plUbound; // [rsp+220h] [rbp+118h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarSrc.vt = 3;
  pvarSrc.lVal = 1;
  memset(&v69, 0, sizeof(v69));
  VariantInit(&v69);
  v71.vt = 3;
  v71.lVal = 100;
  memset(&v70, 0, sizeof(v70));
  VariantInit(&v70);
  v4 = (*(__int64 (__fastcall **)(struct IEffectHost *, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 96LL))(
         a2,
         L"IsTiffContainer",
         &v70);
  if ( v4 < 0 )
    ATL::BaseAtlThrow(v4);
  *((_BYTE *)this + 320) = v70.iVal != 0;
  v5 = (*(__int64 (__fastcall **)(struct IEffectHost *, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 96LL))(
         a2,
         L"CameraModelID",
         &v69);
  if ( v5 < 0 )
    ATL::BaseAtlThrow(v5);
  v6 = (*(__int64 (__fastcall **)(struct IEffectHost *, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 96LL))(
         a2,
         L"ISO",
         &v71);
  if ( v6 < 0 )
    ATL::BaseAtlThrow(v6);
  v7 = (*(__int64 (__fastcall **)(struct IEffectHost *, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 96LL))(
         a2,
         L"AsShotOrientation",
         &pvarSrc);
  if ( v7 < 0 )
    ATL::BaseAtlThrow(v7);
  v8 = (*(__int64 (__fastcall **)(struct IEffectHost *, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 96LL))(
         a2,
         L"WhiteBalance",
         &pvarg);
  if ( v8 < 0 )
    ATL::BaseAtlThrow(v8);
  vt = pvarg.vt;
  if ( pvarg.vt )
  {
    pvargDest.iVal = 0;
    v10 = VariantCopy((VARIANTARG *)&pvargDest.decVal.8, &pvarg);
    if ( v10 < 0 )
    {
      pvargDest.iVal = 10;
      *((_DWORD *)&pvargDest.decVal + 4) = v10;
      ATL::BaseAtlThrow(v10);
    }
    ProcessedPipelineEffect::SetPropertyOnBothSceneEffects(this, L"WhiteBalance", &pvargDest.decVal.Lo32);
  }
  ProcessedPipelineEffect::SetSourceEffectPropertiesOnBothSceneEffects(this, a2, L"ExposureCompensation");
  ProcessedPipelineEffect::SetSourceEffectPropertiesOnBothSceneEffects(this, a2, L"Contrast");
  ProcessedPipelineEffect::SetSourceEffectPropertiesOnBothSceneEffects(this, a2, L"Brightness");
  memset(&v64, 0, sizeof(v64));
  VariantInit(&v64);
  if ( (*(int (__fastcall **)(struct IEffectHost *, const WCHAR *, VARIANTARG *))(*(_QWORD *)a2 + 96LL))(
         a2,
         L"OutputProfile",
         &v64) >= 0 )
  {
    *(_OWORD *)&pvargDest.decVal.Lo32 = *(_OWORD *)&v64.vt;
    pRecInfo = v64.pRecInfo;
    ProcessedPipelineEffect::SetInverseRawSceneEffectProperty(
      this,
      L"DestinationColorProfile",
      (struct tagVARIANT *)&pvargDest.decVal.8);
    v11 = (__int64 *)*((_QWORD *)this + 16);
    v12 = *v11;
    *(_OWORD *)&pvargDest.decVal.Lo32 = *(_OWORD *)&v64.vt;
    pRecInfo = v64.pRecInfo;
    v13 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, CY *))(v12 + 104))(
            v11,
            L"DestinationColorProfile",
            &pvargDest.cyVal);
    if ( v13 < 0 )
      ATL::BaseAtlThrow(v13);
  }
  memset(&v68, 0, sizeof(v68));
  VariantInit(&v68);
  if ( (*(int (__fastcall **)(struct IEffectHost *, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 96LL))(
         a2,
         L"LoadedColorProfile",
         &v68) >= 0 )
  {
    v14 = (__int64 *)*((_QWORD *)this + 16);
    v15 = *v14;
    *(_OWORD *)&pvargDest.decVal.Lo32 = *(_OWORD *)&v68.vt;
    pRecInfo = v68.pRecInfo;
    v16 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, CY *))(v15 + 104))(
            v14,
            L"ColorProfileForSave",
            &pvargDest.cyVal);
    if ( v16 <= -1 )
      ATL::BaseAtlThrow(v16);
  }
  v17 = (__int64 *)*((_QWORD *)this + 16);
  v18 = *v17;
  *(_OWORD *)&pvargDest.decVal.Lo32 = *(_OWORD *)&v71.vt;
  pRecInfo = v71.pRecInfo;
  v19 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, CY *))(v18 + 104))(v17, L"ISO", &pvargDest.cyVal);
  if ( v19 < 0 )
    ATL::BaseAtlThrow(v19);
  v20 = (__int64 *)*((_QWORD *)this + 16);
  v21 = *v20;
  *(_OWORD *)&pvargDest.decVal.Lo32 = *(_OWORD *)&v69.vt;
  pRecInfo = v69.pRecInfo;
  v22 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, CY *))(v21 + 104))(
          v20,
          L"CameraModelID",
          &pvargDest.cyVal);
  if ( v22 < 0 )
    ATL::BaseAtlThrow(v22);
  v23 = VariantChangeType(&pvarSrc, &pvarSrc, 0, 3u);
  if ( v23 < 0 )
    ATL::BaseAtlThrow(v23);
  v24 = (__int64 *)*((_QWORD *)this + 16);
  v25 = *v24;
  *(_OWORD *)&pvargDest.decVal.Lo32 = *(_OWORD *)&pvarSrc.vt;
  pRecInfo = pvarSrc.pRecInfo;
  v26 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, CY *))(v25 + 104))(v24, L"Orientation", &pvargDest.cyVal);
  if ( v26 < 0 )
    ATL::BaseAtlThrow(v26);
  v61 = 1;
  rgsabound = (SAFEARRAYBOUND)3LL;
  v27 = SafeArrayCreate(5u, 1u, &rgsabound);
  v28 = v27;
  v74 = v27;
  if ( v27 )
    v29 = SafeArrayLock(v27);
  else
    v29 = -2147024882;
  if ( v29 < 0 )
    ATL::BaseAtlThrow(v29);
  if ( !v28 )
    ATL::BaseAtlThrow(-2147467259);
  rgsabound.cElements = 0;
  LBound = SafeArrayGetLBound(v28, 1u, (LONG *)&rgsabound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  if ( (int)rgsabound.cElements > 2 )
    goto LABEL_78;
  plUbound = 0;
  UBound = SafeArrayGetUBound(v28, 1u, &plUbound);
  if ( UBound < 0 )
    ATL::BaseAtlThrow(UBound);
  if ( plUbound < 2 )
    goto LABEL_78;
  v32 = (double *)((char *)v28->pvData + 8 * (2 - rgsabound.cElements));
  plUbound = 0;
  v33 = SafeArrayGetLBound(v28, 1u, &plUbound);
  if ( v33 < 0 )
    ATL::BaseAtlThrow(v33);
  if ( plUbound > 1 )
    goto LABEL_78;
  rgsabound.cElements = 0;
  v34 = SafeArrayGetUBound(v28, 1u, (LONG *)&rgsabound);
  if ( v34 < 0 )
    ATL::BaseAtlThrow(v34);
  if ( (int)rgsabound.cElements < 1 )
    goto LABEL_78;
  v35 = (double *)((char *)v28->pvData + 8 * (1 - plUbound));
  plLbound = 0;
  v36 = SafeArrayGetLBound(v28, 1u, &plLbound);
  if ( v36 < 0 )
    ATL::BaseAtlThrow(v36);
  v37 = plLbound;
  if ( plLbound > 0 )
    goto LABEL_78;
  rgsabound.cElements = 0;
  v38 = SafeArrayGetUBound(v28, 1u, (LONG *)&rgsabound);
  if ( v38 < 0 )
    ATL::BaseAtlThrow(v38);
  if ( (rgsabound.cElements & 0x80000000) != 0 )
LABEL_78:
    ATL::BaseAtlThrow(-2147024809);
  v39 = DOUBLE_6500_0;
  CaptureOneKelvinConverter::GetWBGainsFromKelvinTint(
    (ProcessedPipelineEffect *)((char *)this + 248),
    6500.0,
    0.0,
    (double *)v28->pvData - v37,
    v35,
    v32,
    &v61);
  v40 = *((_QWORD *)this + 16);
  v41 = *(__int64 (__fastcall **)(__int64, const WCHAR *, ULONG *))(*(_QWORD *)v40 + 104LL);
  rgsabound = 0;
  v42 = SafeArrayCopy(v28, (SAFEARRAY **)&rgsabound);
  Vartype = v42;
  if ( v42 < 0 )
  {
    *((_DWORD *)&pvargDest.decVal + 4) = v42;
  }
  else
  {
    Vartype = SafeArrayGetVartype(v28, &pvargDest.uiVal);
    iVal = pvargDest.iVal;
    if ( Vartype >= 0 && pvargDest.iVal == 13 && (v28->fFeatures & 0x440) == 0x440 )
      iVal = 9;
    if ( Vartype >= 0 )
    {
      v45 = iVal | 0x2000;
      *((SAFEARRAYBOUND *)&pvargDest.decVal + 2) = rgsabound;
      goto LABEL_44;
    }
    *((_DWORD *)&pvargDest.decVal + 4) = Vartype;
  }
  v45 = 10;
LABEL_44:
  pvargDest.iVal = v45;
  if ( Vartype < 0 )
  {
    if ( Vartype != -2147024882 )
      ATL::BaseAtlThrow(Vartype);
    ATL::BaseAtlThrow(-2147024882);
  }
  *(_OWORD *)&v59.decVal.Lo32 = *(_OWORD *)&pvargDest.decVal.Lo32;
  v60 = pRecInfo;
  v46 = v41(v40, L"D65WhiteBalance", (ULONG *)&v59.cyVal);
  VariantClear((VARIANTARG *)&pvargDest.decVal.8);
  if ( v46 < 0 )
    ATL::BaseAtlThrow(v46);
  v62 = DOUBLE_6500_0;
  v63 = 0;
  if ( vt )
  {
    rgsabound.cElements = 0;
    v47 = *((_QWORD *)this + 21);
    *(_OWORD *)&v59.decVal.Lo32 = *(_OWORD *)&pvarg.vt;
    v60 = pvarg.pRecInfo;
    v48 = (*(__int64 (__fastcall **)(char *, CY *, __int64, double *, LONGLONG *, SAFEARRAYBOUND *))(v47 + 24))(
            (char *)this + 168,
            &v59.cyVal,
            2,
            &v62,
            &v63,
            &rgsabound);
    if ( v48 < 0 )
      ATL::BaseAtlThrow(v48);
    if ( rgsabound.cElements )
    {
      v39 = v62;
    }
    else
    {
      v62 = DOUBLE_6500_0;
      v63 = 0;
    }
  }
  v73.vt = 3;
  v73.lVal = (int)v39;
  v49 = (__int64 *)*((_QWORD *)this + 16);
  v50 = *v49;
  *(_OWORD *)&v59.decVal.Lo32 = *(_OWORD *)&v73.vt;
  v60 = v73.pRecInfo;
  v51 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, CY *))(v50 + 104))(v49, L"Temperature", &v59.cyVal);
  if ( v51 < 0 )
    ATL::BaseAtlThrow(v51);
  v72.vt = 5;
  v72.llVal = v63;
  v52 = (__int64 *)*((_QWORD *)this + 16);
  v53 = *v52;
  *(_OWORD *)&v59.decVal.Lo32 = *(_OWORD *)&v72.vt;
  v60 = v72.pRecInfo;
  v54 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, CY *))(v53 + 104))(v52, L"Tint", &v59.cyVal);
  if ( v54 < 0 )
    ATL::BaseAtlThrow(v54);
  ProcessedPipelineEffect::CalculateAndSetWhiteBalance(this);
  memset(&v67, 0, sizeof(v67));
  VariantInit(&v67);
  v55 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
          *((_QWORD *)this + 16),
          L"WhiteBalance",
          &v67);
  if ( v55 < 0 )
    ATL::BaseAtlThrow(v55);
  *(_OWORD *)&v59.decVal.Lo32 = *(_OWORD *)&v67.vt;
  v60 = v67.pRecInfo;
  ProcessedPipelineEffect::SetInverseRawSceneEffectProperty(this, L"WhiteBalance", (struct tagVARIANT *)&v59.decVal.8);
  VariantClear(&v67);
  VariantClear(&v72);
  VariantClear(&v73);
  if ( SafeArrayUnlock(v28) >= 0 )
    SafeArrayDestroy(v28);
  VariantClear(&v68);
  VariantClear(&v64);
  VariantClear(&v70);
  VariantClear(&v71);
  VariantClear(&v69);
  VariantClear(&pvarSrc);
  VariantClear(&pvarg);
}

```

## disassembly

```asm
0x1805011ac  mov     rax, rsp
0x1805011af  mov     [rax+8], rbx
0x1805011b3  push    rbp
0x1805011b4  push    rsi
0x1805011b5  push    rdi
0x1805011b6  push    r12
0x1805011b8  push    r13
0x1805011ba  push    r14
0x1805011bc  push    r15
0x1805011be  lea     rbp, [rax-0F8h]
0x1805011c5  sub     rsp, 1C0h
0x1805011cc  movaps  xmmword ptr [rax-48h], xmm6
0x1805011d0  movaps  xmmword ptr [rax-58h], xmm7
0x1805011d4  mov     rbx, rdx
0x1805011d7  mov     rdi, rcx
0x1805011da  xorps   xmm0, xmm0
0x1805011dd  xor     eax, eax
0x1805011df  movups  xmmword ptr [rbp+0F0h+pvarg], xmm0
0x1805011e3  mov     qword ptr [rbp+0F0h+pvarg+10h], rax
0x1805011e7  lea     rcx, [rbp+0F0h+pvarg]; pvarg
0x1805011eb  call    cs:__imp_VariantInit
0x1805011f1  mov     r15d, 3
0x1805011f7  mov     word ptr [rbp+0F0h+pvarSrc], r15w
0x1805011fc  lea     esi, [r15-2]
0x180501200  mov     dword ptr [rbp+0F0h+pvarSrc+8], esi
0x180501203  xorps   xmm0, xmm0
0x180501206  xor     eax, eax
0x180501208  movups  xmmword ptr [rbp+0F0h+var_D0], xmm0
0x18050120c  mov     qword ptr [rbp+0F0h+var_D0+10h], rax
0x180501210  lea     rcx, [rbp+0F0h+var_D0]; pvarg
0x180501214  call    cs:__imp_VariantInit
0x18050121a  mov     word ptr [rbp+0F0h+var_A0], r15w
0x18050121f  mov     dword ptr [rbp+0F0h+var_A0+8], 64h ; 'd'
0x180501226  xorps   xmm0, xmm0
0x180501229  xor     eax, eax
0x18050122b  movups  xmmword ptr [rbp+0F0h+var_B8], xmm0
0x18050122f  mov     qword ptr [rbp+0F0h+var_B8+10h], rax
0x180501233  lea     rcx, [rbp+0F0h+var_B8]; pvarg
0x180501237  call    cs:__imp_VariantInit
0x18050123d  mov     rax, [rbx]
0x180501240  lea     r8, [rbp+0F0h+var_B8]
0x180501244  lea     rdx, aIstiffcontaine; "IsTiffContainer"
0x18050124b  mov     rcx, rbx
0x18050124e  mov     rax, [rax+60h]
0x180501252  call    cs:__guard_dispatch_icall_fptr
0x180501258  xor     r13d, r13d
0x18050125b  test    eax, eax
0x18050125d  js      loc_180501A7F
0x180501263  cmp     word ptr [rbp+0F0h+var_B8+8], r13w
0x180501268  setnz   al
0x18050126b  mov     [rdi+140h], al
0x180501271  mov     rax, [rbx]
0x180501274  lea     r8, [rbp+0F0h+var_D0]
0x180501278  lea     rdx, aCameramodelid; "CameraModelID"
0x18050127f  mov     rcx, rbx
0x180501282  mov     rax, [rax+60h]
0x180501286  call    cs:__guard_dispatch_icall_fptr
0x18050128c  test    eax, eax
0x18050128e  js      loc_180501A67
0x180501294  mov     rax, [rbx]
0x180501297  lea     r8, [rbp+0F0h+var_A0]
0x18050129b  lea     rdx, aIso; "ISO"
0x1805012a2  mov     rcx, rbx
0x1805012a5  mov     rax, [rax+60h]
0x1805012a9  call    cs:__guard_dispatch_icall_fptr
0x1805012af  test    eax, eax
0x1805012b1  js      loc_180501B79
0x1805012b7  mov     rax, [rbx]
0x1805012ba  lea     r8, [rbp+0F0h+pvarSrc]
0x1805012be  lea     rdx, aAsshotorientat; "AsShotOrientation"
0x1805012c5  mov     rcx, rbx
0x1805012c8  mov     rax, [rax+60h]
0x1805012cc  call    cs:__guard_dispatch_icall_fptr
0x1805012d2  test    eax, eax
0x1805012d4  js      loc_180501B71
0x1805012da  mov     rax, [rbx]
0x1805012dd  lea     r8, [rbp+0F0h+pvarg]
0x1805012e1  lea     rdx, aWhitebalance_0; "WhiteBalance"
0x1805012e8  mov     rcx, rbx
0x1805012eb  mov     rax, [rax+60h]
0x1805012ef  call    cs:__guard_dispatch_icall_fptr
0x1805012f5  test    eax, eax
0x1805012f7  js      loc_180501B69
0x1805012fd  movzx   r12d, word ptr [rbp+0F0h+pvarg]
0x180501302  test    r12d, r12d
0x180501305  jz      short loc_180501338
0x180501307  mov     word ptr [rsp+1F0h+pvargDest+8], r13w
0x18050130d  lea     rdx, [rbp+0F0h+pvarg]; pvargSrc
0x180501311  lea     rcx, [rsp+1F0h+pvargDest+8]; pvargDest
0x180501316  call    cs:__imp_VariantCopy
0x18050131c  test    eax, eax
0x18050131e  js      loc_180501A87
0x180501324  lea     r8, [rsp+1F0h+pvargDest+8]
0x180501329  lea     rdx, aWhitebalance_0; "WhiteBalance"
0x180501330  mov     rcx, rdi
0x180501333  call    ?SetPropertyOnBothSceneEffects@ProcessedPipelineEffect@@AEAAXPEB_WVCComVariant@ATL@@@Z; ProcessedPipelineEffect::SetPropertyOnBothSceneEffects(wchar_t const *,ATL::CComVariant)
0x180501338  lea     r8, aExposurecompen; "ExposureCompensation"
0x18050133f  mov     rdx, rbx; struct IEffectHost *
0x180501342  mov     rcx, rdi; this
0x180501345  call    ?SetSourceEffectPropertiesOnBothSceneEffects@ProcessedPipelineEffect@@AEAA_NPEAUIEffectHost@@PEB_W@Z; ProcessedPipelineEffect::SetSourceEffectPropertiesOnBothSceneEffects(IEffectHost *,wchar_t const *)
0x18050134a  lea     r8, aContrast; "Contrast"
0x180501351  mov     rdx, rbx; struct IEffectHost *
0x180501354  mov     rcx, rdi; this
0x180501357  call    ?SetSourceEffectPropertiesOnBothSceneEffects@ProcessedPipelineEffect@@AEAA_NPEAUIEffectHost@@PEB_W@Z; ProcessedPipelineEffect::SetSourceEffectPropertiesOnBothSceneEffects(IEffectHost *,wchar_t const *)
0x18050135c  lea     r8, aBrightness; "Brightness"
0x180501363  mov     rdx, rbx; struct IEffectHost *
0x180501366  mov     rcx, rdi; this
0x180501369  call    ?SetSourceEffectPropertiesOnBothSceneEffects@ProcessedPipelineEffect@@AEAA_NPEAUIEffectHost@@PEB_W@Z; ProcessedPipelineEffect::SetSourceEffectPropertiesOnBothSceneEffects(IEffectHost *,wchar_t const *)
0x18050136e  xorps   xmm0, xmm0
0x180501371  xor     eax, eax
0x180501373  movups  xmmword ptr [rbp+0F0h+var_148], xmm0
0x180501377  mov     qword ptr [rbp+0F0h+var_148+10h], rax
0x18050137b  lea     rcx, [rbp+0F0h+var_148]; pvarg
0x18050137f  call    cs:__imp_VariantInit
0x180501385  nop
0x180501386  mov     rax, [rbx]
0x180501389  lea     r8, [rbp+0F0h+var_148]
0x18050138d  lea     rdx, aOutputprofile; "OutputProfile"
0x180501394  mov     rcx, rbx
0x180501397  mov     rax, [rax+60h]
0x18050139b  call    cs:__guard_dispatch_icall_fptr
0x1805013a1  mov     r14d, 8007000Eh
0x1805013a7  test    eax, eax
0x1805013a9  js      loc_18050143D
0x1805013af  movups  xmm0, xmmword ptr [rbp+0F0h+var_148]
0x1805013b3  movaps  xmmword ptr [rsp+1F0h+pvargDest+8], xmm0
0x1805013b8  movsd   xmm1, qword ptr [rbp+0F0h+var_148+10h]
0x1805013bd  movsd   [rsp+1F0h+var_1A0], xmm1
0x1805013c3  lea     r8, [rsp+1F0h+pvargDest+8]; struct tagVARIANT
0x1805013c8  lea     rdx, aDestinationcol; "DestinationColorProfile"
0x1805013cf  mov     rcx, rdi; this
0x1805013d2  call    ?SetInverseRawSceneEffectProperty@ProcessedPipelineEffect@@AEAAXPEB_WUtagVARIANT@@@Z; ProcessedPipelineEffect::SetInverseRawSceneEffectProperty(wchar_t const *,tagVARIANT)
0x1805013d7  mov     rcx, [rdi+80h]
0x1805013de  mov     rax, [rcx]
0x1805013e1  movups  xmm0, xmmword ptr [rbp+0F0h+var_148]
0x1805013e5  movaps  xmmword ptr [rsp+1F0h+pvargDest+8], xmm0
0x1805013ea  movsd   xmm1, qword ptr [rbp+0F0h+var_148+10h]
0x1805013ef  movsd   [rsp+1F0h+var_1A0], xmm1
0x1805013f5  lea     r8, [rsp+1F0h+pvargDest+8]
0x1805013fa  lea     rdx, aDestinationcol; "DestinationColorProfile"
0x180501401  mov     rax, [rax+68h]
0x180501405  call    cs:__guard_dispatch_icall_fptr
0x18050140b  cmp     eax, r14d
0x18050140e  jz      loc_180501AA1
0x180501414  cmp     eax, 86160210h
0x180501419  jz      loc_180501AA1
0x18050141f  cmp     eax, 86170103h
0x180501424  jz      loc_180501AA1
0x18050142a  cmp     eax, 86180110h
0x18050142f  jz      loc_180501AA1
0x180501435  test    eax, eax
0x180501437  js      loc_180501AA1
0x18050143d  xorps   xmm0, xmm0
0x180501440  xor     eax, eax
0x180501442  movups  xmmword ptr [rbp+0F0h+var_E8], xmm0
0x180501446  mov     qword ptr [rbp+0F0h+var_E8+10h], rax
0x18050144a  lea     rcx, [rbp+0F0h+var_E8]; pvarg
0x18050144e  call    cs:__imp_VariantInit
0x180501454  nop
0x180501455  mov     rax, [rbx]
0x180501458  lea     r8, [rbp+0F0h+var_E8]
0x18050145c  lea     rdx, aLoadedcolorpro; "LoadedColorProfile"
0x180501463  mov     rcx, rbx
0x180501466  mov     rax, [rax+60h]
0x18050146a  call    cs:__guard_dispatch_icall_fptr
0x180501470  test    eax, eax
0x180501472  js      short loc_1805014B1
0x180501474  mov     rcx, [rdi+80h]
0x18050147b  mov     rax, [rcx]
0x18050147e  movups  xmm0, xmmword ptr [rbp+0F0h+var_E8]
0x180501482  movaps  xmmword ptr [rsp+1F0h+pvargDest+8], xmm0
0x180501487  movsd   xmm1, qword ptr [rbp+0F0h+var_E8+10h]
0x18050148c  movsd   [rsp+1F0h+var_1A0], xmm1
0x180501492  lea     r8, [rsp+1F0h+pvargDest+8]
0x180501497  lea     rdx, aColorprofilefo; "ColorProfileForSave"
0x18050149e  mov     rax, [rax+68h]
0x1805014a2  call    cs:__guard_dispatch_icall_fptr
0x1805014a8  cmp     eax, 0FFFFFFFFh
0x1805014ab  jle     loc_180501AAD
0x1805014b1  mov     rcx, [rdi+80h]
0x1805014b8  mov     rax, [rcx]
0x1805014bb  movups  xmm0, xmmword ptr [rbp+0F0h+var_A0]
0x1805014bf  movaps  xmmword ptr [rsp+1F0h+pvargDest+8], xmm0
0x1805014c4  movsd   xmm1, qword ptr [rbp+0F0h+var_A0+10h]
0x1805014c9  movsd   [rsp+1F0h+var_1A0], xmm1
0x1805014cf  lea     r8, [rsp+1F0h+pvargDest+8]
0x1805014d4  lea     rdx, aIso; "ISO"
0x1805014db  mov     rax, [rax+68h]
0x1805014df  call    cs:__guard_dispatch_icall_fptr
0x1805014e5  test    eax, eax
0x1805014e7  js      loc_180501B5D
0x1805014ed  mov     rcx, [rdi+80h]
0x1805014f4  mov     rax, [rcx]
0x1805014f7  movups  xmm0, xmmword ptr [rbp+0F0h+var_D0]
0x1805014fb  movaps  xmmword ptr [rsp+1F0h+pvargDest+8], xmm0
0x180501500  movsd   xmm1, qword ptr [rbp+0F0h+var_D0+10h]
0x180501505  movsd   [rsp+1F0h+var_1A0], xmm1
0x18050150b  lea     r8, [rsp+1F0h+pvargDest+8]
0x180501510  lea     rdx, aCameramodelid; "CameraModelID"
0x180501517  mov     rax, [rax+68h]
0x18050151b  call    cs:__guard_dispatch_icall_fptr
0x180501521  test    eax, eax
0x180501523  js      loc_180501B55
0x180501529  mov     r9d, r15d; vt
0x18050152c  xor     r8d, r8d; wFlags
0x18050152f  lea     rdx, [rbp+0F0h+pvarSrc]; pvarSrc
0x180501533  lea     rcx, [rbp+0F0h+pvarSrc]; pvargDest
0x180501537  call    cs:__imp_VariantChangeType
0x18050153d  test    eax, eax
0x18050153f  js      loc_180501B4D
0x180501545  mov     rcx, [rdi+80h]
0x18050154c  mov     rax, [rcx]
0x18050154f  movups  xmm0, xmmword ptr [rbp+0F0h+pvarSrc]
0x180501553  movaps  xmmword ptr [rsp+1F0h+pvargDest+8], xmm0
0x180501558  movsd   xmm1, qword ptr [rbp+0F0h+pvarSrc+10h]
0x18050155d  movsd   [rsp+1F0h+var_1A0], xmm1
0x180501563  lea     r8, [rsp+1F0h+pvargDest+8]
0x180501568  lea     rdx, aOrientation; "Orientation"
0x18050156f  mov     rax, [rax+68h]
0x180501573  call    cs:__guard_dispatch_icall_fptr
0x180501579  test    eax, eax
0x18050157b  js      loc_180501B45
0x180501581  mov     [rbp+0F0h+var_160], esi
0x180501584  mov     qword ptr [rbp+0F0h+rgsabound.cElements], 3
0x18050158f  mov     ecx, 5; vt
0x180501594  lea     r8, [rbp+0F0h+rgsabound]; rgsabound
0x18050159b  mov     edx, esi; cDims
0x18050159d  call    cs:__imp_SafeArrayCreate
0x1805015a3  mov     rbx, rax
0x1805015a6  mov     [rbp+0F0h+var_58], rax
0x1805015ad  test    rax, rax
0x1805015b0  jnz     short loc_1805015B7
0x1805015b2  mov     eax, r14d
0x1805015b5  jmp     short loc_1805015C0
0x1805015b7  mov     rcx, rbx; psa
0x1805015ba  call    cs:__imp_SafeArrayLock
0x1805015c0  test    eax, eax
0x1805015c2  js      loc_180501AB5
0x1805015c8  test    rbx, rbx
0x1805015cb  jz      loc_180501AC1
0x1805015d1  mov     [rbp+0F0h+rgsabound.cElements], r13d
0x1805015d8  lea     r8, [rbp+0F0h+rgsabound]; plLbound
0x1805015df  mov     edx, esi; nDim
0x1805015e1  mov     rcx, rbx; psa
0x1805015e4  call    cs:__imp_SafeArrayGetLBound
0x1805015ea  test    eax, eax
0x1805015ec  js      loc_180501ACC
0x1805015f2  cmp     [rbp+0F0h+rgsabound.cElements], 2
0x1805015f9  jg      loc_180501B36
0x1805015ff  mov     [rbp+0F0h+plUbound], r13d
0x180501606  lea     r8, [rbp+0F0h+plUbound]; plUbound
0x18050160d  mov     edx, esi; nDim
0x18050160f  mov     rcx, rbx; psa
0x180501612  call    cs:__imp_SafeArrayGetUBound
0x180501618  test    eax, eax
0x18050161a  js      loc_180501AD4
0x180501620  cmp     [rbp+0F0h+plUbound], 2
0x180501627  jl      loc_180501B36
0x18050162d  mov     eax, 2
0x180501632  sub     eax, [rbp+0F0h+rgsabound.cElements]
0x180501638  movsxd  rcx, eax
0x18050163b  mov     rax, [rbx+10h]
0x18050163f  lea     r15, [rax+rcx*8]
0x180501643  mov     [rbp+0F0h+plUbound], r13d
0x18050164a  lea     r8, [rbp+0F0h+plUbound]; plLbound
0x180501651  mov     edx, esi; nDim
0x180501653  mov     rcx, rbx; psa
0x180501656  call    cs:__imp_SafeArrayGetLBound
0x18050165c  test    eax, eax
0x18050165e  js      loc_180501ADC
0x180501664  cmp     [rbp+0F0h+plUbound], esi
0x18050166a  jg      loc_180501B36
0x180501670  mov     [rbp+0F0h+rgsabound.cElements], r13d
0x180501677  lea     r8, [rbp+0F0h+rgsabound]; plUbound
0x18050167e  mov     edx, esi; nDim
0x180501680  mov     rcx, rbx; psa
0x180501683  call    cs:__imp_SafeArrayGetUBound
0x180501689  test    eax, eax
0x18050168b  js      loc_180501AE4
0x180501691  cmp     [rbp+0F0h+rgsabound.cElements], esi
0x180501697  jl      loc_180501B36
0x18050169d  mov     eax, esi
0x18050169f  sub     eax, [rbp+0F0h+plUbound]
0x1805016a5  movsxd  rcx, eax
0x1805016a8  mov     rax, [rbx+10h]
0x1805016ac  lea     r14, [rax+rcx*8]
0x1805016b0  mov     [rsp+1F0h+plLbound], r13d
0x1805016b5  lea     r8, [rsp+1F0h+plLbound]; plLbound
0x1805016ba  mov     edx, esi; nDim
0x1805016bc  mov     rcx, rbx; psa
0x1805016bf  call    cs:__imp_SafeArrayGetLBound
0x1805016c5  test    eax, eax
0x1805016c7  js      loc_180501AEC
0x1805016cd  mov     esi, [rsp+1F0h+plLbound]
0x1805016d1  test    esi, esi
0x1805016d3  jg      loc_180501B36
0x1805016d9  mov     [rbp+0F0h+rgsabound.cElements], r13d
0x1805016e0  lea     r8, [rbp+0F0h+rgsabound]; plUbound
0x1805016e7  mov     edx, 1; nDim
0x1805016ec  mov     rcx, rbx; psa
  ... truncated ...
```
