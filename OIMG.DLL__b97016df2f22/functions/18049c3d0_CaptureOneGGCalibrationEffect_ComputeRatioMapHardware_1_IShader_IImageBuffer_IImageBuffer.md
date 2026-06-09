# CaptureOneGGCalibrationEffect::ComputeRatioMapHardware<1>(IShader *,IImageBuffer *,IImageBuffer *)

- ea: `0x18049c3d0`
- end: `0x18049c7f4`
- name: `??$ComputeRatioMapHardware@$00@CaptureOneGGCalibrationEffect@@AEAAXPEAUIShader@@PEAUIImageBuffer@@1@Z`
- size: `1060`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1804999ec`

## callees

- `0x1801e1640`
- `0x18049c3d0`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18049c667`
- `OLEAUT32!__imp_VariantClear` at `0x18049c667`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049c491`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049c491`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049c6eb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049c6eb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18049c4fe`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18049c576`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18049c4fe`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18049c576`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18049c4d4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18049c54f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18049c4d4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18049c54f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049c4ad`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049c4ad`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049c6de`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049c6de`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18049c5be`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18049c5be`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18049c5d1`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18049c5d1`

## string_xrefs

- `0x18049c6a0`: `ComputeRatiosG2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HRESULT __fastcall CaptureOneGGCalibrationEffect::ComputeRatioMapHardware<1>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rcx
  int v8; // eax
  SAFEARRAY *v9; // rax
  SAFEARRAY *v10; // rbx
  HRESULT v11; // eax
  HRESULT LBound; // eax
  __int64 v13; // rdi
  HRESULT UBound; // eax
  HRESULT v15; // eax
  HRESULT v16; // eax
  __int64 (__fastcall *v17)(__int64, const wchar_t *, VARIANTARG *); // rdi
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v20; // edi
  __int64 v21; // rsi
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdi
  int v25; // eax
  HRESULT result; // eax
  LONG plLbound; // [rsp+38h] [rbp-79h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp-71h] BYREF
  VARIANTARG pvt; // [rsp+48h] [rbp-69h] BYREF
  __int64 v30; // [rsp+60h] [rbp-51h] BYREF
  __int64 v31; // [rsp+68h] [rbp-49h] BYREF
  __int64 v32; // [rsp+70h] [rbp-41h] BYREF
  _QWORD v33[2]; // [rsp+78h] [rbp-39h] BYREF
  VARIANTARG v34; // [rsp+88h] [rbp-29h] BYREF
  __int128 v35; // [rsp+A8h] [rbp-9h] BYREF
  __int64 v36; // [rsp+B8h] [rbp+7h]
  int v37; // [rsp+C0h] [rbp+Fh]

  v33[0] = 0;
  v30 = 0;
  Convolve1DEffect::LockAndGetTexture(a1, a3, 0, v33, &v30);
  v32 = 0;
  v31 = 0;
  Convolve1DEffect::LockAndGetTexture(v7, a4, 1, &v32, &v31);
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a3 + 56LL))(a3, &v35);
  if ( v8 < 0 )
    ATL::BaseAtlThrow(v8);
  rgsabound = (SAFEARRAYBOUND)2LL;
  v9 = SafeArrayCreate(4u, 1u, &rgsabound);
  v10 = v9;
  v33[1] = v9;
  if ( v9 )
    v11 = SafeArrayLock(v9);
  else
    v11 = -2147024882;
  if ( v11 < 0 )
    ATL::BaseAtlThrow(v11);
  if ( !v10 )
    ATL::BaseAtlThrow(-2147467259);
  plLbound = 0;
  LBound = SafeArrayGetLBound(v10, 1u, &plLbound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  v13 = plLbound;
  if ( plLbound > 0 )
    goto LABEL_41;
  plLbound = 0;
  UBound = SafeArrayGetUBound(v10, 1u, &plLbound);
  if ( UBound < 0 )
    ATL::BaseAtlThrow(UBound);
  if ( plLbound < 0 )
    goto LABEL_41;
  *((float *)v10->pvData - v13) = 1.0 / (float)SHIDWORD(v36);
  plLbound = 0;
  v15 = SafeArrayGetLBound(v10, 1u, &plLbound);
  if ( v15 < 0 )
    ATL::BaseAtlThrow(v15);
  if ( plLbound > 1 )
    goto LABEL_41;
  rgsabound.cElements = 0;
  v16 = SafeArrayGetUBound(v10, 1u, (LONG *)&rgsabound);
  if ( v16 < 0 )
    ATL::BaseAtlThrow(v16);
  if ( (int)rgsabound.cElements < 1 )
LABEL_41:
    ATL::BaseAtlThrow(-2147024809);
  *((float *)v10->pvData + 1 - plLbound) = 1.0 / (float)v37;
  v17 = *(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 104LL);
  rgsabound = 0;
  Vartype = SafeArrayCopy(v10, (SAFEARRAY **)&rgsabound);
  if ( Vartype < 0 )
    goto LABEL_22;
  Vartype = SafeArrayGetVartype(v10, &pvt.vt);
  vt = pvt.vt;
  if ( Vartype >= 0 && pvt.vt == 13 && (v10->fFeatures & 0x440) == 0x440 )
    vt = 9;
  if ( Vartype < 0 )
  {
LABEL_22:
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
  v34 = pvt;
  v20 = v17(a2, L"pixelOffset", &v34);
  VariantClear(&pvt);
  if ( v20 < 0 )
    ATL::BaseAtlThrow(v20);
  v21 = v30;
  v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)a2 + 112LL))(
          a2,
          0,
          L"bayer",
          v30);
  if ( v22 < 0 )
    ATL::BaseAtlThrow(v22);
  v23 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a2 + 88LL))(a2, L"ComputeRatiosG2");
  if ( v23 < 0 )
    ATL::BaseAtlThrow(v23);
  v24 = v31;
  v25 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 120LL))(a2, v31);
  if ( v25 < 0 )
    ATL::BaseAtlThrow(v25);
  result = SafeArrayUnlock(v10);
  if ( result >= 0 )
    result = SafeArrayDestroy(v10);
  if ( v24 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v32 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v21 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v33[0] )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v33[0] + 16LL))(v33[0]);
  return result;
}

```

## disassembly

```asm
0x18049c3d0  mov     rax, rsp
0x18049c3d3  push    rbp
0x18049c3d4  push    rbx
0x18049c3d5  push    rsi
0x18049c3d6  push    rdi
0x18049c3d7  push    r14
0x18049c3d9  lea     rbp, [rax-5Fh]
0x18049c3dd  sub     rsp, 0E0h
0x18049c3e4  movaps  xmmword ptr [rax-38h], xmm6
0x18049c3e8  mov     rax, cs:__security_cookie
0x18049c3ef  xor     rax, rsp
0x18049c3f2  mov     [rbp+57h+var_40], rax
0x18049c3f6  mov     rbx, r9
0x18049c3f9  mov     rdi, r8
0x18049c3fc  mov     r14, rdx
0x18049c3ff  mov     [rbp+57h+var_90], 0
0x18049c407  mov     [rbp+57h+var_A8], 0
0x18049c40f  lea     rax, [rbp+57h+var_A8]
0x18049c413  mov     [rsp+20h], rax
0x18049c418  lea     r9, [rbp+57h+var_90]
0x18049c41c  xor     r8d, r8d
0x18049c41f  mov     rdx, rdi
0x18049c422  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x18049c427  mov     [rbp+57h+var_98], 0
0x18049c42f  mov     [rbp+57h+var_A0], 0
0x18049c437  lea     rax, [rbp+57h+var_A0]
0x18049c43b  mov     [rsp+20h], rax
0x18049c440  lea     r9, [rbp+57h+var_98]
0x18049c444  mov     esi, 1
0x18049c449  mov     r8d, esi
0x18049c44c  mov     rdx, rbx
0x18049c44f  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x18049c454  xorps   xmm0, xmm0
0x18049c457  xor     eax, eax
0x18049c459  movups  [rbp+57h+var_60], xmm0
0x18049c45d  mov     [rbp+57h+var_50], rax
0x18049c461  mov     [rbp+57h+var_48], eax
0x18049c464  mov     rax, [rdi]
0x18049c467  lea     rdx, [rbp+57h+var_60]
0x18049c46b  mov     rcx, rdi
0x18049c46e  mov     rax, [rax+38h]
0x18049c472  call    cs:__guard_dispatch_icall_fptr
0x18049c478  test    eax, eax
0x18049c47a  js      loc_18049C78F
0x18049c480  mov     qword ptr [rbp+57h+rgsabound.cElements], 2
0x18049c488  lea     ecx, [rsi+3]; vt
0x18049c48b  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18049c48f  mov     edx, esi; cDims
0x18049c491  call    cs:__imp_SafeArrayCreate
0x18049c497  mov     rbx, rax
0x18049c49a  mov     [rbp+57h+var_88], rax
0x18049c49e  test    rax, rax
0x18049c4a1  jnz     short loc_18049C4AA
0x18049c4a3  mov     eax, 8007000Eh
0x18049c4a8  jmp     short loc_18049C4B3
0x18049c4aa  mov     rcx, rbx; psa
0x18049c4ad  call    cs:__imp_SafeArrayLock
0x18049c4b3  test    eax, eax
0x18049c4b5  js      loc_18049C797
0x18049c4bb  test    rbx, rbx
0x18049c4be  jz      loc_18049C7A3
0x18049c4c4  mov     [rbp+57h+plLbound], 0
0x18049c4cb  lea     r8, [rbp+57h+plLbound]; plLbound
0x18049c4cf  mov     edx, esi; nDim
0x18049c4d1  mov     rcx, rbx; psa
0x18049c4d4  call    cs:__imp_SafeArrayGetLBound
0x18049c4da  test    eax, eax
0x18049c4dc  js      loc_18049C7AE
0x18049c4e2  movsxd  rdi, [rbp+57h+plLbound]
0x18049c4e6  test    edi, edi
0x18049c4e8  jg      loc_18049C775
0x18049c4ee  mov     [rbp+57h+plLbound], 0
0x18049c4f5  lea     r8, [rbp+57h+plLbound]; plUbound
0x18049c4f9  mov     edx, esi; nDim
0x18049c4fb  mov     rcx, rbx; psa
0x18049c4fe  call    cs:__imp_SafeArrayGetUBound
0x18049c504  test    eax, eax
0x18049c506  js      loc_18049C7B6
0x18049c50c  cmp     [rbp+57h+plLbound], 0
0x18049c510  jl      loc_18049C775
0x18049c516  movd    xmm0, dword ptr [rbp+57h+var_50+4]
0x18049c51b  cvtdq2ps xmm0, xmm0
0x18049c51e  movss   xmm6, cs:__real@3f800000
0x18049c526  movaps  xmm1, xmm6
0x18049c529  divss   xmm1, xmm0
0x18049c52d  mov     rcx, rdi
0x18049c530  shl     rcx, 2
0x18049c534  mov     rax, [rbx+10h]
0x18049c538  sub     rax, rcx
0x18049c53b  movss   dword ptr [rax], xmm1
0x18049c53f  mov     [rbp+57h+plLbound], 0
0x18049c546  lea     r8, [rbp+57h+plLbound]; plLbound
0x18049c54a  mov     edx, esi; nDim
0x18049c54c  mov     rcx, rbx; psa
0x18049c54f  call    cs:__imp_SafeArrayGetLBound
0x18049c555  test    eax, eax
0x18049c557  js      loc_18049C7BE
0x18049c55d  cmp     [rbp+57h+plLbound], esi
0x18049c560  jg      loc_18049C775
0x18049c566  mov     [rbp+57h+rgsabound.cElements], 0
0x18049c56d  lea     r8, [rbp+57h+rgsabound]; plUbound
0x18049c571  mov     edx, esi; nDim
0x18049c573  mov     rcx, rbx; psa
0x18049c576  call    cs:__imp_SafeArrayGetUBound
0x18049c57c  test    eax, eax
0x18049c57e  js      loc_18049C7C6
0x18049c584  cmp     [rbp+57h+rgsabound.cElements], esi
0x18049c587  jl      loc_18049C775
0x18049c58d  movd    xmm0, [rbp+57h+var_48]
0x18049c592  cvtdq2ps xmm0, xmm0
0x18049c595  divss   xmm6, xmm0
0x18049c599  sub     esi, [rbp+57h+plLbound]
0x18049c59c  movsxd  rcx, esi
0x18049c59f  mov     rax, [rbx+10h]
0x18049c5a3  movss   dword ptr [rax+rcx*4], xmm6
0x18049c5a8  mov     rax, [r14]
0x18049c5ab  mov     rdi, [rax+68h]
0x18049c5af  mov     qword ptr [rbp+57h+rgsabound.cElements], 0
0x18049c5b7  lea     rdx, [rbp+57h+rgsabound]; ppsaOut
0x18049c5bb  mov     rcx, rbx; psa
0x18049c5be  call    cs:__imp_SafeArrayCopy
0x18049c5c4  mov     ecx, eax; int
0x18049c5c6  test    eax, eax
0x18049c5c8  js      short loc_18049C617
0x18049c5ca  lea     rdx, [rbp+57h+pvt]; pvt
0x18049c5ce  mov     rcx, rbx; psa
0x18049c5d1  call    cs:__imp_SafeArrayGetVartype
0x18049c5d7  mov     ecx, eax
0x18049c5d9  movzx   edx, [rbp+57h+pvt]
0x18049c5dd  test    eax, eax
0x18049c5df  js      short loc_18049C600
0x18049c5e1  cmp     dx, 0Dh
0x18049c5e5  jnz     short loc_18049C600
0x18049c5e7  movzx   eax, word ptr [rbx+2]
0x18049c5eb  mov     r8d, 440h
0x18049c5f1  and     ax, r8w
0x18049c5f5  cmp     ax, r8w
0x18049c5f9  jnz     short loc_18049C600
0x18049c5fb  mov     edx, 9
0x18049c600  test    ecx, ecx
0x18049c602  js      short loc_18049C617
0x18049c604  or      dx, 2000h
0x18049c609  mov     [rbp+57h+pvt], dx
0x18049c60d  mov     rax, qword ptr [rbp+57h+rgsabound.cElements]
0x18049c611  mov     qword ptr [rbp+57h+pvt+8], rax
0x18049c615  jmp     short loc_18049C623
0x18049c617  mov     eax, 0Ah
0x18049c61c  mov     dword ptr [rbp+57h+pvt+8], ecx
0x18049c61f  mov     [rbp+57h+pvt], ax
0x18049c623  test    ecx, ecx
0x18049c625  jns     short loc_18049C638
0x18049c627  cmp     ecx, 8007000Eh
0x18049c62d  jz      loc_18049C780
0x18049c633  jmp     loc_18049C7CE
0x18049c638  movups  xmm0, xmmword ptr [rbp+57h+pvt]
0x18049c63c  movaps  [rbp+57h+var_80], xmm0
0x18049c640  movsd   xmm1, [rbp+57h+var_B0]
0x18049c645  movsd   [rbp+57h+var_70], xmm1
0x18049c64a  lea     r8, [rbp+57h+var_80]
0x18049c64e  lea     rdx, aPixeloffset; "pixelOffset"
0x18049c655  mov     rcx, r14
0x18049c658  mov     rax, rdi
0x18049c65b  call    cs:__guard_dispatch_icall_fptr
0x18049c661  mov     edi, eax
0x18049c663  lea     rcx, [rbp+57h+pvt]; pvarg
0x18049c667  call    cs:__imp_VariantClear
0x18049c66d  test    edi, edi
0x18049c66f  js      loc_18049C7EC
0x18049c675  mov     rax, [r14]
0x18049c678  mov     rsi, [rbp+57h+var_A8]
0x18049c67c  mov     r9, rsi
0x18049c67f  lea     r8, aBayer; "bayer"
0x18049c686  xor     edx, edx
0x18049c688  mov     rcx, r14
0x18049c68b  mov     rax, [rax+70h]
0x18049c68f  call    cs:__guard_dispatch_icall_fptr
0x18049c695  test    eax, eax
0x18049c697  js      loc_18049C7E4
0x18049c69d  mov     rax, [r14]
0x18049c6a0  lea     rdx, aComputeratiosg_0; "ComputeRatiosG2"
0x18049c6a7  mov     rcx, r14
0x18049c6aa  mov     rax, [rax+58h]
0x18049c6ae  call    cs:__guard_dispatch_icall_fptr
0x18049c6b4  test    eax, eax
0x18049c6b6  js      loc_18049C7DC
0x18049c6bc  mov     rax, [r14]
0x18049c6bf  mov     rdi, [rbp+57h+var_A0]
0x18049c6c3  mov     rdx, rdi
0x18049c6c6  mov     rcx, r14
0x18049c6c9  mov     rax, [rax+78h]
0x18049c6cd  call    cs:__guard_dispatch_icall_fptr
0x18049c6d3  test    eax, eax
0x18049c6d5  js      loc_18049C7D4
0x18049c6db  mov     rcx, rbx; psa
0x18049c6de  call    cs:__imp_SafeArrayUnlock
0x18049c6e4  test    eax, eax
0x18049c6e6  js      short loc_18049C6F2
0x18049c6e8  mov     rcx, rbx; psa
0x18049c6eb  call    cs:__imp_SafeArrayDestroy
0x18049c6f1  nop
0x18049c6f2  test    rdi, rdi
0x18049c6f5  jz      short loc_18049C710
0x18049c6f7  mov     rax, [rdi]
0x18049c6fa  mov     rcx, rdi
0x18049c6fd  mov     rax, [rax+10h]
0x18049c701  call    cs:__guard_dispatch_icall_fptr
0x18049c707  nop
0x18049c708  nop     dword ptr [rax+rax+00000000h]
0x18049c710  mov     rcx, [rbp+57h+var_98]
0x18049c714  test    rcx, rcx
0x18049c717  jz      short loc_18049C727
0x18049c719  mov     rax, [rcx]
0x18049c71c  mov     rax, [rax+10h]
0x18049c720  call    cs:__guard_dispatch_icall_fptr
0x18049c726  nop
0x18049c727  test    rsi, rsi
0x18049c72a  jz      short loc_18049C73D
0x18049c72c  mov     rax, [rsi]
0x18049c72f  mov     rcx, rsi
0x18049c732  mov     rax, [rax+10h]
0x18049c736  call    cs:__guard_dispatch_icall_fptr
0x18049c73c  nop
0x18049c73d  mov     rcx, [rbp+57h+var_90]
0x18049c741  test    rcx, rcx
0x18049c744  jz      short loc_18049C753
0x18049c746  mov     rax, [rcx]
0x18049c749  mov     rax, [rax+10h]
0x18049c74d  call    cs:__guard_dispatch_icall_fptr
0x18049c753  mov     rcx, [rbp+57h+var_40]
0x18049c757  xor     rcx, rsp; StackCookie
0x18049c75a  call    __security_check_cookie
0x18049c75f  movaps  xmm6, [rsp+100h+var_38+8]
0x18049c767  add     rsp, 0E0h
0x18049c76e  pop     r14
0x18049c770  pop     rdi
0x18049c771  pop     rsi
0x18049c772  pop     rbx
0x18049c773  pop     rbp
0x18049c774  retn
0x18049c775  mov     ecx, 80070057h; int
0x18049c77a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c780  mov     ecx, 8007000Eh; int
0x18049c785  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c78b  jmp     short loc_18049C78E
0x18049c78e  nop
0x18049c78f  mov     ecx, eax; int
0x18049c791  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c797  mov     ecx, eax; int
0x18049c799  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c79f  jmp     short loc_18049C7A2
0x18049c7a2  nop
0x18049c7a3  mov     ecx, 80004005h; int
0x18049c7a8  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c7ae  mov     ecx, eax; int
0x18049c7b0  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c7b6  mov     ecx, eax; int
0x18049c7b8  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c7be  mov     ecx, eax; int
0x18049c7c0  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c7c6  mov     ecx, eax; int
0x18049c7c8  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c7ce  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c7d4  mov     ecx, eax; int
0x18049c7d6  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c7dc  mov     ecx, eax; int
0x18049c7de  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c7e4  mov     ecx, eax; int
0x18049c7e6  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049c7ec  mov     ecx, edi; int
0x18049c7ee  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
