# CaptureOneSigmaFilterEffect::HardwareImplementation(IImageBuffer *,RectT<IntegerTypes> const &,bool,ChannelFormat,IImageBuffer * *)

- ea: `0x180484e00`
- end: `0x1804859c1`
- name: `?HardwareImplementation@CaptureOneSigmaFilterEffect@@AEAAXPEAUIImageBuffer@@AEBU?$RectT@UIntegerTypes@@@@_NW4ChannelFormat@@PEAPEAU2@@Z`
- size: `3009`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1804842f0`

## callees

- `0x18001db0c`
- `0x1801e1640`
- `0x1801e8c64`
- `0x180484d60`
- `0x180484e00`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1804852f7`
- `OLEAUT32!__imp_VariantClear` at `0x180485380`
- `OLEAUT32!__imp_VariantClear` at `0x180485675`
- `OLEAUT32!__imp_VariantClear` at `0x1804856fe`
- `OLEAUT32!__imp_VariantClear` at `0x1804852f7`
- `OLEAUT32!__imp_VariantClear` at `0x180485380`
- `OLEAUT32!__imp_VariantClear` at `0x180485675`
- `OLEAUT32!__imp_VariantClear` at `0x1804856fe`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180485169`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804854e8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180485169`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804854e8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180485319`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18048540f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180485697`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18048578d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180485319`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18048540f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180485697`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18048578d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804851e8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180485566`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804851e8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180485566`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804851bf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18048553e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804851bf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18048553e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180485185`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180485504`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180485185`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180485504`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180485308`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180485402`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180485686`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180485780`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180485308`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180485402`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180485686`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180485780`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18048523d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1804855c0`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18048523d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1804855c0`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180485257`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1804855d4`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180485257`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1804855d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CaptureOneSigmaFilterEffect::HardwareImplementation(
        __int64 a1,
        __int64 a2,
        __m128i *a3,
        char a4,
        unsigned int a5,
        _QWORD *a6)
{
  int v8; // eax
  int v9; // eax
  __int64 v10; // rsi
  __int64 v11; // r12
  __int64 v12; // rbx
  __int64 v13; // rdi
  int v14; // edx
  __int32 v15; // ecx
  int v16; // r9d
  int v17; // r8d
  __int64 v18; // r11
  __int64 (__fastcall *v19)(__int64, __int64, unsigned __int64, _QWORD, _DWORD, _DWORD, _DWORD, SAFEARRAYBOUND); // r13
  __int64 v20; // r10
  __int64 v21; // rdx
  int v22; // eax
  CaptureOneSigmaFilterEffect *v23; // r13
  __int64 v24; // rcx
  __int64 (__fastcall *v25)(__int64, _QWORD, unsigned __int64, __int64, _DWORD, _DWORD, _DWORD, __int64 *); // r10
  __int64 v26; // r8
  __int64 v27; // rdx
  int v28; // eax
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  signed int HardwareOffsetTable; // eax
  __int64 v33; // rsi
  SAFEARRAY *v34; // rax
  SAFEARRAY *v35; // rbx
  HRESULT v36; // eax
  int v37; // edi
  __int64 v38; // r14
  __int64 v39; // rsi
  float v40; // xmm6_4
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  __int64 *v43; // rdi
  __int64 (__fastcall *v44)(__int64 *, const wchar_t *, VARIANTARG *); // rsi
  HRESULT v45; // eax
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v48; // edi
  HRESULT v49; // eax
  __int64 v50; // rax
  LONG v51; // xmm0_4
  int v52; // edi
  __int64 v53; // rsi
  int v54; // eax
  int v55; // eax
  __int64 v56; // rdi
  int v57; // eax
  __int64 v58; // rcx
  __int64 v59; // rcx
  signed int v60; // eax
  __int64 v61; // rsi
  SAFEARRAY *v62; // rax
  SAFEARRAY *v63; // rbx
  HRESULT v64; // eax
  int v65; // edi
  __int64 v66; // r12
  __int64 v67; // rsi
  float v68; // xmm6_4
  HRESULT v69; // eax
  HRESULT v70; // eax
  __int64 *v71; // rdi
  __int64 (__fastcall *v72)(__int64 *, const wchar_t *, VARIANTARG *); // rsi
  HRESULT v73; // eax
  HRESULT v74; // ecx
  VARTYPE v75; // dx
  int v76; // edi
  HRESULT v77; // eax
  __int64 v78; // rax
  LONG v79; // xmm0_4
  int v80; // edi
  __int64 v81; // rsi
  int v82; // eax
  int v83; // eax
  __int64 v84; // rdi
  int v85; // eax
  __int64 result; // rax
  SAFEARRAYBOUND rgsabound; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v88; // [rsp+60h] [rbp-A8h]
  __int64 *pvt; // [rsp+68h] [rbp-A0h] BYREF
  VARIANTARG pvt_8; // [rsp+70h] [rbp-98h] BYREF
  LONG plLbound[2]; // [rsp+88h] [rbp-80h] BYREF
  SAFEARRAYBOUND v92; // [rsp+90h] [rbp-78h] BYREF
  __m128i v93; // [rsp+98h] [rbp-70h]
  __int64 v94; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v95; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v96; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v97; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v98[2]; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v99; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v100; // [rsp+F8h] [rbp-10h]
  _BYTE v101[24]; // [rsp+100h] [rbp-8h] BYREF
  int v102; // [rsp+118h] [rbp+10h]
  __int128 v103; // [rsp+120h] [rbp+18h] BYREF
  __int64 v104; // [rsp+130h] [rbp+28h]
  int v105; // [rsp+138h] [rbp+30h]
  float v106[256]; // [rsp+148h] [rbp+40h] BYREF
  wchar_t Buffer[128]; // [rsp+548h] [rbp+440h] BYREF

  LOBYTE(v88) = a4;
  *(_QWORD *)plLbound = a1;
  v92 = (SAFEARRAYBOUND)a6;
  pvt = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**(_QWORD **)(a1 + 128) + 168LL))(*(_QWORD *)(a1 + 128), &pvt);
  if ( v8 < 0 )
    ATL::BaseAtlThrow(v8);
  v100 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  memset(v101, 0, sizeof(v101));
  v102 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 56LL))(a2, v101);
  if ( v9 < 0 )
    ATL::BaseAtlThrow(v9);
  v98[0] = *(_QWORD *)&v101[12];
  v10 = *(int *)&v101[16];
  v11 = *(int *)&v101[12];
  v12 = *(int *)&v101[12] + (__int64)*(int *)&v101[20];
  if ( (unsigned __int64)(v12 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_157;
  v13 = *(int *)&v101[16] + (__int64)v102;
  if ( (unsigned __int64)(v13 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_157;
  v93 = *a3;
  v14 = _mm_cvtsi128_si32(v93);
  if ( v14 <= *(int *)&v101[12] )
    v14 = *(_DWORD *)&v101[12];
  v93.m128i_i32[0] = v14;
  v15 = v93.m128i_i32[1];
  if ( v93.m128i_i32[1] <= *(int *)&v101[16] )
    v15 = *(_DWORD *)&v101[16];
  v93.m128i_i32[1] = v15;
  v16 = v93.m128i_i32[2];
  if ( v93.m128i_i32[2] >= (int)v12 )
    v16 = *(_DWORD *)&v101[12] + *(_DWORD *)&v101[20];
  v17 = v93.m128i_i32[3];
  if ( v93.m128i_i32[3] >= (int)v13 )
    v17 = *(_DWORD *)&v101[16] + v102;
  if ( v14 > v16 || v15 > v17 )
  {
    v17 = 0;
    v16 = 0;
    v15 = 0;
    v14 = 0;
    v93.m128i_i64[0] = 0;
  }
  if ( v14 >= v16 || v15 >= v17 )
  {
    *a6 = 0;
    goto LABEL_122;
  }
  v18 = *(_QWORD *)(*(_QWORD *)plLbound + 128LL);
  v19 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int64, _QWORD, _DWORD, _DWORD, _DWORD, SAFEARRAYBOUND))(*(_QWORD *)v18 + 248LL);
  v20 = v17 - (__int64)v15;
  if ( (unsigned __int64)(v20 + 0x80000000LL) > 0xFFFFFFFF
    || (v21 = v16 - (__int64)v14, (unsigned __int64)(v21 + 0x80000000LL) > 0xFFFFFFFF) )
  {
LABEL_157:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  rgsabound = (SAFEARRAYBOUND)__PAIR64__(v20, v21);
  v22 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD))v19)(
          v18,
          v93.m128i_i64[0],
          __PAIR64__(v20, v21),
          a5,
          0,
          *(_DWORD *)&v101[8],
          (unsigned __int8)v88,
          v92);
  if ( v22 < 0 )
    ATL::BaseAtlThrow(v22);
  v94 = 0;
  v23 = *(CaptureOneSigmaFilterEffect **)plLbound;
  v24 = *(_QWORD *)(*(_QWORD *)plLbound + 128LL);
  v25 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64, __int64, _DWORD, _DWORD, _DWORD, __int64 *))(*(_QWORD *)v24 + 248LL);
  v26 = (int)v13 - v10;
  if ( (unsigned __int64)(v26 + 0x80000000LL) > 0xFFFFFFFF
    || (v27 = (int)v12 - v11, (unsigned __int64)(v27 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  rgsabound = (SAFEARRAYBOUND)__PAIR64__(v26, v27);
  v28 = v25(v24, v98[0], __PAIR64__(v26, v27), 8, 0, *(_DWORD *)&v101[8], (unsigned __int8)v88, &v94);
  if ( v28 < 0 )
    ATL::BaseAtlThrow(v28);
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v29 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v94 + 56LL))(v94, &v103);
  if ( v29 < 0 )
    ATL::BaseAtlThrow(v29);
  StringCchPrintfW(
    Buffer,
    0x80u,
    L"SigmaFilter%d",
    (unsigned int)(2 * (*((_DWORD *)v23 + 36) / *((_DWORD *)v23 + 37)) + 1));
  v98[0] = 0;
  v95 = 0;
  Convolve1DEffect::LockAndGetTexture(v30, a2, 0, v98, &v95);
  v97 = 0;
  v96 = 0;
  Convolve1DEffect::LockAndGetTexture(v31, v94, 1, &v97, &v96);
  HardwareOffsetTable = CaptureOneSigmaFilterEffect::CreateHardwareOffsetTable(v23, *(int *)&v101[20], v102, 0, v106);
  v33 = HardwareOffsetTable;
  rgsabound.cElements = HardwareOffsetTable;
  rgsabound.lLbound = 0;
  v34 = SafeArrayCreate(4u, 1u, &rgsabound);
  v35 = v34;
  v93.m128i_i64[0] = (__int64)v34;
  if ( v34 )
    v36 = SafeArrayLock(v34);
  else
    v36 = -2147024882;
  if ( v36 < 0 )
    ATL::BaseAtlThrow(v36);
  v37 = 0;
  v38 = v33;
  if ( (int)v33 > 0 )
  {
    v39 = 0;
    do
    {
      v40 = v106[v39];
      if ( !v35 )
        ATL::BaseAtlThrow(-2147467259);
      plLbound[0] = 0;
      LBound = SafeArrayGetLBound(v35, 1u, plLbound);
      if ( LBound < 0 )
        ATL::BaseAtlThrow(LBound);
      if ( v37 < plLbound[0] )
        goto LABEL_131;
      rgsabound.cElements = 0;
      UBound = SafeArrayGetUBound(v35, 1u, (LONG *)&rgsabound);
      if ( UBound < 0 )
        ATL::BaseAtlThrow(UBound);
      if ( v37 > (int)rgsabound.cElements )
LABEL_131:
        ATL::BaseAtlThrow(-2147024809);
      *((float *)v35->pvData + v37 - plLbound[0]) = v40;
      ++v37;
      ++v39;
    }
    while ( v39 < v38 );
  }
  v43 = pvt;
  v44 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(*pvt + 104);
  if ( !v35 )
  {
    pvt_8.vt = 10;
    pvt_8.lVal = -2147024809;
    ATL::BaseAtlThrow(-2147024809);
  }
  rgsabound = 0;
  v45 = SafeArrayCopy(v35, (SAFEARRAY **)&rgsabound);
  Vartype = v45;
  if ( v45 < 0 )
  {
    pvt_8.lVal = v45;
  }
  else
  {
    Vartype = SafeArrayGetVartype(v35, &pvt_8.vt);
    vt = pvt_8.vt;
    if ( Vartype >= 0 && pvt_8.vt == 13 && (v35->fFeatures & 0x440) == 0x440 )
      vt = 9;
    if ( Vartype >= 0 )
    {
      pvt_8.vt = vt | 0x2000;
      pvt_8.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
      goto LABEL_50;
    }
    pvt_8.lVal = Vartype;
  }
  pvt_8.vt = 10;
LABEL_50:
  if ( Vartype < 0 )
  {
    if ( Vartype != -2147024882 )
      ATL::BaseAtlThrow(Vartype);
    ATL::BaseAtlThrow(-2147024882);
  }
  v99 = pvt_8;
  v48 = v44(v43, L"offsets", &v99);
  VariantClear(&pvt_8);
  if ( v48 < 0 )
    ATL::BaseAtlThrow(v48);
  v49 = SafeArrayUnlock(v35);
  if ( v49 < 0 )
    goto LABEL_150;
  v49 = SafeArrayDestroy(v35);
  if ( v49 >= 0 )
    v35 = 0;
  v93.m128i_i64[0] = (__int64)v35;
  if ( v49 < 0 )
LABEL_150:
    ATL::BaseAtlThrow(v49);
  v50 = *pvt;
  v51 = *((_DWORD *)v23 + 38);
  pvt_8.vt = 4;
  pvt_8.lVal = v51;
  v99 = pvt_8;
  v52 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v50 + 104))(pvt, L"threshold", &v99);
  VariantClear(&pvt_8);
  if ( v52 < 0 )
    ATL::BaseAtlThrow(v52);
  v53 = v95;
  v54 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const wchar_t *, __int64))(*pvt + 112))(pvt, 0, L"image", v95);
  if ( v54 < 0 )
    ATL::BaseAtlThrow(v54);
  v55 = (*(__int64 (__fastcall **)(__int64 *, wchar_t *))(*pvt + 88))(pvt, Buffer);
  if ( v55 < 0 )
    ATL::BaseAtlThrow(v55);
  v56 = v96;
  v57 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*pvt + 120))(pvt, v96);
  if ( v57 < 0 )
    ATL::BaseAtlThrow(v57);
  if ( v35 && SafeArrayUnlock(v35) >= 0 )
    SafeArrayDestroy(v35);
  if ( v56 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  if ( v97 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  v58 = v98[0];
  if ( v98[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v98[0] + 16LL))(v98[0]);
  v95 = 0;
  v98[0] = 0;
  Convolve1DEffect::LockAndGetTexture(v58, v94, 0, &v95, v98);
  v96 = 0;
  v97 = 0;
  Convolve1DEffect::LockAndGetTexture(v59, **(_QWORD **)&v92, 1, &v96, &v97);
  v60 = CaptureOneSigmaFilterEffect::CreateHardwareOffsetTable(v23, *(int *)&v101[20], v102, 1, v106);
  v61 = v60;
  v92.cElements = v60;
  v92.lLbound = 0;
  v62 = SafeArrayCreate(4u, 1u, &v92);
  v63 = v62;
  v93.m128i_i64[0] = (__int64)v62;
  if ( v62 )
    v64 = SafeArrayLock(v62);
  else
    v64 = -2147024882;
  if ( v64 < 0 )
    ATL::BaseAtlThrow(v64);
  v65 = 0;
  v66 = v61;
  if ( (int)v61 > 0 )
  {
    v67 = 0;
    do
    {
      v68 = v106[v67];
      if ( !v63 )
        ATL::BaseAtlThrow(-2147467259);
      plLbound[0] = 0;
      v69 = SafeArrayGetLBound(v63, 1u, plLbound);
      if ( v69 < 0 )
        ATL::BaseAtlThrow(v69);
      if ( v65 < plLbound[0] )
        goto LABEL_136;
      rgsabound.cElements = 0;
      v70 = SafeArrayGetUBound(v63, 1u, (LONG *)&rgsabound);
      if ( v70 < 0 )
        ATL::BaseAtlThrow(v70);
      if ( v65 > (int)rgsabound.cElements )
LABEL_136:
        ATL::BaseAtlThrow(-2147024809);
      *((float *)v63->pvData + v65 - plLbound[0]) = v68;
      ++v65;
      ++v67;
    }
    while ( v67 < v66 );
  }
  v71 = pvt;
  v72 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(*pvt + 104);
  if ( !v63 )
  {
    pvt_8.vt = 10;
    pvt_8.lVal = -2147024809;
    ATL::BaseAtlThrow(-2147024809);
  }
  v92 = 0;
  v73 = SafeArrayCopy(v63, (SAFEARRAY **)&v92);
  v74 = v73;
  if ( v73 < 0 )
  {
    pvt_8.lVal = v73;
    goto LABEL_95;
  }
  v74 = SafeArrayGetVartype(v63, &pvt_8.vt);
  v75 = pvt_8.vt;
  if ( v74 >= 0 && pvt_8.vt == 13 && (v63->fFeatures & 0x440) == 0x440 )
    v75 = 9;
  if ( v74 < 0 )
  {
    pvt_8.lVal = v74;
LABEL_95:
    pvt_8.vt = 10;
    goto LABEL_96;
  }
  pvt_8.vt = v75 | 0x2000;
  pvt_8.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)v92;
LABEL_96:
  if ( v74 < 0 )
  {
    if ( v74 != -2147024882 )
      ATL::BaseAtlThrow(v74);
    ATL::BaseAtlThrow(-2147024882);
  }
  v99 = pvt_8;
  v76 = v72(v71, L"offsets", &v99);
  VariantClear(&pvt_8);
  if ( v76 < 0 )
    ATL::BaseAtlThrow(v76);
  v77 = SafeArrayUnlock(v63);
  if ( v77 < 0 )
    goto LABEL_143;
  v77 = SafeArrayDestroy(v63);
  if ( v77 >= 0 )
    v63 = 0;
  v93.m128i_i64[0] = (__int64)v63;
  if ( v77 < 0 )
LABEL_143:
    ATL::BaseAtlThrow(v77);
  v78 = *pvt;
  v79 = *((_DWORD *)v23 + 38);
  pvt_8.vt = 4;
  pvt_8.lVal = v79;
  v99 = pvt_8;
  v80 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v78 + 104))(pvt, L"threshold", &v99);
  VariantClear(&pvt_8);
  if ( v80 < 0 )
    ATL::BaseAtlThrow(v80);
  v81 = v98[0];
  v82 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const wchar_t *, _QWORD))(*pvt + 112))(pvt, 0, L"image", v98[0]);
  if ( v82 < 0 )
    ATL::BaseAtlThrow(v82);
  v83 = (*(__int64 (__fastcall **)(__int64 *, wchar_t *))(*pvt + 88))(pvt, Buffer);
  if ( v83 < 0 )
    ATL::BaseAtlThrow(v83);
  v84 = v97;
  v85 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*pvt + 120))(pvt, v97);
  if ( v85 < 0 )
    ATL::BaseAtlThrow(v85);
  if ( v63 && SafeArrayUnlock(v63) >= 0 )
    SafeArrayDestroy(v63);
  if ( v84 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
  if ( v96 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
  if ( v81 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
  if ( v95 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
  if ( v94 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
LABEL_122:
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
  if ( pvt )
    return (*(__int64 (__fastcall **)(__int64 *))(*pvt + 16))(pvt);
  return result;
}

```

## disassembly

```asm
0x180484e00  mov     rax, rsp
0x180484e03  mov     [rax+10h], rbx
0x180484e07  push    rbp
0x180484e08  push    rsi
0x180484e09  push    rdi
0x180484e0a  push    r12
0x180484e0c  push    r13
0x180484e0e  push    r14
0x180484e10  push    r15
0x180484e12  lea     rbp, [rax-598h]
0x180484e19  sub     rsp, 660h
0x180484e20  movaps  xmmword ptr [rax-48h], xmm6
0x180484e24  mov     rax, cs:__security_cookie
0x180484e2b  xor     rax, rsp
0x180484e2e  mov     [rbp+590h+var_50], rax
0x180484e35  mov     byte ptr [rsp+690h+var_638], r9b
0x180484e3a  mov     r14, r8
0x180484e3d  mov     r15, rdx
0x180484e40  mov     qword ptr [rbp+590h+plLbound], rcx
0x180484e44  mov     r13, [rbp+590h+arg_28]
0x180484e4b  mov     qword ptr [rbp+590h+var_608.cElements], r13
0x180484e4f  xor     ebx, ebx
0x180484e51  mov     qword ptr [rsp+690h+pvt], rbx
0x180484e56  mov     rcx, [rcx+80h]
0x180484e5d  mov     rax, [rcx]
0x180484e60  lea     rdx, [rsp+690h+pvt]
0x180484e65  mov     rax, [rax+0A8h]
0x180484e6c  call    cs:__guard_dispatch_icall_fptr
0x180484e72  test    eax, eax
0x180484e74  js      loc_180485886
0x180484e7a  mov     [rbp+590h+var_5A0], r15
0x180484e7e  test    r15, r15
0x180484e81  jz      short loc_180484E94
0x180484e83  mov     rax, [r15]
0x180484e86  mov     rcx, r15
0x180484e89  mov     rax, [rax+8]
0x180484e8d  call    cs:__guard_dispatch_icall_fptr
0x180484e93  nop
0x180484e94  xorps   xmm0, xmm0
0x180484e97  xor     eax, eax
0x180484e99  movups  [rbp+590h+var_598], xmm0
0x180484e9d  mov     qword ptr [rbp+590h+var_588], rax
0x180484ea1  mov     [rbp+590h+var_580], eax
0x180484ea4  mov     rax, [r15]
0x180484ea7  lea     rdx, [rbp+590h+var_598]
0x180484eab  mov     rcx, r15
0x180484eae  mov     rax, [rax+38h]
0x180484eb2  call    cs:__guard_dispatch_icall_fptr
0x180484eb8  xor     r10d, r10d
0x180484ebb  test    eax, eax
0x180484ebd  js      loc_180485860
0x180484ec3  movsxd  rcx, dword ptr [rbp+590h+var_598+0Ch]
0x180484ec7  mov     dword ptr [rbp+590h+var_5D0], ecx
0x180484eca  movsxd  rsi, [rbp+590h+var_588]
0x180484ece  mov     dword ptr [rbp+590h+var_5D0+4], esi
0x180484ed1  mov     r12, rcx
0x180484ed4  movsxd  rbx, [rbp+590h+var_588+4]
0x180484ed8  add     rbx, rcx
0x180484edb  mov     edx, 80000000h
0x180484ee0  lea     rax, [rdx+rbx]
0x180484ee4  mov     r8d, 0FFFFFFFFh
0x180484eea  cmp     rax, r8
0x180484eed  ja      loc_1804859BB
0x180484ef3  movsxd  rdi, [rbp+590h+var_580]
0x180484ef7  add     rdi, rsi
0x180484efa  lea     rax, [rdi+rdx]
0x180484efe  cmp     rax, r8
0x180484f01  ja      loc_1804859BB
0x180484f07  movups  xmm0, xmmword ptr [r14]
0x180484f0b  movups  [rbp+590h+var_600], xmm0
0x180484f0f  movd    edx, xmm0
0x180484f13  cmp     edx, ecx
0x180484f15  cmovle  edx, ecx
0x180484f18  mov     dword ptr [rbp+590h+var_600], edx
0x180484f1b  mov     ecx, dword ptr [rbp+590h+var_600+4]
0x180484f1e  cmp     ecx, esi
0x180484f20  cmovle  ecx, esi
0x180484f23  mov     dword ptr [rbp+590h+var_600+4], ecx
0x180484f26  mov     r9d, dword ptr [rbp+590h+var_600+8]
0x180484f2a  cmp     r9d, ebx
0x180484f2d  cmovge  r9d, ebx
0x180484f31  mov     r8d, dword ptr [rbp+590h+var_600+0Ch]
0x180484f35  cmp     r8d, edi
0x180484f38  cmovge  r8d, edi
0x180484f3c  cmp     edx, r9d
0x180484f3f  jg      short loc_180484F46
0x180484f41  cmp     ecx, r8d
0x180484f44  jle     short loc_180484F58
0x180484f46  mov     r8d, r10d
0x180484f49  mov     r9d, r10d
0x180484f4c  mov     ecx, r10d
0x180484f4f  mov     dword ptr [rbp+590h+var_600+4], ecx
0x180484f52  mov     edx, r10d
0x180484f55  mov     dword ptr [rbp+590h+var_600], edx
0x180484f58  cmp     edx, r9d
0x180484f5b  jge     loc_180485806
0x180484f61  cmp     ecx, r8d
0x180484f64  jge     loc_180485806
0x180484f6a  mov     r11, qword ptr [rbp+590h+plLbound]
0x180484f6e  mov     r11, [r11+80h]
0x180484f75  mov     rax, [r11]
0x180484f78  mov     r13, [rax+0F8h]
0x180484f7f  movsxd  rax, ecx
0x180484f82  movsxd  r10, r8d
0x180484f85  sub     r10, rax
0x180484f88  mov     ecx, 80000000h
0x180484f8d  lea     rax, [r10+rcx]
0x180484f91  mov     r8d, 0FFFFFFFFh
0x180484f97  cmp     rax, r8
0x180484f9a  ja      loc_1804859BB
0x180484fa0  movsxd  rax, edx
0x180484fa3  movsxd  rdx, r9d
0x180484fa6  sub     rdx, rax
0x180484fa9  lea     rax, [rcx+rdx]
0x180484fad  cmp     rax, r8
0x180484fb0  ja      loc_1804859BB
0x180484fb6  mov     [rsp+690h+rgsabound.cElements], edx
0x180484fba  mov     [rsp+690h+rgsabound.lLbound], r10d
0x180484fbf  movzx   r14d, byte ptr [rsp+690h+var_638]
0x180484fc5  mov     rax, qword ptr [rbp+590h+var_608.cElements]
0x180484fc9  mov     [rsp+690h+var_658], rax
0x180484fce  mov     dword ptr [rsp+690h+var_660], r14d
0x180484fd3  mov     edx, dword ptr [rbp+590h+var_598+8]
0x180484fd6  mov     [rsp+690h+var_668], edx
0x180484fda  xor     edx, edx
0x180484fdc  mov     dword ptr [rsp+690h+var_670], edx
0x180484fe0  mov     r9d, [rbp+590h+arg_20]
0x180484fe7  mov     r8, qword ptr [rsp+690h+rgsabound.cElements]
0x180484fec  mov     rdx, qword ptr [rbp+590h+var_600]
0x180484ff0  mov     rcx, r11
0x180484ff3  mov     rax, r13
0x180484ff6  call    cs:__guard_dispatch_icall_fptr
0x180484ffc  xor     ecx, ecx
0x180484ffe  test    eax, eax
0x180485000  js      loc_1804859B3
0x180485006  mov     [rbp+590h+var_5F0], rcx
0x18048500a  mov     r13, qword ptr [rbp+590h+plLbound]
0x18048500e  mov     rcx, [r13+80h]
0x180485015  mov     rax, [rcx]
0x180485018  mov     r10, [rax+0F8h]
0x18048501f  movsxd  r8, edi
0x180485022  sub     r8, rsi
0x180485025  mov     r9d, 80000000h
0x18048502b  lea     rax, [r8+r9]
0x18048502f  mov     r11d, 0FFFFFFFFh
0x180485035  cmp     rax, r11
0x180485038  ja      loc_1804859AA
0x18048503e  movsxd  rdx, ebx
0x180485041  sub     rdx, r12
0x180485044  lea     rax, [r9+rdx]
0x180485048  cmp     rax, r11
0x18048504b  ja      loc_1804859AA
0x180485051  mov     [rsp+690h+rgsabound.cElements], edx
0x180485055  mov     [rsp+690h+rgsabound.lLbound], r8d
0x18048505a  lea     rax, [rbp+590h+var_5F0]
0x18048505e  mov     [rsp+690h+var_658], rax
0x180485063  mov     dword ptr [rsp+690h+var_660], r14d
0x180485068  mov     edx, dword ptr [rbp+590h+var_598+8]
0x18048506b  mov     [rsp+690h+var_668], edx
0x18048506f  xor     r12d, r12d
0x180485072  mov     dword ptr [rsp+690h+var_670], r12d
0x180485077  lea     r9d, [r12+8]
0x18048507c  mov     r8, qword ptr [rsp+690h+rgsabound.cElements]
0x180485081  mov     rdx, [rbp+590h+var_5D0]
0x180485085  mov     rax, r10
0x180485088  call    cs:__guard_dispatch_icall_fptr
0x18048508e  test    eax, eax
0x180485090  js      loc_1804859A2
0x180485096  xorps   xmm0, xmm0
0x180485099  xor     eax, eax
0x18048509b  movups  [rbp+590h+var_578], xmm0
0x18048509f  mov     [rbp+590h+var_568], rax
0x1804850a3  mov     [rbp+590h+var_560], eax
0x1804850a6  mov     rcx, [rbp+590h+var_5F0]
0x1804850aa  mov     rax, [rcx]
0x1804850ad  lea     rdx, [rbp+590h+var_578]
0x1804850b1  mov     rax, [rax+38h]
0x1804850b5  call    cs:__guard_dispatch_icall_fptr
0x1804850bb  test    eax, eax
0x1804850bd  js      loc_18048599A
0x1804850c3  mov     eax, [r13+90h]
0x1804850ca  cdq
0x1804850cb  idiv    dword ptr [r13+94h]
0x1804850d2  lea     r9d, ds:1[rax*2]
0x1804850da  lea     r8, aSigmafilterD; "SigmaFilter%d"
0x1804850e1  mov     edx, 80h; unsigned __int64
0x1804850e6  lea     rcx, [rbp+590h+Buffer]; Buffer
0x1804850ed  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1804850f2  mov     [rbp+590h+var_5D0], r12
0x1804850f6  mov     [rbp+590h+var_5E8], r12
0x1804850fa  lea     rax, [rbp+590h+var_5E8]
0x1804850fe  mov     [rsp+690h+var_670], rax
0x180485103  lea     r9, [rbp+590h+var_5D0]
0x180485107  xor     r8d, r8d
0x18048510a  mov     rdx, r15
0x18048510d  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x180485112  mov     [rbp+590h+var_5D8], r12
0x180485116  mov     [rbp+590h+var_5E0], r12
0x18048511a  lea     rax, [rbp+590h+var_5E0]
0x18048511e  mov     [rsp+690h+var_670], rax
0x180485123  lea     r9, [rbp+590h+var_5D8]
0x180485127  lea     r8d, [r12+1]
0x18048512c  mov     rdx, [rbp+590h+var_5F0]
0x180485130  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x180485135  lea     rax, [rbp+590h+var_550]
0x180485139  mov     [rsp+690h+var_670], rax; float *
0x18048513e  xor     r9d, r9d; bool
0x180485141  mov     r8d, [rbp+590h+var_580]; int
0x180485145  mov     edx, [rbp+590h+var_588+4]; int
0x180485148  mov     rcx, r13; this
0x18048514b  call    ?CreateHardwareOffsetTable@CaptureOneSigmaFilterEffect@@AEAAHHH_NPEAM@Z; CaptureOneSigmaFilterEffect::CreateHardwareOffsetTable(int,int,bool,float *)
0x180485150  movsxd  rsi, eax
0x180485153  mov     [rsp+690h+rgsabound.cElements], esi
0x180485157  mov     [rsp+690h+rgsabound.lLbound], r12d
0x18048515c  lea     ecx, [r12+4]; vt
0x180485161  lea     r8, [rsp+690h+rgsabound]; rgsabound
0x180485166  lea     edx, [rcx-3]; cDims
0x180485169  call    cs:__imp_SafeArrayCreate
0x18048516f  mov     rbx, rax
0x180485172  mov     qword ptr [rbp+590h+var_600], rax
0x180485176  test    rax, rax
0x180485179  jnz     short loc_180485182
0x18048517b  mov     eax, 8007000Eh
0x180485180  jmp     short loc_18048518B
0x180485182  mov     rcx, rbx; psa
0x180485185  call    cs:__imp_SafeArrayLock
0x18048518b  test    eax, eax
0x18048518d  js      loc_18048598F
0x180485193  mov     edi, r12d
0x180485196  mov     r14, rsi
0x180485199  test    esi, esi
0x18048519b  jle     short loc_18048521B
0x18048519d  mov     rsi, r12
0x1804851a0  movss   xmm6, [rbp+rsi*4+590h+var_550]
0x1804851a6  test    rbx, rbx
0x1804851a9  jz      loc_1804858CB
0x1804851af  mov     [rbp+590h+plLbound], r12d
0x1804851b3  lea     r8, [rbp+590h+plLbound]; plLbound
0x1804851b7  mov     edx, 1; nDim
0x1804851bc  mov     rcx, rbx; psa
0x1804851bf  call    cs:__imp_SafeArrayGetLBound
0x1804851c5  test    eax, eax
0x1804851c7  js      loc_1804858C3
0x1804851cd  cmp     edi, [rbp+590h+plLbound]
0x1804851d0  jl      loc_1804858B8
0x1804851d6  mov     [rsp+690h+rgsabound.cElements], r12d
0x1804851db  lea     r8, [rsp+690h+rgsabound]; plUbound
0x1804851e0  mov     edx, 1; nDim
0x1804851e5  mov     rcx, rbx; psa
0x1804851e8  call    cs:__imp_SafeArrayGetUBound
0x1804851ee  test    eax, eax
0x1804851f0  js      loc_1804858B0
0x1804851f6  cmp     edi, [rsp+690h+rgsabound.cElements]
0x1804851fa  jg      loc_1804858B8
0x180485200  mov     eax, edi
0x180485202  sub     eax, [rbp+590h+plLbound]
0x180485205  movsxd  rcx, eax
0x180485208  mov     rax, [rbx+10h]
0x18048520c  movss   dword ptr [rax+rcx*4], xmm6
0x180485211  inc     edi
0x180485213  inc     rsi
0x180485216  cmp     rsi, r14
0x180485219  jl      short loc_1804851A0
0x18048521b  mov     rdi, qword ptr [rsp+690h+pvt]
0x180485220  mov     rax, [rdi]
0x180485223  mov     rsi, [rax+68h]
0x180485227  test    rbx, rbx
0x18048522a  jz      loc_180485891
0x180485230  mov     qword ptr [rsp+690h+rgsabound.cElements], r12
0x180485235  lea     rdx, [rsp+690h+rgsabound]; ppsaOut
0x18048523a  mov     rcx, rbx; psa
0x18048523d  call    cs:__imp_SafeArrayCopy
0x180485243  mov     ecx, eax; int
0x180485245  mov     r14d, 0Ah
0x18048524b  test    eax, eax
0x18048524d  js      short loc_1804852A6
0x18048524f  lea     rdx, [rsp+690h+pvt+8]; pvt
0x180485254  mov     rcx, rbx; psa
0x180485257  call    cs:__imp_SafeArrayGetVartype
0x18048525d  mov     ecx, eax
0x18048525f  movzx   edx, [rsp+690h+pvt+8]
0x180485264  test    eax, eax
0x180485266  js      short loc_180485286
0x180485268  cmp     dx, 0Dh
0x18048526c  jnz     short loc_180485286
0x18048526e  movzx   eax, word ptr [rbx+2]
0x180485272  mov     r8d, 440h
0x180485278  and     ax, r8w
0x18048527c  cmp     ax, r8w
0x180485280  jnz     short loc_180485286
0x180485282  lea     edx, [r14-1]
0x180485286  test    ecx, ecx
0x180485288  js      short loc_1804852A0
0x18048528a  or      dx, 2000h
0x18048528f  mov     [rsp+690h+pvt+8], dx
0x180485294  mov     rax, qword ptr [rsp+690h+rgsabound.cElements]
0x180485299  mov     [rsp+690h+var_620], rax
0x18048529e  jmp     short loc_1804852B0
0x1804852a0  mov     dword ptr [rsp+690h+var_620], ecx
0x1804852a4  jmp     short loc_1804852AA
  ... truncated ...
```
