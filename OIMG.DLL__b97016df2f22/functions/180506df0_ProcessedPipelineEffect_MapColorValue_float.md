# ProcessedPipelineEffect::MapColorValue(float)

- ea: `0x180506df0`
- end: `0x1805073ec`
- name: `?MapColorValue@ProcessedPipelineEffect@@AEAAMM@Z`
- size: `1532`
- prototype: `float __fastcall(ProcessedPipelineEffect *__hidden this, float)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1805073f0`

## callees

- `0x180201a9c`
- `0x1804c6944`
- `0x180506df0`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1805070eb`
- `OLEAUT32!__imp_VariantInit` at `0x1805070eb`
- `OLEAUT32!__imp_VariantClear` at `0x1805072a2`
- `OLEAUT32!__imp_VariantClear` at `0x1805072c3`
- `OLEAUT32!__imp_VariantClear` at `0x1805072a2`
- `OLEAUT32!__imp_VariantClear` at `0x1805072c3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180506e35`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180506e35`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180507290`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1805072d9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180507290`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1805072d9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506ea2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506f00`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506f62`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506fc0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180507177`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805071d0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050722c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506ea2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506f00`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506f62`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180506fc0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180507177`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805071d0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050722c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506e7a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506eda`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506f38`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506f98`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18050714f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805071ab`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180507204`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506e7a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506eda`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506f38`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180506f98`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18050714f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805071ab`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180507204`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180506e55`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180506e55`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180507282`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1805072cc`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180507282`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1805072cc`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180506ff1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180506ff1`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180507004`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180507004`

## string_xrefs

- `0x180507078`: `CompositeSceneEffect`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
float __fastcall ProcessedPipelineEffect::MapColorValue(ProcessedPipelineEffect *this, float a2)
{
  SAFEARRAY *v3; // rax
  SAFEARRAY *v4; // rbx
  HRESULT v5; // eax
  HRESULT LBound; // eax
  __int64 v7; // rdi
  HRESULT UBound; // eax
  HRESULT v9; // eax
  HRESULT v10; // eax
  HRESULT v11; // eax
  HRESULT v12; // eax
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  HRESULT v20; // eax
  LONG v21; // edi
  HRESULT v22; // eax
  __int64 v23; // r15
  float *pvData; // r12
  HRESULT v25; // eax
  HRESULT v26; // eax
  __int64 v27; // rdi
  float *v28; // r14
  HRESULT v29; // eax
  HRESULT v30; // eax
  float v31; // xmm6_4
  SAFEARRAY *psa; // [rsp+38h] [rbp-69h] BYREF
  LONG plUbound; // [rsp+40h] [rbp-61h] BYREF
  __int64 *v35; // [rsp+48h] [rbp-59h] BYREF
  VARIANTARG pvt; // [rsp+50h] [rbp-51h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-39h] BYREF
  SAFEARRAY *v38; // [rsp+80h] [rbp-21h]
  VARIANTARG v39; // [rsp+88h] [rbp-19h] BYREF
  LONG plLbound; // [rsp+110h] [rbp+6Fh] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+118h] [rbp+77h] BYREF
  LONG v42; // [rsp+120h] [rbp+7Fh] BYREF

  rgsabound = (SAFEARRAYBOUND)4LL;
  v3 = SafeArrayCreate(4u, 1u, &rgsabound);
  v4 = v3;
  v38 = v3;
  if ( v3 )
    v5 = SafeArrayLock(v3);
  else
    v5 = -2147024882;
  if ( v5 < 0 )
    ATL::BaseAtlThrow(v5);
  if ( !v4 )
    ATL::BaseAtlThrow(-2147467259);
  plLbound = 0;
  LBound = SafeArrayGetLBound(v4, 1u, &plLbound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  v7 = plLbound;
  if ( plLbound > 0 )
    goto LABEL_62;
  plLbound = 0;
  UBound = SafeArrayGetUBound(v4, 1u, &plLbound);
  if ( UBound < 0 )
    ATL::BaseAtlThrow(UBound);
  if ( plLbound < 0 )
    goto LABEL_62;
  *((float *)v4->pvData - v7) = a2;
  plLbound = 0;
  v9 = SafeArrayGetLBound(v4, 1u, &plLbound);
  if ( v9 < 0 )
    ATL::BaseAtlThrow(v9);
  if ( plLbound > 1 )
    goto LABEL_62;
  rgsabound.cElements = 0;
  v10 = SafeArrayGetUBound(v4, 1u, (LONG *)&rgsabound);
  if ( v10 < 0 )
    ATL::BaseAtlThrow(v10);
  if ( (int)rgsabound.cElements < 1 )
    goto LABEL_62;
  *((float *)v4->pvData + 1 - plLbound) = a2;
  plLbound = 0;
  v11 = SafeArrayGetLBound(v4, 1u, &plLbound);
  if ( v11 < 0 )
    ATL::BaseAtlThrow(v11);
  if ( plLbound > 2 )
    goto LABEL_62;
  rgsabound.cElements = 0;
  v12 = SafeArrayGetUBound(v4, 1u, (LONG *)&rgsabound);
  if ( v12 < 0 )
    ATL::BaseAtlThrow(v12);
  if ( (int)rgsabound.cElements < 2 )
    goto LABEL_62;
  *((float *)v4->pvData + 2 - plLbound) = a2;
  plLbound = 0;
  v13 = SafeArrayGetLBound(v4, 1u, &plLbound);
  if ( v13 < 0 )
    ATL::BaseAtlThrow(v13);
  if ( plLbound > 3 )
    goto LABEL_62;
  rgsabound.cElements = 0;
  v14 = SafeArrayGetUBound(v4, 1u, (LONG *)&rgsabound);
  if ( v14 < 0 )
    ATL::BaseAtlThrow(v14);
  if ( (int)rgsabound.cElements < 3 )
LABEL_62:
    ATL::BaseAtlThrow(-2147024809);
  *((_DWORD *)v4->pvData + 3 - plLbound) = 0;
  rgsabound = 0;
  Vartype = SafeArrayCopy(v4, (SAFEARRAY **)&rgsabound);
  if ( Vartype < 0 )
    goto LABEL_29;
  Vartype = SafeArrayGetVartype(v4, &pvt.vt);
  vt = pvt.vt;
  if ( Vartype >= 0 && pvt.vt == 13 && (v4->fFeatures & 0x440) == 0x440 )
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
    pvt.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
  }
  if ( Vartype < 0 )
  {
    if ( Vartype != -2147024882 )
      ATL::BaseAtlThrow(Vartype);
    ATL::BaseAtlThrow(-2147024882);
  }
  rgsabound = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, SAFEARRAYBOUND *))(**((_QWORD **)this + 18) + 152LL))(
          *((_QWORD *)this + 18),
          L"CompositeSceneEffect",
          &rgsabound);
  if ( v17 < 0 )
    ATL::BaseAtlThrow(v17);
  if ( !*(_QWORD *)&rgsabound )
    ATL::BaseAtlThrow(-2045247222);
  (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
  v35 = 0;
  if ( *(_QWORD *)&rgsabound
    && (***(int (__fastcall ****)(SAFEARRAYBOUND, GUID *, __int64 **))&rgsabound)(
         rgsabound,
         &GUID_0d7f0cfd_d49f_428e_8e69_76aa035fc43d,
         &v35) < 0 )
  {
    v35 = 0;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v18 = *v35;
  v39 = pvt;
  (*(void (__fastcall **)(__int64 *, _QWORD, VARIANTARG *, VARIANTARG *))(v18 + 56))(v35, 0, &v39, &pvarg);
  psa = 0;
  v19 = ATL::CComSafeArray<float,4>::CopyFrom(&psa, pvarg.parray);
  if ( v19 < 0 )
    ATL::BaseAtlThrow(v19);
  if ( !psa )
    ATL::BaseAtlThrow(-2147467259);
  v42 = 0;
  v20 = SafeArrayGetLBound(psa, 1u, &v42);
  if ( v20 < 0 )
    ATL::BaseAtlThrow(v20);
  v21 = v42;
  if ( v42 > 0 )
    goto LABEL_60;
  plLbound = 0;
  v22 = SafeArrayGetUBound(psa, 1u, &plLbound);
  if ( v22 < 0 )
    ATL::BaseAtlThrow(v22);
  if ( plLbound < 0 )
    goto LABEL_60;
  v23 = -v21;
  pvData = (float *)psa->pvData;
  plLbound = 0;
  v25 = SafeArrayGetLBound(psa, 1u, &plLbound);
  if ( v25 < 0 )
    ATL::BaseAtlThrow(v25);
  if ( plLbound > 1 )
    goto LABEL_60;
  rgsabound.cElements = 0;
  v26 = SafeArrayGetUBound(psa, 1u, (LONG *)&rgsabound);
  if ( v26 < 0 )
    ATL::BaseAtlThrow(v26);
  if ( (int)rgsabound.cElements < 1 )
    goto LABEL_60;
  v27 = 1 - plLbound;
  v28 = (float *)psa->pvData;
  rgsabound.cElements = 0;
  v29 = SafeArrayGetLBound(psa, 1u, (LONG *)&rgsabound);
  if ( v29 < 0 )
    ATL::BaseAtlThrow(v29);
  if ( (int)rgsabound.cElements > 2 )
    goto LABEL_60;
  plUbound = 0;
  v30 = SafeArrayGetUBound(psa, 1u, &plUbound);
  if ( v30 < 0 )
    ATL::BaseAtlThrow(v30);
  if ( plUbound < 2 )
LABEL_60:
    ATL::BaseAtlThrow(-2147024809);
  v31 = (float)(*((float *)psa->pvData + 2 - rgsabound.cElements) * 0.11)
      + (float)((float)(pvData[v23] * 0.30000001) + (float)(v28[v27] * 0.50999999));
  if ( SafeArrayUnlock(psa) >= 0 && SafeArrayDestroy(psa) >= 0 )
    psa = 0;
  VariantClear(&pvarg);
  if ( v35 )
    (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
  VariantClear(&pvt);
  if ( SafeArrayUnlock(v4) >= 0 )
    SafeArrayDestroy(v4);
  return v31;
}

```

## disassembly

```asm
0x180506df0  mov     rax, rsp
0x180506df3  mov     [rax+8], rbx
0x180506df7  push    rbp
0x180506df8  push    rsi
0x180506df9  push    rdi
0x180506dfa  push    r12
0x180506dfc  push    r13
0x180506dfe  push    r14
0x180506e00  push    r15
0x180506e02  lea     rbp, [rax-5Fh]
0x180506e06  sub     rsp, 0C0h
0x180506e0d  movaps  xmmword ptr [rax-48h], xmm6
0x180506e11  movaps  xmmword ptr [rax-58h], xmm7
0x180506e15  movaps  xmm6, xmm1
0x180506e18  mov     r14, rcx
0x180506e1b  xorps   xmm7, xmm7
0x180506e1e  mov     ecx, 4; vt
0x180506e23  mov     qword ptr [rbp+57h+rgsabound.cElements], rcx
0x180506e27  xor     r13d, r13d
0x180506e2a  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180506e2e  lea     r15d, [rcx-3]
0x180506e32  mov     edx, r15d; cDims
0x180506e35  call    cs:__imp_SafeArrayCreate
0x180506e3b  mov     rbx, rax
0x180506e3e  mov     [rbp+57h+var_78], rax
0x180506e42  mov     r12d, 8007000Eh
0x180506e48  test    rax, rax
0x180506e4b  jnz     short loc_180506E52
0x180506e4d  mov     eax, r12d
0x180506e50  jmp     short loc_180506E5B
0x180506e52  mov     rcx, rbx; psa
0x180506e55  call    cs:__imp_SafeArrayLock
0x180506e5b  test    eax, eax
0x180506e5d  js      loc_18050732D
0x180506e63  test    rbx, rbx
0x180506e66  jz      loc_180507339
0x180506e6c  mov     [rbp+57h+plLbound], r13d
0x180506e70  lea     r8, [rbp+57h+plLbound]; plLbound
0x180506e74  mov     edx, r15d; nDim
0x180506e77  mov     rcx, rbx; psa
0x180506e7a  call    cs:__imp_SafeArrayGetLBound
0x180506e80  test    eax, eax
0x180506e82  js      loc_180507344
0x180506e88  movsxd  rdi, [rbp+57h+plLbound]
0x180506e8c  test    edi, edi
0x180506e8e  jg      loc_18050731E
0x180506e94  mov     [rbp+57h+plLbound], r13d
0x180506e98  lea     r8, [rbp+57h+plLbound]; plUbound
0x180506e9c  mov     edx, r15d; nDim
0x180506e9f  mov     rcx, rbx; psa
0x180506ea2  call    cs:__imp_SafeArrayGetUBound
0x180506ea8  test    eax, eax
0x180506eaa  js      loc_18050734C
0x180506eb0  cmp     [rbp+57h+plLbound], r13d
0x180506eb4  jl      loc_18050731E
0x180506eba  mov     rcx, rdi
0x180506ebd  shl     rcx, 2
0x180506ec1  mov     rax, [rbx+10h]
0x180506ec5  sub     rax, rcx
0x180506ec8  movss   dword ptr [rax], xmm6
0x180506ecc  mov     [rbp+57h+plLbound], r13d
0x180506ed0  lea     r8, [rbp+57h+plLbound]; plLbound
0x180506ed4  mov     edx, r15d; nDim
0x180506ed7  mov     rcx, rbx; psa
0x180506eda  call    cs:__imp_SafeArrayGetLBound
0x180506ee0  test    eax, eax
0x180506ee2  js      loc_180507354
0x180506ee8  cmp     [rbp+57h+plLbound], r15d
0x180506eec  jg      loc_18050731E
0x180506ef2  mov     [rbp+57h+rgsabound.cElements], r13d
0x180506ef6  lea     r8, [rbp+57h+rgsabound]; plUbound
0x180506efa  mov     edx, r15d; nDim
0x180506efd  mov     rcx, rbx; psa
0x180506f00  call    cs:__imp_SafeArrayGetUBound
0x180506f06  test    eax, eax
0x180506f08  js      loc_18050735C
0x180506f0e  cmp     [rbp+57h+rgsabound.cElements], r15d
0x180506f12  jl      loc_18050731E
0x180506f18  mov     eax, r15d
0x180506f1b  sub     eax, [rbp+57h+plLbound]
0x180506f1e  movsxd  rcx, eax
0x180506f21  mov     rax, [rbx+10h]
0x180506f25  movss   dword ptr [rax+rcx*4], xmm6
0x180506f2a  mov     [rbp+57h+plLbound], r13d
0x180506f2e  lea     r8, [rbp+57h+plLbound]; plLbound
0x180506f32  mov     edx, r15d; nDim
0x180506f35  mov     rcx, rbx; psa
0x180506f38  call    cs:__imp_SafeArrayGetLBound
0x180506f3e  test    eax, eax
0x180506f40  js      loc_180507364
0x180506f46  mov     esi, 2
0x180506f4b  cmp     [rbp+57h+plLbound], esi
0x180506f4e  jg      loc_18050731E
0x180506f54  mov     [rbp+57h+rgsabound.cElements], r13d
0x180506f58  lea     r8, [rbp+57h+rgsabound]; plUbound
0x180506f5c  mov     edx, r15d; nDim
0x180506f5f  mov     rcx, rbx; psa
0x180506f62  call    cs:__imp_SafeArrayGetUBound
0x180506f68  test    eax, eax
0x180506f6a  js      loc_18050736C
0x180506f70  cmp     [rbp+57h+rgsabound.cElements], esi
0x180506f73  jl      loc_18050731E
0x180506f79  mov     eax, esi
0x180506f7b  sub     eax, [rbp+57h+plLbound]
0x180506f7e  movsxd  rcx, eax
0x180506f81  mov     rax, [rbx+10h]
0x180506f85  movss   dword ptr [rax+rcx*4], xmm6
0x180506f8a  mov     [rbp+57h+plLbound], r13d
0x180506f8e  lea     r8, [rbp+57h+plLbound]; plLbound
0x180506f92  mov     edx, r15d; nDim
0x180506f95  mov     rcx, rbx; psa
0x180506f98  call    cs:__imp_SafeArrayGetLBound
0x180506f9e  test    eax, eax
0x180506fa0  js      loc_180507374
0x180506fa6  lea     edi, [rsi+1]
0x180506fa9  cmp     [rbp+57h+plLbound], edi
0x180506fac  jg      loc_18050731E
0x180506fb2  mov     [rbp+57h+rgsabound.cElements], r13d
0x180506fb6  lea     r8, [rbp+57h+rgsabound]; plUbound
0x180506fba  mov     edx, r15d; nDim
0x180506fbd  mov     rcx, rbx; psa
0x180506fc0  call    cs:__imp_SafeArrayGetUBound
0x180506fc6  test    eax, eax
0x180506fc8  js      loc_18050737C
0x180506fce  cmp     [rbp+57h+rgsabound.cElements], edi
0x180506fd1  jl      loc_18050731E
0x180506fd7  sub     edi, [rbp+57h+plLbound]
0x180506fda  movsxd  rcx, edi
0x180506fdd  mov     rax, [rbx+10h]
0x180506fe1  movss   dword ptr [rax+rcx*4], xmm7
0x180506fe6  mov     qword ptr [rbp+57h+rgsabound.cElements], r13
0x180506fea  lea     rdx, [rbp+57h+rgsabound]; ppsaOut
0x180506fee  mov     rcx, rbx; psa
0x180506ff1  call    cs:__imp_SafeArrayCopy
0x180506ff7  mov     ecx, eax; int
0x180506ff9  test    eax, eax
0x180506ffb  js      short loc_180507048
0x180506ffd  lea     rdx, [rbp+57h+pvt]; pvt
0x180507001  mov     rcx, rbx; psa
0x180507004  call    cs:__imp_SafeArrayGetVartype
0x18050700a  mov     ecx, eax
0x18050700c  movzx   edx, [rbp+57h+pvt]
0x180507010  test    eax, eax
0x180507012  js      short loc_180507031
0x180507014  cmp     dx, 0Dh
0x180507018  jnz     short loc_180507031
0x18050701a  movzx   eax, word ptr [rbx+2]
0x18050701e  mov     r8d, 440h
0x180507024  and     ax, r8w
0x180507028  cmp     ax, r8w
0x18050702c  jnz     short loc_180507031
0x18050702e  lea     edx, [rsi+7]
0x180507031  test    ecx, ecx
0x180507033  js      short loc_180507048
0x180507035  or      dx, 2000h
0x18050703a  mov     [rbp+57h+pvt], dx
0x18050703e  mov     rax, qword ptr [rbp+57h+rgsabound.cElements]
0x180507042  mov     qword ptr [rbp+57h+pvt+8], rax
0x180507046  jmp     short loc_180507054
0x180507048  mov     eax, 0Ah
0x18050704d  mov     dword ptr [rbp+57h+pvt+8], ecx
0x180507050  mov     [rbp+57h+pvt], ax
0x180507054  test    ecx, ecx
0x180507056  jns     short loc_180507066
0x180507058  cmp     ecx, r12d
0x18050705b  jz      loc_180507315
0x180507061  jmp     loc_180507384
0x180507066  mov     qword ptr [rbp+57h+rgsabound.cElements], r13
0x18050706a  mov     rcx, [r14+90h]
0x180507071  mov     rax, [rcx]
0x180507074  lea     r8, [rbp+57h+rgsabound]
0x180507078  lea     rdx, aCompositescene; "CompositeSceneEffect"
0x18050707f  mov     rax, [rax+98h]
0x180507086  call    cs:__guard_dispatch_icall_fptr
0x18050708c  test    eax, eax
0x18050708e  js      loc_18050738D
0x180507094  mov     rcx, qword ptr [rbp+57h+rgsabound.cElements]
0x180507098  test    rcx, rcx
0x18050709b  jz      loc_180507395
0x1805070a1  mov     rax, [rcx]
0x1805070a4  mov     rax, [rax+10h]
0x1805070a8  call    cs:__guard_dispatch_icall_fptr
0x1805070ae  mov     rcx, qword ptr [rbp+57h+rgsabound.cElements]
0x1805070b2  mov     [rbp+57h+var_B0], r13
0x1805070b6  test    rcx, rcx
0x1805070b9  jz      short loc_1805070DA
0x1805070bb  mov     rax, [rcx]
0x1805070be  lea     r8, [rbp+57h+var_B0]
0x1805070c2  lea     rdx, _GUID_0d7f0cfd_d49f_428e_8e69_76aa035fc43d
0x1805070c9  mov     rax, [rax]
0x1805070cc  call    cs:__guard_dispatch_icall_fptr
0x1805070d2  test    eax, eax
0x1805070d4  jns     short loc_1805070DA
0x1805070d6  mov     [rbp+57h+var_B0], r13
0x1805070da  xorps   xmm0, xmm0
0x1805070dd  xor     eax, eax
0x1805070df  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1805070e3  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1805070e7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1805070eb  call    cs:__imp_VariantInit
0x1805070f1  mov     rcx, [rbp+57h+var_B0]
0x1805070f5  mov     rax, [rcx]
0x1805070f8  movups  xmm0, xmmword ptr [rbp+57h+pvt]
0x1805070fc  movaps  [rbp+57h+var_70], xmm0
0x180507100  movsd   xmm1, [rbp+57h+var_98]
0x180507105  movsd   [rbp+57h+var_60], xmm1
0x18050710a  lea     r9, [rbp+57h+pvarg]
0x18050710e  lea     r8, [rbp+57h+var_70]
0x180507112  xor     edx, edx
0x180507114  mov     rax, [rax+38h]
0x180507118  call    cs:__guard_dispatch_icall_fptr
0x18050711e  mov     [rbp+57h+psa], r13
0x180507122  mov     rdx, qword ptr [rbp+57h+pvarg+8]; psa
0x180507126  lea     rcx, [rbp+57h+psa]; ppsaOut
0x18050712a  call    ?CopyFrom@?$CComSafeArray@M$03@ATL@@QEAAJPEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<float,4>::CopyFrom(tagSAFEARRAY const *)
0x18050712f  test    eax, eax
0x180507131  js      loc_1805073A5
0x180507137  mov     rcx, [rbp+57h+psa]; psa
0x18050713b  test    rcx, rcx
0x18050713e  jz      loc_1805073B1
0x180507144  mov     [rbp+57h+arg_18], r13d
0x180507148  lea     r8, [rbp+57h+arg_18]; plLbound
0x18050714c  mov     edx, r15d; nDim
0x18050714f  call    cs:__imp_SafeArrayGetLBound
0x180507155  test    eax, eax
0x180507157  js      loc_1805073BC
0x18050715d  mov     edi, [rbp+57h+arg_18]
0x180507160  test    edi, edi
0x180507162  jg      loc_180507307
0x180507168  mov     [rbp+57h+plLbound], r13d
0x18050716c  lea     r8, [rbp+57h+plLbound]; plUbound
0x180507170  mov     edx, r15d; nDim
0x180507173  mov     rcx, [rbp+57h+psa]; psa
0x180507177  call    cs:__imp_SafeArrayGetUBound
0x18050717d  test    eax, eax
0x18050717f  js      loc_1805073C4
0x180507185  cmp     [rbp+57h+plLbound], r13d
0x180507189  jl      loc_180507307
0x18050718f  neg     edi
0x180507191  movsxd  r15, edi
0x180507194  mov     rcx, [rbp+57h+psa]; psa
0x180507198  mov     r12, [rcx+10h]
0x18050719c  mov     [rbp+57h+plLbound], r13d
0x1805071a0  lea     r8, [rbp+57h+plLbound]; plLbound
0x1805071a4  mov     edi, 1
0x1805071a9  mov     edx, edi; nDim
0x1805071ab  call    cs:__imp_SafeArrayGetLBound
0x1805071b1  test    eax, eax
0x1805071b3  js      loc_1805073CC
0x1805071b9  cmp     [rbp+57h+plLbound], edi
0x1805071bc  jg      loc_180507307
0x1805071c2  mov     [rbp+57h+rgsabound.cElements], r13d
0x1805071c6  lea     r8, [rbp+57h+rgsabound]; plUbound
0x1805071ca  mov     edx, edi; nDim
0x1805071cc  mov     rcx, [rbp+57h+psa]; psa
0x1805071d0  call    cs:__imp_SafeArrayGetUBound
0x1805071d6  test    eax, eax
0x1805071d8  js      loc_1805073D4
0x1805071de  cmp     [rbp+57h+rgsabound.cElements], edi
0x1805071e1  jl      loc_180507307
0x1805071e7  mov     eax, edi
0x1805071e9  sub     eax, [rbp+57h+plLbound]
0x1805071ec  movsxd  rdi, eax
0x1805071ef  mov     rcx, [rbp+57h+psa]; psa
0x1805071f3  mov     r14, [rcx+10h]
0x1805071f7  mov     [rbp+57h+rgsabound.cElements], r13d
0x1805071fb  lea     r8, [rbp+57h+rgsabound]; plLbound
0x1805071ff  mov     edx, 1; nDim
0x180507204  call    cs:__imp_SafeArrayGetLBound
0x18050720a  test    eax, eax
0x18050720c  js      loc_1805073DC
0x180507212  cmp     [rbp+57h+rgsabound.cElements], esi
0x180507215  jg      loc_180507307
0x18050721b  mov     [rbp+57h+plUbound], r13d
0x18050721f  lea     r8, [rbp+57h+plUbound]; plUbound
0x180507223  mov     edx, 1; nDim
0x180507228  mov     rcx, [rbp+57h+psa]; psa
0x18050722c  call    cs:__imp_SafeArrayGetUBound
0x180507232  test    eax, eax
0x180507234  js      loc_1805073E4
0x18050723a  cmp     [rbp+57h+plUbound], esi
0x18050723d  jl      loc_180507307
0x180507243  sub     esi, [rbp+57h+rgsabound.cElements]
0x180507246  movsxd  rdx, esi
0x180507249  mov     rcx, [rbp+57h+psa]; psa
0x18050724d  mov     rax, [rcx+10h]
0x180507251  movss   xmm6, dword ptr [rax+rdx*4]
0x180507256  mulss   xmm6, cs:__real@3de147ae
0x18050725e  movss   xmm1, dword ptr [r12+r15*4]
0x180507264  mulss   xmm1, cs:__real@3e99999a
0x18050726c  movss   xmm0, dword ptr [r14+rdi*4]
0x180507272  mulss   xmm0, cs:__real@3f028f5c
0x18050727a  addss   xmm1, xmm0
0x18050727e  addss   xmm6, xmm1
0x180507282  call    cs:__imp_SafeArrayUnlock
0x180507288  test    eax, eax
0x18050728a  js      short loc_18050729E
0x18050728c  mov     rcx, [rbp+57h+psa]; psa
0x180507290  call    cs:__imp_SafeArrayDestroy
0x180507296  test    eax, eax
  ... truncated ...
```
