# TransformEffect::HardwareRender(IImageBufferLock *,RectT<IntegerTypes> const &,ChannelFormat,IImageBufferLock *,RectT<IntegerTypes> const &,ChannelFormat,Transform const &,EdgeModes::Mode,bool,InterpolationModes,IShader *)

- ea: `0x1801a854c`
- end: `0x1801a8f27`
- name: `?HardwareRender@TransformEffect@@CAXPEAUIImageBufferLock@@AEBU?$RectT@UIntegerTypes@@@@W4ChannelFormat@@012AEBVTransform@@W4Mode@EdgeModes@@_NW4InterpolationModes@@PEAUIShader@@@Z`
- size: `2523`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801a5910`

## callees

- `0x18001db0c`
- `0x1801a2ffc`
- `0x1801a31b8`
- `0x1801a34a8`
- `0x1801a3a80`
- `0x1801a4440`
- `0x1801a49e8`
- `0x1801a854c`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056d14c`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1801a8857`
- `OLEAUT32!__imp_VariantClear` at `0x1801a8a29`
- `OLEAUT32!__imp_VariantClear` at `0x1801a8c66`
- `OLEAUT32!__imp_VariantClear` at `0x1801a8857`
- `OLEAUT32!__imp_VariantClear` at `0x1801a8a29`
- `OLEAUT32!__imp_VariantClear` at `0x1801a8c66`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a8672`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a8993`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a8a4d`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a8672`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a8993`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a8a4d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a8d6b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a8d87`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a8d9e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a8d6b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a8d87`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a8d9e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a8718`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a8aea`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a8b79`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a8718`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a8aea`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a8b79`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a86ea`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a8abb`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a8b50`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a86ea`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a8abb`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a8b50`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a868e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a89af`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a8a69`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a868e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a89af`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a8a69`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a8d5e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a8d7a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a8d91`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a8d5e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a8d7a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a8d91`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801a87a4`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801a8bb7`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801a87a4`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801a8bb7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801a87bc`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801a8bca`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801a87bc`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801a8bca`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801a8d54`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801a8d54`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HRESULT __fastcall TransformEffect::HardwareRender(
        __int64 a1,
        int *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        char a9,
        int a10,
        __int64 a11)
{
  int v13; // eax
  int v14; // eax
  const wchar_t *v15; // rdx
  int v16; // eax
  int v17; // eax
  SAFEARRAY *v18; // rax
  SAFEARRAY *v19; // rdi
  HRESULT v20; // eax
  __int64 v21; // rcx
  float v22; // xmm6_4
  HRESULT LBound; // eax
  __int64 v24; // rsi
  HRESULT UBound; // eax
  __int64 v26; // rcx
  __int64 (__fastcall *v27)(__int64, const wchar_t *, VARIANTARG *); // rsi
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v30; // esi
  __int64 v31; // rax
  SAFEARRAY *v32; // rax
  SAFEARRAY *v33; // rsi
  HRESULT v34; // eax
  int v35; // ebx
  int *v36; // r12
  int v37; // xmm6_4
  __int64 (__fastcall *v38)(__int64, const wchar_t *, VARIANTARG *); // rbx
  int v39; // ebx
  SAFEARRAY *v40; // rax
  SAFEARRAY *v41; // rbx
  HRESULT v42; // eax
  __int64 v43; // rcx
  float v44; // xmm6_4
  HRESULT v45; // eax
  __int64 v46; // r12
  HRESULT v47; // eax
  __int64 v48; // rcx
  float v49; // xmm6_4
  HRESULT v50; // eax
  HRESULT v51; // eax
  __int64 (__fastcall *v52)(__int64, const wchar_t *, VARIANTARG *); // r14
  HRESULT v53; // ecx
  VARTYPE v54; // dx
  int v55; // r14d
  char v56; // al
  BSTR bstrVal; // r14
  int v58; // eax
  int v59; // eax
  int v60; // eax
  __int64 v61; // rcx
  HRESULT result; // eax
  LONG plLbound; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG rgsabound_8; // [rsp+68h] [rbp-A0h] BYREF
  VARIANTARG pvt; // [rsp+88h] [rbp-80h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v68; // [rsp+B0h] [rbp-58h] BYREF
  SAFEARRAY *v69; // [rsp+B8h] [rbp-50h] BYREF
  SAFEARRAY *v70; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v71; // [rsp+C8h] [rbp-40h]
  SAFEARRAY *v72; // [rsp+D0h] [rbp-38h]
  _DWORD v73[16]; // [rsp+D8h] [rbp-30h] BYREF
  _DWORD v74[16]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v75[64]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v76[64]; // [rsp+198h] [rbp+90h] BYREF

  v71 = a7;
  v68 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a4 + 80LL))(a4, 0, &v68);
  if ( v13 < 0 )
    ATL::BaseAtlThrow(v13);
  v67 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a1 + 80LL))(a1, 0, &v67);
  if ( v14 < 0 )
    ATL::BaseAtlThrow(v14);
  if ( a10 )
  {
    if ( a10 == 1 )
    {
      if ( a9 || (v15 = L"TransformEffectBilinearBuiltIn", a6 != 1) )
        v15 = L"TransformEffectBilinearPS";
      v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a11 + 88LL))(a11, v15);
      if ( v16 <= -1 )
        ATL::BaseAtlThrow(v16);
    }
  }
  else
  {
    v17 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a11 + 88LL))(
            a11,
            L"TransformEffectNearestNeighbor");
    if ( v17 < 0 )
      ATL::BaseAtlThrow(v17);
  }
  *(_QWORD *)&rgsabound_8.vt = 2;
  v18 = SafeArrayCreate(4u, 1u, (SAFEARRAYBOUND *)&rgsabound_8);
  v19 = v18;
  v69 = v18;
  if ( v18 )
    v20 = SafeArrayLock(v18);
  else
    v20 = -2147024882;
  if ( v20 < 0 )
    ATL::BaseAtlThrow(v20);
  v21 = a2[2] - (__int64)*a2;
  if ( (unsigned __int64)(v21 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_117;
  v22 = -1.0 / (float)(int)v21;
  if ( !v19 )
    ATL::BaseAtlThrow(-2147467259);
  plLbound = 0;
  LBound = SafeArrayGetLBound(v19, 1u, &plLbound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  v24 = plLbound;
  if ( plLbound > 0 )
    goto LABEL_116;
  plLbound = 0;
  UBound = SafeArrayGetUBound(v19, 1u, &plLbound);
  if ( UBound < 0 )
    ATL::BaseAtlThrow(UBound);
  if ( plLbound < 0 )
LABEL_116:
    ATL::BaseAtlThrow(-2147024809);
  *((float *)v19->pvData - v24) = v22;
  v26 = a2[3] - (__int64)a2[1];
  if ( (unsigned __int64)(v26 + 0x80000000LL) > 0xFFFFFFFF )
LABEL_117:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  *(float *)ATL::CComSafeArray<float,4>::GetAt(&v69, 1) = 1.0 / (float)(int)v26;
  v27 = *(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)a11 + 104LL);
  *(_QWORD *)&rgsabound_8.vt = 0;
  Vartype = SafeArrayCopy(v19, (SAFEARRAY **)&rgsabound_8);
  if ( Vartype < 0 )
    goto LABEL_29;
  Vartype = SafeArrayGetVartype(v19, &pvt.vt);
  vt = pvt.vt;
  if ( Vartype >= 0 && pvt.vt == 13 && (v19->fFeatures & 0x440) == 0x440 )
    vt = 9;
  if ( Vartype < 0 )
  {
LABEL_29:
    pvt.lVal = Vartype;
    pvt.vt = 10;
  }
  else
  {
    pvt.vt = vt | 0x2000;
    pvt.llVal = *(_QWORD *)&rgsabound_8.vt;
  }
  if ( Vartype < 0 )
  {
    if ( Vartype != -2147024882 )
      ATL::BaseAtlThrow(Vartype);
    ATL::BaseAtlThrow(-2147024882);
  }
  rgsabound_8 = pvt;
  v30 = v27(a11, L"pixelOffset", &rgsabound_8);
  VariantClear(&pvt);
  if ( v30 < 0 )
    ATL::BaseAtlThrow(v30);
  memset_0(v73, 0, sizeof(v73));
  v73[15] = 1065353216;
  v73[10] = 1065353216;
  v73[5] = 1065353216;
  v73[0] = 1065353216;
  Transform::Scale(
    (Transform *)v73,
    -1.0,
    1.0,
    1.0,
    -1.0,
    (float)*(int *)a5,
    (float)*(int *)(a5 + 4),
    (float)*(int *)(a5 + 8),
    (float)*(int *)(a5 + 12));
  memset_0(v74, 0, sizeof(v74));
  v74[15] = 1065353216;
  v74[10] = 1065353216;
  v74[5] = 1065353216;
  v74[0] = 1065353216;
  Transform::Scale((Transform *)v74, (float)*a2, (float)a2[1], (float)a2[2], (float)a2[3], -1.0, 1.0, 1.0, -1.0);
  v31 = Transform::operator*(v73, v76, a7);
  Transform::operator*(v31, v75, v74);
  *(_QWORD *)&rgsabound_8.vt = 16;
  v32 = SafeArrayCreate(4u, 1u, (SAFEARRAYBOUND *)&rgsabound_8);
  v33 = v32;
  v70 = v32;
  if ( v32 )
    v34 = SafeArrayLock(v32);
  else
    v34 = -2147024882;
  if ( v34 < 0 )
    ATL::BaseAtlThrow(v34);
  v35 = 0;
  v36 = (int *)v75;
  do
  {
    v37 = *v36;
    *(_DWORD *)ATL::CComSafeArray<float,4>::GetAt(&v70, (unsigned int)v35++) = v37;
    ++v36;
  }
  while ( v35 < 16 );
  v38 = *(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)a11 + 104LL);
  pvt = *(VARIANTARG *)ATL::CComVariant::CComVariant(&rgsabound_8.vt, v33);
  v39 = v38(a11, L"fl4x4TransformMatrix", &pvt);
  VariantClear(&rgsabound_8);
  if ( v39 < 0 )
    ATL::BaseAtlThrow(v39);
  *(_QWORD *)&rgsabound_8.vt = 2;
  v40 = SafeArrayCreate(4u, 1u, (SAFEARRAYBOUND *)&rgsabound_8);
  v41 = v40;
  v72 = v40;
  if ( v40 )
    v42 = SafeArrayLock(v40);
  else
    v42 = -2147024882;
  if ( v42 < 0 )
    ATL::BaseAtlThrow(v42);
  v43 = *(int *)(a5 + 8) - (__int64)*(int *)a5;
  if ( (unsigned __int64)(v43 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_113;
  v44 = (float)(int)v43;
  if ( !v41 )
    ATL::BaseAtlThrow(-2147467259);
  plLbound = 0;
  v45 = SafeArrayGetLBound(v41, 1u, &plLbound);
  if ( v45 < 0 )
    ATL::BaseAtlThrow(v45);
  v46 = plLbound;
  if ( plLbound > 0 )
    goto LABEL_112;
  plLbound = 0;
  v47 = SafeArrayGetUBound(v41, 1u, &plLbound);
  if ( v47 < 0 )
    ATL::BaseAtlThrow(v47);
  if ( plLbound < 0 )
LABEL_112:
    ATL::BaseAtlThrow(-2147024809);
  *((float *)v41->pvData - v46) = v44;
  v48 = *(int *)(a5 + 12) - (__int64)*(int *)(a5 + 4);
  if ( (unsigned __int64)(v48 + 0x80000000LL) > 0xFFFFFFFF )
LABEL_113:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  v49 = (float)(int)v48;
  plLbound = 0;
  v50 = SafeArrayGetLBound(v41, 1u, &plLbound);
  if ( v50 < 0 )
    ATL::BaseAtlThrow(v50);
  if ( plLbound > 1 )
    goto LABEL_112;
  *(_DWORD *)&rgsabound_8.vt = 0;
  v51 = SafeArrayGetUBound(v41, 1u, (LONG *)&rgsabound_8);
  if ( v51 < 0 )
    ATL::BaseAtlThrow(v51);
  if ( *(int *)&rgsabound_8.vt < 1 )
    goto LABEL_112;
  *((float *)v41->pvData + 1 - plLbound) = v49;
  v52 = *(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)a11 + 104LL);
  *(_QWORD *)&rgsabound_8.vt = 0;
  v53 = SafeArrayCopy(v41, (SAFEARRAY **)&rgsabound_8);
  if ( v53 < 0 )
    goto LABEL_63;
  v53 = SafeArrayGetVartype(v41, &pvt.vt);
  v54 = pvt.vt;
  if ( v53 >= 0 && pvt.vt == 13 && (v41->fFeatures & 0x440) == 0x440 )
    v54 = 9;
  if ( v53 < 0 )
  {
LABEL_63:
    pvt.lVal = v53;
    pvt.vt = 10;
  }
  else
  {
    pvt.vt = v54 | 0x2000;
    pvt.llVal = *(_QWORD *)&rgsabound_8.vt;
  }
  if ( v53 < 0 )
  {
    if ( v53 != -2147024882 )
      ATL::BaseAtlThrow(v53);
    ATL::BaseAtlThrow(-2147024882);
  }
  rgsabound_8 = pvt;
  v55 = v52(a11, L"rectSourceSize", &rgsabound_8);
  VariantClear(&pvt);
  if ( v55 < 0 )
    ATL::BaseAtlThrow(v55);
  *(_OWORD *)&rgsabound_8.vt = 0u;
  v56 = Transform::PreservesRectangles(v71, a5);
  VertexBuffer::GenerateVertexBuffer(&rgsabound_8, a5 & -(__int64)(v56 != 0));
  bstrVal = rgsabound_8.bstrVal;
  v58 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, LONGLONG))(*(_QWORD *)a11 + 128LL))(
          a11,
          *(unsigned int *)&rgsabound_8.vt,
          rgsabound_8.decVal.Hi32,
          8 * rgsabound_8.decVal.Hi32 + 12,
          rgsabound_8.llVal);
  if ( v58 < 0 )
    ATL::BaseAtlThrow(v58);
  v59 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)a11 + 112LL))(
          a11,
          0,
          L"Input0",
          v68);
  if ( v59 < 0 )
    ATL::BaseAtlThrow(v59);
  v60 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a11 + 120LL))(a11, v67);
  if ( v60 < 0 )
    ATL::BaseAtlThrow(v60);
  if ( bstrVal )
  {
    v61 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v61 || (*(unsigned int (__fastcall **)(__int64, BSTR))(*(_QWORD *)v61 + 88LL))(v61, bstrVal) != 0 )
      free(bstrVal);
  }
  if ( SafeArrayUnlock(v41) >= 0 )
    SafeArrayDestroy(v41);
  if ( v33 && SafeArrayUnlock(v33) >= 0 )
    SafeArrayDestroy(v33);
  result = SafeArrayUnlock(v19);
  if ( result >= 0 )
    result = SafeArrayDestroy(v19);
  if ( v67 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  if ( v68 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
  return result;
}

```

## disassembly

```asm
0x1801a854c  mov     rax, rsp
0x1801a854f  mov     [rax+10h], rbx
0x1801a8553  push    rbp
0x1801a8554  push    rsi
0x1801a8555  push    rdi
0x1801a8556  push    r12
0x1801a8558  push    r13
0x1801a855a  push    r14
0x1801a855c  push    r15
0x1801a855e  lea     rbp, [rax-148h]
0x1801a8565  sub     rsp, 210h
0x1801a856c  movaps  xmmword ptr [rax-48h], xmm6
0x1801a8570  movaps  xmmword ptr [rax-58h], xmm7
0x1801a8574  movaps  xmmword ptr [rax-68h], xmm8
0x1801a8579  mov     rax, cs:__security_cookie
0x1801a8580  xor     rax, rsp
0x1801a8583  mov     [rbp+140h+var_70], rax
0x1801a858a  mov     rbx, rdx
0x1801a858d  mov     rdi, rcx
0x1801a8590  mov     r13, [rbp+140h+arg_20]
0x1801a8597  mov     r12, [rbp+140h+arg_30]
0x1801a859e  mov     [rbp+140h+var_180], r12
0x1801a85a2  mov     r15, [rbp+140h+arg_50]
0x1801a85a9  xor     esi, esi
0x1801a85ab  mov     [rbp+140h+var_198], rsi
0x1801a85af  mov     rax, [r9]
0x1801a85b2  lea     r8, [rbp+140h+var_198]
0x1801a85b6  xor     edx, edx
0x1801a85b8  mov     rcx, r9
0x1801a85bb  mov     rax, [rax+50h]
0x1801a85bf  call    cs:__guard_dispatch_icall_fptr
0x1801a85c5  test    eax, eax
0x1801a85c7  js      loc_1801A8E37
0x1801a85cd  mov     [rbp+140h+var_1A0], rsi
0x1801a85d1  mov     rax, [rdi]
0x1801a85d4  lea     r8, [rbp+140h+var_1A0]
0x1801a85d8  xor     edx, edx
0x1801a85da  mov     rcx, rdi
0x1801a85dd  mov     rax, [rax+50h]
0x1801a85e1  call    cs:__guard_dispatch_icall_fptr
0x1801a85e7  test    eax, eax
0x1801a85e9  js      loc_1801A8E0B
0x1801a85ef  mov     ecx, [rbp+140h+arg_48]
0x1801a85f5  lea     r14d, [rsi+1]
0x1801a85f9  test    ecx, ecx
0x1801a85fb  jz      short loc_1801A863D
0x1801a85fd  cmp     ecx, r14d
0x1801a8600  jnz     short loc_1801A865C
0x1801a8602  mov     rax, [r15]
0x1801a8605  cmp     [rbp+140h+arg_40], sil
0x1801a860c  jnz     short loc_1801A861E
0x1801a860e  cmp     [rbp+140h+arg_28], r14d
0x1801a8615  lea     rdx, aTransformeffec_0; "TransformEffectBilinearBuiltIn"
0x1801a861c  jz      short loc_1801A8625
0x1801a861e  lea     rdx, aTransformeffec_5; "TransformEffectBilinearPS"
0x1801a8625  mov     rcx, r15
0x1801a8628  mov     rax, [rax+58h]
0x1801a862c  call    cs:__guard_dispatch_icall_fptr
0x1801a8632  cmp     eax, 0FFFFFFFFh
0x1801a8635  jle     loc_1801A8E13
0x1801a863b  jmp     short loc_1801A865C
0x1801a863d  mov     rax, [r15]
0x1801a8640  lea     rdx, aTransformeffec_2; "TransformEffectNearestNeighbor"
0x1801a8647  mov     rcx, r15
0x1801a864a  mov     rax, [rax+58h]
0x1801a864e  call    cs:__guard_dispatch_icall_fptr
0x1801a8654  test    eax, eax
0x1801a8656  js      loc_1801A8F1F
0x1801a865c  mov     qword ptr [rsp+240h+rgsabound.cElements+8], 2
0x1801a8665  mov     ecx, 4; vt
0x1801a866a  lea     r8, [rsp+240h+rgsabound.cElements+8]; rgsabound
0x1801a866f  mov     edx, r14d; cDims
0x1801a8672  call    cs:__imp_SafeArrayCreate
0x1801a8678  mov     rdi, rax
0x1801a867b  mov     [rbp+140h+var_190], rax
0x1801a867f  test    rax, rax
0x1801a8682  jnz     short loc_1801A868B
0x1801a8684  mov     eax, 8007000Eh
0x1801a8689  jmp     short loc_1801A8694
0x1801a868b  mov     rcx, rdi; psa
0x1801a868e  call    cs:__imp_SafeArrayLock
0x1801a8694  test    eax, eax
0x1801a8696  js      loc_1801A8E43
0x1801a869c  movsxd  rax, dword ptr [rbx]
0x1801a869f  movsxd  rcx, dword ptr [rbx+8]
0x1801a86a3  sub     rcx, rax
0x1801a86a6  mov     eax, 80000000h
0x1801a86ab  add     rax, rcx
0x1801a86ae  mov     edx, 0FFFFFFFFh
0x1801a86b3  cmp     rax, rdx
0x1801a86b6  ja      loc_1801A8F16
0x1801a86bc  movd    xmm0, ecx
0x1801a86c0  cvtdq2ps xmm0, xmm0
0x1801a86c3  movss   xmm7, cs:__real@bf800000
0x1801a86cb  movaps  xmm6, xmm7
0x1801a86ce  divss   xmm6, xmm0
0x1801a86d2  test    rdi, rdi
0x1801a86d5  jz      loc_1801A8E4F
0x1801a86db  mov     [rsp+240h+plLbound], esi
0x1801a86df  lea     r8, [rsp+240h+plLbound]; plLbound
0x1801a86e4  mov     edx, r14d; nDim
0x1801a86e7  mov     rcx, rdi; psa
0x1801a86ea  call    cs:__imp_SafeArrayGetLBound
0x1801a86f0  test    eax, eax
0x1801a86f2  js      loc_1801A8E5A
0x1801a86f8  movsxd  rsi, [rsp+240h+plLbound]
0x1801a86fd  test    esi, esi
0x1801a86ff  jg      loc_1801A8F0B
0x1801a8705  mov     [rsp+240h+plLbound], 0
0x1801a870d  lea     r8, [rsp+240h+plLbound]; plUbound
0x1801a8712  mov     edx, r14d; nDim
0x1801a8715  mov     rcx, rdi; psa
0x1801a8718  call    cs:__imp_SafeArrayGetUBound
0x1801a871e  test    eax, eax
0x1801a8720  js      loc_1801A8E62
0x1801a8726  cmp     [rsp+240h+plLbound], 0
0x1801a872b  jl      loc_1801A8F0B
0x1801a8731  mov     rcx, rsi
0x1801a8734  shl     rcx, 2
0x1801a8738  mov     rax, [rdi+10h]
0x1801a873c  sub     rax, rcx
0x1801a873f  movss   dword ptr [rax], xmm6
0x1801a8743  movsxd  rcx, dword ptr [rbx+0Ch]
0x1801a8747  movsxd  rax, dword ptr [rbx+4]
0x1801a874b  sub     rcx, rax
0x1801a874e  mov     eax, 80000000h
0x1801a8753  add     rax, rcx
0x1801a8756  mov     edx, 0FFFFFFFFh
0x1801a875b  cmp     rax, rdx
0x1801a875e  ja      loc_1801A8F16
0x1801a8764  movd    xmm0, ecx
0x1801a8768  cvtdq2ps xmm0, xmm0
0x1801a876b  movss   xmm8, cs:__real@3f800000
0x1801a8774  movaps  xmm6, xmm8
0x1801a8778  divss   xmm6, xmm0
0x1801a877c  mov     edx, r14d
0x1801a877f  lea     rcx, [rbp+140h+var_190]
0x1801a8783  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1801a8788  movss   dword ptr [rax], xmm6
0x1801a878c  mov     rax, [r15]
0x1801a878f  mov     rsi, [rax+68h]
0x1801a8793  mov     qword ptr [rsp+240h+rgsabound.cElements+8], 0
0x1801a879c  lea     rdx, [rsp+240h+rgsabound.cElements+8]; ppsaOut
0x1801a87a1  mov     rcx, rdi; psa
0x1801a87a4  call    cs:__imp_SafeArrayCopy
0x1801a87aa  mov     ecx, eax
0x1801a87ac  mov     eax, 0Ah
0x1801a87b1  test    ecx, ecx
0x1801a87b3  js      short loc_1801A8808
0x1801a87b5  lea     rdx, [rbp+140h+pvt]; pvt
0x1801a87b9  mov     rcx, rdi; psa
0x1801a87bc  call    cs:__imp_SafeArrayGetVartype
0x1801a87c2  mov     ecx, eax; int
0x1801a87c4  movzx   edx, [rbp+140h+pvt]
0x1801a87c8  test    eax, eax
0x1801a87ca  js      short loc_1801A87EB
0x1801a87cc  cmp     dx, 0Dh
0x1801a87d0  jnz     short loc_1801A87EB
0x1801a87d2  movzx   eax, word ptr [rdi+2]
0x1801a87d6  mov     r8d, 440h
0x1801a87dc  and     ax, r8w
0x1801a87e0  cmp     ax, r8w
0x1801a87e4  jnz     short loc_1801A87EB
0x1801a87e6  mov     edx, 9
0x1801a87eb  test    ecx, ecx
0x1801a87ed  js      short loc_1801A8803
0x1801a87ef  or      dx, 2000h
0x1801a87f4  mov     [rbp+140h+pvt], dx
0x1801a87f8  mov     rax, qword ptr [rsp+240h+rgsabound.cElements+8]
0x1801a87fd  mov     qword ptr [rbp+140h+pvt+8], rax
0x1801a8801  jmp     short loc_1801A880F
0x1801a8803  mov     eax, 0Ah
0x1801a8808  mov     dword ptr [rbp+140h+pvt+8], ecx
0x1801a880b  mov     [rbp+140h+pvt], ax
0x1801a880f  test    ecx, ecx
0x1801a8811  jns     short loc_1801A8825
0x1801a8813  mov     eax, 8007000Eh
0x1801a8818  cmp     ecx, eax
0x1801a881a  jz      loc_1801A8E1F
0x1801a8820  jmp     loc_1801A8E6A
0x1801a8825  movups  xmm0, xmmword ptr [rbp+140h+pvt]
0x1801a8829  movaps  xmmword ptr [rsp+240h+rgsabound.cElements+8], xmm0
0x1801a882e  movsd   xmm1, [rbp+140h+var_1B0]
0x1801a8833  movsd   [rsp+240h+var_1D0], xmm1
0x1801a8839  lea     r8, [rsp+240h+rgsabound.cElements+8]
0x1801a883e  lea     rdx, aPixeloffset; "pixelOffset"
0x1801a8845  mov     rcx, r15
0x1801a8848  mov     rax, rsi
0x1801a884b  call    cs:__guard_dispatch_icall_fptr
0x1801a8851  mov     esi, eax
0x1801a8853  lea     rcx, [rbp+140h+pvt]; pvarg
0x1801a8857  call    cs:__imp_VariantClear
0x1801a885d  test    esi, esi
0x1801a885f  js      loc_1801A8F03
0x1801a8865  mov     esi, 40h ; '@'
0x1801a886a  mov     r8d, esi; Size
0x1801a886d  xor     edx, edx; Val
0x1801a886f  lea     rcx, [rbp+140h+var_170]; void *
0x1801a8873  call    memset_0
0x1801a8878  mov     [rbp+140h+var_134], 3F800000h
0x1801a887f  mov     [rbp+140h+var_148], 3F800000h
0x1801a8886  mov     [rbp+140h+var_15C], 3F800000h
0x1801a888d  mov     [rbp+140h+var_170], 3F800000h
0x1801a8894  movd    xmm0, dword ptr [r13+0Ch]
0x1801a889a  cvtdq2ps xmm0, xmm0
0x1801a889d  movd    xmm1, dword ptr [r13+8]
0x1801a88a3  cvtdq2ps xmm1, xmm1
0x1801a88a6  movd    xmm2, dword ptr [r13+4]
0x1801a88ac  cvtdq2ps xmm2, xmm2
0x1801a88af  movd    xmm3, dword ptr [r13+0]
0x1801a88b5  cvtdq2ps xmm3, xmm3
0x1801a88b8  movss   [rsp+240h+var_200], xmm0; float
0x1801a88be  movss   [rsp+240h+var_208], xmm1; float
0x1801a88c4  movss   [rsp+240h+var_210], xmm2; float
0x1801a88ca  movss   [rsp+240h+var_218], xmm3; float
0x1801a88d0  movss   [rsp+240h+var_220], xmm7; float
0x1801a88d6  movaps  xmm3, xmm8; float
0x1801a88da  movaps  xmm2, xmm8; float
0x1801a88de  movaps  xmm1, xmm7; float
0x1801a88e1  lea     rcx, [rbp+140h+var_170]; this
0x1801a88e5  call    ?Scale@Transform@@QEAAXMMMMMMMM@Z; Transform::Scale(float,float,float,float,float,float,float,float)
0x1801a88ea  mov     r8d, esi; Size
0x1801a88ed  xor     edx, edx; Val
0x1801a88ef  lea     rcx, [rbp+140h+var_130]; void *
0x1801a88f3  call    memset_0
0x1801a88f8  mov     [rbp+140h+var_F4], 3F800000h
0x1801a88ff  mov     [rbp+140h+var_108], 3F800000h
0x1801a8906  mov     [rbp+140h+var_11C], 3F800000h
0x1801a890d  mov     [rbp+140h+var_130], 3F800000h
0x1801a8914  movd    xmm0, dword ptr [rbx+0Ch]
0x1801a8919  cvtdq2ps xmm0, xmm0
0x1801a891c  movd    xmm3, dword ptr [rbx+8]
0x1801a8921  cvtdq2ps xmm3, xmm3; float
0x1801a8924  movd    xmm2, dword ptr [rbx+4]
0x1801a8929  cvtdq2ps xmm2, xmm2; float
0x1801a892c  movd    xmm1, dword ptr [rbx]
0x1801a8930  cvtdq2ps xmm1, xmm1; float
0x1801a8933  movss   [rsp+240h+var_200], xmm7; float
0x1801a8939  movss   [rsp+240h+var_208], xmm8; float
0x1801a8940  movss   [rsp+240h+var_210], xmm8; float
0x1801a8947  movss   [rsp+240h+var_218], xmm7; float
0x1801a894d  movss   [rsp+240h+var_220], xmm0; float
0x1801a8953  lea     rcx, [rbp+140h+var_130]; this
0x1801a8957  call    ?Scale@Transform@@QEAAXMMMMMMMM@Z; Transform::Scale(float,float,float,float,float,float,float,float)
0x1801a895c  mov     r8, r12
0x1801a895f  lea     rdx, [rbp+140h+var_B0]
0x1801a8966  lea     rcx, [rbp+140h+var_170]
0x1801a896a  call    ??DTransform@@QEBA?AV0@AEBV0@@Z; Transform::operator*(Transform const &)
0x1801a896f  lea     r8, [rbp+140h+var_130]
0x1801a8973  lea     rdx, [rbp+140h+var_F0]
0x1801a8977  mov     rcx, rax
0x1801a897a  call    ??DTransform@@QEBA?AV0@AEBV0@@Z; Transform::operator*(Transform const &)
0x1801a897f  mov     qword ptr [rsp+240h+rgsabound.cElements+8], 10h
0x1801a8988  lea     ecx, [rsi-3Ch]; vt
0x1801a898b  lea     r8, [rsp+240h+rgsabound.cElements+8]; rgsabound
0x1801a8990  mov     edx, r14d; cDims
0x1801a8993  call    cs:__imp_SafeArrayCreate
0x1801a8999  mov     rsi, rax
0x1801a899c  mov     [rbp+140h+var_188], rax
0x1801a89a0  test    rax, rax
0x1801a89a3  jnz     short loc_1801A89AC
0x1801a89a5  mov     eax, 8007000Eh
0x1801a89aa  jmp     short loc_1801A89B5
0x1801a89ac  mov     rcx, rsi; psa
0x1801a89af  call    cs:__imp_SafeArrayLock
0x1801a89b5  test    eax, eax
0x1801a89b7  js      loc_1801A8E70
0x1801a89bd  xor     ebx, ebx
0x1801a89bf  lea     r12, [rbp+140h+var_F0]
0x1801a89c3  movss   xmm6, dword ptr [r12]
0x1801a89c9  mov     edx, ebx
0x1801a89cb  lea     rcx, [rbp+140h+var_188]
0x1801a89cf  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x1801a89d4  movss   dword ptr [rax], xmm6
0x1801a89d8  add     ebx, r14d
0x1801a89db  lea     r12, [r12+4]
0x1801a89e0  cmp     ebx, 10h
0x1801a89e3  jl      short loc_1801A89C3
0x1801a89e5  mov     rax, [r15]
0x1801a89e8  mov     rbx, [rax+68h]
0x1801a89ec  mov     rdx, rsi; psa
0x1801a89ef  lea     rcx, [rsp+240h+rgsabound.cElements+8]; pvt
0x1801a89f4  call    ??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::CComVariant(tagSAFEARRAY const *)
0x1801a89f9  nop
0x1801a89fa  movups  xmm0, xmmword ptr [rax]
0x1801a89fd  movaps  xmmword ptr [rbp+140h+pvt], xmm0
0x1801a8a01  movsd   xmm1, qword ptr [rax+10h]
0x1801a8a06  movsd   [rbp+140h+var_1B0], xmm1
0x1801a8a0b  lea     r8, [rbp+140h+pvt]
0x1801a8a0f  lea     rdx, aFl4x4transform; "fl4x4TransformMatrix"
0x1801a8a16  mov     rcx, r15
0x1801a8a19  mov     rax, rbx
0x1801a8a1c  call    cs:__guard_dispatch_icall_fptr
0x1801a8a22  mov     ebx, eax
0x1801a8a24  lea     rcx, [rsp+240h+rgsabound.cElements+8]; pvarg
0x1801a8a29  call    cs:__imp_VariantClear
0x1801a8a2f  test    ebx, ebx
0x1801a8a31  js      loc_1801A8EF7
0x1801a8a37  mov     qword ptr [rsp+240h+rgsabound.cElements+8], 2
0x1801a8a40  mov     ecx, 4; vt
  ... truncated ...
```
