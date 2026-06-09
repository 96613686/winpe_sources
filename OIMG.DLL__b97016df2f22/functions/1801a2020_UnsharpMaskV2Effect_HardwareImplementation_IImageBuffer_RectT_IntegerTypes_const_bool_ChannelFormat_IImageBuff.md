# UnsharpMaskV2Effect::HardwareImplementation(IImageBuffer *,RectT<IntegerTypes> const &,bool,ChannelFormat,IImageBuffer * *)

- ea: `0x1801a2020`
- end: `0x1801a2de5`
- name: `?HardwareImplementation@UnsharpMaskV2Effect@@AEAAXPEAUIImageBuffer@@AEBU?$RectT@UIntegerTypes@@@@_NW4ChannelFormat@@PEAPEAU2@@Z`
- size: `3525`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1801a1810`

## callees

- `0x18001db0c`
- `0x1801985ac`
- `0x1801a0f98`
- `0x1801a2020`
- `0x1801a2de8`
- `0x1801a30a0`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1801a2990`
- `OLEAUT32!__imp_VariantClear` at `0x1801a29f2`
- `OLEAUT32!__imp_VariantClear` at `0x1801a2a50`
- `OLEAUT32!__imp_VariantClear` at `0x1801a2aba`
- `OLEAUT32!__imp_VariantClear` at `0x1801a2990`
- `OLEAUT32!__imp_VariantClear` at `0x1801a29f2`
- `OLEAUT32!__imp_VariantClear` at `0x1801a2a50`
- `OLEAUT32!__imp_VariantClear` at `0x1801a2aba`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a2538`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a2538`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a2bc0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a2bc0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a260b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a2686`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a2712`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a27ea`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a2879`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a260b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a2686`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a2712`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a27ea`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a2879`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a25de`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a2659`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a26e5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a27bf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a284f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a25de`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a2659`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a26e5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a27bf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a284f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a2554`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a2554`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a2bb3`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a2bb3`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801a28da`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801a28da`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801a28f4`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801a28f4`

## string_xrefs

- `0x1801a29da`: `flAmount`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
HRESULT __fastcall UnsharpMaskV2Effect::HardwareImplementation(
        UnsharpMaskV2Effect *a1,
        __int64 a2,
        __m128i *a3,
        unsigned __int8 a4,
        unsigned int a5,
        _QWORD *a6)
{
  int v6; // r12d
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  HRESULT result; // eax
  int v14; // edi
  __int32 v15; // ebx
  int v16; // r14d
  __int32 v17; // esi
  __int64 v18; // r15
  __int64 v19; // r8
  __int64 v20; // rdx
  int v21; // eax
  UnsharpMaskV2Effect *v22; // r15
  __int64 v23; // rcx
  __int64 (__fastcall *v24)(__int64, __int64, unsigned __int64, _QWORD, _DWORD, _DWORD, int, __int64); // r10
  __int64 v25; // r8
  __int64 v26; // rdx
  _QWORD *v27; // rsi
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  SAFEARRAYBOUND v31; // rdi
  int v32; // eax
  int v33; // eax
  float *v34; // rbx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // r14
  int v39; // eax
  __int64 v40; // rsi
  int v41; // eax
  __int64 v42; // rbx
  int v43; // eax
  int v44; // edx
  int v45; // r8d
  int v46; // r9d
  int v47; // r10d
  int v48; // r11d
  float v49; // xmm7_4
  float v50; // xmm8_4
  SAFEARRAY *v51; // rax
  SAFEARRAY *v52; // rbx
  HRESULT v53; // eax
  LONG v54; // edi
  int GaussianKernelSize; // ecx
  UnsharpMaskV2Effect *v56; // r8
  int v57; // r15d
  int v58; // r13d
  int v59; // r12d
  SAFEARRAY *v60; // rdx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  LONG v63; // edi
  HRESULT v64; // eax
  HRESULT v65; // eax
  LONG v66; // edi
  float v67; // xmm6_4
  HRESULT v68; // eax
  HRESULT v69; // eax
  float v70; // xmm7_4
  int v71; // r12d
  LONG v72; // edi
  LONG v73; // r15d
  HRESULT v74; // eax
  HRESULT v75; // eax
  HRESULT v76; // eax
  HRESULT v77; // eax
  __int64 *v78; // rdi
  __int64 (__fastcall *v79)(__int64 *, const wchar_t *, VARIANTARG *); // r15
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v82; // edi
  __int64 v83; // rax
  UnsharpMaskV2Effect *v84; // r15
  LONG v85; // xmm0_4
  int v86; // edi
  __int64 v87; // rax
  LONG v88; // xmm0_4
  int v89; // edi
  float v90; // xmm0_4
  __int64 v91; // rax
  int v92; // edi
  int v93; // eax
  const wchar_t *v94; // rdx
  int v95; // eax
  int v96; // eax
  _QWORD *v97; // rdx
  LONG plUbound; // [rsp+58h] [rbp-B0h] BYREF
  LONG plLbound; // [rsp+5Ch] [rbp-ACh] BYREF
  LONG v100[2]; // [rsp+60h] [rbp-A8h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+68h] [rbp-A0h] BYREF
  __int64 *pvt; // [rsp+70h] [rbp-98h] BYREF
  VARIANTARG pvt_8; // [rsp+78h] [rbp-90h] BYREF
  __int64 v104; // [rsp+90h] [rbp-78h] BYREF
  float *v105; // [rsp+98h] [rbp-70h] BYREF
  __int64 v106; // [rsp+A0h] [rbp-68h] BYREF
  UnsharpMaskV2Effect *v107; // [rsp+A8h] [rbp-60h]
  SAFEARRAY *ppsaOut; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v109; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v110; // [rsp+C0h] [rbp-48h] BYREF
  __int64 (__fastcall *v111)(__int64, _QWORD, unsigned __int64, _QWORD, _DWORD, _DWORD, int, __int64 *); // [rsp+C8h] [rbp-40h] BYREF
  __m128i v112; // [rsp+D0h] [rbp-38h]
  VARIANTARG v113; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v114; // [rsp+108h] [rbp+0h] BYREF
  __int64 v115; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v116[24]; // [rsp+118h] [rbp+10h] BYREF
  int v117; // [rsp+130h] [rbp+28h]
  __int128 v118; // [rsp+138h] [rbp+30h] BYREF
  __int64 v119; // [rsp+148h] [rbp+40h]
  int v120; // [rsp+150h] [rbp+48h]
  __int128 v121; // [rsp+158h] [rbp+50h] BYREF
  __int64 v122; // [rsp+168h] [rbp+60h]
  int v123; // [rsp+170h] [rbp+68h]

  v6 = a4;
  v107 = a1;
  v110 = (__int64)a6;
  pvt = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD *, __int64 **))(**((_QWORD **)a1 + 16) + 168LL))(*((_QWORD **)a1 + 16), &pvt);
  if ( v9 < 0 )
    ATL::BaseAtlThrow(v9);
  memset(v116, 0, sizeof(v116));
  v117 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 56LL))(a2, v116);
  if ( v10 < 0 )
    ATL::BaseAtlThrow(v10);
  *(_QWORD *)&pvt_8.vt = *(_QWORD *)&v116[12];
  v11 = *(int *)&v116[12] + (__int64)*(int *)&v116[20];
  if ( (unsigned __int64)(v11 + 0x80000000LL) > 0xFFFFFFFF
    || (v12 = *(int *)&v116[16] + (__int64)v117,
        result = v12 + 0x80000000,
        (unsigned __int64)(v12 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  v112 = *a3;
  v14 = _mm_cvtsi128_si32(v112);
  if ( v14 <= *(int *)&v116[12] )
    v14 = *(_DWORD *)&v116[12];
  v112.m128i_i32[0] = v14;
  v15 = v112.m128i_i32[1];
  if ( v112.m128i_i32[1] <= *(int *)&v116[16] )
    v15 = *(_DWORD *)&v116[16];
  v112.m128i_i32[1] = v15;
  v16 = v112.m128i_i32[2];
  if ( v112.m128i_i32[2] >= (int)v11 )
    v16 = *(_DWORD *)&v116[12] + *(_DWORD *)&v116[20];
  v17 = v112.m128i_i32[3];
  if ( v112.m128i_i32[3] >= (int)v12 )
    v17 = *(_DWORD *)&v116[16] + v117;
  if ( v14 > v16 || v15 > v17 )
  {
    v17 = 0;
    v16 = 0;
    v15 = 0;
    v112.m128i_i64[0] = 0;
    v14 = 0;
  }
  if ( v14 >= v16 || v15 >= v17 )
  {
    *a6 = 0;
    goto LABEL_126;
  }
  v109 = 0;
  v18 = *((_QWORD *)v107 + 16);
  v111 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64, _QWORD, _DWORD, _DWORD, int, __int64 *))(*(_QWORD *)v18 + 248LL);
  v19 = (int)v12 - (__int64)*(int *)&v116[16];
  if ( (unsigned __int64)(v19 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_162;
  v20 = (int)v11 - (__int64)*(int *)&v116[12];
  if ( (unsigned __int64)(v20 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_162;
  rgsabound = (SAFEARRAYBOUND)__PAIR64__(v19, v20);
  v21 = v111(v18, *(_QWORD *)&pvt_8.vt, __PAIR64__(v19, v20), a5, 0, *(_DWORD *)&v116[8], v6, &v109);
  if ( v21 < 0 )
    ATL::BaseAtlThrow(v21);
  v22 = v107;
  v23 = *((_QWORD *)v107 + 16);
  v24 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int64, _QWORD, _DWORD, _DWORD, int, __int64))(*(_QWORD *)v23 + 248LL);
  v25 = v17 - (__int64)v15;
  if ( (unsigned __int64)(v25 + 0x80000000LL) > 0xFFFFFFFF
    || (v26 = v16 - (__int64)v14, (unsigned __int64)(v26 + 0x80000000LL) > 0xFFFFFFFF) )
  {
LABEL_162:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  rgsabound = (SAFEARRAYBOUND)__PAIR64__(v25, v26);
  v27 = (_QWORD *)v110;
  v28 = v24(v23, v112.m128i_i64[0], __PAIR64__(v25, v26), a5, 0, *(_DWORD *)&v116[8], v6, v110);
  if ( v28 < 0 )
    ATL::BaseAtlThrow(v28);
  v106 = 0;
  rgsabound = 0;
  UnsharpMaskV2Effect::LockAndGetTexture(v29, a2, 0, &v106, &rgsabound);
  v104 = 0;
  v105 = 0;
  UnsharpMaskV2Effect::LockAndGetTexture(v30, v109, 1, &v104, &v105);
  v31 = rgsabound;
  v32 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const wchar_t *, SAFEARRAYBOUND))(*pvt + 112))(
          pvt,
          0,
          L"Input0",
          rgsabound);
  if ( v32 < 0 )
    ATL::BaseAtlThrow(v32);
  v33 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *))(*pvt + 88))(pvt, L"UnsharpMaskRgbToYcc");
  if ( v33 < 0 )
    ATL::BaseAtlThrow(v33);
  v34 = v105;
  v35 = (*(__int64 (__fastcall **)(__int64 *, float *))(*pvt + 120))(pvt, v105);
  if ( v35 < 0 )
    ATL::BaseAtlThrow(v35);
  if ( v34 )
    (*(void (__fastcall **)(float *))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v104 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
  if ( v31 )
    (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v31 + 16LL))(v31);
  v36 = v106;
  if ( v106 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
  v111 = 0;
  v114 = 0;
  UnsharpMaskV2Effect::LockAndGetTexture(v36, v109, 0, &v111, &v114);
  v110 = 0;
  v115 = 0;
  UnsharpMaskV2Effect::LockAndGetTexture(v37, *v27, 1, &v110, &v115);
  v118 = 0;
  v119 = 0;
  v120 = 0;
  v121 = 0;
  v122 = 0;
  v123 = 0;
  v38 = v114;
  v39 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v114 + 80LL))(v114, &v118);
  if ( v39 < 0 )
    ATL::BaseAtlThrow(v39);
  v40 = v115;
  v41 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v115 + 80LL))(v115, &v121);
  if ( v41 < 0 )
    ATL::BaseAtlThrow(v41);
  if ( (unsigned __int64)(SHIDWORD(v118) + (__int64)SHIDWORD(v119) + 0x80000000LL) > 0xFFFFFFFF
    || (unsigned __int64)((int)v119 + (__int64)v120 + 0x80000000LL) > 0xFFFFFFFF
    || (unsigned __int64)(SHIDWORD(v121) + (__int64)SHIDWORD(v122) + 0x80000000LL) > 0xFFFFFFFF
    || (v42 = (int)v122 + (__int64)v123, (unsigned __int64)(v42 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  v43 = (int)UnsharpMaskV2Effect::GetGaussianKernelSize(v22) >> 1;
  if ( v48 - (_DWORD)v119 != v43 || v46 - HIDWORD(v118) != v43 || v44 - v47 != v43 || v45 - (_DWORD)v42 != v43 )
    ATL::BaseAtlThrow(-2045378033);
  v49 = 1.0 / (float)*(int *)&v116[20];
  v50 = 1.0 / (float)v117;
  rgsabound = (SAFEARRAYBOUND)75LL;
  v51 = SafeArrayCreate(4u, 1u, &rgsabound);
  v52 = v51;
  v112.m128i_i64[0] = (__int64)v51;
  if ( v51 )
    v53 = SafeArrayLock(v51);
  else
    v53 = -2147024882;
  if ( v53 < 0 )
    ATL::BaseAtlThrow(v53);
  v54 = 0;
  GaussianKernelSize = UnsharpMaskV2Effect::GetGaussianKernelSize(v107);
  LODWORD(v106) = GaussianKernelSize;
  v57 = GaussianKernelSize >> 1;
  v58 = -(GaussianKernelSize >> 1);
  v59 = v58;
  if ( v58 <= GaussianKernelSize >> 1 )
  {
    v60 = (SAFEARRAY *)-(__int64)v57;
    *(_QWORD *)&pvt_8.vt = v60;
    rgsabound = (SAFEARRAYBOUND)((char *)v56 + 4 * v58 + 4 * v57 + 168);
    while ( 1 )
    {
      v100[0] = v58;
      ppsaOut = v60;
      v105 = (float *)((char *)v56 + 168);
      do
      {
        if ( !v52 )
          goto LABEL_145;
        plLbound = 0;
        LBound = SafeArrayGetLBound(v52, 1u, &plLbound);
        if ( LBound < 0 )
          ATL::BaseAtlThrow(LBound);
        if ( v54 < plLbound )
          goto LABEL_143;
        plUbound = 0;
        UBound = SafeArrayGetUBound(v52, 1u, &plUbound);
        if ( UBound < 0 )
          ATL::BaseAtlThrow(UBound);
        if ( v54 > plUbound )
          goto LABEL_143;
        *((float *)v52->pvData + v54 - plLbound) = (float)v100[0] * v49;
        v63 = v54 + 1;
        plLbound = 0;
        v64 = SafeArrayGetLBound(v52, 1u, &plLbound);
        if ( v64 < 0 )
          ATL::BaseAtlThrow(v64);
        if ( v63 < plLbound )
          goto LABEL_143;
        plUbound = 0;
        v65 = SafeArrayGetUBound(v52, 1u, &plUbound);
        if ( v65 < 0 )
          ATL::BaseAtlThrow(v65);
        if ( v63 > plUbound )
          goto LABEL_143;
        *((float *)v52->pvData + v63 - plLbound) = (float)v59 * v50;
        v66 = v63 + 1;
        v67 = *(float *)rgsabound.cElements * *v105;
        plLbound = 0;
        v68 = SafeArrayGetLBound(v52, 1u, &plLbound);
        if ( v68 < 0 )
          ATL::BaseAtlThrow(v68);
        if ( v66 < plLbound )
          goto LABEL_143;
        plUbound = 0;
        v69 = SafeArrayGetUBound(v52, 1u, &plUbound);
        if ( v69 < 0 )
          ATL::BaseAtlThrow(v69);
        if ( v66 > plUbound )
LABEL_143:
          ATL::BaseAtlThrow(-2147024809);
        *((float *)v52->pvData + v66 - plLbound) = v67;
        v54 = v66 + 1;
        ++v100[0];
        ppsaOut = (SAFEARRAY *)((char *)ppsaOut + 1);
        ++v105;
      }
      while ( (__int64)ppsaOut <= v57 );
      ++v59;
      *(_QWORD *)&rgsabound += 4LL;
      if ( v59 > v57 )
        break;
      v60 = *(SAFEARRAY **)&pvt_8.vt;
      v56 = v107;
    }
    GaussianKernelSize = v106;
  }
  v70 = 0.0;
  v71 = 3 * GaussianKernelSize * GaussianKernelSize;
  v72 = 2;
  if ( v71 > 0 )
  {
    v73 = 2;
    while ( v52 )
    {
      v100[0] = 0;
      v74 = SafeArrayGetLBound(v52, 1u, v100);
      if ( v74 < 0 )
        ATL::BaseAtlThrow(v74);
      if ( v73 < v100[0] )
        goto LABEL_143;
      plUbound = 0;
      v75 = SafeArrayGetUBound(v52, 1u, &plUbound);
      if ( v75 < 0 )
        ATL::BaseAtlThrow(v75);
      if ( v73 > plUbound )
        goto LABEL_143;
      v70 = v70 + *((float *)v52->pvData + v73 - v100[0]);
      v73 += 3;
      if ( v73 - 2 >= v71 )
        goto LABEL_77;
    }
LABEL_145:
    ATL::BaseAtlThrow(-2147467259);
  }
LABEL_77:
  if ( v71 > 0 )
  {
    while ( v52 )
    {
      v100[0] = 0;
      v76 = SafeArrayGetLBound(v52, 1u, v100);
      if ( v76 < 0 )
        ATL::BaseAtlThrow(v76);
      if ( v72 < v100[0] )
        goto LABEL_143;
      plUbound = 0;
      v77 = SafeArrayGetUBound(v52, 1u, &plUbound);
      if ( v77 < 0 )
        ATL::BaseAtlThrow(v77);
      if ( v72 > plUbound )
        goto LABEL_143;
      *((float *)v52->pvData + v72 - v100[0]) = (float)(1.0 / v70) * *((float *)v52->pvData + v72 - v100[0]);
      v72 += 3;
      if ( v72 - 2 >= v71 )
        goto LABEL_84;
    }
    goto LABEL_145;
  }
LABEL_84:
  v78 = pvt;
  v79 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(*pvt + 104);
  if ( !v52 )
  {
    pvt_8.vt = 10;
    pvt_8.lVal = -2147024809;
    ATL::BaseAtlThrow(-2147024809);
  }
  ppsaOut = 0;
  Vartype = SafeArrayCopy(v52, &ppsaOut);
  if ( Vartype < 0 )
    goto LABEL_92;
  Vartype = SafeArrayGetVartype(v52, &pvt_8.vt);
  vt = pvt_8.vt;
  if ( Vartype >= 0 && pvt_8.vt == 13 && (v52->fFeatures & 0x440) == 0x440 )
    vt = 9;
  if ( Vartype < 0 )
  {
LABEL_92:
    pvt_8.lVal = Vartype;
    pvt_8.vt = 10;
  }
  else
  {
    pvt_8.vt = vt | 0x2000;
    pvt_8.llVal = (LONGLONG)ppsaOut;
  }
  if ( Vartype < 0 )
  {
    if ( Vartype != -2147024882 )
      ATL::BaseAtlThrow(Vartype);
    ATL::BaseAtlThrow(-2147024882);
  }
  v113 = pvt_8;
  v82 = v79(v78, L"afl3OffsetsCoeffs", &v113);
  VariantClear(&pvt_8);
  if ( v82 < 0 )
    ATL::BaseAtlThrow(v82);
  v83 = *pvt;
  v84 = v107;
  v85 = *((_DWORD *)v107 + 36);
  pvt_8.vt = 4;
  pvt_8.lVal = v85;
  v113 = pvt_8;
  v86 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v83 + 104))(pvt, L"flAmount", &v113);
  VariantClear(&pvt_8);
  if ( v86 < 0 )
    ATL::BaseAtlThrow(v86);
  v87 = *pvt;
  v88 = *((_DWORD *)v84 + 38);
  pvt_8.vt = 4;
  pvt_8.lVal = v88;
  v113 = pvt_8;
  v89 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v87 + 104))(pvt, L"flThreshold", &v113);
  VariantClear(&pvt_8);
  if ( v89 < 0 )
    ATL::BaseAtlThrow(v89);
  v90 = *((float *)v84 + 38);
  if ( v90 > 0.0 )
  {
    v91 = *pvt;
    pvt_8.vt = 4;
    pvt_8.fltVal = 1.0 / v90;
    v113 = pvt_8;
    v92 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v91 + 104))(
            pvt,
            L"flThresholdInv",
            &v113);
    VariantClear(&pvt_8);
    if ( v92 <= -1 )
      ATL::BaseAtlThrow(v92);
  }
  v93 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const wchar_t *, __int64))(*pvt + 112))(pvt, 0, L"Input0", v38);
  if ( v93 < 0 )
    ATL::BaseAtlThrow(v93);
  Base::String::String((Base::String *)&v104, L"UnsharpMaskSharpening");
  if ( (_DWORD)v106 == 3 )
  {
    v94 = L"3x3";
    goto LABEL_106;
  }
  if ( (_DWORD)v106 == 5 )
  {
    v94 = L"5x5";
LABEL_106:
    ATL::CSimpleStringT<wchar_t,0>::Append(&v104, v94, 3);
  }
  if ( *((float *)v84 + 38) > 0.0 )
    ATL::CSimpleStringT<wchar_t,0>::Append(&v104, L"Threshold", 9);
  v95 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*pvt + 88))(pvt, v104);
  if ( v95 < 0 )
    ATL::BaseAtlThrow(v95);
  v96 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*pvt + 120))(pvt, v40);
  if ( v96 < 0 )
    ATL::BaseAtlThrow(v96);
  v97 = (_QWORD *)(v104 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v104 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v97 + 8LL))(*v97);
  result = SafeArrayUnlock(v52);
  if ( result >= 0 )
    result = SafeArrayDestroy(v52);
  if ( v40 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v110 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  if ( v38 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v111 )
    result = (*(__int64 (__fastcall **)(__int64 (__fastcall *)(__int64, _QWORD, unsigned __int64, _QWORD, _DWORD, _DWORD, int, __int64 *)))(*(_QWORD *)v111 + 16LL))(v111);
  if ( v109 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
LABEL_126:
  if ( pvt )
    return (*(__int64 (__fastcall **)(__int64 *))(*pvt + 16))(pvt);
  return result;
}

```

## disassembly

```asm
0x1801a2020  mov     rax, rsp
0x1801a2023  push    rbp
0x1801a2024  push    rbx
0x1801a2025  push    rsi
0x1801a2026  push    rdi
0x1801a2027  push    r12
0x1801a2029  push    r13
0x1801a202b  push    r14
0x1801a202d  push    r15
0x1801a202f  lea     rbp, [rax-108h]
0x1801a2036  sub     rsp, 1C8h
0x1801a203d  movaps  xmmword ptr [rax-58h], xmm6
0x1801a2041  movaps  xmmword ptr [rax-68h], xmm7
0x1801a2045  movaps  xmmword ptr [rax-78h], xmm8
0x1801a204a  movaps  xmmword ptr [rax-88h], xmm9
0x1801a2052  mov     rax, cs:__security_cookie
0x1801a2059  xor     rax, rsp
0x1801a205c  mov     [rbp+100h+var_90], rax
0x1801a2060  movzx   r12d, r9b
0x1801a2064  mov     rbx, r8
0x1801a2067  mov     r13, rdx
0x1801a206a  mov     [rbp+100h+var_160], rcx
0x1801a206e  mov     r15, [rbp+100h+arg_28]
0x1801a2075  mov     [rbp+100h+var_148], r15
0x1801a2079  mov     qword ptr [rsp+200h+pvt], 0
0x1801a2082  mov     rcx, [rcx+80h]
0x1801a2089  mov     rax, [rcx]
0x1801a208c  lea     rdx, [rsp+200h+pvt]
0x1801a2091  mov     rax, [rax+0A8h]
0x1801a2098  call    cs:__guard_dispatch_icall_fptr
0x1801a209e  test    eax, eax
0x1801a20a0  js      loc_1801A2CA7
0x1801a20a6  xorps   xmm0, xmm0
0x1801a20a9  xor     eax, eax
0x1801a20ab  movups  [rbp+100h+var_F0], xmm0
0x1801a20af  mov     [rbp+100h+var_E0], rax
0x1801a20b3  mov     [rbp+100h+var_D8], eax
0x1801a20b6  mov     rax, [r13+0]
0x1801a20ba  lea     rdx, [rbp+100h+var_F0]
0x1801a20be  mov     rcx, r13
0x1801a20c1  mov     rax, [rax+38h]
0x1801a20c5  call    cs:__guard_dispatch_icall_fptr
0x1801a20cb  test    eax, eax
0x1801a20cd  js      loc_1801A2C8F
0x1801a20d3  movsxd  r8, dword ptr [rbp+100h+var_F0+0Ch]
0x1801a20d7  mov     dword ptr [rsp+200h+pvt+8], r8d
0x1801a20dc  movsxd  r9, dword ptr [rbp+100h+var_E0]
0x1801a20e0  mov     dword ptr [rsp+200h+pvt+0Ch], r9d
0x1801a20e5  mov     r10, r8
0x1801a20e8  movsxd  rcx, dword ptr [rbp+100h+var_E0+4]
0x1801a20ec  add     rcx, r8
0x1801a20ef  mov     edi, 80000000h
0x1801a20f4  lea     rax, [rcx+rdi]
0x1801a20f8  mov     esi, 0FFFFFFFFh
0x1801a20fd  cmp     rax, rsi
0x1801a2100  ja      loc_1801A2DDF
0x1801a2106  movsxd  rdx, [rbp+100h+var_D8]
0x1801a210a  add     rdx, r9
0x1801a210d  lea     rax, [rdi+rdx]
0x1801a2111  cmp     rax, rsi
0x1801a2114  ja      loc_1801A2DDF
0x1801a211a  movups  xmm0, xmmword ptr [rbx]
0x1801a211d  movups  [rbp+100h+var_138], xmm0
0x1801a2121  movd    edi, xmm0
0x1801a2125  cmp     edi, r8d
0x1801a2128  cmovle  edi, r8d
0x1801a212c  mov     dword ptr [rbp+100h+var_138], edi
0x1801a212f  mov     ebx, dword ptr [rbp+100h+var_138+4]
0x1801a2132  cmp     ebx, r9d
0x1801a2135  cmovle  ebx, r9d
0x1801a2139  mov     dword ptr [rbp+100h+var_138+4], ebx
0x1801a213c  mov     r14d, dword ptr [rbp+100h+var_138+8]
0x1801a2140  cmp     r14d, ecx
0x1801a2143  cmovge  r14d, ecx
0x1801a2147  mov     esi, dword ptr [rbp+100h+var_138+0Ch]
0x1801a214a  cmp     esi, edx
0x1801a214c  cmovge  esi, edx
0x1801a214f  cmp     edi, r14d
0x1801a2152  jg      short loc_1801A2158
0x1801a2154  cmp     ebx, esi
0x1801a2156  jle     short loc_1801A2165
0x1801a2158  xor     esi, esi
0x1801a215a  xor     r14d, r14d
0x1801a215d  xor     ebx, ebx
0x1801a215f  mov     qword ptr [rbp+100h+var_138], rbx
0x1801a2163  xor     edi, edi
0x1801a2165  cmp     edi, r14d
0x1801a2168  jge     loc_1801A2C39
0x1801a216e  cmp     ebx, esi
0x1801a2170  jge     loc_1801A2C39
0x1801a2176  mov     [rbp+100h+var_150], 0
0x1801a217e  mov     r15, [rbp+100h+var_160]
0x1801a2182  mov     r15, [r15+80h]
0x1801a2189  mov     rax, [r15]
0x1801a218c  mov     rax, [rax+0F8h]
0x1801a2193  mov     [rbp+100h+var_140], rax
0x1801a2197  movsxd  r8, edx
0x1801a219a  sub     r8, r9
0x1801a219d  mov     r9d, 80000000h
0x1801a21a3  lea     rax, [r8+r9]
0x1801a21a7  mov     r11d, 0FFFFFFFFh
0x1801a21ad  cmp     rax, r11
0x1801a21b0  ja      loc_1801A2DD5
0x1801a21b6  movsxd  rdx, ecx
0x1801a21b9  sub     rdx, r10
0x1801a21bc  lea     rax, [r9+rdx]
0x1801a21c0  cmp     rax, r11
0x1801a21c3  ja      loc_1801A2DD5
0x1801a21c9  mov     [rsp+200h+rgsabound.cElements], edx
0x1801a21cd  mov     [rsp+200h+rgsabound.lLbound], r8d
0x1801a21d2  lea     rax, [rbp+100h+var_150]
0x1801a21d6  mov     [rsp+200h+var_1C8], rax
0x1801a21db  mov     dword ptr [rsp+200h+var_1D0], r12d
0x1801a21e0  mov     edx, dword ptr [rbp+100h+var_F0+8]
0x1801a21e3  mov     [rsp+200h+var_1D8], edx
0x1801a21e7  mov     [rsp+200h+var_1E0], 0
0x1801a21ef  mov     r9d, [rbp+100h+arg_20]
0x1801a21f6  mov     r8, qword ptr [rsp+200h+rgsabound.cElements]
0x1801a21fb  mov     rdx, qword ptr [rsp+200h+pvt+8]
0x1801a2200  mov     rcx, r15
0x1801a2203  mov     rax, [rbp+100h+var_140]
0x1801a2207  call    cs:__guard_dispatch_icall_fptr
0x1801a220d  test    eax, eax
0x1801a220f  js      loc_1801A2DCD
0x1801a2215  mov     r15, [rbp+100h+var_160]
0x1801a2219  mov     rcx, [r15+80h]
0x1801a2220  mov     rax, [rcx]
0x1801a2223  mov     r10, [rax+0F8h]
0x1801a222a  movsxd  r8, esi
0x1801a222d  movsxd  rax, ebx
0x1801a2230  sub     r8, rax
0x1801a2233  mov     r9d, 80000000h
0x1801a2239  lea     rax, [r8+r9]
0x1801a223d  mov     r11d, 0FFFFFFFFh
0x1801a2243  cmp     rax, r11
0x1801a2246  ja      loc_1801A2DD5
0x1801a224c  movsxd  rax, edi
0x1801a224f  movsxd  rdx, r14d
0x1801a2252  sub     rdx, rax
0x1801a2255  lea     rax, [r9+rdx]
0x1801a2259  cmp     rax, r11
0x1801a225c  ja      loc_1801A2DD5
0x1801a2262  mov     [rsp+200h+rgsabound.cElements], edx
0x1801a2266  mov     [rsp+200h+rgsabound.lLbound], r8d
0x1801a226b  mov     rsi, [rbp+100h+var_148]
0x1801a226f  mov     [rsp+200h+var_1C8], rsi
0x1801a2274  mov     dword ptr [rsp+200h+var_1D0], r12d
0x1801a2279  mov     edx, dword ptr [rbp+100h+var_F0+8]
0x1801a227c  mov     [rsp+200h+var_1D8], edx
0x1801a2280  xor     r12d, r12d
0x1801a2283  mov     [rsp+200h+var_1E0], r12d
0x1801a2288  mov     r9d, [rbp+100h+arg_20]
0x1801a228f  mov     r8, qword ptr [rsp+200h+rgsabound.cElements]
0x1801a2294  mov     rdx, qword ptr [rbp+100h+var_138]
0x1801a2298  mov     rax, r10
0x1801a229b  call    cs:__guard_dispatch_icall_fptr
0x1801a22a1  test    eax, eax
0x1801a22a3  js      loc_1801A2DC5
0x1801a22a9  mov     [rbp+100h+var_168], r12
0x1801a22ad  mov     qword ptr [rsp+200h+rgsabound.cElements], r12
0x1801a22b2  lea     rax, [rsp+200h+rgsabound]
0x1801a22b7  mov     qword ptr [rsp+200h+var_1E0], rax
0x1801a22bc  lea     r9, [rbp+100h+var_168]
0x1801a22c0  xor     r8d, r8d
0x1801a22c3  mov     rdx, r13
0x1801a22c6  call    ?LockAndGetTexture@UnsharpMaskV2Effect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; UnsharpMaskV2Effect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x1801a22cb  mov     [rbp+100h+var_178], r12
0x1801a22cf  mov     [rbp+100h+var_170], r12
0x1801a22d3  lea     rax, [rbp+100h+var_170]
0x1801a22d7  mov     qword ptr [rsp+200h+var_1E0], rax
0x1801a22dc  lea     r9, [rbp+100h+var_178]
0x1801a22e0  lea     r8d, [r12+1]
0x1801a22e5  mov     rdx, [rbp+100h+var_150]
0x1801a22e9  call    ?LockAndGetTexture@UnsharpMaskV2Effect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; UnsharpMaskV2Effect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x1801a22ee  mov     rcx, qword ptr [rsp+200h+pvt]
0x1801a22f3  mov     rax, [rcx]
0x1801a22f6  mov     rdi, qword ptr [rsp+200h+rgsabound.cElements]
0x1801a22fb  mov     r9, rdi
0x1801a22fe  lea     r8, aInput0_0; "Input0"
0x1801a2305  xor     edx, edx
0x1801a2307  mov     rax, [rax+70h]
0x1801a230b  call    cs:__guard_dispatch_icall_fptr
0x1801a2311  test    eax, eax
0x1801a2313  js      loc_1801A2DB9
0x1801a2319  mov     rcx, qword ptr [rsp+200h+pvt]
0x1801a231e  mov     rax, [rcx]
0x1801a2321  lea     rdx, aUnsharpmaskrgb; "UnsharpMaskRgbToYcc"
0x1801a2328  mov     rax, [rax+58h]
0x1801a232c  call    cs:__guard_dispatch_icall_fptr
0x1801a2332  test    eax, eax
0x1801a2334  js      loc_1801A2DB1
0x1801a233a  mov     rcx, qword ptr [rsp+200h+pvt]
0x1801a233f  mov     rax, [rcx]
0x1801a2342  mov     rbx, [rbp+100h+var_170]
0x1801a2346  mov     rdx, rbx
0x1801a2349  mov     rax, [rax+78h]
0x1801a234d  call    cs:__guard_dispatch_icall_fptr
0x1801a2353  test    eax, eax
0x1801a2355  js      loc_1801A2DA9
0x1801a235b  test    rbx, rbx
0x1801a235e  jz      short loc_1801A2371
0x1801a2360  mov     rax, [rbx]
0x1801a2363  mov     rcx, rbx
0x1801a2366  mov     rax, [rax+10h]
0x1801a236a  call    cs:__guard_dispatch_icall_fptr
0x1801a2370  nop
0x1801a2371  mov     rcx, [rbp+100h+var_178]
0x1801a2375  test    rcx, rcx
0x1801a2378  jz      short loc_1801A2388
0x1801a237a  mov     rax, [rcx]
0x1801a237d  mov     rax, [rax+10h]
0x1801a2381  call    cs:__guard_dispatch_icall_fptr
0x1801a2387  nop
0x1801a2388  test    rdi, rdi
0x1801a238b  jz      short loc_1801A239E
0x1801a238d  mov     rax, [rdi]
0x1801a2390  mov     rcx, rdi
0x1801a2393  mov     rax, [rax+10h]
0x1801a2397  call    cs:__guard_dispatch_icall_fptr
0x1801a239d  nop
0x1801a239e  mov     rcx, [rbp+100h+var_168]
0x1801a23a2  test    rcx, rcx
0x1801a23a5  jz      short loc_1801A23B4
0x1801a23a7  mov     rax, [rcx]
0x1801a23aa  mov     rax, [rax+10h]
0x1801a23ae  call    cs:__guard_dispatch_icall_fptr
0x1801a23b4  mov     [rbp+100h+var_140], r12
0x1801a23b8  mov     [rbp+100h+var_100], r12
0x1801a23bc  lea     rax, [rbp+100h+var_100]
0x1801a23c0  mov     qword ptr [rsp+200h+var_1E0], rax
0x1801a23c5  lea     r9, [rbp+100h+var_140]
0x1801a23c9  xor     r8d, r8d
0x1801a23cc  mov     rdx, [rbp+100h+var_150]
0x1801a23d0  call    ?LockAndGetTexture@UnsharpMaskV2Effect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; UnsharpMaskV2Effect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x1801a23d5  mov     [rbp+100h+var_148], r12
0x1801a23d9  mov     [rbp+100h+var_F8], r12
0x1801a23dd  lea     rax, [rbp+100h+var_F8]
0x1801a23e1  mov     qword ptr [rsp+200h+var_1E0], rax
0x1801a23e6  lea     r9, [rbp+100h+var_148]
0x1801a23ea  mov     r8d, 1
0x1801a23f0  mov     rdx, [rsi]
0x1801a23f3  call    ?LockAndGetTexture@UnsharpMaskV2Effect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; UnsharpMaskV2Effect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x1801a23f8  xorps   xmm0, xmm0
0x1801a23fb  xor     eax, eax
0x1801a23fd  movups  [rbp+100h+var_D0], xmm0
0x1801a2401  mov     [rbp+100h+var_C0], rax
0x1801a2405  mov     [rbp+100h+var_B8], eax
0x1801a2408  movups  [rbp+100h+var_B0], xmm0
0x1801a240c  mov     [rbp+100h+var_A0], rax
0x1801a2410  mov     [rbp+100h+var_98], eax
0x1801a2413  mov     r14, [rbp+100h+var_100]
0x1801a2417  mov     rax, [r14]
0x1801a241a  lea     rdx, [rbp+100h+var_D0]
0x1801a241e  mov     rcx, r14
0x1801a2421  mov     rax, [rax+50h]
0x1801a2425  call    cs:__guard_dispatch_icall_fptr
0x1801a242b  test    eax, eax
0x1801a242d  js      loc_1801A2D9E
0x1801a2433  mov     rsi, [rbp+100h+var_F8]
0x1801a2437  mov     rax, [rsi]
0x1801a243a  lea     rdx, [rbp+100h+var_B0]
0x1801a243e  mov     rcx, rsi
0x1801a2441  mov     rax, [rax+50h]
0x1801a2445  call    cs:__guard_dispatch_icall_fptr
0x1801a244b  test    eax, eax
0x1801a244d  js      loc_1801A2D96
0x1801a2453  movsxd  rdx, dword ptr [rbp+100h+var_C0+4]
0x1801a2457  movsxd  rax, dword ptr [rbp+100h+var_D0+0Ch]
0x1801a245b  add     rdx, rax
0x1801a245e  mov     ecx, 80000000h
0x1801a2463  lea     rax, [rcx+rdx]
0x1801a2467  mov     edi, 0FFFFFFFFh
0x1801a246c  cmp     rax, rdi
0x1801a246f  ja      loc_1801A2D90
0x1801a2475  movsxd  r8, [rbp+100h+var_B8]
0x1801a2479  movsxd  rax, dword ptr [rbp+100h+var_C0]
0x1801a247d  add     r8, rax
0x1801a2480  lea     rax, [r8+rcx]
0x1801a2484  cmp     rax, rdi
0x1801a2487  ja      loc_1801A2D90
0x1801a248d  movsxd  r10, dword ptr [rbp+100h+var_A0+4]
0x1801a2491  movsxd  r9, dword ptr [rbp+100h+var_B0+0Ch]
0x1801a2495  add     r10, r9
0x1801a2498  lea     rax, [r10+rcx]
0x1801a249c  cmp     rax, rdi
0x1801a249f  ja      loc_1801A2D90
0x1801a24a5  movsxd  rbx, [rbp+100h+var_98]
0x1801a24a9  movsxd  r11, dword ptr [rbp+100h+var_A0]
0x1801a24ad  add     rbx, r11
0x1801a24b0  lea     rax, [rbx+rcx]
0x1801a24b4  cmp     rax, rdi
0x1801a24b7  ja      loc_1801A2D90
0x1801a24bd  mov     rcx, r15; this
0x1801a24c0  call    ?GetGaussianKernelSize@UnsharpMaskV2Effect@@AEAAHXZ; UnsharpMaskV2Effect::GetGaussianKernelSize(void)
0x1801a24c5  sar     eax, 1
0x1801a24c7  sub     r11d, dword ptr [rbp+100h+var_C0]
0x1801a24cb  cmp     r11d, eax
0x1801a24ce  jnz     loc_1801A2D85
0x1801a24d4  sub     r9d, dword ptr [rbp+100h+var_D0+0Ch]
0x1801a24d8  cmp     r9d, eax
  ... truncated ...
```
