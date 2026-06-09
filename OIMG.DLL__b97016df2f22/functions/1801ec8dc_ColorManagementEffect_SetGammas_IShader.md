# ColorManagementEffect::SetGammas(IShader *)

- ea: `0x1801ec8dc`
- end: `0x1801ecf81`
- name: `?SetGammas@ColorManagementEffect@@AEBAXPEAUIShader@@@Z`
- size: `1701`
- prototype: `void __fastcall(ColorManagementEffect *__hidden this, struct IShader *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801ed5c0`

## callees

- `0x1801ec8dc`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1801ecba9`
- `OLEAUT32!__imp_VariantClear` at `0x1801ece45`
- `OLEAUT32!__imp_VariantClear` at `0x1801ecba9`
- `OLEAUT32!__imp_VariantClear` at `0x1801ece45`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801ec921`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801ecbcb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801ec921`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801ecbcb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801ece63`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801ece7a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801ece63`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801ece7a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ec9b6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801eca38`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ecac0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ecc5b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ecce3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ecd60`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ec9b6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801eca38`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ecac0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ecc5b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ecce3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ecd60`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ec98e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801eca12`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801eca94`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ecc30`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801eccbd`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ecd3a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ec98e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801eca12`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801eca94`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ecc30`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801eccbd`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ecd3a`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801ec93d`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801ecbe7`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801ec93d`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801ecbe7`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801ece56`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801ece6d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801ece56`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801ece6d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801ecafd`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801ecd9b`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801ecafd`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801ecd9b`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801ecb14`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801ecdae`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801ecb14`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801ecdae`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ColorManagementEffect::SetGammas(ColorManagementEffect *this, struct IShader *a2)
{
  SAFEARRAY *v4; // rax
  SAFEARRAY *v5; // rdi
  HRESULT v6; // eax
  int v7; // eax
  float v8; // xmm7_4
  float v9; // xmm6_4
  HRESULT LBound; // eax
  __int64 cElements; // rbx
  HRESULT UBound; // eax
  int v13; // eax
  float v14; // xmm6_4
  HRESULT v15; // eax
  HRESULT v16; // eax
  int v17; // eax
  float v18; // xmm6_4
  HRESULT v19; // eax
  HRESULT v20; // eax
  __int64 (__fastcall *v21)(struct IShader *, const wchar_t *, VARIANTARG *); // rbx
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v24; // ebx
  SAFEARRAY *v25; // rax
  SAFEARRAY *v26; // rbx
  HRESULT v27; // eax
  int v28; // eax
  float v29; // xmm6_4
  HRESULT v30; // eax
  __int64 v31; // r14
  HRESULT v32; // eax
  int v33; // eax
  float v34; // xmm6_4
  HRESULT v35; // eax
  HRESULT v36; // eax
  int v37; // eax
  HRESULT v38; // eax
  HRESULT v39; // eax
  __int64 (__fastcall *v40)(struct IShader *, const wchar_t *, VARIANTARG *); // rsi
  HRESULT v41; // ecx
  VARTYPE v42; // dx
  int v43; // esi
  VARIANTARG pvt; // [rsp+38h] [rbp-39h] BYREF
  VARIANTARG v45; // [rsp+58h] [rbp-19h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+E8h] [rbp+77h] BYREF
  LONG plUbound; // [rsp+F0h] [rbp+7Fh] BYREF

  rgsabound = (SAFEARRAYBOUND)3LL;
  v4 = SafeArrayCreate(4u, 1u, &rgsabound);
  v5 = v4;
  if ( v4 )
    v6 = SafeArrayLock(v4);
  else
    v6 = -2147024882;
  if ( v6 < 0 )
    ATL::BaseAtlThrow(v6);
  v7 = *((_DWORD *)this + 154);
  v8 = FLOAT_1_0;
  if ( v7 )
  {
    if ( v7 == 1 )
      v9 = **((float **)this + 76);
    else
      v9 = 0.0;
  }
  else
  {
    v9 = FLOAT_1_0;
  }
  if ( !v5 )
    ATL::BaseAtlThrow(-2147467259);
  rgsabound.cElements = 0;
  LBound = SafeArrayGetLBound(v5, 1u, (LONG *)&rgsabound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  cElements = (int)rgsabound.cElements;
  if ( (int)rgsabound.cElements > 0 )
    goto LABEL_96;
  rgsabound.cElements = 0;
  UBound = SafeArrayGetUBound(v5, 1u, (LONG *)&rgsabound);
  if ( UBound < 0 )
    ATL::BaseAtlThrow(UBound);
  if ( (rgsabound.cElements & 0x80000000) != 0 )
    goto LABEL_96;
  *((float *)v5->pvData - cElements) = v9;
  v13 = *((_DWORD *)this + 158);
  if ( v13 )
  {
    if ( v13 == 1 )
      v14 = **((float **)this + 78);
    else
      v14 = 0.0;
  }
  else
  {
    v14 = FLOAT_1_0;
  }
  rgsabound.cElements = 0;
  v15 = SafeArrayGetLBound(v5, 1u, (LONG *)&rgsabound);
  if ( v15 < 0 )
    ATL::BaseAtlThrow(v15);
  if ( (int)rgsabound.cElements > 1 )
    goto LABEL_96;
  plUbound = 0;
  v16 = SafeArrayGetUBound(v5, 1u, &plUbound);
  if ( v16 < 0 )
    ATL::BaseAtlThrow(v16);
  if ( plUbound < 1 )
    goto LABEL_96;
  *((float *)v5->pvData + 1 - rgsabound.cElements) = v14;
  v17 = *((_DWORD *)this + 162);
  if ( v17 )
  {
    if ( v17 == 1 )
      v18 = **((float **)this + 80);
    else
      v18 = 0.0;
  }
  else
  {
    v18 = FLOAT_1_0;
  }
  rgsabound.cElements = 0;
  v19 = SafeArrayGetLBound(v5, 1u, (LONG *)&rgsabound);
  if ( v19 < 0 )
    ATL::BaseAtlThrow(v19);
  if ( (int)rgsabound.cElements > 2 )
    goto LABEL_96;
  plUbound = 0;
  v20 = SafeArrayGetUBound(v5, 1u, &plUbound);
  if ( v20 < 0 )
    ATL::BaseAtlThrow(v20);
  if ( plUbound < 2 )
LABEL_96:
    ATL::BaseAtlThrow(-2147024809);
  *((float *)v5->pvData + 2 - rgsabound.cElements) = v18;
  v21 = *(__int64 (__fastcall **)(struct IShader *, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 104LL);
  rgsabound = 0;
  Vartype = SafeArrayCopy(v5, (SAFEARRAY **)&rgsabound);
  if ( Vartype < 0 )
    goto LABEL_40;
  Vartype = SafeArrayGetVartype(v5, &pvt.vt);
  vt = pvt.vt;
  if ( Vartype >= 0 && pvt.vt == 13 && (v5->fFeatures & 0x440) == 0x440 )
    vt = 9;
  if ( Vartype < 0 )
  {
LABEL_40:
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
  v45 = pvt;
  v24 = v21(a2, L"aflGamma1", &v45);
  VariantClear(&pvt);
  if ( v24 < 0 )
    ATL::BaseAtlThrow(v24);
  rgsabound = (SAFEARRAYBOUND)3LL;
  v25 = SafeArrayCreate(4u, 1u, &rgsabound);
  v26 = v25;
  if ( v25 )
    v27 = SafeArrayLock(v25);
  else
    v27 = -2147024882;
  if ( v27 < 0 )
    ATL::BaseAtlThrow(v27);
  v28 = *((_DWORD *)this + 62);
  if ( v28 )
  {
    if ( v28 == 1 )
      v29 = **((float **)this + 30);
    else
      v29 = 0.0;
  }
  else
  {
    v29 = FLOAT_1_0;
  }
  if ( !v26 )
    ATL::BaseAtlThrow(-2147467259);
  rgsabound.cElements = 0;
  v30 = SafeArrayGetLBound(v26, 1u, (LONG *)&rgsabound);
  if ( v30 < 0 )
    ATL::BaseAtlThrow(v30);
  v31 = (int)rgsabound.cElements;
  if ( (int)rgsabound.cElements > 0 )
    goto LABEL_114;
  rgsabound.cElements = 0;
  v32 = SafeArrayGetUBound(v26, 1u, (LONG *)&rgsabound);
  if ( v32 < 0 )
    ATL::BaseAtlThrow(v32);
  if ( (rgsabound.cElements & 0x80000000) != 0 )
    goto LABEL_114;
  *((float *)v26->pvData - v31) = v29;
  v33 = *((_DWORD *)this + 66);
  if ( v33 )
  {
    if ( v33 == 1 )
      v34 = **((float **)this + 32);
    else
      v34 = 0.0;
  }
  else
  {
    v34 = FLOAT_1_0;
  }
  rgsabound.cElements = 0;
  v35 = SafeArrayGetLBound(v26, 1u, (LONG *)&rgsabound);
  if ( v35 < 0 )
    ATL::BaseAtlThrow(v35);
  if ( (int)rgsabound.cElements > 1 )
    goto LABEL_114;
  plUbound = 0;
  v36 = SafeArrayGetUBound(v26, 1u, &plUbound);
  if ( v36 < 0 )
    ATL::BaseAtlThrow(v36);
  if ( plUbound < 1 )
    goto LABEL_114;
  *((float *)v26->pvData + 1 - rgsabound.cElements) = v34;
  v37 = *((_DWORD *)this + 70);
  if ( v37 )
  {
    if ( v37 == 1 )
      v8 = **((float **)this + 34);
    else
      v8 = 0.0;
  }
  rgsabound.cElements = 0;
  v38 = SafeArrayGetLBound(v26, 1u, (LONG *)&rgsabound);
  if ( v38 < 0 )
    ATL::BaseAtlThrow(v38);
  if ( (int)rgsabound.cElements > 2 )
    goto LABEL_114;
  plUbound = 0;
  v39 = SafeArrayGetUBound(v26, 1u, &plUbound);
  if ( v39 < 0 )
    ATL::BaseAtlThrow(v39);
  if ( plUbound < 2 )
LABEL_114:
    ATL::BaseAtlThrow(-2147024809);
  *((float *)v26->pvData + 2 - rgsabound.cElements) = v8;
  v40 = *(__int64 (__fastcall **)(struct IShader *, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 104LL);
  rgsabound = 0;
  v41 = SafeArrayCopy(v26, (SAFEARRAY **)&rgsabound);
  if ( v41 < 0 )
    goto LABEL_83;
  v41 = SafeArrayGetVartype(v26, &pvt.vt);
  v42 = pvt.vt;
  if ( v41 >= 0 && pvt.vt == 13 && (v26->fFeatures & 0x440) == 0x440 )
    v42 = 9;
  if ( v41 < 0 )
  {
LABEL_83:
    pvt.lVal = v41;
    pvt.vt = 10;
  }
  else
  {
    pvt.vt = v42 | 0x2000;
    pvt.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
  }
  if ( v41 < 0 )
  {
    if ( v41 != -2147024882 )
      ATL::BaseAtlThrow(v41);
    ATL::BaseAtlThrow(-2147024882);
  }
  v45 = pvt;
  v43 = v40(a2, L"aflGamma2Inv", &v45);
  VariantClear(&pvt);
  if ( v43 < 0 )
    ATL::BaseAtlThrow(v43);
  if ( SafeArrayUnlock(v26) >= 0 )
    SafeArrayDestroy(v26);
  if ( SafeArrayUnlock(v5) >= 0 )
    SafeArrayDestroy(v5);
}

```

## disassembly

```asm
0x1801ec8dc  mov     rax, rsp
0x1801ec8df  mov     [rax+8], rbx
0x1801ec8e3  push    rbp
0x1801ec8e4  push    rsi
0x1801ec8e5  push    rdi
0x1801ec8e6  push    r12
0x1801ec8e8  push    r13
0x1801ec8ea  push    r14
0x1801ec8ec  push    r15
0x1801ec8ee  lea     rbp, [rax-5Fh]
0x1801ec8f2  sub     rsp, 90h
0x1801ec8f9  movaps  xmmword ptr [rax-48h], xmm6
0x1801ec8fd  movaps  xmmword ptr [rax-58h], xmm7
0x1801ec901  mov     r12, rdx
0x1801ec904  mov     rsi, rcx
0x1801ec907  mov     qword ptr [rbp+57h+rgsabound.cElements], 3
0x1801ec90f  xor     r13d, r13d
0x1801ec912  lea     ecx, [r13+4]; vt
0x1801ec916  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1801ec91a  lea     r14d, [r13+1]
0x1801ec91e  mov     edx, r14d; cDims
0x1801ec921  call    cs:__imp_SafeArrayCreate
0x1801ec927  mov     rdi, rax
0x1801ec92a  mov     [rbp+57h+var_A0], rax
0x1801ec92e  test    rax, rax
0x1801ec931  jnz     short loc_1801EC93A
0x1801ec933  mov     eax, 8007000Eh
0x1801ec938  jmp     short loc_1801EC943
0x1801ec93a  mov     rcx, rdi; psa
0x1801ec93d  call    cs:__imp_SafeArrayLock
0x1801ec943  test    eax, eax
0x1801ec945  js      loc_1801ECED5
0x1801ec94b  mov     eax, [rsi+268h]
0x1801ec951  movss   xmm7, cs:__real@3f800000
0x1801ec959  test    eax, eax
0x1801ec95b  jnz     short loc_1801EC962
0x1801ec95d  movaps  xmm6, xmm7
0x1801ec960  jmp     short loc_1801EC977
0x1801ec962  cmp     eax, r14d
0x1801ec965  jnz     short loc_1801EC974
0x1801ec967  mov     rax, [rsi+260h]
0x1801ec96e  movss   xmm6, dword ptr [rax]
0x1801ec972  jmp     short loc_1801EC977
0x1801ec974  xorps   xmm6, xmm6
0x1801ec977  test    rdi, rdi
0x1801ec97a  jz      loc_1801ECEE1
0x1801ec980  mov     [rbp+57h+rgsabound.cElements], r13d
0x1801ec984  lea     r8, [rbp+57h+rgsabound]; plLbound
0x1801ec988  mov     edx, r14d; nDim
0x1801ec98b  mov     rcx, rdi; psa
0x1801ec98e  call    cs:__imp_SafeArrayGetLBound
0x1801ec994  test    eax, eax
0x1801ec996  js      loc_1801ECEEC
0x1801ec99c  movsxd  rbx, [rbp+57h+rgsabound.cElements]
0x1801ec9a0  test    ebx, ebx
0x1801ec9a2  jg      loc_1801ECEC6
0x1801ec9a8  mov     [rbp+57h+rgsabound.cElements], r13d
0x1801ec9ac  lea     r8, [rbp+57h+rgsabound]; plUbound
0x1801ec9b0  mov     edx, r14d; nDim
0x1801ec9b3  mov     rcx, rdi; psa
0x1801ec9b6  call    cs:__imp_SafeArrayGetUBound
0x1801ec9bc  test    eax, eax
0x1801ec9be  js      loc_1801ECEF4
0x1801ec9c4  cmp     [rbp+57h+rgsabound.cElements], r13d
0x1801ec9c8  jl      loc_1801ECEC6
0x1801ec9ce  mov     rcx, rbx
0x1801ec9d1  shl     rcx, 2
0x1801ec9d5  mov     rax, [rdi+10h]
0x1801ec9d9  sub     rax, rcx
0x1801ec9dc  movss   dword ptr [rax], xmm6
0x1801ec9e0  mov     eax, [rsi+278h]
0x1801ec9e6  test    eax, eax
0x1801ec9e8  jnz     short loc_1801EC9EF
0x1801ec9ea  movaps  xmm6, xmm7
0x1801ec9ed  jmp     short loc_1801ECA04
0x1801ec9ef  cmp     eax, r14d
0x1801ec9f2  jnz     short loc_1801ECA01
0x1801ec9f4  mov     rax, [rsi+270h]
0x1801ec9fb  movss   xmm6, dword ptr [rax]
0x1801ec9ff  jmp     short loc_1801ECA04
0x1801eca01  xorps   xmm6, xmm6
0x1801eca04  mov     [rbp+57h+rgsabound.cElements], r13d
0x1801eca08  lea     r8, [rbp+57h+rgsabound]; plLbound
0x1801eca0c  mov     edx, r14d; nDim
0x1801eca0f  mov     rcx, rdi; psa
0x1801eca12  call    cs:__imp_SafeArrayGetLBound
0x1801eca18  test    eax, eax
0x1801eca1a  js      loc_1801ECEFC
0x1801eca20  cmp     [rbp+57h+rgsabound.cElements], r14d
0x1801eca24  jg      loc_1801ECEC6
0x1801eca2a  mov     [rbp+57h+plUbound], r13d
0x1801eca2e  lea     r8, [rbp+57h+plUbound]; plUbound
0x1801eca32  mov     edx, r14d; nDim
0x1801eca35  mov     rcx, rdi; psa
0x1801eca38  call    cs:__imp_SafeArrayGetUBound
0x1801eca3e  test    eax, eax
0x1801eca40  js      loc_1801ECF04
0x1801eca46  cmp     [rbp+57h+plUbound], r14d
0x1801eca4a  jl      loc_1801ECEC6
0x1801eca50  mov     eax, r14d
0x1801eca53  sub     eax, [rbp+57h+rgsabound.cElements]
0x1801eca56  movsxd  rcx, eax
0x1801eca59  mov     rax, [rdi+10h]
0x1801eca5d  movss   dword ptr [rax+rcx*4], xmm6
0x1801eca62  mov     eax, [rsi+288h]
0x1801eca68  test    eax, eax
0x1801eca6a  jnz     short loc_1801ECA71
0x1801eca6c  movaps  xmm6, xmm7
0x1801eca6f  jmp     short loc_1801ECA86
0x1801eca71  cmp     eax, r14d
0x1801eca74  jnz     short loc_1801ECA83
0x1801eca76  mov     rax, [rsi+280h]
0x1801eca7d  movss   xmm6, dword ptr [rax]
0x1801eca81  jmp     short loc_1801ECA86
0x1801eca83  xorps   xmm6, xmm6
0x1801eca86  mov     [rbp+57h+rgsabound.cElements], r13d
0x1801eca8a  lea     r8, [rbp+57h+rgsabound]; plLbound
0x1801eca8e  mov     edx, r14d; nDim
0x1801eca91  mov     rcx, rdi; psa
0x1801eca94  call    cs:__imp_SafeArrayGetLBound
0x1801eca9a  test    eax, eax
0x1801eca9c  js      loc_1801ECF0C
0x1801ecaa2  mov     r15d, 2
0x1801ecaa8  cmp     [rbp+57h+rgsabound.cElements], r15d
0x1801ecaac  jg      loc_1801ECEC6
0x1801ecab2  mov     [rbp+57h+plUbound], r13d
0x1801ecab6  lea     r8, [rbp+57h+plUbound]; plUbound
0x1801ecaba  mov     edx, r14d; nDim
0x1801ecabd  mov     rcx, rdi; psa
0x1801ecac0  call    cs:__imp_SafeArrayGetUBound
0x1801ecac6  test    eax, eax
0x1801ecac8  js      loc_1801ECF14
0x1801ecace  cmp     [rbp+57h+plUbound], r15d
0x1801ecad2  jl      loc_1801ECEC6
0x1801ecad8  mov     eax, r15d
0x1801ecadb  sub     eax, [rbp+57h+rgsabound.cElements]
0x1801ecade  movsxd  rcx, eax
0x1801ecae1  mov     rax, [rdi+10h]
0x1801ecae5  movss   dword ptr [rax+rcx*4], xmm6
0x1801ecaea  mov     rax, [r12]
0x1801ecaee  mov     rbx, [rax+68h]
0x1801ecaf2  mov     qword ptr [rbp+57h+rgsabound.cElements], r13
0x1801ecaf6  lea     rdx, [rbp+57h+rgsabound]; ppsaOut
0x1801ecafa  mov     rcx, rdi; psa
0x1801ecafd  call    cs:__imp_SafeArrayCopy
0x1801ecb03  mov     ecx, eax
0x1801ecb05  lea     eax, [r15+8]
0x1801ecb09  test    ecx, ecx
0x1801ecb0b  js      short loc_1801ECB5E
0x1801ecb0d  lea     rdx, [rbp+57h+pvt]; pvt
0x1801ecb11  mov     rcx, rdi; psa
0x1801ecb14  call    cs:__imp_SafeArrayGetVartype
0x1801ecb1a  mov     ecx, eax; int
0x1801ecb1c  movzx   edx, [rbp+57h+pvt]
0x1801ecb20  test    eax, eax
0x1801ecb22  js      short loc_1801ECB42
0x1801ecb24  cmp     dx, 0Dh
0x1801ecb28  jnz     short loc_1801ECB42
0x1801ecb2a  movzx   eax, word ptr [rdi+2]
0x1801ecb2e  mov     r8d, 440h
0x1801ecb34  and     ax, r8w
0x1801ecb38  cmp     ax, r8w
0x1801ecb3c  jnz     short loc_1801ECB42
0x1801ecb3e  lea     edx, [r15+7]
0x1801ecb42  test    ecx, ecx
0x1801ecb44  js      short loc_1801ECB59
0x1801ecb46  or      dx, 2000h
0x1801ecb4b  mov     [rbp+57h+pvt], dx
0x1801ecb4f  mov     rax, qword ptr [rbp+57h+rgsabound.cElements]
0x1801ecb53  mov     qword ptr [rbp+57h+pvt+8], rax
0x1801ecb57  jmp     short loc_1801ECB65
0x1801ecb59  mov     eax, 0Ah
0x1801ecb5e  mov     dword ptr [rbp+57h+pvt+8], ecx
0x1801ecb61  mov     [rbp+57h+pvt], ax
0x1801ecb65  test    ecx, ecx
0x1801ecb67  jns     short loc_1801ECB7A
0x1801ecb69  cmp     ecx, 8007000Eh
0x1801ecb6f  jz      loc_1801ECEAD
0x1801ecb75  jmp     loc_1801ECF1C
0x1801ecb7a  movups  xmm0, xmmword ptr [rbp+57h+pvt]
0x1801ecb7e  movaps  [rbp+57h+var_70], xmm0
0x1801ecb82  movsd   xmm1, [rbp+57h+var_80]
0x1801ecb87  movsd   [rbp+57h+var_60], xmm1
0x1801ecb8c  lea     r8, [rbp+57h+var_70]
0x1801ecb90  lea     rdx, aAflgamma1; "aflGamma1"
0x1801ecb97  mov     rcx, r12
0x1801ecb9a  mov     rax, rbx
0x1801ecb9d  call    cs:__guard_dispatch_icall_fptr
0x1801ecba3  mov     ebx, eax
0x1801ecba5  lea     rcx, [rbp+57h+pvt]; pvarg
0x1801ecba9  call    cs:__imp_VariantClear
0x1801ecbaf  test    ebx, ebx
0x1801ecbb1  js      loc_1801ECEA5
0x1801ecbb7  mov     qword ptr [rbp+57h+rgsabound.cElements], 3
0x1801ecbbf  mov     ecx, 4; vt
0x1801ecbc4  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1801ecbc8  mov     edx, r14d; cDims
0x1801ecbcb  call    cs:__imp_SafeArrayCreate
0x1801ecbd1  mov     rbx, rax
0x1801ecbd4  mov     [rbp+57h+var_98], rax
0x1801ecbd8  test    rax, rax
0x1801ecbdb  jnz     short loc_1801ECBE4
0x1801ecbdd  mov     eax, 8007000Eh
0x1801ecbe2  jmp     short loc_1801ECBED
0x1801ecbe4  mov     rcx, rbx; psa
0x1801ecbe7  call    cs:__imp_SafeArrayLock
0x1801ecbed  test    eax, eax
0x1801ecbef  js      loc_1801ECF22
0x1801ecbf5  mov     eax, [rsi+0F8h]
0x1801ecbfb  test    eax, eax
0x1801ecbfd  jnz     short loc_1801ECC04
0x1801ecbff  movaps  xmm6, xmm7
0x1801ecc02  jmp     short loc_1801ECC19
0x1801ecc04  cmp     eax, r14d
0x1801ecc07  jnz     short loc_1801ECC16
0x1801ecc09  mov     rax, [rsi+0F0h]
0x1801ecc10  movss   xmm6, dword ptr [rax]
0x1801ecc14  jmp     short loc_1801ECC19
0x1801ecc16  xorps   xmm6, xmm6
0x1801ecc19  test    rbx, rbx
0x1801ecc1c  jz      loc_1801ECF2D
0x1801ecc22  mov     [rbp+57h+rgsabound.cElements], r13d
0x1801ecc26  lea     r8, [rbp+57h+rgsabound]; plLbound
0x1801ecc2a  mov     edx, r14d; nDim
0x1801ecc2d  mov     rcx, rbx; psa
0x1801ecc30  call    cs:__imp_SafeArrayGetLBound
0x1801ecc36  test    eax, eax
0x1801ecc38  js      loc_1801ECF38
0x1801ecc3e  movsxd  r14, [rbp+57h+rgsabound.cElements]
0x1801ecc42  test    r14d, r14d
0x1801ecc45  jg      loc_1801ECF76
0x1801ecc4b  mov     [rbp+57h+rgsabound.cElements], r13d
0x1801ecc4f  lea     r8, [rbp+57h+rgsabound]; plUbound
0x1801ecc53  mov     edx, 1; nDim
0x1801ecc58  mov     rcx, rbx; psa
0x1801ecc5b  call    cs:__imp_SafeArrayGetUBound
0x1801ecc61  test    eax, eax
0x1801ecc63  js      loc_1801ECF40
0x1801ecc69  cmp     [rbp+57h+rgsabound.cElements], r13d
0x1801ecc6d  jl      loc_1801ECF76
0x1801ecc73  mov     rcx, r14
0x1801ecc76  shl     rcx, 2
0x1801ecc7a  mov     rax, [rbx+10h]
0x1801ecc7e  sub     rax, rcx
0x1801ecc81  movss   dword ptr [rax], xmm6
0x1801ecc85  mov     eax, [rsi+108h]
0x1801ecc8b  mov     r14d, 1
0x1801ecc91  test    eax, eax
0x1801ecc93  jnz     short loc_1801ECC9A
0x1801ecc95  movaps  xmm6, xmm7
0x1801ecc98  jmp     short loc_1801ECCAF
0x1801ecc9a  cmp     eax, r14d
0x1801ecc9d  jnz     short loc_1801ECCAC
0x1801ecc9f  mov     rax, [rsi+100h]
0x1801ecca6  movss   xmm6, dword ptr [rax]
0x1801eccaa  jmp     short loc_1801ECCAF
0x1801eccac  xorps   xmm6, xmm6
0x1801eccaf  mov     [rbp+57h+rgsabound.cElements], r13d
0x1801eccb3  lea     r8, [rbp+57h+rgsabound]; plLbound
0x1801eccb7  mov     edx, r14d; nDim
0x1801eccba  mov     rcx, rbx; psa
0x1801eccbd  call    cs:__imp_SafeArrayGetLBound
0x1801eccc3  test    eax, eax
0x1801eccc5  js      loc_1801ECF48
0x1801ecccb  cmp     [rbp+57h+rgsabound.cElements], r14d
0x1801ecccf  jg      loc_1801ECF76
0x1801eccd5  mov     [rbp+57h+plUbound], r13d
0x1801eccd9  lea     r8, [rbp+57h+plUbound]; plUbound
0x1801eccdd  mov     edx, r14d; nDim
0x1801ecce0  mov     rcx, rbx; psa
0x1801ecce3  call    cs:__imp_SafeArrayGetUBound
0x1801ecce9  test    eax, eax
0x1801ecceb  js      loc_1801ECF50
0x1801eccf1  cmp     [rbp+57h+plUbound], r14d
0x1801eccf5  jl      loc_1801ECF76
0x1801eccfb  mov     eax, r14d
0x1801eccfe  sub     eax, [rbp+57h+rgsabound.cElements]
0x1801ecd01  movsxd  rcx, eax
0x1801ecd04  mov     rax, [rbx+10h]
0x1801ecd08  movss   dword ptr [rax+rcx*4], xmm6
0x1801ecd0d  mov     eax, [rsi+118h]
0x1801ecd13  test    eax, eax
0x1801ecd15  jz      short loc_1801ECD2C
0x1801ecd17  cmp     eax, r14d
0x1801ecd1a  jnz     short loc_1801ECD29
0x1801ecd1c  mov     rax, [rsi+110h]
0x1801ecd23  movss   xmm7, dword ptr [rax]
0x1801ecd27  jmp     short loc_1801ECD2C
0x1801ecd29  xorps   xmm7, xmm7
0x1801ecd2c  mov     [rbp+57h+rgsabound.cElements], r13d
0x1801ecd30  lea     r8, [rbp+57h+rgsabound]; plLbound
0x1801ecd34  mov     edx, r14d; nDim
0x1801ecd37  mov     rcx, rbx; psa
0x1801ecd3a  call    cs:__imp_SafeArrayGetLBound
0x1801ecd40  test    eax, eax
0x1801ecd42  js      loc_1801ECF58
0x1801ecd48  cmp     [rbp+57h+rgsabound.cElements], r15d
0x1801ecd4c  jg      loc_1801ECF76
0x1801ecd52  mov     [rbp+57h+plUbound], r13d
0x1801ecd56  lea     r8, [rbp+57h+plUbound]; plUbound
  ... truncated ...
```
