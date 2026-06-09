# ProcessedPipelineEffect::WhitePointAutoEyedropper(bool,ATL::CComVariant *)

- ea: `0x1805062f0`
- end: `0x180506cc7`
- name: `?WhitePointAutoEyedropper@ProcessedPipelineEffect@@AEAAX_NPEAVCComVariant@ATL@@@Z`
- size: `2519`
- prototype: `void __fastcall(ProcessedPipelineEffect *__hidden this, bool, struct ATL::CComVariant *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1804ff740`

## callees

- `0x1804c6944`
- `0x1804fc350`
- `0x1804fc448`
- `0x18050608c`
- `0x1805061bc`
- `0x1805062f0`
- `0x18051d85c`
- `0x18056bd00`
- `0x18056d14c`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1805063d0`
- `OLEAUT32!__imp_VariantInit` at `0x1805063e7`
- `OLEAUT32!__imp_VariantInit` at `0x1805063fe`
- `OLEAUT32!__imp_VariantInit` at `0x18050644a`
- `OLEAUT32!__imp_VariantInit` at `0x1805064ea`
- `OLEAUT32!__imp_VariantInit` at `0x180506a49`
- `OLEAUT32!__imp_VariantInit` at `0x1805063d0`
- `OLEAUT32!__imp_VariantInit` at `0x1805063e7`
- `OLEAUT32!__imp_VariantInit` at `0x1805063fe`
- `OLEAUT32!__imp_VariantInit` at `0x18050644a`
- `OLEAUT32!__imp_VariantInit` at `0x1805064ea`
- `OLEAUT32!__imp_VariantInit` at `0x180506a49`
- `OLEAUT32!__imp_VariantClear` at `0x1805064c0`
- `OLEAUT32!__imp_VariantClear` at `0x180506584`
- `OLEAUT32!__imp_VariantClear` at `0x1805065f9`
- `OLEAUT32!__imp_VariantClear` at `0x180506a17`
- `OLEAUT32!__imp_VariantClear` at `0x180506a57`
- `OLEAUT32!__imp_VariantClear` at `0x180506a83`
- `OLEAUT32!__imp_VariantClear` at `0x180506b49`
- `OLEAUT32!__imp_VariantClear` at `0x180506b53`
- `OLEAUT32!__imp_VariantClear` at `0x180506b5d`
- `OLEAUT32!__imp_VariantClear` at `0x180506b67`
- `OLEAUT32!__imp_VariantClear` at `0x1805064c0`
- `OLEAUT32!__imp_VariantClear` at `0x180506584`
- `OLEAUT32!__imp_VariantClear` at `0x1805065f9`
- `OLEAUT32!__imp_VariantClear` at `0x180506a17`
- `OLEAUT32!__imp_VariantClear` at `0x180506a57`
- `OLEAUT32!__imp_VariantClear` at `0x180506a83`
- `OLEAUT32!__imp_VariantClear` at `0x180506b49`
- `OLEAUT32!__imp_VariantClear` at `0x180506b53`
- `OLEAUT32!__imp_VariantClear` at `0x180506b5d`
- `OLEAUT32!__imp_VariantClear` at `0x180506b67`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180506712`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180506712`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180506a2d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180506a2d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506783`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805067f2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506863`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805068d4`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506783`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805067f2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506863`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805068d4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506755`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805067c9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506833`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805068a4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506755`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805067c9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506833`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805068a4`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18050672e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18050672e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180506a20`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180506a20`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180506910`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180506910`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180506924`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180506924`

## string_xrefs

- `0x180506369`: `CompositeSceneEffect`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall ProcessedPipelineEffect::WhitePointAutoEyedropper(
        ProcessedPipelineEffect *this,
        char a2,
        struct ATL::CComVariant *a3)
{
  __int64 *v6; // rdi
  int v7; // eax
  _QWORD *v8; // rsi
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  int v14; // ebx
  int v15; // eax
  __int64 v16; // rax
  int v17; // ebx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // r8
  SAFEARRAY *v23; // rax
  SAFEARRAY *v24; // rbx
  HRESULT v25; // eax
  HRESULT LBound; // eax
  __int64 v27; // r14
  HRESULT UBound; // eax
  HRESULT v29; // eax
  HRESULT v30; // eax
  HRESULT v31; // eax
  HRESULT v32; // eax
  HRESULT v33; // eax
  HRESULT v34; // eax
  HRESULT Vartype; // ecx
  SHORT iVal; // dx
  __int64 *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // rax
  int v42; // eax
  LONG plLbound; // [rsp+48h] [rbp-C0h] BYREF
  VARIANTARG v44; // [rsp+50h] [rbp-B8h] BYREF
  IRecordInfo *pRecInfo; // [rsp+68h] [rbp-A0h]
  SAFEARRAYBOUND rgsabound; // [rsp+78h] [rbp-90h] BYREF
  _QWORD *v47; // [rsp+80h] [rbp-88h] BYREF
  __int64 v48; // [rsp+88h] [rbp-80h] BYREF
  __int128 v49; // [rsp+98h] [rbp-70h] BYREF
  IRecordInfo *v50; // [rsp+A8h] [rbp-60h]
  __int64 v51; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v53; // [rsp+C8h] [rbp-40h]
  __int64 v54; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v55; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG v56; // [rsp+F0h] [rbp-18h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+0h] BYREF
  VARIANTARG v58; // [rsp+120h] [rbp+18h] BYREF
  __int64 *v59; // [rsp+138h] [rbp+30h]
  _QWORD *v60; // [rsp+140h] [rbp+38h]
  SAFEARRAY *v61; // [rsp+148h] [rbp+40h]
  _BYTE v62[112]; // [rsp+158h] [rbp+50h] BYREF

  v6 = (__int64 *)*((_QWORD *)this + 16);
  v59 = v6;
  if ( v6 )
    (*(void (__fastcall **)(__int64 *))(*v6 + 8))(v6);
  v47 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD **))(**((_QWORD **)this + 18) + 152LL))(
         *((_QWORD *)this + 18),
         L"CompositeSceneEffect",
         &v47);
  if ( v7 < 0 )
    ATL::BaseAtlThrow(v7);
  if ( !v47 )
    ATL::BaseAtlThrow(-2045247222);
  (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
  v8 = v47;
  v60 = v47;
  if ( v47 )
    (*(void (__fastcall **)(_QWORD *))(*v47 + 8LL))(v47);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  memset(&v56, 0, sizeof(v56));
  VariantInit(&v56);
  memset(&v55, 0, sizeof(v55));
  VariantInit(&v55);
  memset_0(v62, 0, 0x68u);
  ProcessedPipelineEffect::SaveCurrentSceneSettings(this, (struct SceneSettings *)v62);
  ProcessedPipelineEffect::SetSceneSettings(this, (const struct SceneSettings *)qword_180601E80);
  if ( a2 )
  {
    *(_OWORD *)&v44.decVal.Lo32 = 0;
    pRecInfo = 0;
    VariantInit((VARIANTARG *)&v44.decVal.8);
    v9 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, CY *))(*v6 + 96))(v6, L"D65WhiteBalance", &v44.cyVal);
    if ( v9 < 0 )
      ATL::BaseAtlThrow(v9);
    v10 = *v6;
    v49 = *(_OWORD *)&v44.decVal.Lo32;
    v50 = pRecInfo;
    v11 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int128 *))(v10 + 104))(v6, L"WhiteBalance", &v49);
    if ( v11 < 0 )
      ATL::BaseAtlThrow(v11);
    VariantClear((VARIANTARG *)&v44.decVal.8);
  }
  ProcessedPipelineEffect::GetRawSceneEffectProperty(this, L"DestinationColorProfile", &v56);
  memset(&v58, 0, sizeof(v58));
  VariantInit(&v58);
  *(_OWORD *)&v44.decVal.Lo32 = *(_OWORD *)&v58.vt;
  pRecInfo = v58.pRecInfo;
  ProcessedPipelineEffect::SetRawSceneEffectProperty(
    this,
    L"DestinationColorProfile",
    (struct tagVARIANT *)&v44.decVal.8);
  v12 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, VARIANTARG *))(*v6 + 96))(
          v6,
          L"PostProcessingEnabled",
          &pvarg);
  if ( v12 < 0 )
    ATL::BaseAtlThrow(v12);
  v13 = *v6;
  v44.iVal = 11;
  *((_WORD *)&v44.decVal + 8) = 0;
  v49 = *(_OWORD *)&v44.decVal.Lo32;
  v50 = pRecInfo;
  v14 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, __int128 *))(v13 + 104))(
          v6,
          L"PostProcessingEnabled",
          &v49);
  VariantClear((VARIANTARG *)&v44.decVal.8);
  if ( v14 < 0 )
    ATL::BaseAtlThrow(v14);
  v15 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, VARIANTARG *))(*v6 + 96))(
          v6,
          L"SceneProcessingEnabled",
          &v55);
  if ( v15 < 0 )
    ATL::BaseAtlThrow(v15);
  v16 = *v6;
  v44.iVal = 11;
  *((_WORD *)&v44.decVal + 8) = -1;
  v49 = *(_OWORD *)&v44.decVal.Lo32;
  v50 = pRecInfo;
  v17 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, __int128 *))(v16 + 104))(
          v6,
          L"SceneProcessingEnabled",
          &v49);
  VariantClear((VARIANTARG *)&v44.decVal.8);
  if ( v17 < 0 )
    ATL::BaseAtlThrow(v17);
  v54 = 0;
  v48 = 0;
  v18 = (*(__int64 (__fastcall **)(ProcessedPipelineEffect *, __int64, _QWORD, __int64 *, __int64 *, _QWORD))(*(_QWORD *)this + 72LL))(
          this,
          1,
          0,
          &v54,
          &v48,
          *(_QWORD *)&DOUBLE_1_0);
  if ( v18 < 0 )
    ATL::BaseAtlThrow(v18);
  v19 = HIDWORD(v48);
  if ( (int)v48 > SHIDWORD(v48) )
    v19 = v48;
  if ( v19 <= 0 )
    ATL::BaseAtlThrow(-2147467259);
  v52 = 0;
  v51 = 0;
  v20 = (*(__int64 (__fastcall **)(ProcessedPipelineEffect *, __int64, _QWORD, __int64 *, __int64 *, double))(*(_QWORD *)this + 72LL))(
          this,
          1,
          0,
          &v52,
          &v51,
          fmin(640.0 / (double)v19, 1.0));
  if ( v20 < 0 )
    ATL::BaseAtlThrow(v20);
  v53 = 0;
  v21 = (*(__int64 (__fastcall **)(ProcessedPipelineEffect *, __int64, __int64))(*(_QWORD *)this + 112LL))(
          this,
          v52,
          v51);
  if ( v21 < 0 )
    ATL::BaseAtlThrow(v21);
  v49 = 0;
  if ( (unsigned __int8)AutoNeutralPointExtractor::CalculateNeutralPoint(v53, &v49, v22, 0) )
  {
    rgsabound = (SAFEARRAYBOUND)4LL;
    v23 = SafeArrayCreate(4u, 1u, &rgsabound);
    v24 = v23;
    v61 = v23;
    if ( v23 )
      v25 = SafeArrayLock(v23);
    else
      v25 = -2147024882;
    if ( v25 < 0 )
      ATL::BaseAtlThrow(v25);
    if ( !v24 )
      ATL::BaseAtlThrow(-2147467259);
    plLbound = 0;
    LBound = SafeArrayGetLBound(v24, 1u, &plLbound);
    if ( LBound < 0 )
      ATL::BaseAtlThrow(LBound);
    v27 = plLbound;
    if ( plLbound > 0 )
      goto LABEL_91;
    plLbound = 0;
    UBound = SafeArrayGetUBound(v24, 1u, &plLbound);
    if ( UBound < 0 )
      ATL::BaseAtlThrow(UBound);
    if ( plLbound < 0 )
      goto LABEL_91;
    *((_DWORD *)v24->pvData - v27) = v49;
    plLbound = 0;
    v29 = SafeArrayGetLBound(v24, 1u, &plLbound);
    if ( v29 < 0 )
      ATL::BaseAtlThrow(v29);
    if ( plLbound > 1 )
      goto LABEL_91;
    rgsabound.cElements = 0;
    v30 = SafeArrayGetUBound(v24, 1u, (LONG *)&rgsabound);
    if ( v30 < 0 )
      ATL::BaseAtlThrow(v30);
    if ( (int)rgsabound.cElements < 1 )
      goto LABEL_91;
    *((_DWORD *)v24->pvData + 1 - plLbound) = DWORD1(v49);
    plLbound = 0;
    v31 = SafeArrayGetLBound(v24, 1u, &plLbound);
    if ( v31 < 0 )
      ATL::BaseAtlThrow(v31);
    if ( plLbound > 2 )
      goto LABEL_91;
    rgsabound.cElements = 0;
    v32 = SafeArrayGetUBound(v24, 1u, (LONG *)&rgsabound);
    if ( v32 < 0 )
      ATL::BaseAtlThrow(v32);
    if ( (int)rgsabound.cElements < 2 )
      goto LABEL_91;
    *((_DWORD *)v24->pvData + 2 - plLbound) = DWORD2(v49);
    plLbound = 0;
    v33 = SafeArrayGetLBound(v24, 1u, &plLbound);
    if ( v33 < 0 )
      ATL::BaseAtlThrow(v33);
    if ( plLbound > 3 )
      goto LABEL_91;
    rgsabound.cElements = 0;
    v34 = SafeArrayGetUBound(v24, 1u, (LONG *)&rgsabound);
    if ( v34 < 0 )
      ATL::BaseAtlThrow(v34);
    if ( (int)rgsabound.cElements < 3 )
LABEL_91:
      ATL::BaseAtlThrow(-2147024809);
    *((_DWORD *)v24->pvData + 3 - plLbound) = HIDWORD(v49);
    rgsabound = 0;
    Vartype = SafeArrayCopy(v24, (SAFEARRAY **)&rgsabound);
    if ( Vartype < 0 )
      goto LABEL_50;
    Vartype = SafeArrayGetVartype(v24, &v44.uiVal);
    iVal = v44.iVal;
    if ( Vartype >= 0 && v44.iVal == 13 && (v24->fFeatures & 0x440) == 0x440 )
      iVal = 9;
    if ( Vartype < 0 )
    {
LABEL_50:
      *((_DWORD *)&v44.decVal + 4) = Vartype;
      v44.iVal = 10;
    }
    else
    {
      v44.iVal = iVal | 0x2000;
      *((SAFEARRAYBOUND *)&v44.decVal + 2) = rgsabound;
    }
    if ( Vartype < 0 )
    {
      if ( Vartype != -2147024882 )
        ATL::BaseAtlThrow(Vartype);
      ATL::BaseAtlThrow(-2147024882);
    }
    v37 = 0;
    v47 = 0;
    if ( v8 )
    {
      if ( (*(int (__fastcall **)(_QWORD *, GUID *, _QWORD **))*v8)(
             v8,
             &GUID_0d7f0cfd_d49f_428e_8e69_76aa035fc43d,
             &v47) >= 0 )
      {
        v37 = v47;
      }
      else
      {
        v37 = 0;
        v47 = 0;
      }
    }
    v38 = *v37;
    v49 = *(_OWORD *)&v44.decVal.Lo32;
    v50 = pRecInfo;
    (*(void (__fastcall **)(__int64 *, __int64, __int128 *, struct ATL::CComVariant *))(v38 + 56))(v37, 1, &v49, a3);
    if ( v47 )
      (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
    VariantClear((VARIANTARG *)&v44.decVal.8);
    if ( SafeArrayUnlock(v24) >= 0 )
      SafeArrayDestroy(v24);
  }
  else
  {
    *(_OWORD *)&v44.decVal.Lo32 = 0;
    pRecInfo = 0;
    VariantInit((VARIANTARG *)&v44.decVal.8);
    if ( a3 && VariantClear((VARIANTARG *)a3) >= 0 )
    {
      *(_OWORD *)a3 = *(_OWORD *)&v44.decVal.Lo32;
      *((_QWORD *)a3 + 2) = pRecInfo;
      v44.iVal = 0;
    }
    VariantClear((VARIANTARG *)&v44.decVal.8);
  }
  *(_OWORD *)&v44.decVal.Lo32 = *(_OWORD *)&v56.vt;
  pRecInfo = v56.pRecInfo;
  ProcessedPipelineEffect::SetRawSceneEffectProperty(
    this,
    L"DestinationColorProfile",
    (struct tagVARIANT *)&v44.decVal.8);
  v39 = *v6;
  *(_OWORD *)&v44.decVal.Lo32 = *(_OWORD *)&v55.vt;
  pRecInfo = v55.pRecInfo;
  v40 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, CY *))(v39 + 104))(
          v6,
          L"SceneProcessingEnabled",
          &v44.cyVal);
  if ( v40 < 0 )
    ATL::BaseAtlThrow(v40);
  v41 = *v6;
  *(_OWORD *)&v44.decVal.Lo32 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  v42 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, CY *))(v41 + 104))(
          v6,
          L"PostProcessingEnabled",
          &v44.cyVal);
  if ( v42 < 0 )
    ATL::BaseAtlThrow(v42);
  ProcessedPipelineEffect::SetSceneSettings(this, (const struct SceneSettings *)v62);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  VariantClear(&v58);
  VariantClear(&v55);
  VariantClear(&v56);
  VariantClear(&pvarg);
  if ( v8 )
    (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
  (*(void (__fastcall **)(__int64 *))(*v6 + 16))(v6);
}

```

## disassembly

```asm
0x1805062f0  mov     rax, rsp
0x1805062f3  mov     [rax+10h], rbx
0x1805062f7  push    rbp
0x1805062f8  push    rsi
0x1805062f9  push    rdi
0x1805062fa  push    r12
0x1805062fc  push    r13
0x1805062fe  push    r14
0x180506300  push    r15
0x180506302  lea     rbp, [rax-128h]
0x180506309  sub     rsp, 1F0h
0x180506310  movaps  xmmword ptr [rax-48h], xmm6
0x180506314  movaps  xmmword ptr [rax-58h], xmm7
0x180506318  mov     rax, cs:__security_cookie
0x18050631f  xor     rax, rsp
0x180506322  mov     [rbp+120h+var_60], rax
0x180506329  mov     r12, r8
0x18050632c  mov     bl, dl
0x18050632e  mov     r15, rcx
0x180506331  mov     rdi, [rcx+80h]
0x180506338  mov     [rbp+120h+var_F0], rdi
0x18050633c  xor     r13d, r13d
0x18050633f  test    rdi, rdi
0x180506342  jz      short loc_180506355
0x180506344  mov     rax, [rdi]
0x180506347  mov     rcx, rdi
0x18050634a  mov     rax, [rax+8]
0x18050634e  call    cs:__guard_dispatch_icall_fptr
0x180506354  nop
0x180506355  mov     [rsp+220h+var_1A8], r13
0x18050635a  mov     rcx, [r15+90h]
0x180506361  mov     rax, [rcx]
0x180506364  lea     r8, [rsp+220h+var_1A8]
0x180506369  lea     rdx, aCompositescene; "CompositeSceneEffect"
0x180506370  mov     rax, [rax+98h]
0x180506377  call    cs:__guard_dispatch_icall_fptr
0x18050637d  test    eax, eax
0x18050637f  js      loc_180506BE8
0x180506385  mov     rcx, [rsp+220h+var_1A8]
0x18050638a  test    rcx, rcx
0x18050638d  jz      loc_180506BF0
0x180506393  mov     rax, [rcx]
0x180506396  mov     rax, [rax+10h]
0x18050639a  call    cs:__guard_dispatch_icall_fptr
0x1805063a0  mov     rsi, [rsp+220h+var_1A8]
0x1805063a5  mov     [rbp+120h+var_E8], rsi
0x1805063a9  test    rsi, rsi
0x1805063ac  jz      short loc_1805063BF
0x1805063ae  mov     rax, [rsi]
0x1805063b1  mov     rcx, rsi
0x1805063b4  mov     rax, [rax+8]
0x1805063b8  call    cs:__guard_dispatch_icall_fptr
0x1805063be  nop
0x1805063bf  xorps   xmm0, xmm0
0x1805063c2  xor     eax, eax
0x1805063c4  movups  xmmword ptr [rbp+120h+pvarg], xmm0
0x1805063c8  mov     qword ptr [rbp+120h+pvarg+10h], rax
0x1805063cc  lea     rcx, [rbp+120h+pvarg]; pvarg
0x1805063d0  call    cs:__imp_VariantInit
0x1805063d6  xorps   xmm0, xmm0
0x1805063d9  xor     eax, eax
0x1805063db  movups  xmmword ptr [rbp+120h+var_138], xmm0
0x1805063df  mov     qword ptr [rbp+120h+var_138+10h], rax
0x1805063e3  lea     rcx, [rbp+120h+var_138]; pvarg
0x1805063e7  call    cs:__imp_VariantInit
0x1805063ed  xorps   xmm0, xmm0
0x1805063f0  xor     eax, eax
0x1805063f2  movups  xmmword ptr [rbp+120h+var_150], xmm0
0x1805063f6  mov     qword ptr [rbp+120h+var_150+10h], rax
0x1805063fa  lea     rcx, [rbp+120h+var_150]; pvarg
0x1805063fe  call    cs:__imp_VariantInit
0x180506404  xor     edx, edx; Val
0x180506406  lea     r8d, [rdx+68h]; Size
0x18050640a  lea     rcx, [rbp+120h+var_D0]; void *
0x18050640e  call    memset_0
0x180506413  lea     rdx, [rbp+120h+var_D0]; struct SceneSettings *
0x180506417  mov     rcx, r15; this
0x18050641a  call    ?SaveCurrentSceneSettings@ProcessedPipelineEffect@@AEAAXPEAUSceneSettings@@@Z; ProcessedPipelineEffect::SaveCurrentSceneSettings(SceneSettings *)
0x18050641f  lea     rdx, qword_180601E80; struct SceneSettings *
0x180506426  mov     rcx, r15; this
0x180506429  call    ?SetSceneSettings@ProcessedPipelineEffect@@AEAAXAEBUSceneSettings@@@Z; ProcessedPipelineEffect::SetSceneSettings(SceneSettings const &)
0x18050642e  test    bl, bl
0x180506430  jz      loc_1805064C6
0x180506436  xorps   xmm0, xmm0
0x180506439  xor     eax, eax
0x18050643b  movups  xmmword ptr [rsp+220h+var_1D8+8], xmm0
0x180506440  mov     [rsp+220h+var_1C0], rax
0x180506445  lea     rcx, [rsp+220h+var_1D8+8]; pvarg
0x18050644a  call    cs:__imp_VariantInit
0x180506450  nop
0x180506451  nop     dword ptr [rax+00h]
0x180506455  nop     word ptr [rax+rax+00000000h]
0x180506460  mov     rax, [rdi]
0x180506463  lea     r8, [rsp+220h+var_1D8+8]
0x180506468  lea     rdx, aD65whitebalanc; "D65WhiteBalance"
0x18050646f  mov     rcx, rdi
0x180506472  mov     rax, [rax+60h]
0x180506476  call    cs:__guard_dispatch_icall_fptr
0x18050647c  test    eax, eax
0x18050647e  js      loc_180506C17
0x180506484  mov     rax, [rdi]
0x180506487  movups  xmm0, xmmword ptr [rsp+220h+var_1D8+8]
0x18050648c  movaps  [rbp+120h+var_190], xmm0
0x180506490  movsd   xmm1, [rsp+220h+var_1C0]
0x180506496  movsd   [rbp+120h+var_180], xmm1
0x18050649b  lea     r8, [rbp+120h+var_190]
0x18050649f  lea     rdx, aWhitebalance_0; "WhiteBalance"
0x1805064a6  mov     rcx, rdi
0x1805064a9  mov     rax, [rax+68h]
0x1805064ad  call    cs:__guard_dispatch_icall_fptr
0x1805064b3  test    eax, eax
0x1805064b5  js      loc_180506C0F
0x1805064bb  lea     rcx, [rsp+220h+var_1D8+8]; pvarg
0x1805064c0  call    cs:__imp_VariantClear
0x1805064c6  lea     r8, [rbp+120h+var_138]; struct tagVARIANT *
0x1805064ca  lea     rdx, aDestinationcol; "DestinationColorProfile"
0x1805064d1  mov     rcx, r15; this
0x1805064d4  call    ?GetRawSceneEffectProperty@ProcessedPipelineEffect@@AEAAXPEB_WPEAUtagVARIANT@@@Z; ProcessedPipelineEffect::GetRawSceneEffectProperty(wchar_t const *,tagVARIANT *)
0x1805064d9  xorps   xmm0, xmm0
0x1805064dc  xor     eax, eax
0x1805064de  movups  xmmword ptr [rbp+120h+var_108], xmm0
0x1805064e2  mov     qword ptr [rbp+120h+var_108+10h], rax
0x1805064e6  lea     rcx, [rbp+120h+var_108]; pvarg
0x1805064ea  call    cs:__imp_VariantInit
0x1805064f0  nop
0x1805064f1  movups  xmm0, xmmword ptr [rbp+120h+var_108]
0x1805064f5  movaps  xmmword ptr [rsp+220h+var_1D8+8], xmm0
0x1805064fa  movsd   xmm1, qword ptr [rbp+120h+var_108+10h]
0x1805064ff  movsd   [rsp+220h+var_1C0], xmm1
0x180506505  lea     r8, [rsp+220h+var_1D8+8]; struct tagVARIANT
0x18050650a  lea     rdx, aDestinationcol; "DestinationColorProfile"
0x180506511  mov     rcx, r15; this
0x180506514  call    ?SetRawSceneEffectProperty@ProcessedPipelineEffect@@AEAAXPEB_WUtagVARIANT@@@Z; ProcessedPipelineEffect::SetRawSceneEffectProperty(wchar_t const *,tagVARIANT)
0x180506519  mov     rax, [rdi]
0x18050651c  lea     r8, [rbp+120h+pvarg]
0x180506520  lea     rdx, aPostprocessing; "PostProcessingEnabled"
0x180506527  mov     rcx, rdi
0x18050652a  mov     rax, [rax+60h]
0x18050652e  call    cs:__guard_dispatch_icall_fptr
0x180506534  test    eax, eax
0x180506536  js      loc_180506BDD
0x18050653c  mov     rax, [rdi]
0x18050653f  mov     r14d, 0Bh
0x180506545  mov     word ptr [rsp+220h+var_1D8+8], r14w
0x18050654b  mov     word ptr [rsp+220h+var_1D8+10h], r13w
0x180506551  movups  xmm0, xmmword ptr [rsp+220h+var_1D8+8]
0x180506556  movaps  [rbp+120h+var_190], xmm0
0x18050655a  movsd   xmm1, [rsp+220h+var_1C0]
0x180506560  movsd   [rbp+120h+var_180], xmm1
0x180506565  lea     r8, [rbp+120h+var_190]
0x180506569  lea     rdx, aPostprocessing; "PostProcessingEnabled"
0x180506570  mov     rcx, rdi
0x180506573  mov     rax, [rax+68h]
0x180506577  call    cs:__guard_dispatch_icall_fptr
0x18050657d  mov     ebx, eax
0x18050657f  lea     rcx, [rsp+220h+var_1D8+8]; pvarg
0x180506584  call    cs:__imp_VariantClear
0x18050658a  test    ebx, ebx
0x18050658c  js      loc_180506BC7
0x180506592  mov     rax, [rdi]
0x180506595  lea     r8, [rbp+120h+var_150]
0x180506599  lea     rdx, aSceneprocessin; "SceneProcessingEnabled"
0x1805065a0  mov     rcx, rdi
0x1805065a3  mov     rax, [rax+60h]
0x1805065a7  call    cs:__guard_dispatch_icall_fptr
0x1805065ad  test    eax, eax
0x1805065af  js      loc_180506CBF
0x1805065b5  mov     rax, [rdi]
0x1805065b8  mov     word ptr [rsp+220h+var_1D8+8], r14w
0x1805065be  or      ecx, 0FFFFFFFFh
0x1805065c1  mov     word ptr [rsp+220h+var_1D8+10h], cx
0x1805065c6  movups  xmm0, xmmword ptr [rsp+220h+var_1D8+8]
0x1805065cb  movaps  [rbp+120h+var_190], xmm0
0x1805065cf  movsd   xmm1, [rsp+220h+var_1C0]
0x1805065d5  movsd   [rbp+120h+var_180], xmm1
0x1805065da  lea     r8, [rbp+120h+var_190]
0x1805065de  lea     rdx, aSceneprocessin; "SceneProcessingEnabled"
0x1805065e5  mov     rcx, rdi
0x1805065e8  mov     rax, [rax+68h]
0x1805065ec  call    cs:__guard_dispatch_icall_fptr
0x1805065f2  mov     ebx, eax
0x1805065f4  lea     rcx, [rsp+220h+var_1D8+8]; pvarg
0x1805065f9  call    cs:__imp_VariantClear
0x1805065ff  test    ebx, ebx
0x180506601  js      loc_180506CB7
0x180506607  mov     [rbp+120h+var_158], r13
0x18050660b  mov     [rbp+120h+var_1A0], r13
0x18050660f  mov     rax, [r15]
0x180506612  movsd   xmm7, cs:__real@3ff0000000000000
0x18050661a  movsd   [rsp+220h+var_1F8], xmm7
0x180506620  lea     rcx, [rbp+120h+var_1A0]
0x180506624  mov     [rsp+220h+var_200], rcx
0x180506629  lea     r9, [rbp+120h+var_158]
0x18050662d  xor     r8d, r8d
0x180506630  lea     r14d, [r8+1]
0x180506634  mov     edx, r14d
0x180506637  mov     rcx, r15
0x18050663a  mov     rax, [rax+48h]
0x18050663e  call    cs:__guard_dispatch_icall_fptr
0x180506644  test    eax, eax
0x180506646  js      loc_180506CAF
0x18050664c  mov     eax, dword ptr [rbp+120h+var_1A0+4]
0x18050664f  cmp     dword ptr [rbp+120h+var_1A0], eax
0x180506652  cmovg   eax, dword ptr [rbp+120h+var_1A0]
0x180506656  test    eax, eax
0x180506658  jle     loc_180506C01
0x18050665e  movd    xmm0, eax
0x180506662  cvtdq2pd xmm0, xmm0
0x180506666  movsd   xmm6, cs:__real@4084000000000000
0x18050666e  divsd   xmm6, xmm0
0x180506672  minsd   xmm6, xmm7
0x180506676  mov     [rbp+120h+var_168], r13
0x18050667a  mov     [rbp+120h+var_170], r13
0x18050667e  mov     rax, [r15]
0x180506681  movsd   [rsp+220h+var_1F8], xmm6
0x180506687  lea     rcx, [rbp+120h+var_170]
0x18050668b  mov     [rsp+220h+var_200], rcx
0x180506690  lea     r9, [rbp+120h+var_168]
0x180506694  xor     r8d, r8d
0x180506697  mov     edx, r14d
0x18050669a  mov     rcx, r15
0x18050669d  mov     rax, [rax+48h]
0x1805066a1  call    cs:__guard_dispatch_icall_fptr
0x1805066a7  test    eax, eax
0x1805066a9  js      loc_180506CA7
0x1805066af  mov     [rbp+120h+var_160], r13
0x1805066b3  mov     rax, [r15]
0x1805066b6  lea     rcx, [rbp+120h+var_160]
0x1805066ba  mov     [rsp+220h+var_200], rcx
0x1805066bf  movaps  xmm3, xmm6
0x1805066c2  mov     r8, [rbp+120h+var_170]
0x1805066c6  mov     rdx, [rbp+120h+var_168]
0x1805066ca  mov     rcx, r15
0x1805066cd  mov     rax, [rax+70h]
0x1805066d1  call    cs:__guard_dispatch_icall_fptr
0x1805066d7  test    eax, eax
0x1805066d9  js      loc_180506C9C
0x1805066df  xorps   xmm0, xmm0
0x1805066e2  movups  [rbp+120h+var_190], xmm0
0x1805066e6  xor     r9d, r9d
0x1805066e9  xorps   xmm2, xmm2
0x1805066ec  lea     rdx, [rbp+120h+var_190]
0x1805066f0  mov     rcx, [rbp+120h+var_160]
0x1805066f4  call    ?CalculateNeutralPoint@AutoNeutralPointExtractor@@SA_NPEAUIImageBuffer@@PEAUPixel32f@@NW4PixelWorkingSpace@@@Z; AutoNeutralPointExtractor::CalculateNeutralPoint(IImageBuffer *,Pixel32f *,double,PixelWorkingSpace)
0x1805066f9  test    al, al
0x1805066fb  jz      loc_180506A35
0x180506701  lea     ecx, [r14+3]; vt
0x180506705  mov     qword ptr [rsp+220h+rgsabound.cElements], rcx
0x18050670a  lea     r8, [rsp+220h+rgsabound]; rgsabound
0x18050670f  mov     edx, r14d; cDims
0x180506712  call    cs:__imp_SafeArrayCreate
0x180506718  mov     rbx, rax
0x18050671b  mov     [rbp+120h+var_E0], rax
0x18050671f  test    rax, rax
0x180506722  jnz     short loc_18050672B
0x180506724  mov     eax, 8007000Eh
0x180506729  jmp     short loc_180506734
0x18050672b  mov     rcx, rbx; psa
0x18050672e  call    cs:__imp_SafeArrayLock
0x180506734  test    eax, eax
0x180506736  js      loc_180506C22
0x18050673c  test    rbx, rbx
0x18050673f  jz      loc_180506C2D
0x180506745  mov     [rsp+220h+plLbound], r13d
0x18050674a  lea     r8, [rsp+220h+plLbound]; plLbound
0x18050674f  mov     edx, r14d; nDim
0x180506752  mov     rcx, rbx; psa
0x180506755  call    cs:__imp_SafeArrayGetLBound
0x18050675b  test    eax, eax
0x18050675d  js      loc_180506C38
0x180506763  movsxd  r14, [rsp+220h+plLbound]
0x180506768  test    r14d, r14d
0x18050676b  jg      loc_180506C7E
0x180506771  mov     [rsp+220h+plLbound], r13d
0x180506776  lea     r8, [rsp+220h+plLbound]; plUbound
0x18050677b  mov     edx, 1; nDim
0x180506780  mov     rcx, rbx; psa
0x180506783  call    cs:__imp_SafeArrayGetUBound
0x180506789  test    eax, eax
0x18050678b  js      loc_180506C40
0x180506791  cmp     [rsp+220h+plLbound], r13d
0x180506796  jl      loc_180506C7E
0x18050679c  mov     rax, r14
0x18050679f  shl     rax, 2
0x1805067a3  mov     rcx, [rbx+10h]
0x1805067a7  sub     rcx, rax
0x1805067aa  movss   xmm0, dword ptr [rbp+120h+var_190]
0x1805067af  movss   dword ptr [rcx], xmm0
0x1805067b3  mov     [rsp+220h+plLbound], r13d
0x1805067b8  lea     r8, [rsp+220h+plLbound]; plLbound
0x1805067bd  mov     r14d, 1
0x1805067c3  mov     edx, r14d; nDim
0x1805067c6  mov     rcx, rbx; psa
0x1805067c9  call    cs:__imp_SafeArrayGetLBound
0x1805067cf  test    eax, eax
0x1805067d1  js      loc_180506C48
0x1805067d7  cmp     [rsp+220h+plLbound], r14d
0x1805067dc  jg      loc_180506C7E
0x1805067e2  mov     [rsp+220h+rgsabound.cElements], r13d
0x1805067e7  lea     r8, [rsp+220h+rgsabound]; plUbound
  ... truncated ...
```
