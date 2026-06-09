# CaptureOneGGCalibrationEffect::CustomFilter3x3Hardware<1>(IShader *,IImageBuffer *,IImageBuffer *)

- ea: `0x18049b548`
- end: `0x18049ba30`
- name: `??$CustomFilter3x3Hardware@$00@CaptureOneGGCalibrationEffect@@AEAAXPEAUIShader@@PEAUIImageBuffer@@1@Z`
- size: `1256`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1804999ec`
- `0x18049a5ac`

## callees

- `0x1801a2ffc`
- `0x1801a31b8`
- `0x1801e1640`
- `0x18049b548`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18049b7aa`
- `OLEAUT32!__imp_VariantClear` at `0x18049b88d`
- `OLEAUT32!__imp_VariantClear` at `0x18049b7aa`
- `OLEAUT32!__imp_VariantClear` at `0x18049b88d`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049b678`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049b6b8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049b678`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049b6b8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049b913`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049b92f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049b913`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049b92f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049b697`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049b6d2`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049b697`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049b6d2`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049b906`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049b922`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049b906`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049b922`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18049b7d9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18049b7d9`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18049b7ed`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18049b7ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
HRESULT __fastcall CaptureOneGGCalibrationEffect::CustomFilter3x3Hardware<1>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rcx
  int v8; // eax
  float v9; // xmm8_4
  float v10; // xmm7_4
  SAFEARRAY *v11; // rdi
  HRESULT v12; // eax
  SAFEARRAY *v13; // rax
  SAFEARRAY *v14; // rbx
  HRESULT v15; // eax
  int v16; // r14d
  __int64 v17; // r12
  float v18; // xmm6_4
  float v19; // xmm6_4
  float v20; // xmm6_4
  float v21; // xmm6_4
  __int64 (__fastcall *v22)(__int64, const wchar_t *, __m128i *); // rsi
  __int64 v23; // rax
  int v24; // esi
  __int64 (__fastcall *v25)(__int64, const wchar_t *, _BYTE *); // rsi
  HRESULT Vartype; // ecx
  __int16 v27; // dx
  int v28; // esi
  __int64 v29; // r14
  int v30; // eax
  int v31; // eax
  __int64 v32; // rsi
  int v33; // eax
  HRESULT result; // eax
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-D0h] BYREF
  __m128i pvt_8; // [rsp+48h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+58h] [rbp-B0h]
  SAFEARRAY *v38; // [rsp+68h] [rbp-A0h] BYREF
  SAFEARRAY *v39; // [rsp+70h] [rbp-98h] BYREF
  __int64 v40; // [rsp+78h] [rbp-90h] BYREF
  __int64 v41; // [rsp+80h] [rbp-88h] BYREF
  __int64 v42; // [rsp+88h] [rbp-80h] BYREF
  __int64 v43; // [rsp+90h] [rbp-78h] BYREF
  _BYTE pvarg[32]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v45; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v46; // [rsp+C8h] [rbp-40h]
  int v47; // [rsp+D0h] [rbp-38h]

  *(__m128i *)pvarg = _mm_load_si128((const __m128i *)&_xmm);
  *(__m128i *)&pvarg[16] = _mm_load_si128((const __m128i *)&_xmm);
  pvt_8 = _mm_load_si128((const __m128i *)&_xmm);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v43 = 0;
  v40 = 0;
  Convolve1DEffect::LockAndGetTexture(a1, a3, 0, &v43, &v40);
  v42 = 0;
  v41 = 0;
  Convolve1DEffect::LockAndGetTexture(v7, a4, 1, &v42, &v41);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a3 + 56LL))(a3, &v45);
  if ( v8 < 0 )
    ATL::BaseAtlThrow(v8);
  v9 = 1.0 / (float)SHIDWORD(v46);
  v10 = 1.0 / (float)v47;
  rgsabound = (SAFEARRAYBOUND)8LL;
  v11 = SafeArrayCreate(4u, 1u, &rgsabound);
  v38 = v11;
  if ( v11 )
    v12 = SafeArrayLock(v11);
  else
    v12 = -2147024882;
  if ( v12 < 0 )
    ATL::BaseAtlThrow(v12);
  rgsabound = (SAFEARRAYBOUND)8LL;
  v13 = SafeArrayCreate(4u, 1u, &rgsabound);
  v14 = v13;
  v39 = v13;
  if ( v13 )
    v15 = SafeArrayLock(v13);
  else
    v15 = -2147024882;
  if ( v15 < 0 )
    ATL::BaseAtlThrow(v15);
  v16 = 0;
  v17 = 0;
  do
  {
    v18 = v9 * *(float *)&pvarg[v17 * 4];
    *(float *)ATL::CComSafeArray<float,4>::GetAt(&v38, (unsigned int)v16) = v18;
    v19 = v10 * *(float *)&pvarg[v17 * 4 + 4];
    *(float *)ATL::CComSafeArray<float,4>::GetAt(&v38, (unsigned int)(v16 + 1)) = v19;
    v20 = v9 * *(float *)&pvt_8.m128i_i32[v17];
    *(float *)ATL::CComSafeArray<float,4>::GetAt(&v39, (unsigned int)v16) = v20;
    v21 = v10 * *(float *)&pvt_8.m128i_i32[v17 + 1];
    *(float *)ATL::CComSafeArray<float,4>::GetAt(&v39, (unsigned int)(v16 + 1)) = v21;
    v16 += 2;
    v17 += 2;
  }
  while ( v16 < 8 );
  v22 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __m128i *))(*(_QWORD *)a2 + 104LL);
  v23 = ATL::CComVariant::CComVariant((VARTYPE *)pvarg, v11);
  pvt_8 = *(__m128i *)v23;
  si128.m128i_i64[0] = *(_QWORD *)(v23 + 16);
  v24 = v22(a2, L"customDiagonalOffsets", &pvt_8);
  VariantClear((VARIANTARG *)pvarg);
  if ( v24 < 0 )
    ATL::BaseAtlThrow(v24);
  v25 = *(__int64 (__fastcall **)(__int64, const wchar_t *, _BYTE *))(*(_QWORD *)a2 + 104LL);
  if ( !v14 )
  {
    pvt_8.m128i_i16[0] = 10;
    pvt_8.m128i_i32[2] = -2147024809;
    ATL::BaseAtlThrow(-2147024809);
  }
  rgsabound = 0;
  Vartype = SafeArrayCopy(v14, (SAFEARRAY **)&rgsabound);
  if ( Vartype < 0 )
    goto LABEL_21;
  Vartype = SafeArrayGetVartype(v14, (VARTYPE *)&pvt_8);
  v27 = pvt_8.m128i_i16[0];
  if ( Vartype >= 0 && pvt_8.m128i_i16[0] == 13 && (v14->fFeatures & 0x440) == 0x440 )
    v27 = 9;
  if ( Vartype < 0 )
  {
LABEL_21:
    pvt_8.m128i_i32[2] = Vartype;
    pvt_8.m128i_i16[0] = 10;
  }
  else
  {
    pvt_8.m128i_i16[0] = v27 | 0x2000;
    pvt_8.m128i_u64[1] = (unsigned __int64)rgsabound;
  }
  if ( Vartype < 0 )
  {
    if ( Vartype != -2147024882 )
      ATL::BaseAtlThrow(Vartype);
    ATL::BaseAtlThrow(-2147024882);
  }
  *(__m128i *)pvarg = pvt_8;
  *(_QWORD *)&pvarg[16] = si128.m128i_i64[0];
  v28 = v25(a2, L"customHorzVertOffsets", pvarg);
  VariantClear((VARIANTARG *)&pvt_8);
  if ( v28 < 0 )
    ATL::BaseAtlThrow(v28);
  v29 = v40;
  v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)a2 + 112LL))(
          a2,
          0,
          L"ratio",
          v40);
  if ( v30 < 0 )
    ATL::BaseAtlThrow(v30);
  v31 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a2 + 88LL))(a2, L"CustomFilterSharp");
  if ( v31 < 0 )
    ATL::BaseAtlThrow(v31);
  v32 = v41;
  v33 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 120LL))(a2, v41);
  if ( v33 < 0 )
    ATL::BaseAtlThrow(v33);
  result = SafeArrayUnlock(v14);
  if ( result >= 0 )
    result = SafeArrayDestroy(v14);
  if ( v11 )
  {
    result = SafeArrayUnlock(v11);
    if ( result >= 0 )
      result = SafeArrayDestroy(v11);
  }
  if ( v32 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v42 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v29 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v43 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  return result;
}

```

## disassembly

```asm
0x18049b548  mov     rax, rsp
0x18049b54b  push    rbp
0x18049b54c  push    rbx
0x18049b54d  push    rsi
0x18049b54e  push    rdi
0x18049b54f  push    r12
0x18049b551  push    r14
0x18049b553  push    r15
0x18049b555  lea     rbp, [rax-48h]
0x18049b559  sub     rsp, 110h
0x18049b560  movaps  xmmword ptr [rax-48h], xmm6
0x18049b564  movaps  xmmword ptr [rax-58h], xmm7
0x18049b568  movaps  xmmword ptr [rax-68h], xmm8
0x18049b56d  mov     rax, cs:__security_cookie
0x18049b574  xor     rax, rsp
0x18049b577  mov     [rbp+40h+var_70], rax
0x18049b57b  mov     rbx, r9
0x18049b57e  mov     rdi, r8
0x18049b581  mov     r15, rdx
0x18049b584  movdqa  xmm0, cs:__xmm@3f800000bf800000bf800000bf800000
0x18049b58c  movups  xmmword ptr [rbp+40h+pvarg], xmm0
0x18049b590  movdqa  xmm1, cs:__xmm@3f8000003f800000bf8000003f800000
0x18049b598  movups  xmmword ptr [rbp+40h+pvarg+10h], xmm1
0x18049b59c  movdqa  xmm0, cs:__xmm@3f80000000000000bf80000000000000
0x18049b5a4  movups  xmmword ptr [rsp+140h+pvt+8], xmm0
0x18049b5a9  movdqa  xmm1, cs:__xmm@000000003f80000000000000bf800000
0x18049b5b1  movups  xmmword ptr [rsp+140h+var_F8+8], xmm1
0x18049b5b6  mov     [rbp+40h+var_B8], 0
0x18049b5be  mov     [rsp+140h+var_D0], 0
0x18049b5c7  lea     rax, [rsp+140h+var_D0]
0x18049b5cc  mov     [rsp+140h+var_120], rax
0x18049b5d1  lea     r9, [rbp+40h+var_B8]
0x18049b5d5  xor     r8d, r8d
0x18049b5d8  mov     rdx, rdi
0x18049b5db  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x18049b5e0  mov     [rbp+40h+var_C0], 0
0x18049b5e8  mov     [rsp+140h+var_C8], 0
0x18049b5f1  lea     rax, [rsp+140h+var_C8]
0x18049b5f6  mov     [rsp+140h+var_120], rax
0x18049b5fb  lea     r9, [rbp+40h+var_C0]
0x18049b5ff  mov     r14d, 1
0x18049b605  mov     r8d, r14d
0x18049b608  mov     rdx, rbx
0x18049b60b  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x18049b610  xorps   xmm0, xmm0
0x18049b613  xor     eax, eax
0x18049b615  movups  [rbp+40h+var_90], xmm0
0x18049b619  mov     [rbp+40h+var_80], rax
0x18049b61d  mov     [rbp+40h+var_78], eax
0x18049b620  mov     rax, [rdi]
0x18049b623  lea     rdx, [rbp+40h+var_90]
0x18049b627  mov     rcx, rdi
0x18049b62a  mov     rax, [rax+38h]
0x18049b62e  call    cs:__guard_dispatch_icall_fptr
0x18049b634  test    eax, eax
0x18049b636  js      loc_18049B9D3
0x18049b63c  movd    xmm0, dword ptr [rbp+40h+var_80+4]
0x18049b641  cvtdq2ps xmm0, xmm0
0x18049b644  movss   xmm7, cs:__real@3f800000
0x18049b64c  movaps  xmm8, xmm7
0x18049b650  divss   xmm8, xmm0
0x18049b655  movd    xmm0, [rbp+40h+var_78]
0x18049b65a  cvtdq2ps xmm0, xmm0
0x18049b65d  divss   xmm7, xmm0
0x18049b661  mov     qword ptr [rsp+140h+rgsabound.cElements], 8
0x18049b66a  lea     ebx, [r14+3]
0x18049b66e  mov     ecx, ebx; vt
0x18049b670  lea     r8, [rsp+140h+rgsabound]; rgsabound
0x18049b675  mov     edx, r14d; cDims
0x18049b678  call    cs:__imp_SafeArrayCreate
0x18049b67e  mov     rdi, rax
0x18049b681  mov     [rsp+140h+var_E0], rax
0x18049b686  mov     esi, 8007000Eh
0x18049b68b  test    rax, rax
0x18049b68e  jnz     short loc_18049B694
0x18049b690  mov     eax, esi
0x18049b692  jmp     short loc_18049B69D
0x18049b694  mov     rcx, rdi; psa
0x18049b697  call    cs:__imp_SafeArrayLock
0x18049b69d  test    eax, eax
0x18049b69f  js      loc_18049B9DB
0x18049b6a5  mov     qword ptr [rsp+140h+rgsabound.cElements], 8
0x18049b6ae  mov     ecx, ebx; vt
0x18049b6b0  lea     r8, [rsp+140h+rgsabound]; rgsabound
0x18049b6b5  mov     edx, r14d; cDims
0x18049b6b8  call    cs:__imp_SafeArrayCreate
0x18049b6be  mov     rbx, rax
0x18049b6c1  mov     [rsp+140h+var_D8], rax
0x18049b6c6  test    rax, rax
0x18049b6c9  jnz     short loc_18049B6CF
0x18049b6cb  mov     eax, esi
0x18049b6cd  jmp     short loc_18049B6D8
0x18049b6cf  mov     rcx, rbx; psa
0x18049b6d2  call    cs:__imp_SafeArrayLock
0x18049b6d8  test    eax, eax
0x18049b6da  js      loc_18049B9E6
0x18049b6e0  xor     r14d, r14d
0x18049b6e3  xor     r12d, r12d
0x18049b6e6  movaps  xmm6, xmm8
0x18049b6ea  mulss   xmm6, dword ptr [rbp+r12+40h+pvarg]
0x18049b6f1  mov     edx, r14d
0x18049b6f4  lea     rcx, [rsp+140h+var_E0]
0x18049b6f9  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x18049b6fe  movss   dword ptr [rax], xmm6
0x18049b702  movaps  xmm6, xmm7
0x18049b705  mulss   xmm6, dword ptr [rbp+r12+40h+pvarg+4]
0x18049b70c  lea     edx, [r14+1]
0x18049b710  lea     rcx, [rsp+140h+var_E0]
0x18049b715  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x18049b71a  movss   dword ptr [rax], xmm6
0x18049b71e  movaps  xmm6, xmm8
0x18049b722  mulss   xmm6, dword ptr [rsp+r12+140h+pvt+8]
0x18049b729  mov     edx, r14d
0x18049b72c  lea     rcx, [rsp+140h+var_D8]
0x18049b731  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x18049b736  movss   dword ptr [rax], xmm6
0x18049b73a  movaps  xmm6, xmm7
0x18049b73d  mulss   xmm6, dword ptr [rsp+r12+140h+pvt+0Ch]
0x18049b744  lea     edx, [r14+1]
0x18049b748  lea     rcx, [rsp+140h+var_D8]
0x18049b74d  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x18049b752  movss   dword ptr [rax], xmm6
0x18049b756  add     r14d, 2
0x18049b75a  lea     r12, [r12+8]
0x18049b75f  cmp     r14d, 8
0x18049b763  jl      short loc_18049B6E6
0x18049b765  mov     rax, [r15]
0x18049b768  mov     rsi, [rax+68h]
0x18049b76c  mov     rdx, rdi; psa
0x18049b76f  lea     rcx, [rbp+40h+pvarg]; pvt
0x18049b773  call    ??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::CComVariant(tagSAFEARRAY const *)
0x18049b778  nop
0x18049b779  movups  xmm0, xmmword ptr [rax]
0x18049b77c  movaps  xmmword ptr [rsp+140h+pvt+8], xmm0
0x18049b781  movsd   xmm1, qword ptr [rax+10h]
0x18049b786  movsd   qword ptr [rsp+140h+var_F8+8], xmm1
0x18049b78c  lea     r8, [rsp+140h+pvt+8]
0x18049b791  lea     rdx, aCustomdiagonal; "customDiagonalOffsets"
0x18049b798  mov     rcx, r15
0x18049b79b  mov     rax, rsi
0x18049b79e  call    cs:__guard_dispatch_icall_fptr
0x18049b7a4  mov     esi, eax
0x18049b7a6  lea     rcx, [rbp+40h+pvarg]; pvarg
0x18049b7aa  call    cs:__imp_VariantClear
0x18049b7b0  test    esi, esi
0x18049b7b2  js      loc_18049B9C0
0x18049b7b8  mov     rax, [r15]
0x18049b7bb  mov     rsi, [rax+68h]
0x18049b7bf  test    rbx, rbx
0x18049b7c2  jz      loc_18049B9F1
0x18049b7c8  mov     qword ptr [rsp+140h+rgsabound.cElements], 0
0x18049b7d1  lea     rdx, [rsp+140h+rgsabound]; ppsaOut
0x18049b7d6  mov     rcx, rbx; psa
0x18049b7d9  call    cs:__imp_SafeArrayCopy
0x18049b7df  mov     ecx, eax; int
0x18049b7e1  test    eax, eax
0x18049b7e3  js      short loc_18049B837
0x18049b7e5  lea     rdx, [rsp+140h+pvt+8]; pvt
0x18049b7ea  mov     rcx, rbx; psa
0x18049b7ed  call    cs:__imp_SafeArrayGetVartype
0x18049b7f3  mov     ecx, eax
0x18049b7f5  movzx   edx, [rsp+140h+pvt+8]
0x18049b7fa  test    eax, eax
0x18049b7fc  js      short loc_18049B81D
0x18049b7fe  cmp     dx, 0Dh
0x18049b802  jnz     short loc_18049B81D
0x18049b804  movzx   eax, word ptr [rbx+2]
0x18049b808  mov     r8d, 440h
0x18049b80e  and     ax, r8w
0x18049b812  cmp     ax, r8w
0x18049b816  jnz     short loc_18049B81D
0x18049b818  mov     edx, 9
0x18049b81d  test    ecx, ecx
0x18049b81f  js      short loc_18049B837
0x18049b821  or      dx, 2000h
0x18049b826  mov     [rsp+140h+pvt+8], dx
0x18049b82b  mov     rax, qword ptr [rsp+140h+rgsabound.cElements]
0x18049b830  mov     qword ptr [rsp+140h+var_F8], rax
0x18049b835  jmp     short loc_18049B845
0x18049b837  mov     eax, 0Ah
0x18049b83c  mov     dword ptr [rsp+140h+var_F8], ecx
0x18049b840  mov     [rsp+140h+pvt+8], ax
0x18049b845  test    ecx, ecx
0x18049b847  jns     short loc_18049B85B
0x18049b849  mov     eax, 8007000Eh
0x18049b84e  cmp     ecx, eax
0x18049b850  jz      loc_18049B9C8
0x18049b856  jmp     loc_18049BA0A
0x18049b85b  movups  xmm0, xmmword ptr [rsp+140h+pvt+8]
0x18049b860  movaps  xmmword ptr [rbp+40h+pvarg], xmm0
0x18049b864  movsd   xmm1, qword ptr [rsp+140h+var_F8+8]
0x18049b86a  movsd   qword ptr [rbp+40h+pvarg+10h], xmm1
0x18049b86f  lea     r8, [rbp+40h+pvarg]
0x18049b873  lea     rdx, aCustomhorzvert; "customHorzVertOffsets"
0x18049b87a  mov     rcx, r15
0x18049b87d  mov     rax, rsi
0x18049b880  call    cs:__guard_dispatch_icall_fptr
0x18049b886  mov     esi, eax
0x18049b888  lea     rcx, [rsp+140h+pvt+8]; pvarg
0x18049b88d  call    cs:__imp_VariantClear
0x18049b893  test    esi, esi
0x18049b895  js      loc_18049BA28
0x18049b89b  mov     rax, [r15]
0x18049b89e  mov     r14, [rsp+140h+var_D0]
0x18049b8a3  mov     r9, r14
0x18049b8a6  lea     r8, aRatio; "ratio"
0x18049b8ad  xor     edx, edx
0x18049b8af  mov     rcx, r15
0x18049b8b2  mov     rax, [rax+70h]
0x18049b8b6  call    cs:__guard_dispatch_icall_fptr
0x18049b8bc  test    eax, eax
0x18049b8be  js      loc_18049BA20
0x18049b8c4  mov     rax, [r15]
0x18049b8c7  lea     rdx, aCustomfiltersh; "CustomFilterSharp"
0x18049b8ce  mov     rcx, r15
0x18049b8d1  mov     rax, [rax+58h]
0x18049b8d5  call    cs:__guard_dispatch_icall_fptr
0x18049b8db  test    eax, eax
0x18049b8dd  js      loc_18049BA18
0x18049b8e3  mov     rax, [r15]
0x18049b8e6  mov     rsi, [rsp+140h+var_C8]
0x18049b8eb  mov     rdx, rsi
0x18049b8ee  mov     rcx, r15
0x18049b8f1  mov     rax, [rax+78h]
0x18049b8f5  call    cs:__guard_dispatch_icall_fptr
0x18049b8fb  test    eax, eax
0x18049b8fd  js      loc_18049BA10
0x18049b903  mov     rcx, rbx; psa
0x18049b906  call    cs:__imp_SafeArrayUnlock
0x18049b90c  test    eax, eax
0x18049b90e  js      short loc_18049B91A
0x18049b910  mov     rcx, rbx; psa
0x18049b913  call    cs:__imp_SafeArrayDestroy
0x18049b919  nop
0x18049b91a  test    rdi, rdi
0x18049b91d  jz      short loc_18049B936
0x18049b91f  mov     rcx, rdi; psa
0x18049b922  call    cs:__imp_SafeArrayUnlock
0x18049b928  test    eax, eax
0x18049b92a  js      short loc_18049B936
0x18049b92c  mov     rcx, rdi; psa
0x18049b92f  call    cs:__imp_SafeArrayDestroy
0x18049b935  nop
0x18049b936  test    rsi, rsi
0x18049b939  jz      short loc_18049B94C
0x18049b93b  mov     rax, [rsi]
0x18049b93e  mov     rcx, rsi
0x18049b941  mov     rax, [rax+10h]
0x18049b945  call    cs:__guard_dispatch_icall_fptr
0x18049b94b  nop
0x18049b94c  mov     rcx, [rbp+40h+var_C0]
0x18049b950  test    rcx, rcx
0x18049b953  jz      short loc_18049B963
0x18049b955  mov     rax, [rcx]
0x18049b958  mov     rax, [rax+10h]
0x18049b95c  call    cs:__guard_dispatch_icall_fptr
0x18049b962  nop
0x18049b963  test    r14, r14
0x18049b966  jz      short loc_18049B979
0x18049b968  mov     rax, [r14]
0x18049b96b  mov     rcx, r14
0x18049b96e  mov     rax, [rax+10h]
0x18049b972  call    cs:__guard_dispatch_icall_fptr
0x18049b978  nop
0x18049b979  mov     rcx, [rbp+40h+var_B8]
0x18049b97d  test    rcx, rcx
0x18049b980  jz      short loc_18049B98F
0x18049b982  mov     rax, [rcx]
0x18049b985  mov     rax, [rax+10h]
0x18049b989  call    cs:__guard_dispatch_icall_fptr
0x18049b98f  mov     rcx, [rbp+40h+var_70]
0x18049b993  xor     rcx, rsp; StackCookie
0x18049b996  call    __security_check_cookie
0x18049b99b  lea     r11, [rsp+140h+var_30]
0x18049b9a3  movaps  xmm6, xmmword ptr [r11-10h]
0x18049b9a8  movaps  xmm7, xmmword ptr [r11-20h]
0x18049b9ad  movaps  xmm8, xmmword ptr [r11-30h]
0x18049b9b2  mov     rsp, r11
0x18049b9b5  pop     r15
0x18049b9b7  pop     r14
0x18049b9b9  pop     r12
0x18049b9bb  pop     rdi
0x18049b9bc  pop     rsi
0x18049b9bd  pop     rbx
0x18049b9be  pop     rbp
0x18049b9bf  retn
0x18049b9c0  mov     ecx, esi; int
0x18049b9c2  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b9c8  mov     ecx, eax; int
0x18049b9ca  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b9d0  jmp     short $+2
0x18049b9d2  nop
0x18049b9d3  mov     ecx, eax; int
0x18049b9d5  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b9db  mov     ecx, eax; int
0x18049b9dd  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b9e3  jmp     short $+2
0x18049b9e5  nop
0x18049b9e6  mov     ecx, eax; int
0x18049b9e8  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
  ... truncated ...
```
