# TransformEffect::SetShaderRectVariable(IShader *,wchar_t const *,wchar_t const *,RectT<IntegerTypes> const &)

- ea: `0x1801a6d64`
- end: `0x1801a72b3`
- name: `?SetShaderRectVariable@TransformEffect@@CAXPEAUIShader@@PEB_W1AEBU?$RectT@UIntegerTypes@@@@@Z`
- size: `1359`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1801a72b4`

## callees

- `0x18001db0c`
- `0x1801a6d64`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1801a6f75`
- `OLEAUT32!__imp_VariantClear` at `0x1801a718f`
- `OLEAUT32!__imp_VariantClear` at `0x1801a6f75`
- `OLEAUT32!__imp_VariantClear` at `0x1801a718f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a6dad`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a6f96`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a6dad`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801a6f96`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a71ad`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a71c4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a71ad`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801a71c4`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a6e22`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a6e8c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a702b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a70b1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a6e22`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a6e8c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a702b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a70b1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a6df8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a6e65`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a7000`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a708d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a6df8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a6e65`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a7000`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801a708d`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a6dc9`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a6fb2`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a6dc9`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801a6fb2`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a71a0`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a71b7`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a71a0`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801a71b7`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801a6ecb`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801a70ea`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801a6ecb`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801a70ea`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801a6ee3`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801a70fd`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801a6ee3`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801a70fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall TransformEffect::SetShaderRectVariable(__int64 a1, __int64 a2, __int64 a3, int *a4)
{
  SAFEARRAY *v8; // rax
  SAFEARRAY *v9; // rdi
  HRESULT v10; // eax
  float v11; // xmm6_4
  HRESULT LBound; // eax
  __int64 v13; // rbx
  HRESULT UBound; // eax
  float v15; // xmm6_4
  HRESULT v16; // eax
  HRESULT v17; // eax
  __int64 (__fastcall *v18)(__int64, __int64, VARIANTARG *); // rbx
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v21; // ebx
  SAFEARRAY *v22; // rax
  SAFEARRAY *v23; // rbx
  HRESULT v24; // eax
  __int64 v25; // rcx
  float v26; // xmm6_4
  HRESULT v27; // eax
  __int64 cElements; // r14
  HRESULT v29; // eax
  __int64 v30; // rcx
  float v31; // xmm6_4
  HRESULT v32; // eax
  HRESULT v33; // eax
  __int64 (__fastcall *v34)(__int64, __int64, VARIANTARG *); // rsi
  HRESULT v35; // ecx
  VARTYPE v36; // dx
  int v37; // esi
  int result; // eax
  LONG plLbound; // [rsp+28h] [rbp-39h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-31h] BYREF
  VARIANTARG pvt; // [rsp+38h] [rbp-29h] BYREF
  VARIANTARG v42; // [rsp+58h] [rbp-9h] BYREF
  SAFEARRAY *v43; // [rsp+78h] [rbp+17h]
  SAFEARRAY *v44; // [rsp+80h] [rbp+1Fh]

  rgsabound = (SAFEARRAYBOUND)2LL;
  v8 = SafeArrayCreate(4u, 1u, &rgsabound);
  v9 = v8;
  v43 = v8;
  if ( v8 )
    v10 = SafeArrayLock(v8);
  else
    v10 = -2147024882;
  if ( v10 < 0 )
    ATL::BaseAtlThrow(v10);
  v11 = (float)*a4;
  if ( !v9 )
    ATL::BaseAtlThrow(-2147467259);
  plLbound = 0;
  LBound = SafeArrayGetLBound(v9, 1u, &plLbound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  v13 = plLbound;
  if ( plLbound > 0 )
    goto LABEL_61;
  plLbound = 0;
  UBound = SafeArrayGetUBound(v9, 1u, &plLbound);
  if ( UBound < 0 )
    ATL::BaseAtlThrow(UBound);
  if ( plLbound < 0 )
    goto LABEL_61;
  *((float *)v9->pvData - v13) = v11;
  v15 = (float)a4[1];
  plLbound = 0;
  v16 = SafeArrayGetLBound(v9, 1u, &plLbound);
  if ( v16 < 0 )
    ATL::BaseAtlThrow(v16);
  if ( plLbound > 1 )
    goto LABEL_61;
  rgsabound.cElements = 0;
  v17 = SafeArrayGetUBound(v9, 1u, (LONG *)&rgsabound);
  if ( v17 < 0 )
    ATL::BaseAtlThrow(v17);
  if ( (int)rgsabound.cElements < 1 )
LABEL_61:
    ATL::BaseAtlThrow(-2147024809);
  *((float *)v9->pvData + 1 - plLbound) = v15;
  v18 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)a1 + 104LL);
  rgsabound = 0;
  Vartype = SafeArrayCopy(v9, (SAFEARRAY **)&rgsabound);
  if ( Vartype < 0 )
    goto LABEL_21;
  Vartype = SafeArrayGetVartype(v9, &pvt.vt);
  vt = pvt.vt;
  if ( Vartype >= 0 && pvt.vt == 13 && (v9->fFeatures & 0x440) == 0x440 )
    vt = 9;
  if ( Vartype < 0 )
  {
LABEL_21:
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
  v42 = pvt;
  v21 = v18(a1, a2, &v42);
  VariantClear(&pvt);
  if ( v21 < 0 )
    ATL::BaseAtlThrow(v21);
  rgsabound = (SAFEARRAYBOUND)2LL;
  v22 = SafeArrayCreate(4u, 1u, &rgsabound);
  v23 = v22;
  v44 = v22;
  if ( v22 )
    v24 = SafeArrayLock(v22);
  else
    v24 = -2147024882;
  if ( v24 < 0 )
    ATL::BaseAtlThrow(v24);
  v25 = a4[2] - (__int64)*a4;
  if ( (unsigned __int64)(v25 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_76;
  v26 = (float)(int)v25;
  if ( !v23 )
    ATL::BaseAtlThrow(-2147467259);
  rgsabound.cElements = 0;
  v27 = SafeArrayGetLBound(v23, 1u, (LONG *)&rgsabound);
  if ( v27 < 0 )
    ATL::BaseAtlThrow(v27);
  cElements = (int)rgsabound.cElements;
  if ( (int)rgsabound.cElements > 0 )
    goto LABEL_75;
  rgsabound.cElements = 0;
  v29 = SafeArrayGetUBound(v23, 1u, (LONG *)&rgsabound);
  if ( v29 < 0 )
    ATL::BaseAtlThrow(v29);
  if ( (rgsabound.cElements & 0x80000000) != 0 )
LABEL_75:
    ATL::BaseAtlThrow(-2147024809);
  *((float *)v23->pvData - cElements) = v26;
  v30 = a4[3] - (__int64)a4[1];
  if ( (unsigned __int64)(v30 + 0x80000000LL) > 0xFFFFFFFF )
LABEL_76:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  v31 = (float)(int)v30;
  plLbound = 0;
  v32 = SafeArrayGetLBound(v23, 1u, &plLbound);
  if ( v32 < 0 )
    ATL::BaseAtlThrow(v32);
  if ( plLbound > 1 )
    goto LABEL_75;
  rgsabound.cElements = 0;
  v33 = SafeArrayGetUBound(v23, 1u, (LONG *)&rgsabound);
  if ( v33 < 0 )
    ATL::BaseAtlThrow(v33);
  if ( (int)rgsabound.cElements < 1 )
    goto LABEL_75;
  *((float *)v23->pvData + 1 - plLbound) = v31;
  v34 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)a1 + 104LL);
  rgsabound = 0;
  v35 = SafeArrayCopy(v23, (SAFEARRAY **)&rgsabound);
  if ( v35 < 0 )
    goto LABEL_48;
  v35 = SafeArrayGetVartype(v23, &pvt.vt);
  v36 = pvt.vt;
  if ( v35 >= 0 && pvt.vt == 13 && (v23->fFeatures & 0x440) == 0x440 )
    v36 = 9;
  if ( v35 < 0 )
  {
LABEL_48:
    pvt.lVal = v35;
    pvt.vt = 10;
  }
  else
  {
    pvt.vt = v36 | 0x2000;
    pvt.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
  }
  if ( v35 < 0 )
  {
    if ( v35 != -2147024882 )
      ATL::BaseAtlThrow(v35);
    ATL::BaseAtlThrow(-2147024882);
  }
  v42 = pvt;
  v37 = v34(a1, a3, &v42);
  VariantClear(&pvt);
  if ( v37 < 0 )
    ATL::BaseAtlThrow(v37);
  if ( SafeArrayUnlock(v23) >= 0 )
    SafeArrayDestroy(v23);
  result = SafeArrayUnlock(v9);
  if ( result >= 0 )
    return SafeArrayDestroy(v9);
  return result;
}

```

## disassembly

```asm
0x1801a6d64  mov     rax, rsp
0x1801a6d67  mov     [rax+8], rbx
0x1801a6d6b  mov     [rax+10h], rsi
0x1801a6d6f  mov     [rax+18h], rdi
0x1801a6d73  push    rbp
0x1801a6d74  push    r12
0x1801a6d76  push    r13
0x1801a6d78  push    r14
0x1801a6d7a  push    r15
0x1801a6d7c  lea     rbp, [rax-5Fh]
0x1801a6d80  sub     rsp, 90h
0x1801a6d87  movaps  xmmword ptr [rax-38h], xmm6
0x1801a6d8b  mov     r15, r9
0x1801a6d8e  mov     r13, r8
0x1801a6d91  mov     r14, rdx
0x1801a6d94  mov     r12, rcx
0x1801a6d97  mov     qword ptr [rbp+57h+rgsabound.cElements], 2
0x1801a6d9f  mov     ecx, 4; vt
0x1801a6da4  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1801a6da8  lea     esi, [rcx-3]
0x1801a6dab  mov     edx, esi; cDims
0x1801a6dad  call    cs:__imp_SafeArrayCreate
0x1801a6db3  mov     rdi, rax
0x1801a6db6  mov     [rbp+57h+var_40], rax
0x1801a6dba  test    rax, rax
0x1801a6dbd  jnz     short loc_1801A6DC6
0x1801a6dbf  mov     eax, 8007000Eh
0x1801a6dc4  jmp     short loc_1801A6DCF
0x1801a6dc6  mov     rcx, rdi; psa
0x1801a6dc9  call    cs:__imp_SafeArrayLock
0x1801a6dcf  test    eax, eax
0x1801a6dd1  js      loc_1801A7221
0x1801a6dd7  movd    xmm6, dword ptr [r15]
0x1801a6ddc  cvtdq2ps xmm6, xmm6
0x1801a6ddf  test    rdi, rdi
0x1801a6de2  jz      loc_1801A722C
0x1801a6de8  mov     [rbp+57h+plLbound], 0
0x1801a6def  lea     r8, [rbp+57h+plLbound]; plLbound
0x1801a6df3  mov     edx, esi; nDim
0x1801a6df5  mov     rcx, rdi; psa
0x1801a6df8  call    cs:__imp_SafeArrayGetLBound
0x1801a6dfe  test    eax, eax
0x1801a6e00  js      loc_1801A7237
0x1801a6e06  movsxd  rbx, [rbp+57h+plLbound]
0x1801a6e0a  test    ebx, ebx
0x1801a6e0c  jg      loc_1801A7213
0x1801a6e12  mov     [rbp+57h+plLbound], 0
0x1801a6e19  lea     r8, [rbp+57h+plLbound]; plUbound
0x1801a6e1d  mov     edx, esi; nDim
0x1801a6e1f  mov     rcx, rdi; psa
0x1801a6e22  call    cs:__imp_SafeArrayGetUBound
0x1801a6e28  test    eax, eax
0x1801a6e2a  js      loc_1801A723F
0x1801a6e30  cmp     [rbp+57h+plLbound], 0
0x1801a6e34  jl      loc_1801A7213
0x1801a6e3a  mov     rcx, rbx
0x1801a6e3d  shl     rcx, 2
0x1801a6e41  mov     rax, [rdi+10h]
0x1801a6e45  sub     rax, rcx
0x1801a6e48  movss   dword ptr [rax], xmm6
0x1801a6e4c  movd    xmm6, dword ptr [r15+4]
0x1801a6e52  cvtdq2ps xmm6, xmm6
0x1801a6e55  mov     [rbp+57h+plLbound], 0
0x1801a6e5c  lea     r8, [rbp+57h+plLbound]; plLbound
0x1801a6e60  mov     edx, esi; nDim
0x1801a6e62  mov     rcx, rdi; psa
0x1801a6e65  call    cs:__imp_SafeArrayGetLBound
0x1801a6e6b  test    eax, eax
0x1801a6e6d  js      loc_1801A7247
0x1801a6e73  cmp     [rbp+57h+plLbound], esi
0x1801a6e76  jg      loc_1801A7213
0x1801a6e7c  mov     [rbp+57h+rgsabound.cElements], 0
0x1801a6e83  lea     r8, [rbp+57h+rgsabound]; plUbound
0x1801a6e87  mov     edx, esi; nDim
0x1801a6e89  mov     rcx, rdi; psa
0x1801a6e8c  call    cs:__imp_SafeArrayGetUBound
0x1801a6e92  test    eax, eax
0x1801a6e94  js      loc_1801A724F
0x1801a6e9a  cmp     [rbp+57h+rgsabound.cElements], esi
0x1801a6e9d  jl      loc_1801A7213
0x1801a6ea3  mov     eax, esi
0x1801a6ea5  sub     eax, [rbp+57h+plLbound]
0x1801a6ea8  movsxd  rcx, eax
0x1801a6eab  mov     rax, [rdi+10h]
0x1801a6eaf  movss   dword ptr [rax+rcx*4], xmm6
0x1801a6eb4  mov     rax, [r12]
0x1801a6eb8  mov     rbx, [rax+68h]
0x1801a6ebc  mov     qword ptr [rbp+57h+rgsabound.cElements], 0
0x1801a6ec4  lea     rdx, [rbp+57h+rgsabound]; ppsaOut
0x1801a6ec8  mov     rcx, rdi; psa
0x1801a6ecb  call    cs:__imp_SafeArrayCopy
0x1801a6ed1  mov     ecx, eax
0x1801a6ed3  mov     eax, 0Ah
0x1801a6ed8  test    ecx, ecx
0x1801a6eda  js      short loc_1801A6F2E
0x1801a6edc  lea     rdx, [rbp+57h+pvt]; pvt
0x1801a6ee0  mov     rcx, rdi; psa
0x1801a6ee3  call    cs:__imp_SafeArrayGetVartype
0x1801a6ee9  mov     ecx, eax; int
0x1801a6eeb  movzx   edx, [rbp+57h+pvt]
0x1801a6eef  test    eax, eax
0x1801a6ef1  js      short loc_1801A6F12
0x1801a6ef3  cmp     dx, 0Dh
0x1801a6ef7  jnz     short loc_1801A6F12
0x1801a6ef9  movzx   eax, word ptr [rdi+2]
0x1801a6efd  mov     r8d, 440h
0x1801a6f03  and     ax, r8w
0x1801a6f07  cmp     ax, r8w
0x1801a6f0b  jnz     short loc_1801A6F12
0x1801a6f0d  mov     edx, 9
0x1801a6f12  test    ecx, ecx
0x1801a6f14  js      short loc_1801A6F29
0x1801a6f16  or      dx, 2000h
0x1801a6f1b  mov     [rbp+57h+pvt], dx
0x1801a6f1f  mov     rax, qword ptr [rbp+57h+rgsabound.cElements]
0x1801a6f23  mov     qword ptr [rbp+57h+pvt+8], rax
0x1801a6f27  jmp     short loc_1801A6F35
0x1801a6f29  mov     eax, 0Ah
0x1801a6f2e  mov     dword ptr [rbp+57h+pvt+8], ecx
0x1801a6f31  mov     [rbp+57h+pvt], ax
0x1801a6f35  test    ecx, ecx
0x1801a6f37  jns     short loc_1801A6F4A
0x1801a6f39  cmp     ecx, 8007000Eh
0x1801a6f3f  jz      loc_1801A71F8
0x1801a6f45  jmp     loc_1801A7257
0x1801a6f4a  movups  xmm0, xmmword ptr [rbp+57h+pvt]
0x1801a6f4e  movaps  [rbp+57h+var_60], xmm0
0x1801a6f52  movsd   xmm1, [rbp+57h+var_70]
0x1801a6f57  movsd   [rbp+57h+var_50], xmm1
0x1801a6f5c  lea     r8, [rbp+57h+var_60]
0x1801a6f60  mov     rdx, r14
0x1801a6f63  mov     rcx, r12
0x1801a6f66  mov     rax, rbx
0x1801a6f69  call    cs:__guard_dispatch_icall_fptr
0x1801a6f6f  mov     ebx, eax
0x1801a6f71  lea     rcx, [rbp+57h+pvt]; pvarg
0x1801a6f75  call    cs:__imp_VariantClear
0x1801a6f7b  test    ebx, ebx
0x1801a6f7d  js      loc_1801A71F0
0x1801a6f83  mov     qword ptr [rbp+57h+rgsabound.cElements], 2
0x1801a6f8b  mov     ecx, 4; vt
0x1801a6f90  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1801a6f94  mov     edx, esi; cDims
0x1801a6f96  call    cs:__imp_SafeArrayCreate
0x1801a6f9c  mov     rbx, rax
0x1801a6f9f  mov     [rbp+57h+var_38], rax
0x1801a6fa3  test    rax, rax
0x1801a6fa6  jnz     short loc_1801A6FAF
0x1801a6fa8  mov     eax, 8007000Eh
0x1801a6fad  jmp     short loc_1801A6FB8
0x1801a6faf  mov     rcx, rbx; psa
0x1801a6fb2  call    cs:__imp_SafeArrayLock
0x1801a6fb8  test    eax, eax
0x1801a6fba  js      loc_1801A725D
0x1801a6fc0  movsxd  rcx, dword ptr [r15+8]
0x1801a6fc4  movsxd  rax, dword ptr [r15]
0x1801a6fc7  sub     rcx, rax
0x1801a6fca  mov     eax, 80000000h
0x1801a6fcf  add     rax, rcx
0x1801a6fd2  mov     edx, 0FFFFFFFFh
0x1801a6fd7  cmp     rax, rdx
0x1801a6fda  ja      loc_1801A72AD
0x1801a6fe0  movd    xmm6, ecx
0x1801a6fe4  cvtdq2ps xmm6, xmm6
0x1801a6fe7  test    rbx, rbx
0x1801a6fea  jz      loc_1801A7269
0x1801a6ff0  mov     [rbp+57h+rgsabound.cElements], 0
0x1801a6ff7  lea     r8, [rbp+57h+rgsabound]; plLbound
0x1801a6ffb  mov     edx, esi; nDim
0x1801a6ffd  mov     rcx, rbx; psa
0x1801a7000  call    cs:__imp_SafeArrayGetLBound
0x1801a7006  test    eax, eax
0x1801a7008  js      loc_1801A7274
0x1801a700e  movsxd  r14, [rbp+57h+rgsabound.cElements]
0x1801a7012  test    r14d, r14d
0x1801a7015  jg      loc_1801A72A2
0x1801a701b  mov     [rbp+57h+rgsabound.cElements], 0
0x1801a7022  lea     r8, [rbp+57h+rgsabound]; plUbound
0x1801a7026  mov     edx, esi; nDim
0x1801a7028  mov     rcx, rbx; psa
0x1801a702b  call    cs:__imp_SafeArrayGetUBound
0x1801a7031  test    eax, eax
0x1801a7033  js      loc_1801A727C
0x1801a7039  cmp     [rbp+57h+rgsabound.cElements], 0
0x1801a703d  jl      loc_1801A72A2
0x1801a7043  mov     rcx, r14
0x1801a7046  shl     rcx, 2
0x1801a704a  mov     rax, [rbx+10h]
0x1801a704e  sub     rax, rcx
0x1801a7051  movss   dword ptr [rax], xmm6
0x1801a7055  movsxd  rcx, dword ptr [r15+0Ch]
0x1801a7059  movsxd  rax, dword ptr [r15+4]
0x1801a705d  sub     rcx, rax
0x1801a7060  mov     eax, 80000000h
0x1801a7065  add     rax, rcx
0x1801a7068  mov     edx, 0FFFFFFFFh
0x1801a706d  cmp     rax, rdx
0x1801a7070  ja      loc_1801A72AD
0x1801a7076  movd    xmm6, ecx
0x1801a707a  cvtdq2ps xmm6, xmm6
0x1801a707d  xor     r14d, r14d
0x1801a7080  mov     [rbp+57h+plLbound], r14d
0x1801a7084  lea     r8, [rbp+57h+plLbound]; plLbound
0x1801a7088  mov     edx, esi; nDim
0x1801a708a  mov     rcx, rbx; psa
0x1801a708d  call    cs:__imp_SafeArrayGetLBound
0x1801a7093  test    eax, eax
0x1801a7095  js      loc_1801A7284
0x1801a709b  cmp     [rbp+57h+plLbound], esi
0x1801a709e  jg      loc_1801A72A2
0x1801a70a4  mov     [rbp+57h+rgsabound.cElements], r14d
0x1801a70a8  lea     r8, [rbp+57h+rgsabound]; plUbound
0x1801a70ac  mov     edx, esi; nDim
0x1801a70ae  mov     rcx, rbx; psa
0x1801a70b1  call    cs:__imp_SafeArrayGetUBound
0x1801a70b7  test    eax, eax
0x1801a70b9  js      loc_1801A728C
0x1801a70bf  cmp     [rbp+57h+rgsabound.cElements], esi
0x1801a70c2  jl      loc_1801A72A2
0x1801a70c8  sub     esi, [rbp+57h+plLbound]
0x1801a70cb  movsxd  rcx, esi
0x1801a70ce  mov     rax, [rbx+10h]
0x1801a70d2  movss   dword ptr [rax+rcx*4], xmm6
0x1801a70d7  mov     rax, [r12]
0x1801a70db  mov     rsi, [rax+68h]
0x1801a70df  mov     qword ptr [rbp+57h+rgsabound.cElements], r14
0x1801a70e3  lea     rdx, [rbp+57h+rgsabound]; ppsaOut
0x1801a70e7  mov     rcx, rbx; psa
0x1801a70ea  call    cs:__imp_SafeArrayCopy
0x1801a70f0  mov     ecx, eax; int
0x1801a70f2  test    eax, eax
0x1801a70f4  js      short loc_1801A7142
0x1801a70f6  lea     rdx, [rbp+57h+pvt]; pvt
0x1801a70fa  mov     rcx, rbx; psa
0x1801a70fd  call    cs:__imp_SafeArrayGetVartype
0x1801a7103  mov     ecx, eax
0x1801a7105  movzx   edx, [rbp+57h+pvt]
0x1801a7109  test    eax, eax
0x1801a710b  js      short loc_1801A712B
0x1801a710d  cmp     dx, 0Dh
0x1801a7111  jnz     short loc_1801A712B
0x1801a7113  movzx   eax, word ptr [rbx+2]
0x1801a7117  mov     r8d, 440h
0x1801a711d  and     ax, r8w
0x1801a7121  cmp     ax, r8w
0x1801a7125  jnz     short loc_1801A712B
0x1801a7127  lea     edx, [r14+9]
0x1801a712b  test    ecx, ecx
0x1801a712d  js      short loc_1801A7142
0x1801a712f  or      dx, 2000h
0x1801a7134  mov     [rbp+57h+pvt], dx
0x1801a7138  mov     rax, qword ptr [rbp+57h+rgsabound.cElements]
0x1801a713c  mov     qword ptr [rbp+57h+pvt+8], rax
0x1801a7140  jmp     short loc_1801A714E
0x1801a7142  mov     eax, 0Ah
0x1801a7147  mov     dword ptr [rbp+57h+pvt+8], ecx
0x1801a714a  mov     [rbp+57h+pvt], ax
0x1801a714e  test    ecx, ecx
0x1801a7150  jns     short loc_1801A7164
0x1801a7152  mov     eax, 8007000Eh
0x1801a7157  cmp     ecx, eax
0x1801a7159  jz      loc_1801A7207
0x1801a715f  jmp     loc_1801A7294
0x1801a7164  movups  xmm0, xmmword ptr [rbp+57h+pvt]
0x1801a7168  movaps  [rbp+57h+var_60], xmm0
0x1801a716c  movsd   xmm1, [rbp+57h+var_70]
0x1801a7171  movsd   [rbp+57h+var_50], xmm1
0x1801a7176  lea     r8, [rbp+57h+var_60]
0x1801a717a  mov     rdx, r13
0x1801a717d  mov     rcx, r12
0x1801a7180  mov     rax, rsi
0x1801a7183  call    cs:__guard_dispatch_icall_fptr
0x1801a7189  mov     esi, eax
0x1801a718b  lea     rcx, [rbp+57h+pvt]; pvarg
0x1801a718f  call    cs:__imp_VariantClear
0x1801a7195  test    esi, esi
0x1801a7197  js      loc_1801A729A
0x1801a719d  mov     rcx, rbx; psa
0x1801a71a0  call    cs:__imp_SafeArrayUnlock
0x1801a71a6  test    eax, eax
0x1801a71a8  js      short loc_1801A71B4
0x1801a71aa  mov     rcx, rbx; psa
0x1801a71ad  call    cs:__imp_SafeArrayDestroy
0x1801a71b3  nop
0x1801a71b4  mov     rcx, rdi; psa
0x1801a71b7  call    cs:__imp_SafeArrayUnlock
0x1801a71bd  test    eax, eax
0x1801a71bf  js      short loc_1801A71CA
0x1801a71c1  mov     rcx, rdi; psa
0x1801a71c4  call    cs:__imp_SafeArrayDestroy
0x1801a71ca  lea     r11, [rsp+0B0h+var_20]
0x1801a71d2  mov     rbx, [r11+30h]
0x1801a71d6  mov     rsi, [r11+38h]
0x1801a71da  mov     rdi, [r11+40h]
0x1801a71de  movaps  xmm6, xmmword ptr [r11-10h]
0x1801a71e3  mov     rsp, r11
0x1801a71e6  pop     r15
0x1801a71e8  pop     r14
0x1801a71ea  pop     r13
0x1801a71ec  pop     r12
  ... truncated ...
```
