# CaptureOneGGCalibrationEffect::ComputeRatioMapHardware<0>(IShader *,IImageBuffer *,IImageBuffer *)

- ea: `0x18049b12c`
- end: `0x18049b548`
- name: `??$ComputeRatioMapHardware@$0A@@CaptureOneGGCalibrationEffect@@AEAAXPEAUIShader@@PEAUIImageBuffer@@1@Z`
- size: `1052`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18049a5ac`

## callees

- `0x1801e1640`
- `0x18049b12c`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18049b3c3`
- `OLEAUT32!__imp_VariantClear` at `0x18049b3c3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049b1ed`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18049b1ed`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049b447`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18049b447`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18049b25a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18049b2d2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18049b25a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18049b2d2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18049b230`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18049b2ab`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18049b230`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18049b2ab`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049b209`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18049b209`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049b43a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18049b43a`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18049b31a`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18049b31a`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18049b32d`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18049b32d`

## string_xrefs

- `0x18049b3fc`: `ComputeRatiosG1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HRESULT __fastcall CaptureOneGGCalibrationEffect::ComputeRatioMapHardware<0>(
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
  v23 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a2 + 88LL))(a2, L"ComputeRatiosG1");
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
0x18049b12c  mov     rax, rsp
0x18049b12f  push    rbp
0x18049b130  push    rbx
0x18049b131  push    rsi
0x18049b132  push    rdi
0x18049b133  push    r14
0x18049b135  lea     rbp, [rax-5Fh]
0x18049b139  sub     rsp, 0E0h
0x18049b140  movaps  xmmword ptr [rax-38h], xmm6
0x18049b144  mov     rax, cs:__security_cookie
0x18049b14b  xor     rax, rsp
0x18049b14e  mov     [rbp+57h+var_40], rax
0x18049b152  mov     rbx, r9
0x18049b155  mov     rdi, r8
0x18049b158  mov     r14, rdx
0x18049b15b  mov     [rbp+57h+var_90], 0
0x18049b163  mov     [rbp+57h+var_A8], 0
0x18049b16b  lea     rax, [rbp+57h+var_A8]
0x18049b16f  mov     [rsp+20h], rax
0x18049b174  lea     r9, [rbp+57h+var_90]
0x18049b178  xor     r8d, r8d
0x18049b17b  mov     rdx, rdi
0x18049b17e  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x18049b183  mov     [rbp+57h+var_98], 0
0x18049b18b  mov     [rbp+57h+var_A0], 0
0x18049b193  lea     rax, [rbp+57h+var_A0]
0x18049b197  mov     [rsp+20h], rax
0x18049b19c  lea     r9, [rbp+57h+var_98]
0x18049b1a0  mov     esi, 1
0x18049b1a5  mov     r8d, esi
0x18049b1a8  mov     rdx, rbx
0x18049b1ab  call    ?LockAndGetTexture@Convolve1DEffect@@AEAAXPEAUIImageBuffer@@W4AccessType@@PEAPEAUIImageBufferLock@@PEAPEAUITexture@@@Z; Convolve1DEffect::LockAndGetTexture(IImageBuffer *,AccessType,IImageBufferLock * *,ITexture * *)
0x18049b1b0  xorps   xmm0, xmm0
0x18049b1b3  xor     eax, eax
0x18049b1b5  movups  [rbp+57h+var_60], xmm0
0x18049b1b9  mov     [rbp+57h+var_50], rax
0x18049b1bd  mov     [rbp+57h+var_48], eax
0x18049b1c0  mov     rax, [rdi]
0x18049b1c3  lea     rdx, [rbp+57h+var_60]
0x18049b1c7  mov     rcx, rdi
0x18049b1ca  mov     rax, [rax+38h]
0x18049b1ce  call    cs:__guard_dispatch_icall_fptr
0x18049b1d4  test    eax, eax
0x18049b1d6  js      loc_18049B4E3
0x18049b1dc  mov     qword ptr [rbp+57h+rgsabound.cElements], 2
0x18049b1e4  lea     ecx, [rsi+3]; vt
0x18049b1e7  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18049b1eb  mov     edx, esi; cDims
0x18049b1ed  call    cs:__imp_SafeArrayCreate
0x18049b1f3  mov     rbx, rax
0x18049b1f6  mov     [rbp+57h+var_88], rax
0x18049b1fa  test    rax, rax
0x18049b1fd  jnz     short loc_18049B206
0x18049b1ff  mov     eax, 8007000Eh
0x18049b204  jmp     short loc_18049B20F
0x18049b206  mov     rcx, rbx; psa
0x18049b209  call    cs:__imp_SafeArrayLock
0x18049b20f  test    eax, eax
0x18049b211  js      loc_18049B4EB
0x18049b217  test    rbx, rbx
0x18049b21a  jz      loc_18049B4F7
0x18049b220  mov     [rbp+57h+plLbound], 0
0x18049b227  lea     r8, [rbp+57h+plLbound]; plLbound
0x18049b22b  mov     edx, esi; nDim
0x18049b22d  mov     rcx, rbx; psa
0x18049b230  call    cs:__imp_SafeArrayGetLBound
0x18049b236  test    eax, eax
0x18049b238  js      loc_18049B502
0x18049b23e  movsxd  rdi, [rbp+57h+plLbound]
0x18049b242  test    edi, edi
0x18049b244  jg      loc_18049B4C9
0x18049b24a  mov     [rbp+57h+plLbound], 0
0x18049b251  lea     r8, [rbp+57h+plLbound]; plUbound
0x18049b255  mov     edx, esi; nDim
0x18049b257  mov     rcx, rbx; psa
0x18049b25a  call    cs:__imp_SafeArrayGetUBound
0x18049b260  test    eax, eax
0x18049b262  js      loc_18049B50A
0x18049b268  cmp     [rbp+57h+plLbound], 0
0x18049b26c  jl      loc_18049B4C9
0x18049b272  movd    xmm0, dword ptr [rbp+57h+var_50+4]
0x18049b277  cvtdq2ps xmm0, xmm0
0x18049b27a  movss   xmm6, cs:__real@3f800000
0x18049b282  movaps  xmm1, xmm6
0x18049b285  divss   xmm1, xmm0
0x18049b289  mov     rcx, rdi
0x18049b28c  shl     rcx, 2
0x18049b290  mov     rax, [rbx+10h]
0x18049b294  sub     rax, rcx
0x18049b297  movss   dword ptr [rax], xmm1
0x18049b29b  mov     [rbp+57h+plLbound], 0
0x18049b2a2  lea     r8, [rbp+57h+plLbound]; plLbound
0x18049b2a6  mov     edx, esi; nDim
0x18049b2a8  mov     rcx, rbx; psa
0x18049b2ab  call    cs:__imp_SafeArrayGetLBound
0x18049b2b1  test    eax, eax
0x18049b2b3  js      loc_18049B512
0x18049b2b9  cmp     [rbp+57h+plLbound], esi
0x18049b2bc  jg      loc_18049B4C9
0x18049b2c2  mov     [rbp+57h+rgsabound.cElements], 0
0x18049b2c9  lea     r8, [rbp+57h+rgsabound]; plUbound
0x18049b2cd  mov     edx, esi; nDim
0x18049b2cf  mov     rcx, rbx; psa
0x18049b2d2  call    cs:__imp_SafeArrayGetUBound
0x18049b2d8  test    eax, eax
0x18049b2da  js      loc_18049B51A
0x18049b2e0  cmp     [rbp+57h+rgsabound.cElements], esi
0x18049b2e3  jl      loc_18049B4C9
0x18049b2e9  movd    xmm0, [rbp+57h+var_48]
0x18049b2ee  cvtdq2ps xmm0, xmm0
0x18049b2f1  divss   xmm6, xmm0
0x18049b2f5  sub     esi, [rbp+57h+plLbound]
0x18049b2f8  movsxd  rcx, esi
0x18049b2fb  mov     rax, [rbx+10h]
0x18049b2ff  movss   dword ptr [rax+rcx*4], xmm6
0x18049b304  mov     rax, [r14]
0x18049b307  mov     rdi, [rax+68h]
0x18049b30b  mov     qword ptr [rbp+57h+rgsabound.cElements], 0
0x18049b313  lea     rdx, [rbp+57h+rgsabound]; ppsaOut
0x18049b317  mov     rcx, rbx; psa
0x18049b31a  call    cs:__imp_SafeArrayCopy
0x18049b320  mov     ecx, eax; int
0x18049b322  test    eax, eax
0x18049b324  js      short loc_18049B373
0x18049b326  lea     rdx, [rbp+57h+pvt]; pvt
0x18049b32a  mov     rcx, rbx; psa
0x18049b32d  call    cs:__imp_SafeArrayGetVartype
0x18049b333  mov     ecx, eax
0x18049b335  movzx   edx, [rbp+57h+pvt]
0x18049b339  test    eax, eax
0x18049b33b  js      short loc_18049B35C
0x18049b33d  cmp     dx, 0Dh
0x18049b341  jnz     short loc_18049B35C
0x18049b343  movzx   eax, word ptr [rbx+2]
0x18049b347  mov     r8d, 440h
0x18049b34d  and     ax, r8w
0x18049b351  cmp     ax, r8w
0x18049b355  jnz     short loc_18049B35C
0x18049b357  mov     edx, 9
0x18049b35c  test    ecx, ecx
0x18049b35e  js      short loc_18049B373
0x18049b360  or      dx, 2000h
0x18049b365  mov     [rbp+57h+pvt], dx
0x18049b369  mov     rax, qword ptr [rbp+57h+rgsabound.cElements]
0x18049b36d  mov     qword ptr [rbp+57h+pvt+8], rax
0x18049b371  jmp     short loc_18049B37F
0x18049b373  mov     eax, 0Ah
0x18049b378  mov     dword ptr [rbp+57h+pvt+8], ecx
0x18049b37b  mov     [rbp+57h+pvt], ax
0x18049b37f  test    ecx, ecx
0x18049b381  jns     short loc_18049B394
0x18049b383  cmp     ecx, 8007000Eh
0x18049b389  jz      loc_18049B4D4
0x18049b38f  jmp     loc_18049B522
0x18049b394  movups  xmm0, xmmword ptr [rbp+57h+pvt]
0x18049b398  movaps  [rbp+57h+var_80], xmm0
0x18049b39c  movsd   xmm1, [rbp+57h+var_B0]
0x18049b3a1  movsd   [rbp+57h+var_70], xmm1
0x18049b3a6  lea     r8, [rbp+57h+var_80]
0x18049b3aa  lea     rdx, aPixeloffset; "pixelOffset"
0x18049b3b1  mov     rcx, r14
0x18049b3b4  mov     rax, rdi
0x18049b3b7  call    cs:__guard_dispatch_icall_fptr
0x18049b3bd  mov     edi, eax
0x18049b3bf  lea     rcx, [rbp+57h+pvt]; pvarg
0x18049b3c3  call    cs:__imp_VariantClear
0x18049b3c9  test    edi, edi
0x18049b3cb  js      loc_18049B540
0x18049b3d1  mov     rax, [r14]
0x18049b3d4  mov     rsi, [rbp+57h+var_A8]
0x18049b3d8  mov     r9, rsi
0x18049b3db  lea     r8, aBayer; "bayer"
0x18049b3e2  xor     edx, edx
0x18049b3e4  mov     rcx, r14
0x18049b3e7  mov     rax, [rax+70h]
0x18049b3eb  call    cs:__guard_dispatch_icall_fptr
0x18049b3f1  test    eax, eax
0x18049b3f3  js      loc_18049B538
0x18049b3f9  mov     rax, [r14]
0x18049b3fc  lea     rdx, aComputeratiosg; "ComputeRatiosG1"
0x18049b403  mov     rcx, r14
0x18049b406  mov     rax, [rax+58h]
0x18049b40a  call    cs:__guard_dispatch_icall_fptr
0x18049b410  test    eax, eax
0x18049b412  js      loc_18049B530
0x18049b418  mov     rax, [r14]
0x18049b41b  mov     rdi, [rbp+57h+var_A0]
0x18049b41f  mov     rdx, rdi
0x18049b422  mov     rcx, r14
0x18049b425  mov     rax, [rax+78h]
0x18049b429  call    cs:__guard_dispatch_icall_fptr
0x18049b42f  test    eax, eax
0x18049b431  js      loc_18049B528
0x18049b437  mov     rcx, rbx; psa
0x18049b43a  call    cs:__imp_SafeArrayUnlock
0x18049b440  test    eax, eax
0x18049b442  js      short loc_18049B44E
0x18049b444  mov     rcx, rbx; psa
0x18049b447  call    cs:__imp_SafeArrayDestroy
0x18049b44d  nop
0x18049b44e  test    rdi, rdi
0x18049b451  jz      short loc_18049B464
0x18049b453  mov     rax, [rdi]
0x18049b456  mov     rcx, rdi
0x18049b459  mov     rax, [rax+10h]
0x18049b45d  call    cs:__guard_dispatch_icall_fptr
0x18049b463  nop
0x18049b464  mov     rcx, [rbp+57h+var_98]
0x18049b468  test    rcx, rcx
0x18049b46b  jz      short loc_18049B47B
0x18049b46d  mov     rax, [rcx]
0x18049b470  mov     rax, [rax+10h]
0x18049b474  call    cs:__guard_dispatch_icall_fptr
0x18049b47a  nop
0x18049b47b  test    rsi, rsi
0x18049b47e  jz      short loc_18049B491
0x18049b480  mov     rax, [rsi]
0x18049b483  mov     rcx, rsi
0x18049b486  mov     rax, [rax+10h]
0x18049b48a  call    cs:__guard_dispatch_icall_fptr
0x18049b490  nop
0x18049b491  mov     rcx, [rbp+57h+var_90]
0x18049b495  test    rcx, rcx
0x18049b498  jz      short loc_18049B4A7
0x18049b49a  mov     rax, [rcx]
0x18049b49d  mov     rax, [rax+10h]
0x18049b4a1  call    cs:__guard_dispatch_icall_fptr
0x18049b4a7  mov     rcx, [rbp+57h+var_40]
0x18049b4ab  xor     rcx, rsp; StackCookie
0x18049b4ae  call    __security_check_cookie
0x18049b4b3  movaps  xmm6, [rsp+100h+var_38+8]
0x18049b4bb  add     rsp, 0E0h
0x18049b4c2  pop     r14
0x18049b4c4  pop     rdi
0x18049b4c5  pop     rsi
0x18049b4c6  pop     rbx
0x18049b4c7  pop     rbp
0x18049b4c8  retn
0x18049b4c9  mov     ecx, 80070057h; int
0x18049b4ce  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b4d4  mov     ecx, 8007000Eh; int
0x18049b4d9  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b4df  jmp     short loc_18049B4E2
0x18049b4e2  nop
0x18049b4e3  mov     ecx, eax; int
0x18049b4e5  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b4eb  mov     ecx, eax; int
0x18049b4ed  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b4f3  jmp     short loc_18049B4F6
0x18049b4f6  nop
0x18049b4f7  mov     ecx, 80004005h; int
0x18049b4fc  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b502  mov     ecx, eax; int
0x18049b504  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b50a  mov     ecx, eax; int
0x18049b50c  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b512  mov     ecx, eax; int
0x18049b514  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b51a  mov     ecx, eax; int
0x18049b51c  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b522  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b528  mov     ecx, eax; int
0x18049b52a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b530  mov     ecx, eax; int
0x18049b532  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b538  mov     ecx, eax; int
0x18049b53a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18049b540  mov     ecx, edi; int
0x18049b542  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
