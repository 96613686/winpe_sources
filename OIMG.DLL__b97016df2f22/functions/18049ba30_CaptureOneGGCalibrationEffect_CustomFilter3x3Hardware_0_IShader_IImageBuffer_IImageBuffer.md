# CaptureOneGGCalibrationEffect::CustomFilter3x3Hardware<0>(IShader *,IImageBuffer *,IImageBuffer *)

- ea: `0x18049ba30`
- end: `0x18049bf18`
- name: `??$CustomFilter3x3Hardware@$0A@@CaptureOneGGCalibrationEffect@@AEAAXPEAUIShader@@PEAUIImageBuffer@@1@Z`
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
- `0x18049ba30`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18049bc92`
- `OLEAUT32!__imp_VariantClear` at `0x18049bd75`
- `OLEAUT32!__imp_VariantClear` at `0x18049bc92`
- `OLEAUT32!__imp_VariantClear` at `0x18049bd75`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049bb60`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049bba0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049bb60`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049bba0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049bdfb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049be17`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049bdfb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049be17`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049bb7f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049bbba`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049bb7f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049bbba`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049bdee`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049be0a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049bdee`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049be0a`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18049bcc1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18049bcc1`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18049bcd5`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18049bcd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
HRESULT __fastcall CaptureOneGGCalibrationEffect::CustomFilter3x3Hardware<0>(
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
  v31 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a2 + 88LL))(a2, L"CustomFilterNormal");
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
0x18049ba30  mov     rax, rsp
0x18049ba33  push    rbp
0x18049ba34  push    rbx
0x18049ba35  push    rsi
0x18049ba36  push    rdi
0x18049ba37  push    r12
0x18049ba39  push    r14
0x18049ba3b  push    r15
0x18049ba3d  lea     rbp, [rax-48h]
0x18049ba41  sub     rsp, 110h
0x18049ba48  movaps  xmmword ptr [rax-48h], xmm6
0x18049ba4c  movaps  xmmword ptr [rax-58h], xmm7
0x18049ba50  movaps  xmmword ptr [rax-68h], xmm8
0x18049ba55  mov     rax, cs:__security_cookie
0x18049ba5c  xor     rax, rsp
0x18049ba5f  mov     [rbp+40h+var_70], rax
0x18049ba63  mov     rbx, r9
0x18049ba66  mov     rdi, r8
0x18049ba69  mov     r15, rdx
0x18049ba6c  movdqa  xmm0, cs:__xmm@3f800000bf800000bf800000bf800000
0x18049ba74  movups  xmmword ptr [rbp+40h+pvarg], xmm0
0x18049ba78  movdqa  xmm1, cs:__xmm@3f8000003f800000bf8000003f800000
0x18049ba80  movups  xmmword ptr [rbp+40h+pvarg+10h], xmm1
0x18049ba84  movdqa  xmm0, cs:__xmm@3f80000000000000bf80000000000000
0x18049ba8c  movups  xmmword ptr [rsp+140h+pvt+8], xmm0
0x18049ba91  movdqa  xmm1, cs:__xmm@000000003f80000000000000bf800000
0x18049ba99  movups  xmmword ptr [rsp+140h+var_F8+8], xmm1
0x18049ba9e  mov     [rbp+40h+var_B8], 0
0x18049baa6  mov     [rsp+140h+var_D0], 0
0x18049baaf  lea     rax, [rsp+140h+var_D0]
0x18049bab4  mov     [rsp+140h+var_120], rax
0x18049bab9  lea     r9, [rbp+40h+var_B8]
0x18049babd  xor     r8d, r8d
0x18049bac0  mov     rdx, rdi
0x18049bac3  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x18049bac8  mov     [rbp+40h+var_C0], 0
0x18049bad0  mov     [rsp+140h+var_C8], 0
0x18049bad9  lea     rax, [rsp+140h+var_C8]
0x18049bade  mov     [rsp+140h+var_120], rax
0x18049bae3  lea     r9, [rbp+40h+var_C0]
0x18049bae7  mov     r14d, 1
0x18049baed  mov     r8d, r14d
0x18049baf0  mov     rdx, rbx
0x18049baf3  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x18049baf8  xorps   xmm0, xmm0
0x18049bafb  xor     eax, eax
0x18049bafd  movups  [rbp+40h+var_90], xmm0
0x18049bb01  mov     [rbp+40h+var_80], rax
0x18049bb05  mov     [rbp+40h+var_78], eax
0x18049bb08  mov     rax, [rdi]
0x18049bb0b  lea     rdx, [rbp+40h+var_90]
0x18049bb0f  mov     rcx, rdi
0x18049bb12  mov     rax, [rax+38h]
0x18049bb16  call    cs:__guard_dispatch_icall_fptr
0x18049bb1c  test    eax, eax
0x18049bb1e  js      loc_18049BEBB
0x18049bb24  movd    xmm0, dword ptr [rbp+40h+var_80+4]
0x18049bb29  cvtdq2ps xmm0, xmm0
0x18049bb2c  movss   xmm7, cs:__real@3f800000
0x18049bb34  movaps  xmm8, xmm7
0x18049bb38  divss   xmm8, xmm0
0x18049bb3d  movd    xmm0, [rbp+40h+var_78]
0x18049bb42  cvtdq2ps xmm0, xmm0
0x18049bb45  divss   xmm7, xmm0
0x18049bb49  mov     qword ptr [rsp+140h+rgsabound.cElements], 8
0x18049bb52  lea     ebx, [r14+3]
0x18049bb56  mov     ecx, ebx; vt
0x18049bb58  lea     r8, [rsp+140h+rgsabound]; rgsabound
0x18049bb5d  mov     edx, r14d; cDims
0x18049bb60  call    cs:__imp_SafeArrayCreate
0x18049bb66  mov     rdi, rax
0x18049bb69  mov     [rsp+140h+var_E0], rax
0x18049bb6e  mov     esi, 8007000Eh
0x18049bb73  test    rax, rax
0x18049bb76  jnz     short loc_18049BB7C
0x18049bb78  mov     eax, esi
0x18049bb7a  jmp     short loc_18049BB85
0x18049bb7c  mov     rcx, rdi; psa
0x18049bb7f  call    cs:__imp_SafeArrayLock
0x18049bb85  test    eax, eax
0x18049bb87  js      loc_18049BEC3
0x18049bb8d  mov     qword ptr [rsp+140h+rgsabound.cElements], 8
0x18049bb96  mov     ecx, ebx; vt
0x18049bb98  lea     r8, [rsp+140h+rgsabound]; rgsabound
0x18049bb9d  mov     edx, r14d; cDims
0x18049bba0  call    cs:__imp_SafeArrayCreate
0x18049bba6  mov     rbx, rax
0x18049bba9  mov     [rsp+140h+var_D8], rax
0x18049bbae  test    rax, rax
0x18049bbb1  jnz     short loc_18049BBB7
0x18049bbb3  mov     eax, esi
0x18049bbb5  jmp     short loc_18049BBC0
0x18049bbb7  mov     rcx, rbx; psa
0x18049bbba  call    cs:__imp_SafeArrayLock
0x18049bbc0  test    eax, eax
0x18049bbc2  js      loc_18049BECE
0x18049bbc8  xor     r14d, r14d
0x18049bbcb  xor     r12d, r12d
0x18049bbce  movaps  xmm6, xmm8
0x18049bbd2  mulss   xmm6, dword ptr [rbp+r12+40h+pvarg]
0x18049bbd9  mov     edx, r14d
0x18049bbdc  lea     rcx, [rsp+140h+var_E0]
0x18049bbe1  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x18049bbe6  movss   dword ptr [rax], xmm6
0x18049bbea  movaps  xmm6, xmm7
0x18049bbed  mulss   xmm6, dword ptr [rbp+r12+40h+pvarg+4]
0x18049bbf4  lea     edx, [r14+1]
0x18049bbf8  lea     rcx, [rsp+140h+var_E0]
0x18049bbfd  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x18049bc02  movss   dword ptr [rax], xmm6
0x18049bc06  movaps  xmm6, xmm8
0x18049bc0a  mulss   xmm6, dword ptr [rsp+r12+140h+pvt+8]
0x18049bc11  mov     edx, r14d
0x18049bc14  lea     rcx, [rsp+140h+var_D8]
0x18049bc19  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x18049bc1e  movss   dword ptr [rax], xmm6
0x18049bc22  movaps  xmm6, xmm7
0x18049bc25  mulss   xmm6, dword ptr [rsp+r12+140h+pvt+0Ch]
0x18049bc2c  lea     edx, [r14+1]
0x18049bc30  lea     rcx, [rsp+140h+var_D8]
0x18049bc35  call    ?GetAt@?$CComSafeArray@M$03@ATL@@QEAAAEAMJ@Z; ATL::CComSafeArray<float,4>::GetAt(long)
0x18049bc3a  movss   dword ptr [rax], xmm6
0x18049bc3e  add     r14d, 2
0x18049bc42  lea     r12, [r12+8]
0x18049bc47  cmp     r14d, 8
0x18049bc4b  jl      short loc_18049BBCE
0x18049bc4d  mov     rax, [r15]
0x18049bc50  mov     rsi, [rax+68h]
0x18049bc54  mov     rdx, rdi; psa
0x18049bc57  lea     rcx, [rbp+40h+pvarg]; pvt
0x18049bc5b  call    ??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::CComVariant(tagSAFEARRAY const *)
0x18049bc60  nop
0x18049bc61  movups  xmm0, xmmword ptr [rax]
0x18049bc64  movaps  xmmword ptr [rsp+140h+pvt+8], xmm0
0x18049bc69  movsd   xmm1, qword ptr [rax+10h]
0x18049bc6e  movsd   qword ptr [rsp+140h+var_F8+8], xmm1
0x18049bc74  lea     r8, [rsp+140h+pvt+8]
0x18049bc79  lea     rdx, aCustomdiagonal; "customDiagonalOffsets"
0x18049bc80  mov     rcx, r15
0x18049bc83  mov     rax, rsi
0x18049bc86  call    cs:__guard_dispatch_icall_fptr
0x18049bc8c  mov     esi, eax
0x18049bc8e  lea     rcx, [rbp+40h+pvarg]; pvarg
0x18049bc92  call    cs:__imp_VariantClear
0x18049bc98  test    esi, esi
0x18049bc9a  js      loc_18049BEA8
0x18049bca0  mov     rax, [r15]
0x18049bca3  mov     rsi, [rax+68h]
0x18049bca7  test    rbx, rbx
0x18049bcaa  jz      loc_18049BED9
0x18049bcb0  mov     qword ptr [rsp+140h+rgsabound.cElements], 0
0x18049bcb9  lea     rdx, [rsp+140h+rgsabound]; ppsaOut
0x18049bcbe  mov     rcx, rbx; psa
0x18049bcc1  call    cs:__imp_SafeArrayCopy
0x18049bcc7  mov     ecx, eax; int
0x18049bcc9  test    eax, eax
0x18049bccb  js      short loc_18049BD1F
0x18049bccd  lea     rdx, [rsp+140h+pvt+8]; pvt
0x18049bcd2  mov     rcx, rbx; psa
0x18049bcd5  call    cs:__imp_SafeArrayGetVartype
0x18049bcdb  mov     ecx, eax
0x18049bcdd  movzx   edx, [rsp+140h+pvt+8]
0x18049bce2  test    eax, eax
0x18049bce4  js      short loc_18049BD05
0x18049bce6  cmp     dx, 0Dh
0x18049bcea  jnz     short loc_18049BD05
0x18049bcec  movzx   eax, word ptr [rbx+2]
0x18049bcf0  mov     r8d, 440h
0x18049bcf6  and     ax, r8w
0x18049bcfa  cmp     ax, r8w
0x18049bcfe  jnz     short loc_18049BD05
0x18049bd00  mov     edx, 9
0x18049bd05  test    ecx, ecx
0x18049bd07  js      short loc_18049BD1F
0x18049bd09  or      dx, 2000h
0x18049bd0e  mov     [rsp+140h+pvt+8], dx
0x18049bd13  mov     rax, qword ptr [rsp+140h+rgsabound.cElements]
0x18049bd18  mov     qword ptr [rsp+140h+var_F8], rax
0x18049bd1d  jmp     short loc_18049BD2D
0x18049bd1f  mov     eax, 0Ah
0x18049bd24  mov     dword ptr [rsp+140h+var_F8], ecx
0x18049bd28  mov     [rsp+140h+pvt+8], ax
0x18049bd2d  test    ecx, ecx
0x18049bd2f  jns     short loc_18049BD43
0x18049bd31  mov     eax, 8007000Eh
0x18049bd36  cmp     ecx, eax
0x18049bd38  jz      loc_18049BEB0
0x18049bd3e  jmp     loc_18049BEF2
0x18049bd43  movups  xmm0, xmmword ptr [rsp+140h+pvt+8]
0x18049bd48  movaps  xmmword ptr [rbp+40h+pvarg], xmm0
0x18049bd4c  movsd   xmm1, qword ptr [rsp+140h+var_F8+8]
0x18049bd52  movsd   qword ptr [rbp+40h+pvarg+10h], xmm1
0x18049bd57  lea     r8, [rbp+40h+pvarg]
0x18049bd5b  lea     rdx, aCustomhorzvert; "customHorzVertOffsets"
0x18049bd62  mov     rcx, r15
0x18049bd65  mov     rax, rsi
0x18049bd68  call    cs:__guard_dispatch_icall_fptr
0x18049bd6e  mov     esi, eax
0x18049bd70  lea     rcx, [rsp+140h+pvt+8]; pvarg
0x18049bd75  call    cs:__imp_VariantClear
0x18049bd7b  test    esi, esi
0x18049bd7d  js      loc_18049BF10
0x18049bd83  mov     rax, [r15]
0x18049bd86  mov     r14, [rsp+140h+var_D0]
0x18049bd8b  mov     r9, r14
0x18049bd8e  lea     r8, aRatio; "ratio"
0x18049bd95  xor     edx, edx
0x18049bd97  mov     rcx, r15
0x18049bd9a  mov     rax, [rax+70h]
0x18049bd9e  call    cs:__guard_dispatch_icall_fptr
0x18049bda4  test    eax, eax
0x18049bda6  js      loc_18049BF08
0x18049bdac  mov     rax, [r15]
0x18049bdaf  lea     rdx, aCustomfilterno; "CustomFilterNormal"
0x18049bdb6  mov     rcx, r15
0x18049bdb9  mov     rax, [rax+58h]
0x18049bdbd  call    cs:__guard_dispatch_icall_fptr
0x18049bdc3  test    eax, eax
0x18049bdc5  js      loc_18049BF00
0x18049bdcb  mov     rax, [r15]
0x18049bdce  mov     rsi, [rsp+140h+var_C8]
0x18049bdd3  mov     rdx, rsi
0x18049bdd6  mov     rcx, r15
0x18049bdd9  mov     rax, [rax+78h]
0x18049bddd  call    cs:__guard_dispatch_icall_fptr
0x18049bde3  test    eax, eax
0x18049bde5  js      loc_18049BEF8
0x18049bdeb  mov     rcx, rbx; psa
0x18049bdee  call    cs:__imp_SafeArrayUnlock
0x18049bdf4  test    eax, eax
0x18049bdf6  js      short loc_18049BE02
0x18049bdf8  mov     rcx, rbx; psa
0x18049bdfb  call    cs:__imp_SafeArrayDestroy
0x18049be01  nop
0x18049be02  test    rdi, rdi
0x18049be05  jz      short loc_18049BE1E
0x18049be07  mov     rcx, rdi; psa
0x18049be0a  call    cs:__imp_SafeArrayUnlock
0x18049be10  test    eax, eax
0x18049be12  js      short loc_18049BE1E
0x18049be14  mov     rcx, rdi; psa
0x18049be17  call    cs:__imp_SafeArrayDestroy
0x18049be1d  nop
0x18049be1e  test    rsi, rsi
0x18049be21  jz      short loc_18049BE34
0x18049be23  mov     rax, [rsi]
0x18049be26  mov     rcx, rsi
0x18049be29  mov     rax, [rax+10h]
0x18049be2d  call    cs:__guard_dispatch_icall_fptr
0x18049be33  nop
0x18049be34  mov     rcx, [rbp+40h+var_C0]
0x18049be38  test    rcx, rcx
0x18049be3b  jz      short loc_18049BE4B
0x18049be3d  mov     rax, [rcx]
0x18049be40  mov     rax, [rax+10h]
0x18049be44  call    cs:__guard_dispatch_icall_fptr
0x18049be4a  nop
0x18049be4b  test    r14, r14
0x18049be4e  jz      short loc_18049BE61
0x18049be50  mov     rax, [r14]
0x18049be53  mov     rcx, r14
0x18049be56  mov     rax, [rax+10h]
0x18049be5a  call    cs:__guard_dispatch_icall_fptr
0x18049be60  nop
0x18049be61  mov     rcx, [rbp+40h+var_B8]
0x18049be65  test    rcx, rcx
0x18049be68  jz      short loc_18049BE77
0x18049be6a  mov     rax, [rcx]
0x18049be6d  mov     rax, [rax+10h]
0x18049be71  call    cs:__guard_dispatch_icall_fptr
0x18049be77  mov     rcx, [rbp+40h+var_70]
0x18049be7b  xor     rcx, rsp; StackCookie
0x18049be7e  call    __security_check_cookie
0x18049be83  lea     r11, [rsp+140h+var_30]
0x18049be8b  movaps  xmm6, xmmword ptr [r11-10h]
0x18049be90  movaps  xmm7, xmmword ptr [r11-20h]
0x18049be95  movaps  xmm8, xmmword ptr [r11-30h]
0x18049be9a  mov     rsp, r11
0x18049be9d  pop     r15
0x18049be9f  pop     r14
0x18049bea1  pop     r12
0x18049bea3  pop     rdi
0x18049bea4  pop     rsi
0x18049bea5  pop     rbx
0x18049bea6  pop     rbp
0x18049bea7  retn
0x18049bea8  mov     ecx, esi; int
0x18049beaa  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049beb0  mov     ecx, eax; int
0x18049beb2  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049beb8  jmp     short $+2
0x18049beba  nop
0x18049bebb  mov     ecx, eax; int
0x18049bebd  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049bec3  mov     ecx, eax; int
0x18049bec5  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049becb  jmp     short $+2
0x18049becd  nop
0x18049bece  mov     ecx, eax; int
0x18049bed0  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
  ... truncated ...
```
