# CaptureOnePostProcessEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x18050d290`
- end: `0x18050e1c1`
- name: `?OnPropertyChanged@CaptureOnePostProcessEffect@@UEAAJPEB_W@Z`
- size: `3889`
- prototype: `int(CaptureOnePostProcessEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1801beff8`
- `0x1804c6944`
- `0x18050d290`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18050d36f`
- `KERNEL32!CompareStringW` at `0x18050d39e`
- `KERNEL32!CompareStringW` at `0x18050d3c9`
- `KERNEL32!CompareStringW` at `0x18050d576`
- `KERNEL32!CompareStringW` at `0x18050d5a1`
- `KERNEL32!CompareStringW` at `0x18050d5cc`
- `KERNEL32!CompareStringW` at `0x18050d5f7`
- `KERNEL32!CompareStringW` at `0x18050d622`
- `KERNEL32!CompareStringW` at `0x18050d64d`
- `KERNEL32!CompareStringW` at `0x18050d678`
- `KERNEL32!CompareStringW` at `0x18050d6a3`
- `KERNEL32!CompareStringW` at `0x18050d6ce`
- `KERNEL32!CompareStringW` at `0x18050d6f9`
- `KERNEL32!CompareStringW` at `0x18050d724`
- `KERNEL32!CompareStringW` at `0x18050d74f`
- `KERNEL32!CompareStringW` at `0x18050d8c9`
- `KERNEL32!CompareStringW` at `0x18050d9b4`
- `KERNEL32!CompareStringW` at `0x18050dbe6`
- `KERNEL32!CompareStringW` at `0x18050dcc2`
- `KERNEL32!CompareStringW` at `0x18050d36f`
- `KERNEL32!CompareStringW` at `0x18050d39e`
- `KERNEL32!CompareStringW` at `0x18050d3c9`
- `KERNEL32!CompareStringW` at `0x18050d576`
- `KERNEL32!CompareStringW` at `0x18050d5a1`
- `KERNEL32!CompareStringW` at `0x18050d5cc`
- `KERNEL32!CompareStringW` at `0x18050d5f7`
- `KERNEL32!CompareStringW` at `0x18050d622`
- `KERNEL32!CompareStringW` at `0x18050d64d`
- `KERNEL32!CompareStringW` at `0x18050d678`
- `KERNEL32!CompareStringW` at `0x18050d6a3`
- `KERNEL32!CompareStringW` at `0x18050d6ce`
- `KERNEL32!CompareStringW` at `0x18050d6f9`
- `KERNEL32!CompareStringW` at `0x18050d724`
- `KERNEL32!CompareStringW` at `0x18050d74f`
- `KERNEL32!CompareStringW` at `0x18050d8c9`
- `KERNEL32!CompareStringW` at `0x18050d9b4`
- `KERNEL32!CompareStringW` at `0x18050dbe6`
- `KERNEL32!CompareStringW` at `0x18050dcc2`
- `OLEAUT32!__imp_VariantInit` at `0x18050d2ef`
- `OLEAUT32!__imp_VariantInit` at `0x18050daaa`
- `OLEAUT32!__imp_VariantInit` at `0x18050d2ef`
- `OLEAUT32!__imp_VariantInit` at `0x18050daaa`
- `OLEAUT32!__imp_VariantClear` at `0x18050d89f`
- `OLEAUT32!__imp_VariantClear` at `0x18050dbbe`
- `OLEAUT32!__imp_VariantClear` at `0x18050d89f`
- `OLEAUT32!__imp_VariantClear` at `0x18050dbbe`
- `VCRUNTIME140!wcschr` at `0x18050d765`
- `VCRUNTIME140!wcschr` at `0x18050d77c`
- `VCRUNTIME140!wcschr` at `0x18050d765`
- `VCRUNTIME140!wcschr` at `0x18050d77c`

## string_xrefs

- `0x18050d70c`: `Amount`
- `0x18050dcaa`: `EnableCacheBelowRedEye`
- `0x18050dbce`: `EnableCacheBelowSharpen`
- `0x18050dc0e`: `CacheBelowSharpen`
- `0x18050dcea`: `CacheBelowRedEye`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CaptureOnePostProcessEffect::OnPropertyChanged(CaptureOnePostProcessEffect *this, const wchar_t *a2)
{
  int v4; // eax
  int v5; // eax
  BOOL v6; // esi
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  wchar_t *v12; // rsi
  __int64 v13; // r8
  __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 result; // rax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rax
  int v36; // eax
  int v37; // eax
  __int64 v38; // rax
  int v39; // eax
  int v40; // eax
  __int64 v41; // rax
  int v42; // eax
  int v43; // [rsp+30h] [rbp-98h] BYREF
  _DWORD v44[4]; // [rsp+38h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-80h] BYREF
  VARIANTARG v46; // [rsp+60h] [rbp-68h] BYREF
  VARIANTARG v47; // [rsp+80h] [rbp-48h] BYREF
  __int64 *v48; // [rsp+D8h] [rbp+10h] BYREF
  __int64 v49; // [rsp+E0h] [rbp+18h] BYREF

  try
  {
    if ( !a2 )
      ATL::BaseAtlThrow(-2147467261);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 272LL))(*((_QWORD *)this + 16));
    if ( v4 < 0 )
      ATL::BaseAtlThrow(v4);
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           a2,
           &pvarg);
    if ( v5 == -2147024882 || v5 == -2045378032 || v5 == -2045312765 || v5 == -2045247216 )
      ATL::BaseAtlThrow(v5);
    if ( v5 < 0 )
      ATL::BaseAtlThrow(v5);
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"DestinationColorProfile", -1) == 2
      || CompareStringW(0x7Fu, 1u, a2, -1, L"SourceColorProfile", -1) == 2 )
    {
      v48 = 0;
      v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
             *((_QWORD *)this + 18),
             L"ColorProfileEffect",
             &v48);
      if ( v9 < 0 )
        ATL::BaseAtlThrow(v9);
      if ( !v48 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      v10 = *v48;
      v46 = pvarg;
      v11 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v10 + 104))(v48, a2, &v46);
      if ( v11 == -2147024882 || v11 == -2045378032 || v11 == -2045312765 || v11 == -2045247216 )
        ATL::BaseAtlThrow(v11);
      if ( v11 < 0 )
        ATL::BaseAtlThrow(v11);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"EnableColorProfile", -1) == 2 )
    {
      if ( pvarg.vt != 11 )
        ATL::BaseAtlThrow(-2147024809);
      v6 = pvarg.iVal != 0;
      v48 = 0;
      v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
             *((_QWORD *)this + 18),
             L"ColorProfileEffect",
             &v48);
      if ( v7 < 0 )
        ATL::BaseAtlThrow(v7);
      if ( !v48 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      v8 = (*(__int64 (__fastcall **)(__int64 *, BOOL))(*v48 + 192))(v48, v6);
      if ( v8 == -2147024882 || v8 == -2045378032 || v8 == -2045312765 || v8 == -2045247216 )
        ATL::BaseAtlThrow(v8);
      if ( v8 < 0 )
        ATL::BaseAtlThrow(v8);
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"TestUpperThreshold", -1) == 2
      || CompareStringW(0x7Fu, 1u, a2, -1, L"TestLowerThreshold", -1) == 2
      || CompareStringW(0x7Fu, 1u, a2, -1, L"UpperThreshold", -1) == 2
      || CompareStringW(0x7Fu, 1u, a2, -1, L"LowerThreshold", -1) == 2
      || CompareStringW(0x7Fu, 1u, a2, -1, L"UpperColor", -1) == 2
      || CompareStringW(0x7Fu, 1u, a2, -1, L"LowerColor", -1) == 2 )
    {
      v48 = 0;
      v40 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"CaptureOneThresholdEffect",
              &v48);
      if ( v40 < 0 )
        ATL::BaseAtlThrow(v40);
      if ( !v48 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      v41 = *v48;
      v47 = pvarg;
      v42 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v41 + 104))(v48, a2, &v47);
      if ( v42 == -2147024882 || v42 == -2045378032 || v42 == -2045312765 || v42 == -2045247216 )
        ATL::BaseAtlThrow(v42);
      if ( v42 < 0 )
        ATL::BaseAtlThrow(v42);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"BandingLuma", -1) == 2
           || CompareStringW(0x7Fu, 1u, a2, -1, L"BandingChroma", -1) == 2
           || CompareStringW(0x7Fu, 1u, a2, -1, L"NoiseDistribution", -1) == 2 )
    {
      v48 = 0;
      v37 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"CaptureOneBandingSuppressionEffect",
              &v48);
      if ( v37 < 0 )
        ATL::BaseAtlThrow(v37);
      if ( !v48 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      v38 = *v48;
      v47 = pvarg;
      v39 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v38 + 104))(v48, a2, &v47);
      if ( v39 == -2147024882 || v39 == -2045378032 || v39 == -2045312765 || v39 == -2045247216 )
        ATL::BaseAtlThrow(v39);
      if ( v39 < 0 )
        ATL::BaseAtlThrow(v39);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Threshold", -1) == 2
           || CompareStringW(0x7Fu, 1u, a2, -1, L"Amount", -1) == 2
           || CompareStringW(0x7Fu, 1u, a2, -1, L"Radius", -1) == 2 )
    {
      v48 = 0;
      v34 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"SharpenEffect",
              &v48);
      if ( v34 < 0 )
        ATL::BaseAtlThrow(v34);
      if ( !v48 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      v35 = *v48;
      v47 = pvarg;
      v36 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v35 + 104))(v48, a2, &v47);
      if ( v36 == -2147024882 || v36 == -2045378032 || v36 == -2045312765 || v36 == -2045247216 )
        ATL::BaseAtlThrow(v36);
      if ( v36 < 0 )
        ATL::BaseAtlThrow(v36);
    }
    else if ( wcschr(a2, 0x2Eu) )
    {
      v12 = wcschr(a2, 0x2Eu);
      v13 = v12 - a2;
      if ( (unsigned __int64)(v13 - 1) > 0x7FFFFFFE )
        ATL::BaseAtlThrow(-2147024809);
      ATL::CSimpleStringT<wchar_t,0>::CSimpleStringT<wchar_t,0>(&v49, a2, v13, &g_stringCRTMgr);
      v48 = 0;
      v14 = v49;
      v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              v49,
              &v48);
      if ( v15 < 0 )
        ATL::BaseAtlThrow(v15);
      if ( !v48 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      v16 = *v48;
      v46 = pvarg;
      v17 = (*(__int64 (__fastcall **)(__int64 *, wchar_t *, VARIANTARG *))(v16 + 104))(v48, v12 + 1, &v46);
      if ( v17 == -2147024882 || v17 == -2045378032 || v17 == -2045312765 || v17 == -2045247216 )
        ATL::BaseAtlThrow(v17);
      if ( v17 < 0 )
        ATL::BaseAtlThrow(v17);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v14 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v14 - 24) + 8LL))(*(_QWORD *)(v14 - 24));
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"EnableUnSharpMaskScaleAdjustment", -1) == 2 )
    {
      v48 = 0;
      v19 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"SharpenEffect",
              &v48);
      if ( v19 < 0 )
        ATL::BaseAtlThrow(v19);
      if ( !v48 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      v20 = *v48;
      v46 = pvarg;
      v21 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v20 + 104))(v48, a2, &v46);
      if ( v21 == -2147024882 || v21 == -2045378032 || v21 == -2045312765 || v21 == -2045247216 )
        ATL::BaseAtlThrow(v21);
      if ( v21 < 0 )
        ATL::BaseAtlThrow(v21);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"StraighteningAutoFix", -1) == 2 )
    {
      v48 = 0;
      v22 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"StraightenEffect",
              &v48);
      if ( v22 < 0 )
        ATL::BaseAtlThrow(v22);
      if ( !v48 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      v23 = *v48;
      v47 = pvarg;
      v24 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, VARIANTARG *))(v23 + 104))(v48, L"_AutoFix", &v47);
      if ( v24 == -2147024882 || v24 == -2045378032 || v24 == -2045312765 || v24 == -2045247216 )
        ATL::BaseAtlThrow(v24);
      if ( v24 < 0 )
        ATL::BaseAtlThrow(v24);
      memset(&v46, 0, sizeof(v46));
      VariantInit(&v46);
      v48 = 0;
      v25 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"StraightenEffect",
              &v48);
      if ( v25 < 0 )
        ATL::BaseAtlThrow(v25);
      if ( !v48 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      v26 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, VARIANTARG *))(*v48 + 96))(v48, L"Angle", &v46);
      if ( v26 == -2147024882 || v26 == -2045378032 || v26 == -2045312765 || v26 == -2045247216 )
        ATL::BaseAtlThrow(v26);
      if ( v26 < 0 )
        ATL::BaseAtlThrow(v26);
      v27 = (__int64 *)*((_QWORD *)this + 16);
      v28 = *v27;
      v47 = v46;
      v29 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v28 + 104))(
              v27,
              L"StraightenEffect.Angle",
              &v47);
      if ( v29 == -2147024882 || v29 == -2045378032 || v29 == -2045312765 || v29 == -2045247216 )
        ATL::BaseAtlThrow(v29);
      if ( v29 < 0 )
        ATL::BaseAtlThrow(v29);
      VariantClear(&v46);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"EnableCacheBelowSharpen", -1) == 2 )
    {
      v48 = 0;
      v30 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"CacheBelowSharpen",
              &v48);
      if ( v30 < 0 )
        ATL::BaseAtlThrow(v30);
      if ( !v48 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      v31 = (*(__int64 (__fastcall **)(__int64 *, bool))(*v48 + 192))(v48, pvarg.iVal != 0);
      if ( v31 == -2147024882 || v31 == -2045378032 || v31 == -2045312765 || v31 == -2045247216 )
        ATL::BaseAtlThrow(v31);
      if ( v31 < 0 )
        ATL::BaseAtlThrow(v31);
    }
    else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"EnableCacheBelowRedEye", -1) == 2 )
    {
      v48 = 0;
      v32 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
              *((_QWORD *)this + 18),
              L"CacheBelowRedEye",
              &v48);
      if ( v32 < 0 )
        ATL::BaseAtlThrow(v32);
      if ( !v48 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
      v33 = (*(__int64 (__fastcall **)(__int64 *, bool))(*v48 + 192))(v48, pvarg.iVal != 0);
      if ( v33 == -2147024882 || v33 == -2045378032 || v33 == -2045312765 || v33 == -2045247216 )
        ATL::BaseAtlThrow(v33);
      if ( v33 < 0 )
        ATL::BaseAtlThrow(v33);
    }
    VariantClear(&pvarg);
    result = 0;
  }
  catch ( Base::Exception v44 )
  {
    LODWORD(v48) = v44[2];
    goto LABEL_124;
  }
  catch ( long v43 )
  {
    LODWORD(v48) = v43;
LABEL_124:
    result = (unsigned int)v48;
    if ( (_WORD)v48 == 534 )
      return 2249588993LL;
  }
  return result;
}

```

## disassembly

```asm
0x18050d290  mov     [rsp+arg_0], rbx
0x18050d295  mov     [rsp+arg_18], rsi
0x18050d29a  push    rdi
0x18050d29b  push    r12
0x18050d29d  push    r13
0x18050d29f  push    r14
0x18050d2a1  push    r15
0x18050d2a3  sub     rsp, 0A0h
0x18050d2aa  mov     rbx, rdx
0x18050d2ad  mov     rdi, rcx
0x18050d2b0  xor     r14d, r14d
0x18050d2b3  test    rdx, rdx
0x18050d2b6  jz      loc_18050E00C
0x18050d2bc  mov     rcx, [rcx+80h]
0x18050d2c3  mov     rax, [rcx]
0x18050d2c6  mov     rax, [rax+110h]
0x18050d2cd  call    cs:__guard_dispatch_icall_fptr
0x18050d2d3  test    eax, eax
0x18050d2d5  js      loc_18050E016
0x18050d2db  xorps   xmm0, xmm0
0x18050d2de  xor     eax, eax
0x18050d2e0  movups  xmmword ptr [rsp+0C8h+pvarg], xmm0
0x18050d2e5  mov     qword ptr [rsp+0C8h+pvarg+10h], rax
0x18050d2ea  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x18050d2ef  call    cs:__imp_VariantInit
0x18050d2f5  mov     rcx, [rdi+80h]
0x18050d2fc  mov     rax, [rcx]
0x18050d2ff  lea     r8, [rsp+0C8h+pvarg]
0x18050d304  mov     rdx, rbx
0x18050d307  mov     rax, [rax+60h]
0x18050d30b  call    cs:__guard_dispatch_icall_fptr
0x18050d311  cmp     eax, 8007000Eh
0x18050d316  jz      loc_18050E1B7
0x18050d31c  cmp     eax, 86160210h
0x18050d321  jz      loc_18050E1B7
0x18050d327  cmp     eax, 86170103h
0x18050d32c  jz      loc_18050E1B7
0x18050d332  cmp     eax, 86180110h
0x18050d337  jz      loc_18050E1B7
0x18050d33d  test    eax, eax
0x18050d33f  js      loc_18050E021
0x18050d345  or      r15d, 0FFFFFFFFh
0x18050d349  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d34e  lea     rax, aDestinationcol; "DestinationColorProfile"
0x18050d355  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d35a  mov     r9d, r15d; cchCount1
0x18050d35d  mov     r8, rbx; lpString1
0x18050d360  lea     r12d, [r15+2]
0x18050d364  mov     edx, r12d; dwCmpFlags
0x18050d367  lea     r13d, [r12+7Eh]
0x18050d36c  mov     ecx, r13d; Locale
0x18050d36f  call    cs:__imp_CompareStringW
0x18050d375  lea     esi, [r15+3]
0x18050d379  cmp     eax, esi
0x18050d37b  jz      loc_18050D497
0x18050d381  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d386  lea     rax, aSourcecolorpro; "SourceColorProfile"
0x18050d38d  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d392  mov     r9d, r15d; cchCount1
0x18050d395  mov     r8, rbx; lpString1
0x18050d398  mov     edx, r12d; dwCmpFlags
0x18050d39b  mov     ecx, r13d; Locale
0x18050d39e  call    cs:__imp_CompareStringW
0x18050d3a4  cmp     eax, esi
0x18050d3a6  jz      loc_18050D497
0x18050d3ac  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d3b1  lea     rax, aEnablecolorpro; "EnableColorProfile"
0x18050d3b8  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d3bd  mov     r9d, r15d; cchCount1
0x18050d3c0  mov     r8, rbx; lpString1
0x18050d3c3  mov     edx, r12d; dwCmpFlags
0x18050d3c6  mov     ecx, r13d; Locale
0x18050d3c9  call    cs:__imp_CompareStringW
0x18050d3cf  cmp     eax, esi
0x18050d3d1  jnz     loc_18050D559
0x18050d3d7  cmp     word ptr [rsp+0C8h+pvarg], 0Bh
0x18050d3dd  jnz     loc_18050E028
0x18050d3e3  mov     esi, r14d
0x18050d3e6  cmp     word ptr [rsp+0C8h+pvarg+8], r14w
0x18050d3ec  setnz   sil
0x18050d3f0  mov     [rsp+0C8h+arg_8], r14
0x18050d3f8  mov     rcx, [rdi+90h]
0x18050d3ff  mov     rax, [rcx]
0x18050d402  lea     r8, [rsp+0C8h+arg_8]
0x18050d40a  lea     rdx, aColorprofileef; "ColorProfileEffect"
0x18050d411  mov     rax, [rax+98h]
0x18050d418  call    cs:__guard_dispatch_icall_fptr
0x18050d41e  test    eax, eax
0x18050d420  js      loc_18050E032
0x18050d426  mov     rcx, [rsp+0C8h+arg_8]
0x18050d42e  test    rcx, rcx
0x18050d431  jz      loc_18050E039
0x18050d437  mov     rax, [rcx]
0x18050d43a  mov     rax, [rax+10h]
0x18050d43e  call    cs:__guard_dispatch_icall_fptr
0x18050d444  mov     rcx, [rsp+0C8h+arg_8]
0x18050d44c  mov     rax, [rcx]
0x18050d44f  mov     edx, esi
0x18050d451  mov     rax, [rax+0C0h]
0x18050d458  call    cs:__guard_dispatch_icall_fptr
0x18050d45e  cmp     eax, 8007000Eh
0x18050d463  jz      loc_18050E04A
0x18050d469  cmp     eax, 86160210h
0x18050d46e  jz      loc_18050E04A
0x18050d474  cmp     eax, 86170103h
0x18050d479  jz      loc_18050E04A
0x18050d47f  cmp     eax, 86180110h
0x18050d484  jz      loc_18050E04A
0x18050d48a  test    eax, eax
0x18050d48c  js      loc_18050E043
0x18050d492  jmp     loc_18050D554
0x18050d497  mov     [rsp+0C8h+arg_8], r14
0x18050d49f  mov     rcx, [rdi+90h]
0x18050d4a6  mov     rax, [rcx]
0x18050d4a9  lea     r8, [rsp+0C8h+arg_8]
0x18050d4b1  lea     rdx, aColorprofileef; "ColorProfileEffect"
0x18050d4b8  mov     rax, [rax+98h]
0x18050d4bf  call    cs:__guard_dispatch_icall_fptr
0x18050d4c5  test    eax, eax
0x18050d4c7  js      loc_18050E051
0x18050d4cd  mov     rcx, [rsp+0C8h+arg_8]
0x18050d4d5  test    rcx, rcx
0x18050d4d8  jz      loc_18050E058
0x18050d4de  mov     rax, [rcx]
0x18050d4e1  mov     rax, [rax+10h]
0x18050d4e5  call    cs:__guard_dispatch_icall_fptr
0x18050d4eb  mov     rcx, [rsp+0C8h+arg_8]
0x18050d4f3  mov     rax, [rcx]
0x18050d4f6  movups  xmm0, xmmword ptr [rsp+0C8h+pvarg]
0x18050d4fb  movaps  xmmword ptr [rsp+0C8h+var_68], xmm0
0x18050d500  movsd   xmm1, qword ptr [rsp+0C8h+pvarg+10h]
0x18050d506  movsd   qword ptr [rsp+0C8h+var_68+10h], xmm1
0x18050d50c  lea     r8, [rsp+0C8h+var_68]
0x18050d511  mov     rdx, rbx
0x18050d514  mov     rax, [rax+68h]
0x18050d518  call    cs:__guard_dispatch_icall_fptr
0x18050d51e  cmp     eax, 8007000Eh
0x18050d523  jz      loc_18050E1B0
0x18050d529  cmp     eax, 86160210h
0x18050d52e  jz      loc_18050E1B0
0x18050d534  cmp     eax, 86170103h
0x18050d539  jz      loc_18050E1B0
0x18050d53f  cmp     eax, 86180110h
0x18050d544  jz      loc_18050E1B0
0x18050d54a  test    eax, eax
0x18050d54c  js      loc_18050E062
0x18050d552  jmp     short loc_18050D559
0x18050d554  mov     esi, 2
0x18050d559  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d55e  lea     rax, aTestupperthres; "TestUpperThreshold"
0x18050d565  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d56a  mov     r9d, r15d; cchCount1
0x18050d56d  mov     r8, rbx; lpString1
0x18050d570  mov     edx, r12d; dwCmpFlags
0x18050d573  mov     ecx, r13d; Locale
0x18050d576  call    cs:__imp_CompareStringW
0x18050d57c  cmp     eax, esi
0x18050d57e  jz      loc_18050DF13
0x18050d584  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d589  lea     rax, aTestlowerthres; "TestLowerThreshold"
0x18050d590  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d595  mov     r9d, r15d; cchCount1
0x18050d598  mov     r8, rbx; lpString1
0x18050d59b  mov     edx, r12d; dwCmpFlags
0x18050d59e  mov     ecx, r13d; Locale
0x18050d5a1  call    cs:__imp_CompareStringW
0x18050d5a7  cmp     eax, esi
0x18050d5a9  jz      loc_18050DF13
0x18050d5af  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d5b4  lea     rax, aUpperthreshold; "UpperThreshold"
0x18050d5bb  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d5c0  mov     r9d, r15d; cchCount1
0x18050d5c3  mov     r8, rbx; lpString1
0x18050d5c6  mov     edx, r12d; dwCmpFlags
0x18050d5c9  mov     ecx, r13d; Locale
0x18050d5cc  call    cs:__imp_CompareStringW
0x18050d5d2  cmp     eax, esi
0x18050d5d4  jz      loc_18050DF13
0x18050d5da  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d5df  lea     rax, aLowerthreshold; "LowerThreshold"
0x18050d5e6  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d5eb  mov     r9d, r15d; cchCount1
0x18050d5ee  mov     r8, rbx; lpString1
0x18050d5f1  mov     edx, r12d; dwCmpFlags
0x18050d5f4  mov     ecx, r13d; Locale
0x18050d5f7  call    cs:__imp_CompareStringW
0x18050d5fd  cmp     eax, esi
0x18050d5ff  jz      loc_18050DF13
0x18050d605  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d60a  lea     rax, aUppercolor; "UpperColor"
0x18050d611  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d616  mov     r9d, r15d; cchCount1
0x18050d619  mov     r8, rbx; lpString1
0x18050d61c  mov     edx, r12d; dwCmpFlags
0x18050d61f  mov     ecx, r13d; Locale
0x18050d622  call    cs:__imp_CompareStringW
0x18050d628  cmp     eax, esi
0x18050d62a  jz      loc_18050DF13
0x18050d630  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d635  lea     rax, aLowercolor; "LowerColor"
0x18050d63c  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d641  mov     r9d, r15d; cchCount1
0x18050d644  mov     r8, rbx; lpString1
0x18050d647  mov     edx, r12d; dwCmpFlags
0x18050d64a  mov     ecx, r13d; Locale
0x18050d64d  call    cs:__imp_CompareStringW
0x18050d653  cmp     eax, esi
0x18050d655  jz      loc_18050DF13
0x18050d65b  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d660  lea     rax, aBandingluma; "BandingLuma"
0x18050d667  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d66c  mov     r9d, r15d; cchCount1
0x18050d66f  mov     r8, rbx; lpString1
0x18050d672  mov     edx, r12d; dwCmpFlags
0x18050d675  mov     ecx, r13d; Locale
0x18050d678  call    cs:__imp_CompareStringW
0x18050d67e  cmp     eax, esi
0x18050d680  jz      loc_18050DE4A
0x18050d686  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d68b  lea     rax, aBandingchroma_0; "BandingChroma"
0x18050d692  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d697  mov     r9d, r15d; cchCount1
0x18050d69a  mov     r8, rbx; lpString1
0x18050d69d  mov     edx, r12d; dwCmpFlags
0x18050d6a0  mov     ecx, r13d; Locale
0x18050d6a3  call    cs:__imp_CompareStringW
0x18050d6a9  cmp     eax, esi
0x18050d6ab  jz      loc_18050DE4A
0x18050d6b1  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d6b6  lea     rax, aNoisedistribut; "NoiseDistribution"
0x18050d6bd  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d6c2  mov     r9d, r15d; cchCount1
0x18050d6c5  mov     r8, rbx; lpString1
0x18050d6c8  mov     edx, r12d; dwCmpFlags
0x18050d6cb  mov     ecx, r13d; Locale
0x18050d6ce  call    cs:__imp_CompareStringW
0x18050d6d4  cmp     eax, esi
0x18050d6d6  jz      loc_18050DE4A
0x18050d6dc  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d6e1  lea     rax, aThreshold_0; "Threshold"
0x18050d6e8  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d6ed  mov     r9d, r15d; cchCount1
0x18050d6f0  mov     r8, rbx; lpString1
0x18050d6f3  mov     edx, r12d; dwCmpFlags
0x18050d6f6  mov     ecx, r13d; Locale
0x18050d6f9  call    cs:__imp_CompareStringW
0x18050d6ff  cmp     eax, esi
0x18050d701  jz      loc_18050DD81
0x18050d707  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d70c  lea     rax, aAmount; "Amount"
0x18050d713  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d718  mov     r9d, r15d; cchCount1
0x18050d71b  mov     r8, rbx; lpString1
0x18050d71e  mov     edx, r12d; dwCmpFlags
0x18050d721  mov     ecx, r13d; Locale
0x18050d724  call    cs:__imp_CompareStringW
0x18050d72a  cmp     eax, esi
0x18050d72c  jz      loc_18050DD81
0x18050d732  mov     [rsp+0C8h+cchCount2], r15d; cchCount2
0x18050d737  lea     rax, aRadius; "Radius"
0x18050d73e  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050d743  mov     r9d, r15d; cchCount1
0x18050d746  mov     r8, rbx; lpString1
0x18050d749  mov     edx, r12d; dwCmpFlags
0x18050d74c  mov     ecx, r13d; Locale
0x18050d74f  call    cs:__imp_CompareStringW
0x18050d755  cmp     eax, esi
0x18050d757  jz      loc_18050DD81
0x18050d75d  mov     edx, 2Eh ; '.'; Ch
0x18050d762  mov     rcx, rbx; Str
0x18050d765  call    cs:__imp_wcschr
0x18050d76b  test    rax, rax
0x18050d76e  jz      loc_18050D8AC
0x18050d774  mov     edx, 2Eh ; '.'; Ch
0x18050d779  mov     rcx, rbx; Str
0x18050d77c  call    cs:__imp_wcschr
0x18050d782  mov     rsi, rax
0x18050d785  mov     r8, rax
0x18050d788  sub     r8, rbx
0x18050d78b  sar     r8, 1
0x18050d78e  lea     rcx, [r8-1]
0x18050d792  cmp     rcx, 7FFFFFFEh
0x18050d799  ja      loc_18050E069
0x18050d79f  lea     r9, ?g_stringCRTMgr@@3VCAtlStringMgr@ATL@@A; ATL::CAtlStringMgr g_stringCRTMgr
0x18050d7a6  mov     rdx, rbx
0x18050d7a9  lea     rcx, [rsp+0C8h+arg_10]
0x18050d7b1  call    ??0?$CSimpleStringT@_W$0A@@ATL@@QEAA@PEB_WHPEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<wchar_t,0>::CSimpleStringT<wchar_t,0>(wchar_t const *,int,ATL::IAtlStringMgr *)
0x18050d7b6  mov     [rsp+0C8h+arg_8], r14
0x18050d7be  mov     rcx, [rdi+90h]
0x18050d7c5  mov     rax, [rcx]
0x18050d7c8  lea     r8, [rsp+0C8h+arg_8]
0x18050d7d0  mov     rbx, [rsp+0C8h+arg_10]
0x18050d7d8  mov     rdx, rbx
0x18050d7db  mov     rax, [rax+98h]
0x18050d7e2  call    cs:__guard_dispatch_icall_fptr
0x18050d7e8  test    eax, eax
0x18050d7ea  js      loc_18050E077
0x18050d7f0  mov     rcx, [rsp+0C8h+arg_8]
0x18050d7f8  test    rcx, rcx
0x18050d7fb  jz      loc_18050E07E
  ... truncated ...
```
