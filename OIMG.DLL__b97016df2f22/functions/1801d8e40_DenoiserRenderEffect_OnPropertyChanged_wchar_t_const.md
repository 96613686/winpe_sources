# DenoiserRenderEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1801d8e40`
- end: `0x1801d9379`
- name: `?OnPropertyChanged@DenoiserRenderEffect@@UEAAJPEB_W@Z`
- size: `1337`
- prototype: `__int64 __fastcall(DenoiserRenderEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1801d8d04`
- `0x1801d8d98`
- `0x1801d8e40`
- `0x180450d7c`
- `0x1804c6944`
- `0x18056d170`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801d8e92`
- `KERNEL32!CompareStringW` at `0x1801d8f8c`
- `KERNEL32!CompareStringW` at `0x1801d90d0`
- `KERNEL32!CompareStringW` at `0x1801d9188`
- `KERNEL32!CompareStringW` at `0x1801d91cd`
- `KERNEL32!CompareStringW` at `0x1801d9210`
- `KERNEL32!CompareStringW` at `0x1801d9253`
- `KERNEL32!CompareStringW` at `0x1801d9290`
- `KERNEL32!CompareStringW` at `0x1801d8e92`
- `KERNEL32!CompareStringW` at `0x1801d8f8c`
- `KERNEL32!CompareStringW` at `0x1801d90d0`
- `KERNEL32!CompareStringW` at `0x1801d9188`
- `KERNEL32!CompareStringW` at `0x1801d91cd`
- `KERNEL32!CompareStringW` at `0x1801d9210`
- `KERNEL32!CompareStringW` at `0x1801d9253`
- `KERNEL32!CompareStringW` at `0x1801d9290`
- `OLEAUT32!__imp_VariantInit` at `0x1801d8eb5`
- `OLEAUT32!__imp_VariantInit` at `0x1801d8faf`
- `OLEAUT32!__imp_VariantInit` at `0x1801d90f3`
- `OLEAUT32!__imp_VariantInit` at `0x1801d8eb5`
- `OLEAUT32!__imp_VariantInit` at `0x1801d8faf`
- `OLEAUT32!__imp_VariantInit` at `0x1801d90f3`
- `OLEAUT32!__imp_VariantClear` at `0x1801d90a9`
- `OLEAUT32!__imp_VariantClear` at `0x1801d915b`
- `OLEAUT32!__imp_VariantClear` at `0x1801d90a9`
- `OLEAUT32!__imp_VariantClear` at `0x1801d915b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DenoiserRenderEffect::OnPropertyChanged(
        DenoiserRenderEffect *this,
        const wchar_t *a2,
        float a3,
        float a4)
{
  int v6; // eax
  int v7; // eax
  _OWORD *v8; // rdi
  _OWORD *v9; // rax
  _OWORD *v10; // rdi
  int v11; // eax
  bool v12; // bl
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  unsigned int IntFromProperties; // eax
  VARIANTARG pvarg; // [rsp+48h] [rbp-30h] BYREF

  if ( !a2 )
    ATL::BaseAtlThrow(-2147467261);
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"NoiseWaveletModel", -1) == 2 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v6 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           L"NoiseWaveletModel",
           &pvarg);
    if ( v6 == -2147024882 || v6 == -2045378032 || v6 == -2045312765 || v6 == -2045247216 )
      ATL::BaseAtlThrow(v6);
    if ( v6 < 0 )
      ATL::BaseAtlThrow(v6);
    if ( pvarg.vt != 8197 )
      ATL::BaseAtlThrow(-2147024809);
    if ( *pvarg.bstrVal != 1 )
      ATL::BaseAtlThrow(-2147024809);
    if ( *(_DWORD *)(pvarg.llVal + 24) != 1152 )
      ATL::BaseAtlThrow(-2147024809);
    memcpy_0((char *)this + 152, *(const void **)(pvarg.llVal + 16), 0x2400u);
    *((_BYTE *)this + 13209) = 1;
    NoiseWaveletModel::CalculateNoiseStatistics((char *)this + 152, *((unsigned int *)this + 3645));
LABEL_22:
    VariantClear(&pvarg);
    return 0;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"SignalStatistics", -1) == 2 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v7 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           L"SignalStatistics",
           &pvarg);
    if ( v7 == -2147024882 || v7 == -2045378032 || v7 == -2045312765 || v7 == -2045247216 )
      ATL::BaseAtlThrow(v7);
    if ( v7 < 0 )
      ATL::BaseAtlThrow(v7);
    v8 = (_OWORD *)((char *)this + 13216);
    if ( pvarg.vt != 8197 )
      ATL::BaseAtlThrow(-2147024809);
    if ( *pvarg.bstrVal != 1 )
      ATL::BaseAtlThrow(-2147024809);
    if ( *(_DWORD *)(pvarg.llVal + 24) != 24 )
      ATL::BaseAtlThrow(-2147024809);
    v9 = *(_OWORD **)(pvarg.llVal + 16);
    *v8 = *v9;
    v8[1] = v9[1];
    v8[2] = v9[2];
    v8[3] = v9[3];
    v8[4] = v9[4];
    v8[5] = v9[5];
    v8[6] = v9[6];
    v10 = v8 + 8;
    *(v10 - 1) = v9[7];
    v9 += 8;
    *v10 = *v9;
    v10[1] = v9[1];
    v10[2] = v9[2];
    v10[3] = v9[3];
    goto LABEL_22;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"UseLocalBandNeighborhood", -1) == 2 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v11 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
            *((_QWORD *)this + 16),
            L"UseLocalBandNeighborhood",
            &pvarg);
    if ( v11 == -2147024882 || v11 == -2045378032 || v11 == -2045312765 || v11 == -2045247216 )
      ATL::BaseAtlThrow(v11);
    if ( v11 < 0 )
      ATL::BaseAtlThrow(v11);
    v12 = pvarg.iVal != 0;
    VariantClear(&pvarg);
    *((_BYTE *)this + 14584) = v12;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"UseParentBandNeighborhoodMaxLevel", -1) == 2 )
  {
    *((_DWORD *)this + 3643) = DenoiserRenderEffect::GetIntFromProperties(
                                 this,
                                 L"UseParentBandNeighborhoodMaxLevel",
                                 v13,
                                 4);
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"NoiseLevelLuminance", -1) == 2 )
  {
    *((float *)this + 3640) = DenoiserRenderEffect::GetFloatFromProperties(this, L"NoiseLevelLuminance", a3, a4);
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"NoiseLevelChrominance", -1) == 2 )
  {
    *((float *)this + 3641) = DenoiserRenderEffect::GetFloatFromProperties(this, L"NoiseLevelChrominance", a3, a4);
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"DenoiserQuality", -1) == 2 )
  {
    *((_DWORD *)this + 3644) = DenoiserRenderEffect::GetIntFromProperties(this, a2, v14, 2);
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"DenoiserDomain", -1) == 2 )
  {
    IntFromProperties = DenoiserRenderEffect::GetIntFromProperties(this, a2, v15, 1);
    *((_DWORD *)this + 3645) = IntFromProperties;
    if ( *((_BYTE *)this + 13209) )
      NoiseWaveletModel::CalculateNoiseStatistics((char *)this + 152, IntFromProperties);
  }
  return 0;
}

```

## disassembly

```asm
0x1801d8e40  mov     [rsp+arg_0], rbx
0x1801d8e45  mov     [rsp+arg_10], rsi
0x1801d8e4a  mov     [rsp+arg_18], rdi
0x1801d8e4f  push    r13
0x1801d8e51  push    r14
0x1801d8e53  push    r15
0x1801d8e55  sub     rsp, 60h
0x1801d8e59  mov     rbx, rdx
0x1801d8e5c  mov     rdi, rcx
0x1801d8e5f  xor     r15d, r15d
0x1801d8e62  test    rdx, rdx
0x1801d8e65  jz      loc_1801D92F8
0x1801d8e6b  or      esi, 0FFFFFFFFh
0x1801d8e6e  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801d8e72  lea     rax, aNoisewaveletmo; "NoiseWaveletModel"
0x1801d8e79  mov     [rsp+78h+lpString2], rax; lpString2
0x1801d8e7e  mov     r9d, esi; cchCount1
0x1801d8e81  mov     r8, rbx; lpString1
0x1801d8e84  lea     r14d, [rsi+2]
0x1801d8e88  mov     edx, r14d; dwCmpFlags
0x1801d8e8b  lea     r13d, [r14+7Eh]
0x1801d8e8f  mov     ecx, r13d; Locale
0x1801d8e92  call    cs:__imp_CompareStringW
0x1801d8e98  cmp     eax, 2
0x1801d8e9b  jnz     loc_1801D8F70
0x1801d8ea1  xorps   xmm0, xmm0
0x1801d8ea4  xor     eax, eax
0x1801d8ea6  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x1801d8eab  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x1801d8eb0  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801d8eb5  call    cs:__imp_VariantInit
0x1801d8ebb  mov     rcx, [rdi+80h]
0x1801d8ec2  mov     rax, [rcx]
0x1801d8ec5  lea     r8, [rsp+78h+pvarg]
0x1801d8eca  lea     rdx, aNoisewaveletmo; "NoiseWaveletModel"
0x1801d8ed1  mov     rax, [rax+60h]
0x1801d8ed5  call    cs:__guard_dispatch_icall_fptr
0x1801d8edb  cmp     eax, 8007000Eh
0x1801d8ee0  jz      loc_1801D932E
0x1801d8ee6  cmp     eax, 86160210h
0x1801d8eeb  jz      loc_1801D932E
0x1801d8ef1  cmp     eax, 86170103h
0x1801d8ef6  jz      loc_1801D932E
0x1801d8efc  cmp     eax, 86180110h
0x1801d8f01  jz      loc_1801D932E
0x1801d8f07  test    eax, eax
0x1801d8f09  js      loc_1801D9309
0x1801d8f0f  lea     rbx, [rdi+98h]
0x1801d8f16  mov     eax, 2005h
0x1801d8f1b  cmp     word ptr [rsp+78h+pvarg], ax
0x1801d8f20  jnz     loc_1801D9310
0x1801d8f26  mov     rdx, qword ptr [rsp+78h+pvarg+8]
0x1801d8f2b  cmp     [rdx], r14w
0x1801d8f2f  jnz     loc_1801D931A
0x1801d8f35  cmp     dword ptr [rdx+18h], 480h
0x1801d8f3c  jnz     loc_1801D9324
0x1801d8f42  mov     r8d, 2400h; Size
0x1801d8f48  mov     rdx, [rdx+10h]; Src
0x1801d8f4c  mov     rcx, rbx; void *
0x1801d8f4f  call    memcpy_0
0x1801d8f54  mov     [rbx+3301h], r14b
0x1801d8f5b  mov     edx, [rdi+38F4h]
0x1801d8f61  mov     rcx, rbx
0x1801d8f64  call    ?CalculateNoiseStatistics@NoiseWaveletModel@@QEAAXW4__MIDL___MIDL_itf_Imaging_0001_0116_0002@@@Z; NoiseWaveletModel::CalculateNoiseStatistics(__MIDL___MIDL_itf_Imaging_0001_0116_0002)
0x1801d8f69  jmp     loc_1801D90A4
0x1801d8f70  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801d8f74  lea     rax, aSignalstatisti; "SignalStatistics"
0x1801d8f7b  mov     [rsp+78h+lpString2], rax; lpString2
0x1801d8f80  mov     r9d, esi; cchCount1
0x1801d8f83  mov     r8, rbx; lpString1
0x1801d8f86  mov     edx, r14d; dwCmpFlags
0x1801d8f89  mov     ecx, r13d; Locale
0x1801d8f8c  call    cs:__imp_CompareStringW
0x1801d8f92  cmp     eax, 2
0x1801d8f95  jnz     loc_1801D90B4
0x1801d8f9b  xorps   xmm0, xmm0
0x1801d8f9e  xor     eax, eax
0x1801d8fa0  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x1801d8fa5  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x1801d8faa  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801d8faf  call    cs:__imp_VariantInit
0x1801d8fb5  mov     rcx, [rdi+80h]
0x1801d8fbc  mov     rax, [rcx]
0x1801d8fbf  lea     r8, [rsp+78h+pvarg]
0x1801d8fc4  lea     rdx, aSignalstatisti; "SignalStatistics"
0x1801d8fcb  mov     rax, [rax+60h]
0x1801d8fcf  call    cs:__guard_dispatch_icall_fptr
0x1801d8fd5  cmp     eax, 8007000Eh
0x1801d8fda  jz      loc_1801D935E
0x1801d8fe0  cmp     eax, 86160210h
0x1801d8fe5  jz      loc_1801D935E
0x1801d8feb  cmp     eax, 86170103h
0x1801d8ff0  jz      loc_1801D935E
0x1801d8ff6  cmp     eax, 86180110h
0x1801d8ffb  jz      loc_1801D935E
0x1801d9001  test    eax, eax
0x1801d9003  js      loc_1801D9339
0x1801d9009  add     rdi, 33A0h
0x1801d9010  mov     eax, 2005h
0x1801d9015  cmp     word ptr [rsp+78h+pvarg], ax
0x1801d901a  jnz     loc_1801D9340
0x1801d9020  mov     rax, qword ptr [rsp+78h+pvarg+8]
0x1801d9025  cmp     [rax], r14w
0x1801d9029  jnz     loc_1801D934A
0x1801d902f  cmp     dword ptr [rax+18h], 18h
0x1801d9033  jnz     loc_1801D9354
0x1801d9039  mov     rax, [rax+10h]
0x1801d903d  movups  xmm0, xmmword ptr [rax]
0x1801d9040  movups  xmmword ptr [rdi], xmm0
0x1801d9043  movups  xmm1, xmmword ptr [rax+10h]
0x1801d9047  movups  xmmword ptr [rdi+10h], xmm1
0x1801d904b  movups  xmm0, xmmword ptr [rax+20h]
0x1801d904f  movups  xmmword ptr [rdi+20h], xmm0
0x1801d9053  movups  xmm1, xmmword ptr [rax+30h]
0x1801d9057  movups  xmmword ptr [rdi+30h], xmm1
0x1801d905b  movups  xmm0, xmmword ptr [rax+40h]
0x1801d905f  movups  xmmword ptr [rdi+40h], xmm0
0x1801d9063  movups  xmm1, xmmword ptr [rax+50h]
0x1801d9067  movups  xmmword ptr [rdi+50h], xmm1
0x1801d906b  movups  xmm0, xmmword ptr [rax+60h]
0x1801d906f  movups  xmmword ptr [rdi+60h], xmm0
0x1801d9073  mov     ecx, 80h
0x1801d9078  add     rdi, rcx
0x1801d907b  movups  xmm0, xmmword ptr [rax+70h]
0x1801d907f  movups  xmmword ptr [rdi-10h], xmm0
0x1801d9083  add     rax, rcx
0x1801d9086  movups  xmm1, xmmword ptr [rax]
0x1801d9089  movups  xmmword ptr [rdi], xmm1
0x1801d908c  movups  xmm0, xmmword ptr [rax+10h]
0x1801d9090  movups  xmmword ptr [rdi+10h], xmm0
0x1801d9094  movups  xmm1, xmmword ptr [rax+20h]
0x1801d9098  movups  xmmword ptr [rdi+20h], xmm1
0x1801d909c  movups  xmm0, xmmword ptr [rax+30h]
0x1801d90a0  movups  xmmword ptr [rdi+30h], xmm0
0x1801d90a4  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801d90a9  call    cs:__imp_VariantClear
0x1801d90af  jmp     loc_1801D92C6
0x1801d90b4  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801d90b8  lea     rax, aUselocalbandne; "UseLocalBandNeighborhood"
0x1801d90bf  mov     [rsp+78h+lpString2], rax; lpString2
0x1801d90c4  mov     r9d, esi; cchCount1
0x1801d90c7  mov     r8, rbx; lpString1
0x1801d90ca  mov     edx, r14d; dwCmpFlags
0x1801d90cd  mov     ecx, r13d; Locale
0x1801d90d0  call    cs:__imp_CompareStringW
0x1801d90d6  cmp     eax, 2
0x1801d90d9  jnz     loc_1801D916C
0x1801d90df  xorps   xmm0, xmm0
0x1801d90e2  xor     eax, eax
0x1801d90e4  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x1801d90e9  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x1801d90ee  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801d90f3  call    cs:__imp_VariantInit
0x1801d90f9  mov     rcx, [rdi+80h]
0x1801d9100  mov     rax, [rcx]
0x1801d9103  lea     r8, [rsp+78h+pvarg]
0x1801d9108  lea     rdx, aUselocalbandne; "UseLocalBandNeighborhood"
0x1801d910f  mov     rax, [rax+60h]
0x1801d9113  call    cs:__guard_dispatch_icall_fptr
0x1801d9119  cmp     eax, 8007000Eh
0x1801d911e  jz      loc_1801D9370
0x1801d9124  cmp     eax, 86160210h
0x1801d9129  jz      loc_1801D9370
0x1801d912f  cmp     eax, 86170103h
0x1801d9134  jz      loc_1801D9370
0x1801d913a  cmp     eax, 86180110h
0x1801d913f  jz      loc_1801D9370
0x1801d9145  test    eax, eax
0x1801d9147  js      loc_1801D9369
0x1801d914d  cmp     word ptr [rsp+78h+pvarg+8], r15w
0x1801d9153  setnz   bl
0x1801d9156  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801d915b  call    cs:__imp_VariantClear
0x1801d9161  mov     [rdi+38F8h], bl
0x1801d9167  jmp     loc_1801D92C6
0x1801d916c  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801d9170  lea     rax, aUseparentbandn; "UseParentBandNeighborhoodMaxLevel"
0x1801d9177  mov     [rsp+78h+lpString2], rax; lpString2
0x1801d917c  mov     r9d, esi; cchCount1
0x1801d917f  mov     r8, rbx; lpString1
0x1801d9182  mov     edx, r14d; dwCmpFlags
0x1801d9185  mov     ecx, r13d; Locale
0x1801d9188  call    cs:__imp_CompareStringW
0x1801d918e  cmp     eax, 2
0x1801d9191  jnz     short loc_1801D91B1
0x1801d9193  lea     r9d, [rax+2]; int
0x1801d9197  lea     rdx, aUseparentbandn; "UseParentBandNeighborhoodMaxLevel"
0x1801d919e  mov     rcx, rdi; this
0x1801d91a1  call    ?GetIntFromProperties@DenoiserRenderEffect@@AEAAHPEB_WHH@Z; DenoiserRenderEffect::GetIntFromProperties(wchar_t const *,int,int)
0x1801d91a6  mov     [rdi+38ECh], eax
0x1801d91ac  jmp     loc_1801D92C6
0x1801d91b1  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801d91b5  lea     rax, aNoiselevellumi; "NoiseLevelLuminance"
0x1801d91bc  mov     [rsp+78h+lpString2], rax; lpString2
0x1801d91c1  mov     r9d, esi; cchCount1
0x1801d91c4  mov     r8, rbx; lpString1
0x1801d91c7  mov     edx, r14d; dwCmpFlags
0x1801d91ca  mov     ecx, r13d; Locale
0x1801d91cd  call    cs:__imp_CompareStringW
0x1801d91d3  cmp     eax, 2
0x1801d91d6  jnz     short loc_1801D91F4
0x1801d91d8  lea     rdx, aNoiselevellumi; "NoiseLevelLuminance"
0x1801d91df  mov     rcx, rdi; this
0x1801d91e2  call    ?GetFloatFromProperties@DenoiserRenderEffect@@AEAAMPEB_WMM@Z; DenoiserRenderEffect::GetFloatFromProperties(wchar_t const *,float,float)
0x1801d91e7  movss   dword ptr [rdi+38E0h], xmm0
0x1801d91ef  jmp     loc_1801D92C6
0x1801d91f4  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801d91f8  lea     rax, aNoiselevelchro; "NoiseLevelChrominance"
0x1801d91ff  mov     [rsp+78h+lpString2], rax; lpString2
0x1801d9204  mov     r9d, esi; cchCount1
0x1801d9207  mov     r8, rbx; lpString1
0x1801d920a  mov     edx, r14d; dwCmpFlags
0x1801d920d  mov     ecx, r13d; Locale
0x1801d9210  call    cs:__imp_CompareStringW
0x1801d9216  cmp     eax, 2
0x1801d9219  jnz     short loc_1801D9237
0x1801d921b  lea     rdx, aNoiselevelchro; "NoiseLevelChrominance"
0x1801d9222  mov     rcx, rdi; this
0x1801d9225  call    ?GetFloatFromProperties@DenoiserRenderEffect@@AEAAMPEB_WMM@Z; DenoiserRenderEffect::GetFloatFromProperties(wchar_t const *,float,float)
0x1801d922a  movss   dword ptr [rdi+38E4h], xmm0
0x1801d9232  jmp     loc_1801D92C6
0x1801d9237  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801d923b  lea     rax, aDenoiserqualit; "DenoiserQuality"
0x1801d9242  mov     [rsp+78h+lpString2], rax; lpString2
0x1801d9247  mov     r9d, esi; cchCount1
0x1801d924a  mov     r8, rbx; lpString1
0x1801d924d  mov     edx, r14d; dwCmpFlags
0x1801d9250  mov     ecx, r13d; Locale
0x1801d9253  call    cs:__imp_CompareStringW
0x1801d9259  cmp     eax, 2
0x1801d925c  jnz     short loc_1801D9274
0x1801d925e  mov     r9d, eax; int
0x1801d9261  mov     rdx, rbx; wchar_t *
0x1801d9264  mov     rcx, rdi; this
0x1801d9267  call    ?GetIntFromProperties@DenoiserRenderEffect@@AEAAHPEB_WHH@Z; DenoiserRenderEffect::GetIntFromProperties(wchar_t const *,int,int)
0x1801d926c  mov     [rdi+38F0h], eax
0x1801d9272  jmp     short loc_1801D92C6
0x1801d9274  mov     [rsp+78h+cchCount2], esi; cchCount2
0x1801d9278  lea     rax, aDenoiserdomain; "DenoiserDomain"
0x1801d927f  mov     [rsp+78h+lpString2], rax; lpString2
0x1801d9284  mov     r9d, esi; cchCount1
0x1801d9287  mov     r8, rbx; lpString1
0x1801d928a  mov     edx, r14d; dwCmpFlags
0x1801d928d  mov     ecx, r13d; Locale
0x1801d9290  call    cs:__imp_CompareStringW
0x1801d9296  cmp     eax, 2
0x1801d9299  jnz     short loc_1801D92C6
0x1801d929b  mov     r9d, r14d; int
0x1801d929e  mov     rdx, rbx; wchar_t *
0x1801d92a1  mov     rcx, rdi; this
0x1801d92a4  call    ?GetIntFromProperties@DenoiserRenderEffect@@AEAAHPEB_WHH@Z; DenoiserRenderEffect::GetIntFromProperties(wchar_t const *,int,int)
0x1801d92a9  mov     [rdi+38F4h], eax
0x1801d92af  cmp     [rdi+3399h], r15b
0x1801d92b6  jz      short loc_1801D92C6
0x1801d92b8  lea     rcx, [rdi+98h]
0x1801d92bf  mov     edx, eax
0x1801d92c1  call    ?CalculateNoiseStatistics@NoiseWaveletModel@@QEAAXW4__MIDL___MIDL_itf_Imaging_0001_0116_0002@@@Z; NoiseWaveletModel::CalculateNoiseStatistics(__MIDL___MIDL_itf_Imaging_0001_0116_0002)
0x1801d92c6  xor     eax, eax
0x1801d92c8  jmp     short loc_1801D92DD
0x1801d92ca  mov     eax, [rsp+78h+arg_8]
0x1801d92d1  mov     edx, 86160101h
0x1801d92d6  cmp     ax, 216h
0x1801d92da  cmovz   eax, edx
0x1801d92dd  lea     r11, [rsp+78h+var_18]
0x1801d92e2  mov     rbx, [r11+20h]
0x1801d92e6  mov     rsi, [r11+30h]
0x1801d92ea  mov     rdi, [r11+38h]
0x1801d92ee  mov     rsp, r11
0x1801d92f1  pop     r15
0x1801d92f3  pop     r14
0x1801d92f5  pop     r13
0x1801d92f7  retn
0x1801d92f8  mov     ecx, 80004003h; int
0x1801d92fd  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d9303  jmp     short loc_1801D9308
0x1801d9308  nop
0x1801d9309  mov     ecx, eax; int
0x1801d930b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d9310  mov     ecx, 80070057h; int
0x1801d9315  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d931a  mov     ecx, 80070057h; int
0x1801d931f  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d9324  mov     ecx, 80070057h; int
0x1801d9329  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d932e  mov     ecx, eax; int
0x1801d9330  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d9336  jmp     short $+2
0x1801d9338  nop
0x1801d9339  mov     ecx, eax; int
0x1801d933b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d9340  mov     ecx, 80070057h; int
0x1801d9345  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d934a  mov     ecx, 80070057h; int
0x1801d934f  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d9354  mov     ecx, 80070057h; int
0x1801d9359  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d935e  mov     ecx, eax; int
0x1801d9360  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d9366  jmp     short $+2
0x1801d9368  nop
  ... truncated ...
```
