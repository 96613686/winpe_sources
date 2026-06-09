# ChromaDenoiseEffect::HardwareImplementation(IImageBuffer *,RectT<IntegerTypes> const &,bool,ChannelFormat,IImageBuffer * *)

- ea: `0x18047854c`
- end: `0x1804793b0`
- name: `?HardwareImplementation@ChromaDenoiseEffect@@AEAAXPEAUIImageBuffer@@AEBU?$RectT@UIntegerTypes@@@@_NW4ChannelFormat@@PEAPEAU2@@Z`
- size: `3684`
- prototype: `__int64 __usercall@<rax>(ChromaDenoiseEffect *this@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180477570`

## callees

- `0x18001db0c`
- `0x1801a2ffc`
- `0x1801a31b8`
- `0x1801e1640`
- `0x18047854c`
- `0x1804793b0`
- `0x1804794dc`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1804788f9`
- `OLEAUT32!__imp_VariantClear` at `0x180478c62`
- `OLEAUT32!__imp_VariantClear` at `0x180478f84`
- `OLEAUT32!__imp_VariantClear` at `0x1804788f9`
- `OLEAUT32!__imp_VariantClear` at `0x180478c62`
- `OLEAUT32!__imp_VariantClear` at `0x180478f84`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180478ad4`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180478df2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180478ad4`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180478df2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180478ce8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180479006`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180478ce8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180479006`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180478b5c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180478e7f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180478b5c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180478e7f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180478b32`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180478e52`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180478b32`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180478e52`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180478af0`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180478e0e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180478af0`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180478e0e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180478cdb`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180478ff9`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180478cdb`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180478ff9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180478bb2`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180478eda`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180478bb2`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180478eda`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180478bcb`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180478eed`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180478bcb`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180478eed`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall ChromaDenoiseEffect::HardwareImplementation(
        ChromaDenoiseEffect *this,
        __int64 a2,
        __m128i *a3,
        char a4,
        unsigned int a5,
        _QWORD *a6)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // rsi
  __int64 v12; // r12
  __int64 v13; // rbx
  __int64 v14; // rdi
  int v15; // edx
  __int32 v16; // ecx
  int v17; // r9d
  __int32 v18; // r8d
  __int64 v19; // r11
  __int64 v20; // r10
  __int64 v21; // rdx
  int v22; // r14d
  int v23; // eax
  __int64 v24; // r10
  __int64 (__fastcall *v25)(__int64, SAFEARRAYBOUND, unsigned __int64, __int64, _DWORD, _DWORD, int, __int64 *); // r11
  __int64 v26; // rdi
  __int64 v27; // rbx
  int v28; // eax
  __int64 *v29; // r10
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rdx
  unsigned int v33; // ebx
  int v34; // xmm6_4
  int v35; // xmm6_4
  int v36; // xmm6_4
  __int64 v37; // rbx
  __int64 (__fastcall *v38)(__int64, const wchar_t *, VARIANTARG *); // rdi
  int v39; // ebx
  __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned __int64 v42; // rdi
  int v43; // eax
  int v44; // eax
  __int64 v45; // rbx
  int v46; // eax
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rdi
  int v50; // eax
  signed int HardwareOffsetTable; // eax
  __int64 v52; // r14
  SAFEARRAY *v53; // rax
  SAFEARRAY *v54; // rbx
  HRESULT v55; // eax
  int v56; // esi
  __int64 v57; // r15
  __int64 v58; // r14
  float v59; // xmm6_4
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  __int64 v62; // rsi
  __int64 (__fastcall *v63)(__int64, const wchar_t *, VARIANTARG *); // r14
  HRESULT v64; // eax
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v67; // esi
  int v68; // eax
  __int64 v69; // r14
  int v70; // eax
  __int64 v71; // rsi
  int v72; // eax
  __int64 v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rsi
  int v76; // eax
  signed int v77; // eax
  __int64 v78; // r12
  LONG v79; // r9d
  SAFEARRAY *v80; // rax
  SAFEARRAY *v81; // rbx
  HRESULT v82; // eax
  int v83; // edi
  __int64 v84; // r13
  __int64 v85; // r12
  float v86; // xmm6_4
  HRESULT v87; // eax
  HRESULT v88; // eax
  __int64 v89; // rdi
  __int64 (__fastcall *v90)(__int64, const wchar_t *, VARIANTARG *); // r12
  HRESULT v91; // eax
  HRESULT v92; // ecx
  VARTYPE v93; // dx
  int v94; // edi
  int v95; // eax
  int v96; // eax
  __int64 v97; // rdi
  int v98; // eax
  SAFEARRAYBOUND v99; // rcx
  __int64 v100; // rcx
  __int64 v101; // rdi
  int v102; // eax
  int v103; // eax
  SAFEARRAYBOUND v104; // rbx
  int v105; // eax
  signed __int32 v106; // eax
  bool v107; // cc
  __int64 result; // rax
  __int64 v109; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 plUbound; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v111; // [rsp+68h] [rbp-A0h]
  SAFEARRAYBOUND rgsabound; // [rsp+70h] [rbp-98h] BYREF
  __int64 v113; // [rsp+78h] [rbp-90h] BYREF
  __int64 plLbound; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v115[2]; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG pvt; // [rsp+98h] [rbp-70h] BYREF
  __int64 v117; // [rsp+B8h] [rbp-50h] BYREF
  SAFEARRAYBOUND v118; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v119; // [rsp+D0h] [rbp-38h] BYREF
  __m128i v120; // [rsp+D8h] [rbp-30h]
  __int64 v121; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD *v122; // [rsp+F0h] [rbp-18h]
  __int64 v123; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+0h] BYREF
  __int128 v125; // [rsp+128h] [rbp+20h] BYREF
  int v126[2]; // [rsp+138h] [rbp+30h]
  int v127; // [rsp+140h] [rbp+38h]
  __int128 v128; // [rsp+148h] [rbp+40h] BYREF
  __int64 v129; // [rsp+158h] [rbp+50h]
  int v130; // [rsp+160h] [rbp+58h]
  float v131[256]; // [rsp+168h] [rbp+60h] BYREF

  LOBYTE(v111) = a4;
  v122 = a6;
  v109 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 16) + 168LL))(*((_QWORD *)this + 16), &v109);
  if ( v9 < 0 )
    ATL::BaseAtlThrow(v9);
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 56LL))(a2, &v128);
  if ( v10 < 0 )
    ATL::BaseAtlThrow(v10);
  v118.cElements = HIDWORD(v128);
  v11 = (int)v129;
  v118.lLbound = v129;
  v12 = SHIDWORD(v128);
  v13 = SHIDWORD(v128) + (__int64)SHIDWORD(v129);
  if ( (unsigned __int64)(v13 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_177;
  v14 = (int)v129 + (__int64)v130;
  if ( (unsigned __int64)(v14 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_177;
  v120 = *a3;
  v15 = _mm_cvtsi128_si32(v120);
  if ( v15 <= SHIDWORD(v128) )
    v15 = HIDWORD(v128);
  v120.m128i_i32[0] = v15;
  v16 = v120.m128i_i32[1];
  if ( v120.m128i_i32[1] <= (int)v129 )
    v16 = v129;
  v120.m128i_i32[1] = v16;
  v17 = v120.m128i_i32[2];
  if ( v120.m128i_i32[2] >= (int)v13 )
    v17 = HIDWORD(v128) + HIDWORD(v129);
  v18 = v120.m128i_i32[3];
  if ( v120.m128i_i32[3] >= (int)v14 )
    v18 = v129 + v130;
  if ( v15 > v17 || v16 > v18 )
  {
    v18 = 0;
    v17 = 0;
    v16 = 0;
    v120.m128i_i64[0] = 0;
    v15 = 0;
  }
  if ( v15 >= v17 || v16 >= v18 )
  {
    result = (__int64)v122;
    *v122 = 0;
    goto LABEL_137;
  }
  v19 = *((_QWORD *)this + 16);
  v115[0] = *(_QWORD *)(*(_QWORD *)v19 + 248LL);
  v20 = v18 - (__int64)v16;
  if ( (unsigned __int64)(v20 + 0x80000000LL) > 0xFFFFFFFF
    || (v21 = v17 - (__int64)v15, (unsigned __int64)(v21 + 0x80000000LL) > 0xFFFFFFFF) )
  {
LABEL_177:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  plUbound = __PAIR64__(v20, v21);
  v22 = (unsigned __int8)v111;
  v23 = ((__int64 (__fastcall *)(__int64, __int64, unsigned __int64, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD *))v115[0])(
          v19,
          v120.m128i_i64[0],
          __PAIR64__(v20, v21),
          a5,
          0,
          DWORD2(v128),
          (unsigned __int8)v111,
          v122);
  if ( v23 < 0 )
    ATL::BaseAtlThrow(v23);
  v119 = 0;
  v24 = *((_QWORD *)this + 16);
  v25 = *(__int64 (__fastcall **)(__int64, SAFEARRAYBOUND, unsigned __int64, __int64, _DWORD, _DWORD, int, __int64 *))(*(_QWORD *)v24 + 248LL);
  v26 = (int)v14 - v11;
  if ( (unsigned __int64)(v26 + 0x80000000LL) > 0xFFFFFFFF
    || (v27 = (int)v13 - v12, (unsigned __int64)(v27 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  plUbound = __PAIR64__(v26, v27);
  v28 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD))v25)(
          v24,
          v118,
          __PAIR64__(v26, v27),
          8,
          0,
          DWORD2(v128),
          v22,
          &v119);
  if ( v28 < 0 )
    ATL::BaseAtlThrow(v28);
  v121 = 0;
  v29 = (__int64 *)*((_QWORD *)this + 16);
  v30 = *v29;
  plUbound = __PAIR64__(v26, v27);
  v31 = (*(__int64 (__fastcall **)(__int64 *, SAFEARRAYBOUND, unsigned __int64, __int64, _DWORD, _DWORD, int, __int64 *))(v30 + 248))(
          v29,
          v118,
          __PAIR64__(v26, v27),
          8,
          0,
          DWORD2(v128),
          v22,
          &v121);
  if ( v31 < 0 )
    ATL::BaseAtlThrow(v31);
  v32 = (unsigned int)(*((int *)this + 41) >> 31);
  LODWORD(v32) = *((_DWORD *)this + 41) % *((_DWORD *)this + 42);
  v33 = 2 * (*((_DWORD *)this + 41) / *((_DWORD *)this + 42)) + 1;
  v123 = ((__int64 (__fastcall *)(void ***, __int64))g_stringCRTMgr[3])(&g_stringCRTMgr, v32) + 24;
  ATL::CStringT<wchar_t,StrTraitBase<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(&v123, L"ChromaDenoise%d", v33);
  v34 = *((_DWORD *)this + 38);
  *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt((char *)this + 144, 0) = v34;
  v35 = *((_DWORD *)this + 39);
  *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt((char *)this + 144, 1) = v35;
  v36 = *((_DWORD *)this + 40);
  *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt((char *)this + 144, 2) = v36;
  v37 = v109;
  v38 = *(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v109 + 104LL);
  pvt = *(VARIANTARG *)ATL::CComVariant::CComVariant(&pvarg.vt, *((SAFEARRAY **)this + 18));
  v39 = v38(v37, L"thresholds", &pvt);
  VariantClear(&pvarg);
  if ( v39 < 0 )
    ATL::BaseAtlThrow(v39);
  v113 = 0;
  plUbound = 0;
  Convolve1DEffect::LockAndGetTexture(v40, a2, 0, &v113, &plUbound);
  rgsabound = 0;
  plLbound = 0;
  Convolve1DEffect::LockAndGetTexture(v41, v119, 1, &rgsabound, &plLbound);
  v42 = plUbound;
  v43 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, unsigned __int64))(*(_QWORD *)v109 + 112LL))(
          v109,
          0,
          L"image",
          plUbound);
  if ( v43 < 0 )
    ATL::BaseAtlThrow(v43);
  v44 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v109 + 88LL))(v109, L"RgbToYC1C2");
  if ( v44 < 0 )
    ATL::BaseAtlThrow(v44);
  v45 = plLbound;
  v46 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v109 + 120LL))(v109, plLbound);
  if ( v46 < 0 )
    ATL::BaseAtlThrow(v46);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( rgsabound )
    (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
  if ( v42 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v42 + 16LL))(v42);
  v47 = v113;
  if ( v113 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
  v115[0] = 0;
  v113 = 0;
  Convolve1DEffect::LockAndGetTexture(v47, v119, 0, v115, &v113);
  v118 = 0;
  v117 = 0;
  Convolve1DEffect::LockAndGetTexture(v48, v121, 1, &v118, &v117);
  v125 = 0;
  *(_QWORD *)v126 = 0;
  v127 = 0;
  v49 = v113;
  v50 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v113 + 80LL))(v113, &v125);
  if ( v50 < 0 )
    ATL::BaseAtlThrow(v50);
  HardwareOffsetTable = ChromaDenoiseEffect::CreateHardwareOffsetTable(this, v126[1], v127, 1, v131);
  v52 = HardwareOffsetTable;
  rgsabound.cElements = HardwareOffsetTable;
  rgsabound.lLbound = 0;
  v53 = SafeArrayCreate(4u, 1u, &rgsabound);
  v54 = v53;
  v120.m128i_i64[0] = (__int64)v53;
  if ( v53 )
    v55 = SafeArrayLock(v53);
  else
    v55 = -2147024882;
  if ( v55 < 0 )
    ATL::BaseAtlThrow(v55);
  v56 = 0;
  v57 = v52;
  if ( (int)v52 > 0 )
  {
    v58 = 0;
    do
    {
      v59 = v131[v58];
      if ( !v54 )
        ATL::BaseAtlThrow(-2147467259);
      LODWORD(plLbound) = 0;
      LBound = SafeArrayGetLBound(v54, 1u, (LONG *)&plLbound);
      if ( LBound < 0 )
        ATL::BaseAtlThrow(LBound);
      if ( v56 < (int)plLbound )
        goto LABEL_146;
      LODWORD(plUbound) = 0;
      UBound = SafeArrayGetUBound(v54, 1u, (LONG *)&plUbound);
      if ( UBound < 0 )
        ATL::BaseAtlThrow(UBound);
      if ( v56 > (int)plUbound )
LABEL_146:
        ATL::BaseAtlThrow(-2147024809);
      *((float *)v54->pvData + v56 - (int)plLbound) = v59;
      ++v56;
      ++v58;
    }
    while ( v58 < v57 );
  }
  v62 = v109;
  v63 = *(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v109 + 104LL);
  if ( !v54 )
  {
    pvt.vt = 10;
    pvt.lVal = -2147024809;
    ATL::BaseAtlThrow(-2147024809);
  }
  rgsabound = 0;
  v64 = SafeArrayCopy(v54, (SAFEARRAY **)&rgsabound);
  Vartype = v64;
  if ( v64 < 0 )
  {
    pvt.lVal = v64;
  }
  else
  {
    Vartype = SafeArrayGetVartype(v54, &pvt.vt);
    vt = pvt.vt;
    if ( Vartype >= 0 && pvt.vt == 13 && (v54->fFeatures & 0x440) == 0x440 )
      vt = 9;
    if ( Vartype >= 0 )
    {
      pvt.vt = vt | 0x2000;
      pvt.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
      goto LABEL_61;
    }
    pvt.lVal = Vartype;
  }
  pvt.vt = 10;
LABEL_61:
  if ( Vartype < 0 )
  {
    if ( Vartype != -2147024882 )
      ATL::BaseAtlThrow(Vartype);
    ATL::BaseAtlThrow(-2147024882);
  }
  pvarg = pvt;
  v67 = v63(v62, L"offsets", &pvarg);
  VariantClear(&pvt);
  if ( v67 < 0 )
    ATL::BaseAtlThrow(v67);
  v68 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)v109 + 112LL))(
          v109,
          0,
          L"image",
          v49);
  if ( v68 < 0 )
    ATL::BaseAtlThrow(v68);
  v69 = v123;
  v70 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v109 + 88LL))(v109, v123);
  if ( v70 < 0 )
    ATL::BaseAtlThrow(v70);
  v71 = v117;
  v72 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v109 + 120LL))(v109, v117);
  if ( v72 < 0 )
    ATL::BaseAtlThrow(v72);
  if ( SafeArrayUnlock(v54) >= 0 )
    SafeArrayDestroy(v54);
  if ( v71 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
  if ( v118 )
    (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v118 + 16LL))(v118);
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  v73 = v115[0];
  if ( v115[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v115[0] + 16LL))(v115[0]);
  rgsabound = 0;
  v115[0] = 0;
  Convolve1DEffect::LockAndGetTexture(v73, v121, 0, &rgsabound, v115);
  v113 = 0;
  v117 = 0;
  Convolve1DEffect::LockAndGetTexture(v74, v119, 1, &v113, &v117);
  v125 = 0;
  *(_QWORD *)v126 = 0;
  v127 = 0;
  v75 = v115[0];
  v76 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v115[0] + 80LL))(v115[0], &v125);
  if ( v76 < 0 )
    ATL::BaseAtlThrow(v76);
  v77 = ChromaDenoiseEffect::CreateHardwareOffsetTable(this, v126[1], v127, 0, v131);
  v78 = v77;
  v118.cElements = v77;
  v118.lLbound = v79;
  v80 = SafeArrayCreate((unsigned __int16)v79 + 4, v79 + 1, &v118);
  v81 = v80;
  v120.m128i_i64[0] = (__int64)v80;
  if ( v80 )
    v82 = SafeArrayLock(v80);
  else
    v82 = -2147024882;
  if ( v82 < 0 )
    ATL::BaseAtlThrow(v82);
  v83 = 0;
  v84 = v78;
  if ( (int)v78 > 0 )
  {
    v85 = 0;
    do
    {
      v86 = v131[v85];
      if ( !v81 )
        ATL::BaseAtlThrow(-2147467259);
      LODWORD(plLbound) = 0;
      v87 = SafeArrayGetLBound(v81, 1u, (LONG *)&plLbound);
      if ( v87 < 0 )
        ATL::BaseAtlThrow(v87);
      if ( v83 < (int)plLbound )
        goto LABEL_151;
      LODWORD(plUbound) = 0;
      v88 = SafeArrayGetUBound(v81, 1u, (LONG *)&plUbound);
      if ( v88 < 0 )
        ATL::BaseAtlThrow(v88);
      if ( v83 > (int)plUbound )
LABEL_151:
        ATL::BaseAtlThrow(-2147024809);
      *((float *)v81->pvData + v83 - (int)plLbound) = v86;
      ++v83;
      ++v85;
    }
    while ( v85 < v84 );
  }
  v89 = v109;
  v90 = *(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v109 + 104LL);
  if ( !v81 )
  {
    pvt.vt = 10;
    pvt.lVal = -2147024809;
    ATL::BaseAtlThrow(-2147024809);
  }
  v118 = 0;
  v91 = SafeArrayCopy(v81, (SAFEARRAY **)&v118);
  v92 = v91;
  if ( v91 < 0 )
  {
    pvt.lVal = v91;
    goto LABEL_101;
  }
  v92 = SafeArrayGetVartype(v81, &pvt.vt);
  v93 = pvt.vt;
  if ( v92 >= 0 && pvt.vt == 13 && (v81->fFeatures & 0x440) == 0x440 )
    v93 = 9;
  if ( v92 < 0 )
  {
    pvt.lVal = v92;
LABEL_101:
    pvt.vt = 10;
    goto LABEL_102;
  }
  pvt.vt = v93 | 0x2000;
  pvt.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)v118;
LABEL_102:
  if ( v92 < 0 )
  {
    if ( v92 != -2147024882 )
      ATL::BaseAtlThrow(v92);
    ATL::BaseAtlThrow(-2147024882);
  }
  pvarg = pvt;
  v94 = v90(v89, L"offsets", &pvarg);
  VariantClear(&pvt);
  if ( v94 < 0 )
    ATL::BaseAtlThrow(v94);
  v95 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)v109 + 112LL))(
          v109,
          0,
          L"image",
          v75);
  if ( v95 < 0 )
    ATL::BaseAtlThrow(v95);
  v96 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v109 + 88LL))(v109, v69);
  if ( v96 < 0 )
    ATL::BaseAtlThrow(v96);
  v97 = v117;
  v98 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v109 + 120LL))(v109, v117);
  if ( v98 < 0 )
    ATL::BaseAtlThrow(v98);
  if ( SafeArrayUnlock(v81) >= 0 )
    SafeArrayDestroy(v81);
  if ( v97 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
  if ( v113 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
  if ( v75 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
  v99 = rgsabound;
  if ( rgsabound )
    (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
  v113 = 0;
  v115[0] = 0;
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))Convolve1DEffect::LockAndGetTexture)(
    v99,
    v119,
    0,
    &v113,
    v115);
  v117 = 0;
  v118 = 0;
  Convolve1DEffect::LockAndGetTexture(v100, *v122, 1, &v117, &v118);
  v101 = v115[0];
  v102 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)v109 + 112LL))(
           v109,
           0,
           L"image",
           v115[0]);
  if ( v102 < 0 )
    ATL::BaseAtlThrow(v102);
  v103 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v109 + 88LL))(v109, L"YC1C2ToRgb");
  if ( v103 < 0 )
    ATL::BaseAtlThrow(v103);
  v104 = v118;
  v105 = (*(__int64 (__fastcall **)(__int64, SAFEARRAYBOUND))(*(_QWORD *)v109 + 120LL))(v109, v118);
  if ( v105 < 0 )
    ATL::BaseAtlThrow(v105);
  if ( v104 )
    (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v104 + 16LL))(v104);
  if ( v117 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
  if ( v101 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
  if ( v113 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
  v106 = _InterlockedExchangeAdd((volatile signed __int32 *)(v69 - 24 + 16), 0xFFFFFFFF);
  v107 = v106 <= 1;
  result = (unsigned int)(v106 - 1);
  if ( v107 )
    result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v69 - 24) + 8LL))(*(_QWORD *)(v69 - 24));
  if ( v121 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
  if ( v119 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
LABEL_137:
  if ( v109 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
  return result;
}

```

## disassembly

```asm
0x18047854c  mov     rax, rsp
0x18047854f  push    rbp
0x180478550  push    rbx
0x180478551  push    rsi
0x180478552  push    rdi
0x180478553  push    r12
0x180478555  push    r13
0x180478557  push    r14
0x180478559  push    r15
0x18047855b  lea     rbp, [rax-4C8h]
0x180478562  sub     rsp, 588h
0x180478569  movaps  xmmword ptr [rax-58h], xmm6
0x18047856d  mov     rax, cs:__security_cookie
0x180478574  xor     rax, rsp
0x180478577  mov     [rbp+4C0h+var_60], rax
0x18047857e  mov     byte ptr [rsp+5C0h+var_560], r9b
0x180478583  mov     r14, r8
0x180478586  mov     r15, rdx
0x180478589  mov     r13, rcx
0x18047858c  mov     rax, [rbp+4C0h+arg_28]
0x180478593  mov     [rbp+4C0h+var_4D8], rax
0x180478597  mov     [rsp+5C0h+var_570], 0
0x1804785a0  mov     rcx, [rcx+80h]
0x1804785a7  mov     rax, [rcx]
0x1804785aa  lea     rdx, [rsp+5C0h+var_570]
0x1804785af  mov     rax, [rax+0A8h]
0x1804785b6  call    cs:__guard_dispatch_icall_fptr
0x1804785bc  test    eax, eax
0x1804785be  js      loc_18047923C
0x1804785c4  xorps   xmm0, xmm0
0x1804785c7  xor     eax, eax
0x1804785c9  movups  [rbp+4C0h+var_480], xmm0
0x1804785cd  mov     [rbp+4C0h+var_470], rax
0x1804785d1  mov     [rbp+4C0h+var_468], eax
0x1804785d4  mov     rax, [r15]
0x1804785d7  lea     rdx, [rbp+4C0h+var_480]
0x1804785db  mov     rcx, r15
0x1804785de  mov     rax, [rax+38h]
0x1804785e2  call    cs:__guard_dispatch_icall_fptr
0x1804785e8  test    eax, eax
0x1804785ea  js      loc_180479217
0x1804785f0  movsxd  rcx, dword ptr [rbp+4C0h+var_480+0Ch]
0x1804785f4  mov     [rbp+4C0h+var_508.cElements], ecx
0x1804785f7  movsxd  rsi, dword ptr [rbp+4C0h+var_470]
0x1804785fb  mov     [rbp+4C0h+var_508.lLbound], esi
0x1804785fe  mov     r12, rcx
0x180478601  movsxd  rbx, dword ptr [rbp+4C0h+var_470+4]
0x180478605  add     rbx, rcx
0x180478608  mov     edx, 80000000h
0x18047860d  lea     rax, [rdx+rbx]
0x180478611  mov     r8d, 0FFFFFFFFh
0x180478617  cmp     rax, r8
0x18047861a  ja      loc_1804793AA
0x180478620  movsxd  rdi, [rbp+4C0h+var_468]
0x180478624  add     rdi, rsi
0x180478627  lea     rax, [rdi+rdx]
0x18047862b  cmp     rax, r8
0x18047862e  ja      loc_1804793AA
0x180478634  movups  xmm0, xmmword ptr [r14]
0x180478638  movups  [rbp+4C0h+var_4F0], xmm0
0x18047863c  movd    edx, xmm0
0x180478640  cmp     edx, ecx
0x180478642  cmovle  edx, ecx
0x180478645  mov     dword ptr [rbp+4C0h+var_4F0], edx
0x180478648  mov     ecx, dword ptr [rbp+4C0h+var_4F0+4]
0x18047864b  cmp     ecx, esi
0x18047864d  cmovle  ecx, esi
0x180478650  mov     dword ptr [rbp+4C0h+var_4F0+4], ecx
0x180478653  mov     r9d, dword ptr [rbp+4C0h+var_4F0+8]
0x180478657  cmp     r9d, ebx
0x18047865a  cmovge  r9d, ebx
0x18047865e  mov     r8d, dword ptr [rbp+4C0h+var_4F0+0Ch]
0x180478662  cmp     r8d, edi
0x180478665  cmovge  r8d, edi
0x180478669  cmp     edx, r9d
0x18047866c  jg      short loc_180478673
0x18047866e  cmp     ecx, r8d
0x180478671  jle     short loc_180478681
0x180478673  xor     r8d, r8d
0x180478676  xor     r9d, r9d
0x180478679  xor     ecx, ecx
0x18047867b  mov     qword ptr [rbp+4C0h+var_4F0], rcx
0x18047867f  xor     edx, edx
0x180478681  cmp     edx, r9d
0x180478684  jge     loc_1804791CA
0x18047868a  cmp     ecx, r8d
0x18047868d  jge     loc_1804791CA
0x180478693  mov     r11, [r13+80h]
0x18047869a  mov     rax, [r11]
0x18047869d  mov     rax, [rax+0F8h]
0x1804786a4  mov     [rbp+4C0h+var_540], rax
0x1804786a8  movsxd  r10, r8d
0x1804786ab  movsxd  rax, ecx
0x1804786ae  sub     r10, rax
0x1804786b1  mov     ecx, 80000000h
0x1804786b6  lea     rax, [r10+rcx]
0x1804786ba  mov     r8d, 0FFFFFFFFh
0x1804786c0  cmp     rax, r8
0x1804786c3  ja      loc_1804793AA
0x1804786c9  movsxd  rax, edx
0x1804786cc  movsxd  rdx, r9d
0x1804786cf  sub     rdx, rax
0x1804786d2  lea     rax, [rcx+rdx]
0x1804786d6  cmp     rax, r8
0x1804786d9  ja      loc_1804793AA
0x1804786df  mov     dword ptr [rsp+5C0h+plUbound], edx
0x1804786e3  mov     dword ptr [rsp+5C0h+plUbound+4], r10d
0x1804786e8  movzx   r14d, byte ptr [rsp+5C0h+var_560]
0x1804786ee  mov     rax, [rbp+4C0h+var_4D8]
0x1804786f2  mov     [rsp+38h], rax
0x1804786f7  mov     dword ptr [rsp+5C0h+var_590], r14d
0x1804786fc  mov     ecx, dword ptr [rbp+4C0h+var_480+8]
0x1804786ff  mov     [rsp+5C0h+var_598], ecx
0x180478703  mov     dword ptr [rsp+5C0h+var_5A0], 0
0x18047870b  mov     r9d, [rbp+4C0h+arg_20]
0x180478712  mov     r8, [rsp+5C0h+plUbound]
0x180478717  mov     rdx, qword ptr [rbp+4C0h+var_4F0]
0x18047871b  mov     rcx, r11
0x18047871e  mov     rax, [rbp+4C0h+var_540]
0x180478722  call    cs:__guard_dispatch_icall_fptr
0x180478728  test    eax, eax
0x18047872a  js      loc_1804793A2
0x180478730  mov     [rbp+4C0h+var_4F8], 0
0x180478738  mov     r10, [r13+80h]
0x18047873f  mov     rax, [r10]
0x180478742  mov     r11, [rax+0F8h]
0x180478749  movsxd  rdi, edi
0x18047874c  sub     rdi, rsi
0x18047874f  mov     ecx, 80000000h
0x180478754  lea     rax, [rcx+rdi]
0x180478758  mov     edx, 0FFFFFFFFh
0x18047875d  cmp     rax, rdx
0x180478760  ja      loc_180479399
0x180478766  movsxd  rbx, ebx
0x180478769  sub     rbx, r12
0x18047876c  lea     rax, [rbx+rcx]
0x180478770  cmp     rax, rdx
0x180478773  ja      loc_180479399
0x180478779  mov     dword ptr [rsp+5C0h+plUbound], ebx
0x18047877d  mov     dword ptr [rsp+5C0h+plUbound+4], edi
0x180478781  lea     rax, [rbp+4C0h+var_4F8]
0x180478785  mov     [rsp+38h], rax
0x18047878a  mov     dword ptr [rsp+5C0h+var_590], r14d
0x18047878f  mov     ecx, dword ptr [rbp+4C0h+var_480+8]
0x180478792  mov     [rsp+5C0h+var_598], ecx
0x180478796  xor     r12d, r12d
0x180478799  mov     dword ptr [rsp+5C0h+var_5A0], r12d
0x18047879e  lea     esi, [r12+8]
0x1804787a3  mov     r9d, esi
0x1804787a6  mov     r8, [rsp+5C0h+plUbound]
0x1804787ab  mov     rdx, qword ptr [rbp+4C0h+var_508.cElements]
0x1804787af  mov     rcx, r10
0x1804787b2  mov     rax, r11
0x1804787b5  call    cs:__guard_dispatch_icall_fptr
0x1804787bb  test    eax, eax
0x1804787bd  js      loc_180479391
0x1804787c3  mov     [rbp+4C0h+var_4E0], r12
0x1804787c7  mov     r10, [r13+80h]
0x1804787ce  mov     rax, [r10]
0x1804787d1  mov     dword ptr [rsp+5C0h+plUbound], ebx
0x1804787d5  mov     dword ptr [rsp+5C0h+plUbound+4], edi
0x1804787d9  lea     rcx, [rbp+4C0h+var_4E0]
0x1804787dd  mov     [rsp+38h], rcx
0x1804787e2  mov     dword ptr [rsp+5C0h+var_590], r14d
0x1804787e7  mov     ecx, dword ptr [rbp+4C0h+var_480+8]
0x1804787ea  mov     [rsp+5C0h+var_598], ecx
0x1804787ee  mov     dword ptr [rsp+5C0h+var_5A0], r12d
0x1804787f3  mov     r9d, esi
0x1804787f6  mov     r8, [rsp+5C0h+plUbound]
0x1804787fb  mov     rdx, qword ptr [rbp+4C0h+var_508.cElements]
0x1804787ff  mov     rcx, r10
0x180478802  mov     rax, [rax+0F8h]
0x180478809  call    cs:__guard_dispatch_icall_fptr
0x18047880f  test    eax, eax
0x180478811  js      loc_180479386
0x180478817  mov     eax, [r13+0A4h]
0x18047881e  cdq
0x18047881f  idiv    dword ptr [r13+0A8h]
0x180478826  lea     ebx, ds:1[rax*2]
0x18047882d  mov     rax, cs:?g_stringCRTMgr@@3VCAtlStringMgr@ATL@@A; ATL::CAtlStringMgr g_stringCRTMgr
0x180478834  lea     rcx, ?g_stringCRTMgr@@3VCAtlStringMgr@ATL@@A; ATL::CAtlStringMgr g_stringCRTMgr
0x18047883b  mov     rax, [rax+18h]
0x18047883f  call    cs:__guard_dispatch_icall_fptr
0x180478845  add     rax, 18h
0x180478849  mov     [rbp+4C0h+var_4D0], rax
0x18047884d  mov     r8d, ebx
0x180478850  lea     rdx, aChromadenoiseD; "ChromaDenoise%d"
0x180478857  lea     rcx, [rbp+4C0h+var_4D0]
0x18047885b  call    ?Format@?$CStringT@_WV?$StrTraitBase@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAXPEB_WZZ; ATL::CStringT<wchar_t,StrTraitBase<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(wchar_t const *,...)
0x180478860  movss   xmm6, dword ptr [r13+98h]
0x180478869  lea     rsi, [r13+90h]
0x180478870  xor     edx, edx
0x180478872  mov     rcx, rsi
0x180478875  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x18047887a  movss   dword ptr [rax], xmm6
0x18047887e  movss   xmm6, dword ptr [r13+9Ch]
0x180478887  lea     edx, [r12+1]
0x18047888c  mov     rcx, rsi
0x18047888f  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x180478894  movss   dword ptr [rax], xmm6
0x180478898  movss   xmm6, dword ptr [r13+0A0h]
0x1804788a1  lea     edx, [r12+2]
0x1804788a6  mov     rcx, rsi
0x1804788a9  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1804788ae  movss   dword ptr [rax], xmm6
0x1804788b2  mov     rbx, [rsp+5C0h+var_570]
0x1804788b7  mov     rax, [rbx]
0x1804788ba  mov     rdi, [rax+68h]
0x1804788be  mov     rdx, [rsi]; psa
0x1804788c1  lea     rcx, [rbp+4C0h+pvarg]; pvt
0x1804788c5  call    ??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::CComVariant(tagSAFEARRAY const *)
0x1804788ca  nop
0x1804788cb  movups  xmm0, xmmword ptr [rax]
0x1804788ce  movaps  xmmword ptr [rbp+4C0h+pvt], xmm0
0x1804788d2  movsd   xmm1, qword ptr [rax+10h]
0x1804788d7  movsd   [rbp+4C0h+var_520], xmm1
0x1804788dc  lea     r8, [rbp+4C0h+pvt]
0x1804788e0  lea     rdx, aThresholds; "thresholds"
0x1804788e7  mov     rcx, rbx
0x1804788ea  mov     rax, rdi
0x1804788ed  call    cs:__guard_dispatch_icall_fptr
0x1804788f3  mov     ebx, eax
0x1804788f5  lea     rcx, [rbp+4C0h+pvarg]; pvarg
0x1804788f9  call    cs:__imp_VariantClear
0x1804788ff  test    ebx, ebx
0x180478901  js      loc_18047937B
0x180478907  mov     [rsp+5C0h+var_550], r12
0x18047890c  mov     [rsp+5C0h+plUbound], r12
0x180478911  lea     rax, [rsp+5C0h+plUbound]
0x180478916  mov     [rsp+5C0h+var_5A0], rax
0x18047891b  lea     r9, [rsp+5C0h+var_550]
0x180478920  xor     r8d, r8d
0x180478923  mov     rdx, r15
0x180478926  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x18047892b  mov     qword ptr [rsp+5C0h+rgsabound.cElements], r12
0x180478930  mov     [rsp+5C0h+plLbound], r12
0x180478935  lea     rax, [rsp+5C0h+plLbound]
0x18047893a  mov     [rsp+5C0h+var_5A0], rax
0x18047893f  lea     r9, [rsp+5C0h+rgsabound]
0x180478944  lea     r8d, [r12+1]
0x180478949  mov     rdx, [rbp+4C0h+var_4F8]
0x18047894d  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x180478952  mov     rcx, [rsp+5C0h+var_570]
0x180478957  mov     rax, [rcx]
0x18047895a  mov     rdi, [rsp+5C0h+plUbound]
0x18047895f  mov     r9, rdi
0x180478962  lea     r8, aImage; "image"
0x180478969  xor     edx, edx
0x18047896b  mov     rax, [rax+70h]
0x18047896f  call    cs:__guard_dispatch_icall_fptr
0x180478975  test    eax, eax
0x180478977  js      loc_180479370
0x18047897d  mov     rcx, [rsp+5C0h+var_570]
0x180478982  mov     rax, [rcx]
0x180478985  lea     rdx, aRgbtoyc1c2; "RgbToYC1C2"
0x18047898c  mov     rax, [rax+58h]
0x180478990  call    cs:__guard_dispatch_icall_fptr
0x180478996  test    eax, eax
0x180478998  js      loc_180479368
0x18047899e  mov     rcx, [rsp+5C0h+var_570]
0x1804789a3  mov     rax, [rcx]
0x1804789a6  mov     rbx, [rsp+5C0h+plLbound]
0x1804789ab  mov     rdx, rbx
0x1804789ae  mov     rax, [rax+78h]
0x1804789b2  call    cs:__guard_dispatch_icall_fptr
0x1804789b8  test    eax, eax
0x1804789ba  js      loc_180479360
0x1804789c0  test    rbx, rbx
0x1804789c3  jz      short loc_1804789D6
0x1804789c5  mov     rax, [rbx]
0x1804789c8  mov     rcx, rbx
0x1804789cb  mov     rax, [rax+10h]
0x1804789cf  call    cs:__guard_dispatch_icall_fptr
0x1804789d5  nop
0x1804789d6  mov     rcx, qword ptr [rsp+5C0h+rgsabound.cElements]
0x1804789db  test    rcx, rcx
0x1804789de  jz      short loc_1804789EE
0x1804789e0  mov     rax, [rcx]
0x1804789e3  mov     rax, [rax+10h]
0x1804789e7  call    cs:__guard_dispatch_icall_fptr
0x1804789ed  nop
0x1804789ee  test    rdi, rdi
0x1804789f1  jz      short loc_180478A10
0x1804789f3  mov     rax, [rdi]
0x1804789f6  mov     rcx, rdi
0x1804789f9  mov     rax, [rax+10h]
0x1804789fd  call    cs:__guard_dispatch_icall_fptr
0x180478a03  nop
0x180478a04  nop     dword ptr [rax+00h]
0x180478a08  nop     dword ptr [rax+rax+00000000h]
0x180478a10  mov     rcx, [rsp+5C0h+var_550]
0x180478a15  test    rcx, rcx
0x180478a18  jz      short loc_180478A27
0x180478a1a  mov     rax, [rcx]
0x180478a1d  mov     rax, [rax+10h]
0x180478a21  call    cs:__guard_dispatch_icall_fptr
0x180478a27  mov     [rbp+4C0h+var_540], r12
0x180478a2b  mov     [rsp+5C0h+var_550], r12
0x180478a30  lea     rax, [rsp+5C0h+var_550]
0x180478a35  mov     [rsp+5C0h+var_5A0], rax
  ... truncated ...
```
