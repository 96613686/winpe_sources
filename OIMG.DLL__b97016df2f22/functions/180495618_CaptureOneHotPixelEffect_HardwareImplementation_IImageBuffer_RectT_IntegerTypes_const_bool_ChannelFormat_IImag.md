# CaptureOneHotPixelEffect::HardwareImplementation(IImageBuffer *,RectT<IntegerTypes> const &,bool,ChannelFormat,IImageBuffer * *)

- ea: `0x180495618`
- end: `0x180495fb5`
- name: `?HardwareImplementation@CaptureOneHotPixelEffect@@AEAAXPEAUIImageBuffer@@AEBU?$RectT@UIntegerTypes@@@@_NW4ChannelFormat@@PEAPEAU2@@Z`
- size: `2461`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180494c00`

## callees

- `0x18001db0c`
- `0x1801e1640`
- `0x180495618`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180495bb6`
- `OLEAUT32!__imp_VariantClear` at `0x180495c17`
- `OLEAUT32!__imp_VariantClear` at `0x180495c72`
- `OLEAUT32!__imp_VariantClear` at `0x180495d4f`
- `OLEAUT32!__imp_VariantClear` at `0x180495bb6`
- `OLEAUT32!__imp_VariantClear` at `0x180495c17`
- `OLEAUT32!__imp_VariantClear` at `0x180495c72`
- `OLEAUT32!__imp_VariantClear` at `0x180495d4f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049582f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049596a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049582f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049596a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180495dd9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180495df0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180495dd9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180495df0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804958a1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18049591c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804959e0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180495a4d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180495aba`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804958a1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18049591c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1804959e0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180495a4d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180495aba`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180495876`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804958f3`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804959b4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180495a24`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180495a92`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180495876`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804958f3`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1804959b4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180495a24`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180495a92`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049584f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180495984`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049584f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180495984`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180495dcc`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180495de3`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180495dcc`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180495de3`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180495afb`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180495c99`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180495afb`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180495c99`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180495b15`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180495cad`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180495b15`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180495cad`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
HRESULT __fastcall CaptureOneHotPixelEffect::HardwareImplementation(
        __int64 a1,
        __int64 a2,
        __m128i *a3,
        unsigned __int8 a4,
        unsigned int a5,
        _QWORD *a6)
{
  int v6; // r14d
  int v10; // eax
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r10
  HRESULT result; // eax
  int v15; // edx
  __int32 v16; // ecx
  int v17; // r9d
  __int32 v18; // r8d
  __int64 v19; // r11
  __int64 (__fastcall *v20)(__int64, __int64, unsigned __int64, _QWORD, _DWORD, _DWORD, int, _QWORD *); // rsi
  __int64 v21; // r10
  __int64 v22; // r8
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  SAFEARRAY *v26; // rax
  SAFEARRAY *v27; // rdi
  HRESULT v28; // eax
  HRESULT LBound; // eax
  __int64 v30; // rbx
  HRESULT UBound; // eax
  HRESULT v32; // eax
  HRESULT v33; // eax
  SAFEARRAY *v34; // rax
  SAFEARRAY *v35; // rbx
  HRESULT v36; // eax
  int v37; // xmm6_4
  HRESULT v38; // eax
  __int64 cElements; // r14
  HRESULT v40; // eax
  int v41; // xmm6_4
  HRESULT v42; // eax
  HRESULT v43; // eax
  int v44; // xmm6_4
  HRESULT v45; // eax
  HRESULT v46; // eax
  __int64 *v47; // rsi
  __int64 (__fastcall *v48)(__int64 *, const wchar_t *, VARIANTARG *); // r14
  HRESULT v49; // eax
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v52; // esi
  __int64 v53; // rax
  LONG v54; // xmm0_4
  int v55; // esi
  __int64 v56; // rax
  LONG v57; // xmm0_4
  int v58; // esi
  __int64 *v59; // rsi
  __int64 (__fastcall *v60)(__int64 *, const wchar_t *, VARIANTARG *); // r14
  HRESULT v61; // eax
  HRESULT v62; // ecx
  VARTYPE v63; // dx
  int v64; // esi
  __int64 v65; // r14
  int v66; // eax
  int v67; // eax
  __int64 v68; // rsi
  int v69; // eax
  LONG plLbound[2]; // [rsp+58h] [rbp-B0h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG rgsabound_8; // [rsp+68h] [rbp-A0h] BYREF
  __int64 *v73; // [rsp+80h] [rbp-88h] BYREF
  __m128i v74; // [rsp+88h] [rbp-80h]
  VARIANTARG v75; // [rsp+98h] [rbp-70h] BYREF
  __int64 v76; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v77; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v78; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v79[2]; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v80; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v81; // [rsp+F0h] [rbp-18h]
  int v82; // [rsp+F8h] [rbp-10h]

  v6 = a4;
  v73 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**(_QWORD **)(a1 + 128) + 168LL))(*(_QWORD *)(a1 + 128), &v73);
  if ( v10 < 0 )
    ATL::BaseAtlThrow(v10);
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 56LL))(a2, &v80);
  if ( v11 < 0 )
    ATL::BaseAtlThrow(v11);
  v12 = SHIDWORD(v80) + (__int64)SHIDWORD(v81);
  if ( (unsigned __int64)(v12 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_128;
  v13 = (int)v81 + (__int64)v82;
  result = v13 + 0x80000000;
  if ( (unsigned __int64)(v13 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_128;
  v74 = *a3;
  v15 = _mm_cvtsi128_si32(v74);
  if ( v15 <= SHIDWORD(v80) )
    v15 = HIDWORD(v80);
  v74.m128i_i32[0] = v15;
  v16 = v74.m128i_i32[1];
  if ( v74.m128i_i32[1] <= (int)v81 )
    v16 = v81;
  v74.m128i_i32[1] = v16;
  v17 = v74.m128i_i32[2];
  if ( v74.m128i_i32[2] >= (int)v12 )
    v17 = HIDWORD(v80) + HIDWORD(v81);
  v18 = v74.m128i_i32[3];
  if ( v74.m128i_i32[3] >= (int)v13 )
    v18 = v81 + v82;
  if ( v15 > v17 || v16 > v18 )
  {
    v18 = 0;
    v17 = 0;
    v16 = 0;
    v15 = 0;
    v74.m128i_i64[0] = 0;
  }
  if ( v15 >= v17 || v16 >= v18 )
  {
    *a6 = 0;
    goto LABEL_97;
  }
  v19 = *(_QWORD *)(a1 + 128);
  v20 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int64, _QWORD, _DWORD, _DWORD, int, _QWORD *))(*(_QWORD *)v19 + 248LL);
  v21 = v18 - (__int64)v16;
  if ( (unsigned __int64)(v21 + 0x80000000LL) > 0xFFFFFFFF
    || (v22 = v17 - (__int64)v15, (unsigned __int64)(v22 + 0x80000000LL) > 0xFFFFFFFF) )
  {
LABEL_128:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  rgsabound = (SAFEARRAYBOUND)__PAIR64__(v21, v22);
  v23 = v20(v19, v74.m128i_i64[0], __PAIR64__(v21, v22), a5, 0, DWORD2(v80), v6, a6);
  if ( v23 < 0 )
    ATL::BaseAtlThrow(v23);
  v79[0] = 0;
  v76 = 0;
  Convolve1DEffect::LockAndGetTexture(v24, a2, 0, v79, &v76);
  v78 = 0;
  v77 = 0;
  Convolve1DEffect::LockAndGetTexture(v25, *a6, 1, &v78, &v77);
  rgsabound = (SAFEARRAYBOUND)2LL;
  v26 = SafeArrayCreate(4u, 1u, &rgsabound);
  v27 = v26;
  v79[1] = v26;
  if ( v26 )
    v28 = SafeArrayLock(v26);
  else
    v28 = -2147024882;
  if ( v28 < 0 )
    ATL::BaseAtlThrow(v28);
  if ( !v27 )
    ATL::BaseAtlThrow(-2147467259);
  plLbound[0] = 0;
  LBound = SafeArrayGetLBound(v27, 1u, plLbound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  v30 = plLbound[0];
  if ( plLbound[0] > 0 )
    goto LABEL_126;
  plLbound[0] = 0;
  UBound = SafeArrayGetUBound(v27, 1u, plLbound);
  if ( UBound < 0 )
    ATL::BaseAtlThrow(UBound);
  if ( plLbound[0] < 0 )
    goto LABEL_126;
  *((float *)v27->pvData - v30) = 1.0 / (float)SHIDWORD(v81);
  plLbound[0] = 0;
  v32 = SafeArrayGetLBound(v27, 1u, plLbound);
  if ( v32 < 0 )
    ATL::BaseAtlThrow(v32);
  if ( plLbound[0] > 1 )
    goto LABEL_126;
  rgsabound.cElements = 0;
  v33 = SafeArrayGetUBound(v27, 1u, (LONG *)&rgsabound);
  if ( v33 < 0 )
    ATL::BaseAtlThrow(v33);
  if ( (int)rgsabound.cElements < 1 )
LABEL_126:
    ATL::BaseAtlThrow(-2147024809);
  *((float *)v27->pvData + 1 - plLbound[0]) = 1.0 / (float)v82;
  rgsabound = (SAFEARRAYBOUND)3LL;
  v34 = SafeArrayCreate(4u, 1u, &rgsabound);
  v35 = v34;
  v74.m128i_i64[0] = (__int64)v34;
  if ( v34 )
    v36 = SafeArrayLock(v34);
  else
    v36 = -2147024882;
  if ( v36 < 0 )
    ATL::BaseAtlThrow(v36);
  v37 = *(_DWORD *)(a1 + 156);
  if ( !v35 )
    ATL::BaseAtlThrow(-2147467259);
  rgsabound.cElements = 0;
  v38 = SafeArrayGetLBound(v35, 1u, (LONG *)&rgsabound);
  if ( v38 < 0 )
    ATL::BaseAtlThrow(v38);
  cElements = (int)rgsabound.cElements;
  if ( (int)rgsabound.cElements > 0 )
    goto LABEL_125;
  rgsabound.cElements = 0;
  v40 = SafeArrayGetUBound(v35, 1u, (LONG *)&rgsabound);
  if ( v40 < 0 )
    ATL::BaseAtlThrow(v40);
  if ( (rgsabound.cElements & 0x80000000) != 0 )
    goto LABEL_125;
  *((_DWORD *)v35->pvData - cElements) = v37;
  v41 = *(_DWORD *)(a1 + 160);
  plLbound[0] = 0;
  v42 = SafeArrayGetLBound(v35, 1u, plLbound);
  if ( v42 < 0 )
    ATL::BaseAtlThrow(v42);
  if ( plLbound[0] > 1 )
    goto LABEL_125;
  rgsabound.cElements = 0;
  v43 = SafeArrayGetUBound(v35, 1u, (LONG *)&rgsabound);
  if ( v43 < 0 )
    ATL::BaseAtlThrow(v43);
  if ( (int)rgsabound.cElements < 1 )
    goto LABEL_125;
  *((_DWORD *)v35->pvData + 1 - plLbound[0]) = v41;
  v44 = *(_DWORD *)(a1 + 164);
  plLbound[0] = 0;
  v45 = SafeArrayGetLBound(v35, 1u, plLbound);
  if ( v45 < 0 )
    ATL::BaseAtlThrow(v45);
  if ( plLbound[0] > 2 )
    goto LABEL_125;
  rgsabound.cElements = 0;
  v46 = SafeArrayGetUBound(v35, 1u, (LONG *)&rgsabound);
  if ( v46 < 0 )
    ATL::BaseAtlThrow(v46);
  if ( (int)rgsabound.cElements < 2 )
LABEL_125:
    ATL::BaseAtlThrow(-2147024809);
  *((_DWORD *)v35->pvData + 2 - plLbound[0]) = v44;
  v47 = v73;
  v48 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(*v73 + 104);
  rgsabound = 0;
  v49 = SafeArrayCopy(v27, (SAFEARRAY **)&rgsabound);
  Vartype = v49;
  if ( v49 < 0 )
  {
    rgsabound_8.lVal = v49;
  }
  else
  {
    Vartype = SafeArrayGetVartype(v27, &rgsabound_8.vt);
    vt = rgsabound_8.vt;
    if ( Vartype >= 0 && rgsabound_8.vt == 13 && (v27->fFeatures & 0x440) == 0x440 )
      vt = 9;
    if ( Vartype >= 0 )
    {
      rgsabound_8.vt = vt | 0x2000;
      rgsabound_8.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
      goto LABEL_61;
    }
    rgsabound_8.lVal = Vartype;
  }
  rgsabound_8.vt = 10;
LABEL_61:
  if ( Vartype < 0 )
  {
    if ( Vartype != -2147024882 )
      ATL::BaseAtlThrow(Vartype);
    ATL::BaseAtlThrow(-2147024882);
  }
  v75 = rgsabound_8;
  v52 = v48(v47, L"pixelOffset", &v75);
  VariantClear(&rgsabound_8);
  if ( v52 < 0 )
    ATL::BaseAtlThrow(v52);
  v53 = *v73;
  v54 = *(_DWORD *)(a1 + 144);
  rgsabound_8.vt = 4;
  rgsabound_8.lVal = v54;
  v75 = rgsabound_8;
  v55 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v53 + 104))(
          v73,
          L"initialThreshold",
          &v75);
  VariantClear(&rgsabound_8);
  if ( v55 < 0 )
    ATL::BaseAtlThrow(v55);
  v56 = *v73;
  v57 = *(_DWORD *)(a1 + 152);
  rgsabound_8.vt = 4;
  rgsabound_8.lVal = v57;
  v75 = rgsabound_8;
  v58 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v56 + 104))(
          v73,
          L"coldPixelPercentage",
          &v75);
  VariantClear(&rgsabound_8);
  if ( v58 < 0 )
    ATL::BaseAtlThrow(v58);
  v59 = v73;
  v60 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(*v73 + 104);
  rgsabound = 0;
  v61 = SafeArrayCopy(v35, (SAFEARRAY **)&rgsabound);
  v62 = v61;
  if ( v61 < 0 )
  {
    rgsabound_8.lVal = v61;
    goto LABEL_76;
  }
  v62 = SafeArrayGetVartype(v35, &rgsabound_8.vt);
  v63 = rgsabound_8.vt;
  if ( v62 >= 0 && rgsabound_8.vt == 13 && (v35->fFeatures & 0x440) == 0x440 )
    v63 = 9;
  if ( v62 < 0 )
  {
    rgsabound_8.lVal = v62;
LABEL_76:
    rgsabound_8.vt = 10;
    goto LABEL_77;
  }
  rgsabound_8.vt = v63 | 0x2000;
  rgsabound_8.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
LABEL_77:
  if ( v62 < 0 )
  {
    if ( v62 != -2147024882 )
      ATL::BaseAtlThrow(v62);
    ATL::BaseAtlThrow(-2147024882);
  }
  v75 = rgsabound_8;
  v64 = v60(v59, L"whiteBalance", &v75);
  VariantClear(&rgsabound_8);
  if ( v64 < 0 )
    ATL::BaseAtlThrow(v64);
  v65 = v76;
  v66 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const wchar_t *, __int64))(*v73 + 112))(v73, 0, L"image", v76);
  if ( v66 < 0 )
    ATL::BaseAtlThrow(v66);
  v67 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *))(*v73 + 88))(v73, L"HotPixel");
  if ( v67 < 0 )
    ATL::BaseAtlThrow(v67);
  v68 = v77;
  v69 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v73 + 120))(v73, v77);
  if ( v69 < 0 )
    ATL::BaseAtlThrow(v69);
  if ( SafeArrayUnlock(v35) >= 0 )
    SafeArrayDestroy(v35);
  result = SafeArrayUnlock(v27);
  if ( result >= 0 )
    result = SafeArrayDestroy(v27);
  if ( v68 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
  if ( v78 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
  if ( v65 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  if ( v79[0] )
    result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v79[0] + 16LL))(v79[0]);
LABEL_97:
  if ( v73 )
    return (*(__int64 (__fastcall **)(__int64 *))(*v73 + 16))(v73);
  return result;
}

```

## disassembly

```asm
0x180495618  mov     rax, rsp
0x18049561b  push    rbp
0x18049561c  push    rbx
0x18049561d  push    rsi
0x18049561e  push    rdi
0x18049561f  push    r12
0x180495621  push    r13
0x180495623  push    r14
0x180495625  push    r15
0x180495627  lea     rbp, [rax-58h]
0x18049562b  sub     rsp, 118h
0x180495632  movaps  xmmword ptr [rax-58h], xmm6
0x180495636  mov     rax, cs:__security_cookie
0x18049563d  xor     rax, rsp
0x180495640  mov     qword ptr [rbp+50h+var_58], rax
0x180495644  movzx   r14d, r9b
0x180495648  mov     rsi, r8
0x18049564b  mov     rdi, rdx
0x18049564e  mov     r15, rcx
0x180495651  mov     rbx, [rbp+50h+arg_28]
0x180495658  xor     r12d, r12d
0x18049565b  mov     [rsp+150h+var_D8], r12
0x180495660  mov     rcx, [rcx+80h]
0x180495667  mov     rax, [rcx]
0x18049566a  lea     rdx, [rsp+150h+var_D8]
0x18049566f  mov     rax, [rax+0A8h]
0x180495676  call    cs:__guard_dispatch_icall_fptr
0x18049567c  test    eax, eax
0x18049567e  js      loc_180495EBE
0x180495684  xorps   xmm0, xmm0
0x180495687  xor     eax, eax
0x180495689  movups  [rbp+50h+var_78], xmm0
0x18049568d  mov     [rbp+50h+var_68], rax
0x180495691  mov     [rbp+50h+var_60], eax
0x180495694  mov     rax, [rdi]
0x180495697  lea     rdx, [rbp+50h+var_78]
0x18049569b  mov     rcx, rdi
0x18049569e  mov     rax, [rax+38h]
0x1804956a2  call    cs:__guard_dispatch_icall_fptr
0x1804956a8  test    eax, eax
0x1804956aa  js      loc_180495EA0
0x1804956b0  movsxd  rcx, dword ptr [rbp+50h+var_78+0Ch]
0x1804956b4  movsxd  r8, dword ptr [rbp+50h+var_68+4]
0x1804956b8  add     r8, rcx
0x1804956bb  mov     r13d, 80000000h
0x1804956c1  lea     rax, [r8+r13]
0x1804956c5  mov     edx, 0FFFFFFFFh
0x1804956ca  cmp     rax, rdx
0x1804956cd  ja      loc_180495FAF
0x1804956d3  movsxd  r9, dword ptr [rbp+50h+var_68]
0x1804956d7  movsxd  r10, [rbp+50h+var_60]
0x1804956db  add     r10, r9
0x1804956de  lea     rax, [r10+r13]
0x1804956e2  cmp     rax, rdx
0x1804956e5  ja      loc_180495FAF
0x1804956eb  movups  xmm0, xmmword ptr [rsi]
0x1804956ee  movups  [rbp+50h+var_D0], xmm0
0x1804956f2  movd    edx, xmm0
0x1804956f6  cmp     edx, ecx
0x1804956f8  cmovle  edx, ecx
0x1804956fb  mov     dword ptr [rbp+50h+var_D0], edx
0x1804956fe  mov     ecx, dword ptr [rbp+50h+var_D0+4]
0x180495701  cmp     ecx, r9d
0x180495704  cmovle  ecx, r9d
0x180495708  mov     dword ptr [rbp+50h+var_D0+4], ecx
0x18049570b  mov     r9d, dword ptr [rbp+50h+var_D0+8]
0x18049570f  cmp     r9d, r8d
0x180495712  cmovge  r9d, r8d
0x180495716  mov     r8d, dword ptr [rbp+50h+var_D0+0Ch]
0x18049571a  cmp     r8d, r10d
0x18049571d  cmovge  r8d, r10d
0x180495721  cmp     edx, r9d
0x180495724  jg      short loc_18049572B
0x180495726  cmp     ecx, r8d
0x180495729  jle     short loc_18049573D
0x18049572b  mov     r8d, r12d
0x18049572e  mov     r9d, r12d
0x180495731  mov     ecx, r12d
0x180495734  mov     dword ptr [rbp+50h+var_D0+4], ecx
0x180495737  mov     edx, r12d
0x18049573a  mov     dword ptr [rbp+50h+var_D0], edx
0x18049573d  cmp     edx, r9d
0x180495740  jge     loc_180495E5E
0x180495746  cmp     ecx, r8d
0x180495749  jge     loc_180495E5E
0x18049574f  mov     r11, [r15+80h]
0x180495756  mov     rax, [r11]
0x180495759  mov     rsi, [rax+0F8h]
0x180495760  movsxd  r10, r8d
0x180495763  movsxd  rax, ecx
0x180495766  sub     r10, rax
0x180495769  lea     rax, [r10+r13]
0x18049576d  mov     ecx, 0FFFFFFFFh
0x180495772  cmp     rax, rcx
0x180495775  ja      loc_180495FAF
0x18049577b  movsxd  r8, r9d
0x18049577e  movsxd  rax, edx
0x180495781  sub     r8, rax
0x180495784  lea     rax, [r8+r13]
0x180495788  cmp     rax, rcx
0x18049578b  ja      loc_180495FAF
0x180495791  mov     [rsp+150h+rgsabound.cElements], r8d
0x180495796  mov     [rsp+150h+rgsabound.lLbound], r10d
0x18049579b  mov     [rsp+38h], rbx
0x1804957a0  mov     dword ptr [rsp+150h+var_120], r14d
0x1804957a5  mov     edx, dword ptr [rbp+50h+var_78+8]
0x1804957a8  mov     [rsp+150h+var_128], edx
0x1804957ac  mov     [rsp+150h+var_130], r12d
0x1804957b1  mov     r9d, [rbp+50h+arg_20]
0x1804957b8  mov     r8, qword ptr [rsp+150h+rgsabound.cElements]
0x1804957bd  mov     rdx, qword ptr [rbp+50h+var_D0]
0x1804957c1  mov     rcx, r11
0x1804957c4  mov     rax, rsi
0x1804957c7  call    cs:__guard_dispatch_icall_fptr
0x1804957cd  test    eax, eax
0x1804957cf  js      loc_180495FA7
0x1804957d5  mov     [rbp+50h+var_88], r12
0x1804957d9  mov     [rbp+50h+var_A0], r12
0x1804957dd  lea     rax, [rbp+50h+var_A0]
0x1804957e1  mov     qword ptr [rsp+150h+var_130], rax
0x1804957e6  lea     r9, [rbp+50h+var_88]
0x1804957ea  xor     r8d, r8d
0x1804957ed  mov     rdx, rdi
0x1804957f0  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x1804957f5  mov     [rbp+50h+var_90], r12
0x1804957f9  mov     [rbp+50h+var_98], r12
0x1804957fd  lea     rax, [rbp+50h+var_98]
0x180495801  mov     qword ptr [rsp+150h+var_130], rax
0x180495806  lea     r9, [rbp+50h+var_90]
0x18049580a  mov     r13d, 1
0x180495810  mov     r8d, r13d
0x180495813  mov     rdx, [rbx]
0x180495816  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x18049581b  lea     esi, [r13+1]
0x18049581f  mov     qword ptr [rsp+150h+rgsabound.cElements], rsi
0x180495824  lea     ecx, [rsi+2]; vt
0x180495827  lea     r8, [rsp+150h+rgsabound]; rgsabound
0x18049582c  mov     edx, r13d; cDims
0x18049582f  call    cs:__imp_SafeArrayCreate
0x180495835  mov     rdi, rax
0x180495838  mov     [rbp+50h+var_80], rax
0x18049583c  mov     r14d, 8007000Eh
0x180495842  test    rax, rax
0x180495845  jnz     short loc_18049584C
0x180495847  mov     eax, r14d
0x18049584a  jmp     short loc_180495855
0x18049584c  mov     rcx, rdi; psa
0x18049584f  call    cs:__imp_SafeArrayLock
0x180495855  test    eax, eax
0x180495857  js      loc_180495EC9
0x18049585d  test    rdi, rdi
0x180495860  jz      loc_180495ED4
0x180495866  mov     [rsp+150h+plLbound], r12d
0x18049586b  lea     r8, [rsp+150h+plLbound]; plLbound
0x180495870  mov     edx, r13d; nDim
0x180495873  mov     rcx, rdi; psa
0x180495876  call    cs:__imp_SafeArrayGetLBound
0x18049587c  test    eax, eax
0x18049587e  js      loc_180495EDF
0x180495884  movsxd  rbx, [rsp+150h+plLbound]
0x180495889  test    ebx, ebx
0x18049588b  jg      loc_180495F99
0x180495891  mov     [rsp+150h+plLbound], r12d
0x180495896  lea     r8, [rsp+150h+plLbound]; plUbound
0x18049589b  mov     edx, r13d; nDim
0x18049589e  mov     rcx, rdi; psa
0x1804958a1  call    cs:__imp_SafeArrayGetUBound
0x1804958a7  test    eax, eax
0x1804958a9  js      loc_180495EE7
0x1804958af  cmp     [rsp+150h+plLbound], r12d
0x1804958b4  jl      loc_180495F99
0x1804958ba  movd    xmm0, dword ptr [rbp+50h+var_68+4]
0x1804958bf  cvtdq2ps xmm0, xmm0
0x1804958c2  movss   xmm6, cs:__real@3f800000
0x1804958ca  movaps  xmm1, xmm6
0x1804958cd  divss   xmm1, xmm0
0x1804958d1  mov     rcx, rbx
0x1804958d4  shl     rcx, 2
0x1804958d8  mov     rax, [rdi+10h]
0x1804958dc  sub     rax, rcx
0x1804958df  movss   dword ptr [rax], xmm1
0x1804958e3  mov     [rsp+150h+plLbound], r12d
0x1804958e8  lea     r8, [rsp+150h+plLbound]; plLbound
0x1804958ed  mov     edx, r13d; nDim
0x1804958f0  mov     rcx, rdi; psa
0x1804958f3  call    cs:__imp_SafeArrayGetLBound
0x1804958f9  test    eax, eax
0x1804958fb  js      loc_180495EEF
0x180495901  cmp     [rsp+150h+plLbound], r13d
0x180495906  jg      loc_180495F99
0x18049590c  mov     [rsp+150h+rgsabound.cElements], r12d
0x180495911  lea     r8, [rsp+150h+rgsabound]; plUbound
0x180495916  mov     edx, r13d; nDim
0x180495919  mov     rcx, rdi; psa
0x18049591c  call    cs:__imp_SafeArrayGetUBound
0x180495922  test    eax, eax
0x180495924  js      loc_180495EF7
0x18049592a  cmp     [rsp+150h+rgsabound.cElements], r13d
0x18049592f  jl      loc_180495F99
0x180495935  movd    xmm0, [rbp+50h+var_60]
0x18049593a  cvtdq2ps xmm0, xmm0
0x18049593d  divss   xmm6, xmm0
0x180495941  mov     eax, r13d
0x180495944  sub     eax, [rsp+150h+plLbound]
0x180495948  movsxd  rcx, eax
0x18049594b  mov     rax, [rdi+10h]
0x18049594f  movss   dword ptr [rax+rcx*4], xmm6
0x180495954  mov     qword ptr [rsp+150h+rgsabound.cElements], 3
0x18049595d  mov     ecx, 4; vt
0x180495962  lea     r8, [rsp+150h+rgsabound]; rgsabound
0x180495967  mov     edx, r13d; cDims
0x18049596a  call    cs:__imp_SafeArrayCreate
0x180495970  mov     rbx, rax
0x180495973  mov     qword ptr [rbp+50h+var_D0], rax
0x180495977  test    rax, rax
0x18049597a  jnz     short loc_180495981
0x18049597c  mov     eax, r14d
0x18049597f  jmp     short loc_18049598A
0x180495981  mov     rcx, rbx; psa
0x180495984  call    cs:__imp_SafeArrayLock
0x18049598a  test    eax, eax
0x18049598c  js      loc_180495EFF
0x180495992  movss   xmm6, dword ptr [r15+9Ch]
0x18049599b  test    rbx, rbx
0x18049599e  jz      loc_180495F0B
0x1804959a4  mov     [rsp+150h+rgsabound.cElements], r12d
0x1804959a9  lea     r8, [rsp+150h+rgsabound]; plLbound
0x1804959ae  mov     edx, r13d; nDim
0x1804959b1  mov     rcx, rbx; psa
0x1804959b4  call    cs:__imp_SafeArrayGetLBound
0x1804959ba  test    eax, eax
0x1804959bc  js      loc_180495F16
0x1804959c2  movsxd  r14, [rsp+150h+rgsabound.cElements]
0x1804959c7  test    r14d, r14d
0x1804959ca  jg      loc_180495F8A
0x1804959d0  mov     [rsp+150h+rgsabound.cElements], r12d
0x1804959d5  lea     r8, [rsp+150h+rgsabound]; plUbound
0x1804959da  mov     edx, r13d; nDim
0x1804959dd  mov     rcx, rbx; psa
0x1804959e0  call    cs:__imp_SafeArrayGetUBound
0x1804959e6  test    eax, eax
0x1804959e8  js      loc_180495F1E
0x1804959ee  cmp     [rsp+150h+rgsabound.cElements], r12d
0x1804959f3  jl      loc_180495F8A
0x1804959f9  mov     rcx, r14
0x1804959fc  shl     rcx, 2
0x180495a00  mov     rax, [rbx+10h]
0x180495a04  sub     rax, rcx
0x180495a07  movss   dword ptr [rax], xmm6
0x180495a0b  movss   xmm6, dword ptr [r15+0A0h]
0x180495a14  mov     [rsp+150h+plLbound], r12d
0x180495a19  lea     r8, [rsp+150h+plLbound]; plLbound
0x180495a1e  mov     edx, r13d; nDim
0x180495a21  mov     rcx, rbx; psa
0x180495a24  call    cs:__imp_SafeArrayGetLBound
0x180495a2a  test    eax, eax
0x180495a2c  js      loc_180495F26
0x180495a32  cmp     [rsp+150h+plLbound], r13d
0x180495a37  jg      loc_180495F8A
0x180495a3d  mov     [rsp+150h+rgsabound.cElements], r12d
0x180495a42  lea     r8, [rsp+150h+rgsabound]; plUbound
0x180495a47  mov     edx, r13d; nDim
0x180495a4a  mov     rcx, rbx; psa
0x180495a4d  call    cs:__imp_SafeArrayGetUBound
0x180495a53  test    eax, eax
0x180495a55  js      loc_180495F2E
0x180495a5b  cmp     [rsp+150h+rgsabound.cElements], r13d
0x180495a60  jl      loc_180495F8A
0x180495a66  mov     eax, r13d
0x180495a69  sub     eax, [rsp+150h+plLbound]
0x180495a6d  movsxd  rcx, eax
0x180495a70  mov     rax, [rbx+10h]
0x180495a74  movss   dword ptr [rax+rcx*4], xmm6
0x180495a79  movss   xmm6, dword ptr [r15+0A4h]
0x180495a82  mov     [rsp+150h+plLbound], r12d
0x180495a87  lea     r8, [rsp+150h+plLbound]; plLbound
0x180495a8c  mov     edx, r13d; nDim
0x180495a8f  mov     rcx, rbx; psa
0x180495a92  call    cs:__imp_SafeArrayGetLBound
0x180495a98  test    eax, eax
0x180495a9a  js      loc_180495F36
0x180495aa0  cmp     [rsp+150h+plLbound], esi
0x180495aa4  jg      loc_180495F8A
0x180495aaa  mov     [rsp+150h+rgsabound.cElements], r12d
0x180495aaf  lea     r8, [rsp+150h+rgsabound]; plUbound
0x180495ab4  mov     edx, r13d; nDim
0x180495ab7  mov     rcx, rbx; psa
0x180495aba  call    cs:__imp_SafeArrayGetUBound
0x180495ac0  test    eax, eax
0x180495ac2  js      loc_180495F3E
0x180495ac8  cmp     [rsp+150h+rgsabound.cElements], esi
0x180495acc  jl      loc_180495F8A
0x180495ad2  sub     esi, [rsp+150h+plLbound]
0x180495ad6  movsxd  rcx, esi
0x180495ad9  mov     rax, [rbx+10h]
0x180495add  movss   dword ptr [rax+rcx*4], xmm6
0x180495ae2  mov     rsi, [rsp+150h+var_D8]
0x180495ae7  mov     rax, [rsi]
0x180495aea  mov     r14, [rax+68h]
0x180495aee  mov     qword ptr [rsp+150h+rgsabound.cElements], r12
  ... truncated ...
```
