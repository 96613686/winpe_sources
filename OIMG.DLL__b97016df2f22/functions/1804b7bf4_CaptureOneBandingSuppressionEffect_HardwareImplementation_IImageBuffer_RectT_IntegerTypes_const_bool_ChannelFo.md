# CaptureOneBandingSuppressionEffect::HardwareImplementation(IImageBuffer *,RectT<IntegerTypes> const &,bool,ChannelFormat,IImageBuffer * *)

- ea: `0x1804b7bf4`
- end: `0x1804b85f2`
- name: `?HardwareImplementation@CaptureOneBandingSuppressionEffect@@AEAAXPEAUIImageBuffer@@AEBU?$RectT@UIntegerTypes@@@@_NW4ChannelFormat@@PEAPEAU2@@Z`
- size: `2558`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1804b7360`

## callees

- `0x18001db0c`
- `0x1801e1640`
- `0x1804b6cc4`
- `0x1804b7bf4`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1804b8146`
- `OLEAUT32!__imp_VariantClear` at `0x1804b8222`
- `OLEAUT32!__imp_VariantClear` at `0x1804b8286`
- `OLEAUT32!__imp_VariantClear` at `0x1804b82e0`
- `OLEAUT32!__imp_VariantClear` at `0x1804b8333`
- `OLEAUT32!__imp_VariantClear` at `0x1804b8146`
- `OLEAUT32!__imp_VariantClear` at `0x1804b8222`
- `OLEAUT32!__imp_VariantClear` at `0x1804b8286`
- `OLEAUT32!__imp_VariantClear` at `0x1804b82e0`
- `OLEAUT32!__imp_VariantClear` at `0x1804b8333`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804b7e49`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804b7f8b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804b7e49`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804b7f8b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804b83e8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804b83ff`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804b83e8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1804b83ff`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b7eaa`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b7f14`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b7fe6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b8048`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b7eaa`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b7f14`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b7fe6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804b8048`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b7e79`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b7eea`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b7fba`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b801f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b7e79`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b7eea`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b7fba`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804b801f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804b7e62`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804b7fa4`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804b7e62`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1804b7fa4`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804b83db`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804b83f2`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804b83db`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1804b83f2`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1804b808c`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1804b816d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1804b808c`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1804b816d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1804b80a5`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1804b8181`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1804b80a5`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1804b8181`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
HRESULT __fastcall CaptureOneBandingSuppressionEffect::HardwareImplementation(
        CaptureOneBandingSuppressionEffect *a1,
        __int64 a2,
        __m128i *a3,
        unsigned __int8 a4,
        unsigned int a5,
        _QWORD *a6)
{
  int v8; // eax
  int v9; // eax
  __int64 v10; // r13
  __int64 v11; // r14
  __int64 v12; // r12
  HRESULT result; // eax
  int v14; // esi
  __int32 v15; // ebx
  int v16; // edx
  __int32 v17; // ecx
  __int64 v18; // r10
  __int64 (__fastcall *v19)(__int64, __int64, unsigned __int64, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD *); // r11
  __int64 v20; // r9
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  SAFEARRAY *v26; // rax
  SAFEARRAY *v27; // rdi
  HRESULT LBound; // eax
  __int64 v29; // r15
  HRESULT UBound; // eax
  HRESULT v31; // eax
  HRESULT v32; // eax
  __int64 v33; // r15
  __int64 v34; // rsi
  SAFEARRAY *v35; // rax
  SAFEARRAY *v36; // rbx
  HRESULT v37; // eax
  __int64 cElements; // r14
  HRESULT v39; // eax
  HRESULT v40; // eax
  HRESULT v41; // eax
  __int64 *v42; // rsi
  __int64 (__fastcall *v43)(__int64 *, const wchar_t *, VARIANTARG *); // r14
  HRESULT v44; // eax
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v47; // esi
  __int64 *v48; // rsi
  __int64 (__fastcall *v49)(__int64 *, const wchar_t *, VARIANTARG *); // r14
  HRESULT v50; // eax
  HRESULT v51; // ecx
  VARTYPE v52; // dx
  int v53; // esi
  __int64 v54; // rax
  CaptureOneBandingSuppressionEffect *v55; // r14
  LONG v56; // xmm0_4
  int v57; // esi
  __int64 v58; // rax
  LONG v59; // xmm0_4
  int v60; // esi
  __int64 v61; // rax
  int v62; // esi
  __int64 v63; // r15
  int v64; // eax
  __int64 v65; // r14
  int v66; // eax
  int v67; // eax
  __int64 v68; // rsi
  int v69; // eax
  LONG plLbound; // [rsp+50h] [rbp-B0h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 v72; // [rsp+60h] [rbp-A0h]
  __int64 *v73; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvt; // [rsp+70h] [rbp-90h] BYREF
  __m128i v75; // [rsp+88h] [rbp-78h]
  VARIANTARG v76; // [rsp+A0h] [rbp-60h] BYREF
  CaptureOneBandingSuppressionEffect *v77; // [rsp+C0h] [rbp-40h]
  struct IImageBuffer *v78; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v79; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v80; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v81; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v82; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v83; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v84; // [rsp+F8h] [rbp-8h] BYREF
  SAFEARRAY *v85; // [rsp+100h] [rbp+0h]
  __int128 v86; // [rsp+108h] [rbp+8h] BYREF
  __int64 v87; // [rsp+118h] [rbp+18h]
  int v88; // [rsp+120h] [rbp+20h]

  v72 = a4;
  v77 = a1;
  v73 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD *, __int64 **))(**((_QWORD **)a1 + 16) + 168LL))(*((_QWORD **)a1 + 16), &v73);
  if ( v8 < 0 )
    ATL::BaseAtlThrow(v8);
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 56LL))(a2, &v86);
  if ( v9 < 0 )
    ATL::BaseAtlThrow(v9);
  v10 = (int)v87;
  v85 = (SAFEARRAY *)SHIDWORD(v86);
  v11 = SHIDWORD(v86) + (__int64)SHIDWORD(v87);
  if ( (unsigned __int64)(v11 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_125;
  v12 = (int)v87 + (__int64)v88;
  result = v12 + 0x80000000;
  if ( (unsigned __int64)(v12 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_125;
  v75 = *a3;
  v14 = _mm_cvtsi128_si32(v75);
  if ( v14 <= SHIDWORD(v86) )
    v14 = HIDWORD(v86);
  v75.m128i_i32[0] = v14;
  v15 = v75.m128i_i32[1];
  if ( v75.m128i_i32[1] <= (int)v87 )
    v15 = v87;
  v75.m128i_i32[1] = v15;
  v16 = v75.m128i_i32[2];
  if ( v75.m128i_i32[2] >= (int)v11 )
    v16 = HIDWORD(v86) + HIDWORD(v87);
  v17 = v75.m128i_i32[3];
  if ( v75.m128i_i32[3] >= (int)v12 )
    v17 = v87 + v88;
  if ( v14 > v16 || v15 > v17 )
  {
    v17 = 0;
    v16 = 0;
    v15 = 0;
    v75.m128i_i64[0] = 0;
    v14 = 0;
  }
  if ( v14 >= v16 || v15 >= v17 )
  {
    *a6 = 0;
    goto LABEL_95;
  }
  v18 = *((_QWORD *)v77 + 16);
  v19 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int64, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD *))(*(_QWORD *)v18 + 248LL);
  v20 = v17 - (__int64)v15;
  if ( (unsigned __int64)(v20 + 0x80000000LL) > 0xFFFFFFFF
    || (v21 = v16 - (__int64)v14, (unsigned __int64)(v21 + 0x80000000LL) > 0xFFFFFFFF) )
  {
LABEL_125:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  rgsabound = (SAFEARRAYBOUND)__PAIR64__(v20, v21);
  v22 = v19(v18, v75.m128i_i64[0], __PAIR64__(v20, v21), a5, 0, DWORD2(v86), v72, a6);
  if ( v22 < 0 )
    ATL::BaseAtlThrow(v22);
  v84 = 0;
  v79 = 0;
  Convolve1DEffect::LockAndGetTexture(v23, a2, 0, &v84, &v79);
  v78 = 0;
  CaptureOneBandingSuppressionEffect::GetRandomImageHardware(v77, &v78);
  v83 = 0;
  v80 = 0;
  Convolve1DEffect::LockAndGetTexture(v24, v78, 0, &v83, &v80);
  v82 = 0;
  v81 = 0;
  Convolve1DEffect::LockAndGetTexture(v25, *a6, 1, &v82, &v81);
  rgsabound = (SAFEARRAYBOUND)2LL;
  v26 = SafeArrayCreate(3u, 1u, &rgsabound);
  v27 = v26;
  v75.m128i_i64[0] = (__int64)v26;
  if ( !v26 )
    ATL::BaseAtlThrow(-2147467259);
  SafeArrayLock(v26);
  plLbound = 0;
  LBound = SafeArrayGetLBound(v27, 1u, &plLbound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  v29 = plLbound;
  if ( plLbound > 0 )
    goto LABEL_122;
  plLbound = 0;
  UBound = SafeArrayGetUBound(v27, 1u, &plLbound);
  if ( UBound < 0 )
    ATL::BaseAtlThrow(UBound);
  if ( plLbound < 0 )
    goto LABEL_122;
  *((_DWORD *)v27->pvData - v29) = v14;
  plLbound = 0;
  v31 = SafeArrayGetLBound(v27, 1u, &plLbound);
  if ( v31 < 0 )
    ATL::BaseAtlThrow(v31);
  if ( plLbound > 1 )
    goto LABEL_122;
  rgsabound.cElements = 0;
  v32 = SafeArrayGetUBound(v27, 1u, (LONG *)&rgsabound);
  if ( v32 < 0 )
    ATL::BaseAtlThrow(v32);
  if ( (int)rgsabound.cElements < 1 )
LABEL_122:
    ATL::BaseAtlThrow(-2147024809);
  *((_DWORD *)v27->pvData + 1 - plLbound) = v15;
  v33 = (int)v12 - v10;
  if ( (unsigned __int64)(v33 + 0x80000000LL) > 0xFFFFFFFF
    || (v34 = (int)v11 - (_QWORD)v85, (unsigned __int64)(v34 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  rgsabound = (SAFEARRAYBOUND)2LL;
  v35 = SafeArrayCreate(3u, 1u, &rgsabound);
  v36 = v35;
  v85 = v35;
  if ( !v35 )
    ATL::BaseAtlThrow(-2147467259);
  SafeArrayLock(v35);
  rgsabound.cElements = 0;
  v37 = SafeArrayGetLBound(v36, 1u, (LONG *)&rgsabound);
  if ( v37 < 0 )
    ATL::BaseAtlThrow(v37);
  cElements = (int)rgsabound.cElements;
  if ( (int)rgsabound.cElements > 0 )
    goto LABEL_119;
  rgsabound.cElements = 0;
  v39 = SafeArrayGetUBound(v36, 1u, (LONG *)&rgsabound);
  if ( v39 < 0 )
    ATL::BaseAtlThrow(v39);
  if ( (rgsabound.cElements & 0x80000000) != 0 )
    goto LABEL_119;
  *((_DWORD *)v36->pvData - cElements) = v34;
  plLbound = 0;
  v40 = SafeArrayGetLBound(v36, 1u, &plLbound);
  if ( v40 < 0 )
    ATL::BaseAtlThrow(v40);
  if ( plLbound > 1 )
    goto LABEL_119;
  rgsabound.cElements = 0;
  v41 = SafeArrayGetUBound(v36, 1u, (LONG *)&rgsabound);
  if ( v41 < 0 )
    ATL::BaseAtlThrow(v41);
  if ( (int)rgsabound.cElements < 1 )
LABEL_119:
    ATL::BaseAtlThrow(-2147024809);
  *((_DWORD *)v36->pvData + 1 - plLbound) = v33;
  v42 = v73;
  v43 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(*v73 + 104);
  rgsabound = 0;
  v44 = SafeArrayCopy(v27, (SAFEARRAY **)&rgsabound);
  Vartype = v44;
  if ( v44 < 0 )
  {
    pvt.lVal = v44;
  }
  else
  {
    Vartype = SafeArrayGetVartype(v27, &pvt.vt);
    vt = pvt.vt;
    if ( Vartype >= 0 && pvt.vt == 13 && (v27->fFeatures & 0x440) == 0x440 )
      vt = 9;
    if ( Vartype >= 0 )
    {
      pvt.vt = vt | 0x2000;
      pvt.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
      goto LABEL_51;
    }
    pvt.lVal = Vartype;
  }
  pvt.vt = 10;
LABEL_51:
  if ( Vartype < 0 )
  {
    if ( Vartype != -2147024882 )
      ATL::BaseAtlThrow(Vartype);
    ATL::BaseAtlThrow(-2147024882);
  }
  v76 = pvt;
  v47 = v43(v42, L"topLeft", &v76);
  VariantClear(&pvt);
  if ( v47 < 0 )
    ATL::BaseAtlThrow(v47);
  v48 = v73;
  v49 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(*v73 + 104);
  rgsabound = 0;
  v50 = SafeArrayCopy(v36, (SAFEARRAY **)&rgsabound);
  v51 = v50;
  if ( v50 < 0 )
  {
    pvt.lVal = v50;
    goto LABEL_64;
  }
  v51 = SafeArrayGetVartype(v36, &pvt.vt);
  v52 = pvt.vt;
  if ( v51 >= 0 && pvt.vt == 13 && (v36->fFeatures & 0x440) == 0x440 )
    v52 = 9;
  if ( v51 < 0 )
  {
    pvt.lVal = v51;
LABEL_64:
    pvt.vt = 10;
    goto LABEL_65;
  }
  pvt.vt = v52 | 0x2000;
  pvt.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
LABEL_65:
  if ( v51 < 0 )
  {
    if ( v51 != -2147024882 )
      ATL::BaseAtlThrow(v51);
    ATL::BaseAtlThrow(-2147024882);
  }
  v76 = pvt;
  v53 = v49(v48, L"tilePixelDims", &v76);
  VariantClear(&pvt);
  if ( v53 < 0 )
    ATL::BaseAtlThrow(v53);
  v54 = *v73;
  v55 = v77;
  v56 = *((_DWORD *)v77 + 36);
  pvt.vt = 4;
  pvt.lVal = v56;
  v76 = pvt;
  v57 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v54 + 104))(v73, L"bandingLuma", &v76);
  VariantClear(&pvt);
  if ( v57 < 0 )
    ATL::BaseAtlThrow(v57);
  v58 = *v73;
  v59 = *((_DWORD *)v55 + 37);
  pvt.vt = 4;
  pvt.lVal = v59;
  v76 = pvt;
  v60 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v58 + 104))(v73, L"bandingChroma", &v76);
  VariantClear(&pvt);
  if ( v60 < 0 )
    ATL::BaseAtlThrow(v60);
  v61 = *v73;
  pvt.vt = 4;
  pvt.lVal = 1140850688;
  v76 = pvt;
  v62 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v61 + 104))(v73, L"noiseImageSize", &v76);
  VariantClear(&pvt);
  if ( v62 < 0 )
    ATL::BaseAtlThrow(v62);
  v63 = v79;
  v64 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const wchar_t *, __int64))(*v73 + 112))(v73, 0, L"image", v79);
  if ( v64 < 0 )
    ATL::BaseAtlThrow(v64);
  v65 = v80;
  v66 = (*(__int64 (__fastcall **)(__int64 *, __int64, const wchar_t *, __int64))(*v73 + 112))(
          v73,
          1,
          L"randomImage",
          v80);
  if ( v66 < 0 )
    ATL::BaseAtlThrow(v66);
  v67 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *))(*v73 + 88))(v73, L"BandingSuppression");
  if ( v67 < 0 )
    ATL::BaseAtlThrow(v67);
  v68 = v81;
  v69 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v73 + 120))(v73, v81);
  if ( v69 < 0 )
    ATL::BaseAtlThrow(v69);
  if ( SafeArrayUnlock(v36) >= 0 )
    SafeArrayDestroy(v36);
  result = SafeArrayUnlock(v27);
  if ( result >= 0 )
    result = SafeArrayDestroy(v27);
  if ( v68 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
  if ( v82 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
  if ( v65 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  if ( v83 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
  if ( v78 )
    result = (*(__int64 (__fastcall **)(struct IImageBuffer *))(*(_QWORD *)v78 + 16LL))(v78);
  if ( v63 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  if ( v84 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
LABEL_95:
  if ( v73 )
    return (*(__int64 (__fastcall **)(__int64 *))(*v73 + 16))(v73);
  return result;
}

```

## disassembly

```asm
0x1804b7bf4  push    rbp
0x1804b7bf6  push    rbx
0x1804b7bf7  push    rsi
0x1804b7bf8  push    rdi
0x1804b7bf9  push    r12
0x1804b7bfb  push    r13
0x1804b7bfd  push    r14
0x1804b7bff  push    r15
0x1804b7c01  lea     rbp, [rsp-38h]
0x1804b7c06  sub     rsp, 138h
0x1804b7c0d  mov     rax, cs:__security_cookie
0x1804b7c14  xor     rax, rsp
0x1804b7c17  mov     [rbp+70h+var_48], rax
0x1804b7c1b  mov     [rsp+170h+var_110], r9b
0x1804b7c20  mov     rbx, r8
0x1804b7c23  mov     r15, rdx
0x1804b7c26  mov     [rbp+70h+var_B0], rcx
0x1804b7c2a  mov     rdi, [rbp+70h+arg_28]
0x1804b7c31  mov     [rsp+170h+var_108], 0
0x1804b7c3a  mov     rcx, [rcx+80h]
0x1804b7c41  mov     rax, [rcx]
0x1804b7c44  lea     rdx, [rsp+170h+var_108]
0x1804b7c49  mov     rax, [rax+0A8h]
0x1804b7c50  call    cs:__guard_dispatch_icall_fptr
0x1804b7c56  test    eax, eax
0x1804b7c58  js      loc_1804B850A
0x1804b7c5e  xorps   xmm0, xmm0
0x1804b7c61  xor     eax, eax
0x1804b7c63  movups  [rbp+70h+var_68], xmm0
0x1804b7c67  mov     [rbp+70h+var_58], rax
0x1804b7c6b  mov     [rbp+70h+var_50], eax
0x1804b7c6e  mov     rax, [r15]
0x1804b7c71  lea     rdx, [rbp+70h+var_68]
0x1804b7c75  mov     rcx, r15
0x1804b7c78  mov     rax, [rax+38h]
0x1804b7c7c  call    cs:__guard_dispatch_icall_fptr
0x1804b7c82  test    eax, eax
0x1804b7c84  js      loc_1804B84EC
0x1804b7c8a  movsxd  r13, dword ptr [rbp+70h+var_58]
0x1804b7c8e  movsxd  rcx, dword ptr [rbp+70h+var_68+0Ch]
0x1804b7c92  mov     [rbp+70h+var_70], rcx
0x1804b7c96  movsxd  r14, dword ptr [rbp+70h+var_58+4]
0x1804b7c9a  add     r14, rcx
0x1804b7c9d  mov     r8d, 80000000h
0x1804b7ca3  lea     rax, [r8+r14]
0x1804b7ca7  mov     edx, 0FFFFFFFFh
0x1804b7cac  cmp     rax, rdx
0x1804b7caf  ja      loc_1804B85EC
0x1804b7cb5  movsxd  r12, [rbp+70h+var_50]
0x1804b7cb9  add     r12, r13
0x1804b7cbc  lea     rax, [r12+r8]
0x1804b7cc0  cmp     rax, rdx
0x1804b7cc3  ja      loc_1804B85EC
0x1804b7cc9  movups  xmm0, xmmword ptr [rbx]
0x1804b7ccc  movups  [rbp+70h+var_E8], xmm0
0x1804b7cd0  movd    esi, xmm0
0x1804b7cd4  cmp     esi, ecx
0x1804b7cd6  cmovle  esi, ecx
0x1804b7cd9  mov     dword ptr [rbp+70h+var_E8], esi
0x1804b7cdc  mov     ebx, dword ptr [rbp+70h+var_E8+4]
0x1804b7cdf  cmp     ebx, r13d
0x1804b7ce2  cmovle  ebx, r13d
0x1804b7ce6  mov     dword ptr [rbp+70h+var_E8+4], ebx
0x1804b7ce9  mov     edx, dword ptr [rbp+70h+var_E8+8]
0x1804b7cec  cmp     edx, r14d
0x1804b7cef  cmovge  edx, r14d
0x1804b7cf3  mov     ecx, dword ptr [rbp+70h+var_E8+0Ch]
0x1804b7cf6  cmp     ecx, r12d
0x1804b7cf9  cmovge  ecx, r12d
0x1804b7cfd  cmp     esi, edx
0x1804b7cff  jg      short loc_1804B7D05
0x1804b7d01  cmp     ebx, ecx
0x1804b7d03  jle     short loc_1804B7D11
0x1804b7d05  xor     ecx, ecx
0x1804b7d07  xor     edx, edx
0x1804b7d09  xor     ebx, ebx
0x1804b7d0b  mov     qword ptr [rbp+70h+var_E8], rbx
0x1804b7d0f  xor     esi, esi
0x1804b7d11  cmp     esi, edx
0x1804b7d13  jge     loc_1804B84AE
0x1804b7d19  cmp     ebx, ecx
0x1804b7d1b  jge     loc_1804B84AE
0x1804b7d21  mov     r10, [rbp+70h+var_B0]
0x1804b7d25  mov     r10, [r10+80h]
0x1804b7d2c  mov     rax, [r10]
0x1804b7d2f  mov     r11, [rax+0F8h]
0x1804b7d36  movsxd  r9, ecx
0x1804b7d39  movsxd  rax, ebx
0x1804b7d3c  sub     r9, rax
0x1804b7d3f  lea     rax, [r8+r9]
0x1804b7d43  mov     ecx, 0FFFFFFFFh
0x1804b7d48  cmp     rax, rcx
0x1804b7d4b  ja      loc_1804B85EC
0x1804b7d51  movsxd  r8, edx
0x1804b7d54  movsxd  rax, esi
0x1804b7d57  sub     r8, rax
0x1804b7d5a  mov     eax, 80000000h
0x1804b7d5f  add     rax, r8
0x1804b7d62  cmp     rax, rcx
0x1804b7d65  ja      loc_1804B85EC
0x1804b7d6b  mov     [rsp+170h+rgsabound.cElements], r8d
0x1804b7d70  mov     [rsp+170h+rgsabound.lLbound], r9d
0x1804b7d75  movzx   edx, [rsp+170h+var_110]
0x1804b7d7a  mov     [rsp+170h+var_138], rdi
0x1804b7d7f  mov     [rsp+170h+var_140], edx
0x1804b7d83  mov     edx, dword ptr [rbp+70h+var_68+8]
0x1804b7d86  mov     [rsp+170h+var_148], edx
0x1804b7d8a  mov     dword ptr [rsp+170h+var_150], 0
0x1804b7d92  mov     r9d, [rbp+70h+arg_20]
0x1804b7d99  mov     r8, qword ptr [rsp+170h+rgsabound.cElements]
0x1804b7d9e  mov     rdx, qword ptr [rbp+70h+var_E8]
0x1804b7da2  mov     rcx, r10
0x1804b7da5  mov     rax, r11
0x1804b7da8  call    cs:__guard_dispatch_icall_fptr
0x1804b7dae  test    eax, eax
0x1804b7db0  js      loc_1804B85E4
0x1804b7db6  mov     [rbp+70h+var_78], 0
0x1804b7dbe  mov     [rbp+70h+var_A0], 0
0x1804b7dc6  lea     rax, [rbp+70h+var_A0]
0x1804b7dca  mov     [rsp+170h+var_150], rax
0x1804b7dcf  lea     r9, [rbp+70h+var_78]
0x1804b7dd3  xor     r8d, r8d
0x1804b7dd6  mov     rdx, r15
0x1804b7dd9  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x1804b7dde  xor     r15d, r15d
0x1804b7de1  mov     [rbp+70h+var_A8], r15
0x1804b7de5  lea     rdx, [rbp+70h+var_A8]; struct IImageBuffer **
0x1804b7de9  mov     rcx, [rbp+70h+var_B0]; this
0x1804b7ded  call    ?GetRandomImageHardware@CaptureOneBandingSuppressionEffect@@AEAAXPEAPEAUIImageBuffer@@@Z; CaptureOneBandingSuppressionEffect::GetRandomImageHardware(IImageBuffer * *)
0x1804b7df2  mov     [rbp+70h+var_80], r15
0x1804b7df6  mov     [rbp+70h+var_98], r15
0x1804b7dfa  lea     rax, [rbp+70h+var_98]
0x1804b7dfe  mov     [rsp+170h+var_150], rax
0x1804b7e03  lea     r9, [rbp+70h+var_80]
0x1804b7e07  xor     r8d, r8d
0x1804b7e0a  mov     rdx, [rbp+70h+var_A8]
0x1804b7e0e  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x1804b7e13  mov     [rbp+70h+var_88], r15
0x1804b7e17  mov     [rbp+70h+var_90], r15
0x1804b7e1b  lea     rax, [rbp+70h+var_90]
0x1804b7e1f  mov     [rsp+170h+var_150], rax
0x1804b7e24  lea     r9, [rbp+70h+var_88]
0x1804b7e28  lea     r8d, [r15+1]
0x1804b7e2c  mov     rdx, [rdi]
0x1804b7e2f  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x1804b7e34  mov     qword ptr [rsp+170h+rgsabound.cElements], 2
0x1804b7e3d  lea     ecx, [r15+3]; vt
0x1804b7e41  lea     r8, [rsp+170h+rgsabound]; rgsabound
0x1804b7e46  lea     edx, [rcx-2]; cDims
0x1804b7e49  call    cs:__imp_SafeArrayCreate
0x1804b7e4f  mov     rdi, rax
0x1804b7e52  mov     qword ptr [rbp+70h+var_E8], rax
0x1804b7e56  test    rax, rax
0x1804b7e59  jz      loc_1804B85D6
0x1804b7e5f  mov     rcx, rax; psa
0x1804b7e62  call    cs:__imp_SafeArrayLock
0x1804b7e68  mov     [rsp+170h+plLbound], r15d
0x1804b7e6d  lea     r8, [rsp+170h+plLbound]; plLbound
0x1804b7e72  lea     edx, [r15+1]; nDim
0x1804b7e76  mov     rcx, rdi; psa
0x1804b7e79  call    cs:__imp_SafeArrayGetLBound
0x1804b7e7f  test    eax, eax
0x1804b7e81  js      loc_1804B8515
0x1804b7e87  movsxd  r15, [rsp+170h+plLbound]
0x1804b7e8c  test    r15d, r15d
0x1804b7e8f  jg      loc_1804B85CB
0x1804b7e95  mov     [rsp+170h+plLbound], 0
0x1804b7e9d  lea     r8, [rsp+170h+plLbound]; plUbound
0x1804b7ea2  mov     edx, 1; nDim
0x1804b7ea7  mov     rcx, rdi; psa
0x1804b7eaa  call    cs:__imp_SafeArrayGetUBound
0x1804b7eb0  test    eax, eax
0x1804b7eb2  js      loc_1804B851D
0x1804b7eb8  cmp     [rsp+170h+plLbound], 0
0x1804b7ebd  jl      loc_1804B85CB
0x1804b7ec3  mov     rcx, r15
0x1804b7ec6  shl     rcx, 2
0x1804b7eca  mov     rax, [rdi+10h]
0x1804b7ece  sub     rax, rcx
0x1804b7ed1  mov     [rax], esi
0x1804b7ed3  mov     [rsp+170h+plLbound], 0
0x1804b7edb  lea     r8, [rsp+170h+plLbound]; plLbound
0x1804b7ee0  mov     esi, 1
0x1804b7ee5  mov     edx, esi; nDim
0x1804b7ee7  mov     rcx, rdi; psa
0x1804b7eea  call    cs:__imp_SafeArrayGetLBound
0x1804b7ef0  test    eax, eax
0x1804b7ef2  js      loc_1804B8525
0x1804b7ef8  cmp     [rsp+170h+plLbound], esi
0x1804b7efc  jg      loc_1804B85CB
0x1804b7f02  mov     [rsp+170h+rgsabound.cElements], 0
0x1804b7f0a  lea     r8, [rsp+170h+rgsabound]; plUbound
0x1804b7f0f  mov     edx, esi; nDim
0x1804b7f11  mov     rcx, rdi; psa
0x1804b7f14  call    cs:__imp_SafeArrayGetUBound
0x1804b7f1a  test    eax, eax
0x1804b7f1c  js      loc_1804B852D
0x1804b7f22  cmp     [rsp+170h+rgsabound.cElements], esi
0x1804b7f26  jl      loc_1804B85CB
0x1804b7f2c  mov     eax, esi
0x1804b7f2e  sub     eax, [rsp+170h+plLbound]
0x1804b7f32  movsxd  rcx, eax
0x1804b7f35  mov     rax, [rdi+10h]
0x1804b7f39  mov     [rax+rcx*4], ebx
0x1804b7f3c  movsxd  r15, r12d
0x1804b7f3f  sub     r15, r13
0x1804b7f42  mov     ecx, 80000000h
0x1804b7f47  lea     rax, [r15+rcx]
0x1804b7f4b  mov     edx, 0FFFFFFFFh
0x1804b7f50  cmp     rax, rdx
0x1804b7f53  ja      loc_1804B85C5
0x1804b7f59  movsxd  rsi, r14d
0x1804b7f5c  sub     rsi, [rbp+70h+var_70]
0x1804b7f60  lea     rax, [rsi+rcx]
0x1804b7f64  cmp     rax, rdx
0x1804b7f67  ja      loc_1804B85C5
0x1804b7f6d  mov     qword ptr [rsp+170h+rgsabound.cElements], 2
0x1804b7f76  xor     r12d, r12d
0x1804b7f79  lea     ecx, [r12+3]; vt
0x1804b7f7e  lea     r8, [rsp+170h+rgsabound]; rgsabound
0x1804b7f83  lea     r13d, [r12+1]
0x1804b7f88  mov     edx, r13d; cDims
0x1804b7f8b  call    cs:__imp_SafeArrayCreate
0x1804b7f91  mov     rbx, rax
0x1804b7f94  mov     [rbp+70h+var_70], rax
0x1804b7f98  test    rax, rax
0x1804b7f9b  jz      loc_1804B85B7
0x1804b7fa1  mov     rcx, rax; psa
0x1804b7fa4  call    cs:__imp_SafeArrayLock
0x1804b7faa  mov     [rsp+170h+rgsabound.cElements], r12d
0x1804b7faf  lea     r8, [rsp+170h+rgsabound]; plLbound
0x1804b7fb4  mov     edx, r13d; nDim
0x1804b7fb7  mov     rcx, rbx; psa
0x1804b7fba  call    cs:__imp_SafeArrayGetLBound
0x1804b7fc0  test    eax, eax
0x1804b7fc2  js      loc_1804B8538
0x1804b7fc8  movsxd  r14, [rsp+170h+rgsabound.cElements]
0x1804b7fcd  test    r14d, r14d
0x1804b7fd0  jg      loc_1804B85AC
0x1804b7fd6  mov     [rsp+170h+rgsabound.cElements], r12d
0x1804b7fdb  lea     r8, [rsp+170h+rgsabound]; plUbound
0x1804b7fe0  mov     edx, r13d; nDim
0x1804b7fe3  mov     rcx, rbx; psa
0x1804b7fe6  call    cs:__imp_SafeArrayGetUBound
0x1804b7fec  test    eax, eax
0x1804b7fee  js      loc_1804B8540
0x1804b7ff4  cmp     [rsp+170h+rgsabound.cElements], r12d
0x1804b7ff9  jl      loc_1804B85AC
0x1804b7fff  mov     rcx, r14
0x1804b8002  shl     rcx, 2
0x1804b8006  mov     rax, [rbx+10h]
0x1804b800a  sub     rax, rcx
0x1804b800d  mov     [rax], esi
0x1804b800f  mov     [rsp+170h+plLbound], r12d
0x1804b8014  lea     r8, [rsp+170h+plLbound]; plLbound
0x1804b8019  mov     edx, r13d; nDim
0x1804b801c  mov     rcx, rbx; psa
0x1804b801f  call    cs:__imp_SafeArrayGetLBound
0x1804b8025  test    eax, eax
0x1804b8027  js      loc_1804B8548
0x1804b802d  cmp     [rsp+170h+plLbound], r13d
0x1804b8032  jg      loc_1804B85AC
0x1804b8038  mov     [rsp+170h+rgsabound.cElements], r12d
0x1804b803d  lea     r8, [rsp+170h+rgsabound]; plUbound
0x1804b8042  mov     edx, r13d; nDim
0x1804b8045  mov     rcx, rbx; psa
0x1804b8048  call    cs:__imp_SafeArrayGetUBound
0x1804b804e  test    eax, eax
0x1804b8050  js      loc_1804B8550
0x1804b8056  cmp     [rsp+170h+rgsabound.cElements], r13d
0x1804b805b  jl      loc_1804B85AC
0x1804b8061  mov     eax, r13d
0x1804b8064  sub     eax, [rsp+170h+plLbound]
0x1804b8068  movsxd  rcx, eax
0x1804b806b  mov     rax, [rbx+10h]
0x1804b806f  mov     [rax+rcx*4], r15d
0x1804b8073  mov     rsi, [rsp+170h+var_108]
0x1804b8078  mov     rax, [rsi]
0x1804b807b  mov     r14, [rax+68h]
0x1804b807f  mov     qword ptr [rsp+170h+rgsabound.cElements], r12
0x1804b8084  lea     rdx, [rsp+170h+rgsabound]; ppsaOut
0x1804b8089  mov     rcx, rdi; psa
0x1804b808c  call    cs:__imp_SafeArrayCopy
0x1804b8092  mov     ecx, eax; int
0x1804b8094  lea     r15d, [r12+0Ah]
0x1804b8099  test    eax, eax
0x1804b809b  js      short loc_1804B80F5
0x1804b809d  lea     rdx, [rsp+170h+pvt]; pvt
0x1804b80a2  mov     rcx, rdi; psa
0x1804b80a5  call    cs:__imp_SafeArrayGetVartype
0x1804b80ab  mov     ecx, eax
0x1804b80ad  movzx   edx, [rsp+170h+pvt]
0x1804b80b2  test    eax, eax
0x1804b80b4  js      short loc_1804B80D5
0x1804b80b6  cmp     dx, 0Dh
0x1804b80ba  jnz     short loc_1804B80D5
0x1804b80bc  movzx   eax, word ptr [rdi+2]
0x1804b80c0  mov     r8d, 440h
0x1804b80c6  and     ax, r8w
0x1804b80ca  cmp     ax, r8w
  ... truncated ...
```
