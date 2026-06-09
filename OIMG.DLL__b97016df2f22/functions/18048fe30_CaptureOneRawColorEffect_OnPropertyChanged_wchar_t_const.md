# CaptureOneRawColorEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x18048fe30`
- end: `0x1804905ee`
- name: `?OnPropertyChanged@CaptureOneRawColorEffect@@UEAAJPEB_W@Z`
- size: `1982`
- prototype: `int(CaptureOneRawColorEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1802017d0`
- `0x180201a9c`
- `0x18047d448`
- `0x18048f53c`
- `0x18048f6e8`
- `0x18048f894`
- `0x18048fe30`
- `0x1804c6944`
- `0x18056dcb2`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18048fef7`
- `KERNEL32!CompareStringW` at `0x18048ff44`
- `KERNEL32!CompareStringW` at `0x18048ff92`
- `KERNEL32!CompareStringW` at `0x18048ffc9`
- `KERNEL32!CompareStringW` at `0x180490007`
- `KERNEL32!CompareStringW` at `0x180490045`
- `KERNEL32!CompareStringW` at `0x180490080`
- `KERNEL32!CompareStringW` at `0x1804900bb`
- `KERNEL32!CompareStringW` at `0x18048fef7`
- `KERNEL32!CompareStringW` at `0x18048ff44`
- `KERNEL32!CompareStringW` at `0x18048ff92`
- `KERNEL32!CompareStringW` at `0x18048ffc9`
- `KERNEL32!CompareStringW` at `0x180490007`
- `KERNEL32!CompareStringW` at `0x180490045`
- `KERNEL32!CompareStringW` at `0x180490080`
- `KERNEL32!CompareStringW` at `0x1804900bb`
- `OLEAUT32!__imp_VariantInit` at `0x18048fe7a`
- `OLEAUT32!__imp_VariantInit` at `0x1804900e5`
- `OLEAUT32!__imp_VariantInit` at `0x18049037b`
- `OLEAUT32!__imp_VariantInit` at `0x18048fe7a`
- `OLEAUT32!__imp_VariantInit` at `0x1804900e5`
- `OLEAUT32!__imp_VariantInit` at `0x18049037b`
- `OLEAUT32!__imp_VariantClear` at `0x180490504`
- `OLEAUT32!__imp_VariantClear` at `0x18049050f`
- `OLEAUT32!__imp_VariantClear` at `0x18049051a`
- `OLEAUT32!__imp_VariantClear` at `0x180490504`
- `OLEAUT32!__imp_VariantClear` at `0x18049050f`
- `OLEAUT32!__imp_VariantClear` at `0x18049051a`

## string_xrefs

- `0x18048ffb1`: `ExposureCompensation`
- `0x180490068`: `HighlightRecoveryCaptureOneCompliant`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CaptureOneRawColorEffect::OnPropertyChanged(CaptureOneRawColorEffect *this, const wchar_t *a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  float v7; // xmm4_4
  _OWORD *v8; // rax
  int v9; // eax
  int v10; // xmm0_4
  int v11; // xmm1_4
  int v12; // xmm0_4
  VARIANTARG pvarg; // [rsp+30h] [rbp-178h] BYREF
  VARIANTARG v15; // [rsp+48h] [rbp-160h] BYREF
  VARIANTARG v16; // [rsp+60h] [rbp-148h] BYREF
  __int128 v17; // [rsp+80h] [rbp-128h] BYREF
  __int128 v18; // [rsp+90h] [rbp-118h]
  __int128 v19; // [rsp+A0h] [rbp-108h]
  __int128 v20; // [rsp+B0h] [rbp-F8h]
  VARIANTARG v21; // [rsp+C0h] [rbp-E8h] BYREF
  _BYTE v22[64]; // [rsp+F0h] [rbp-B8h] BYREF
  _BYTE v23[96]; // [rsp+130h] [rbp-78h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+1B8h] [rbp+10h] BYREF

  if ( !a2 )
    ATL::BaseAtlThrow(-2147467261);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
         *((_QWORD *)this + 16),
         a2,
         &pvarg);
  if ( v4 == -2147024882 || v4 == -2045378032 || v4 == -2045312765 || v4 == -2045247216 )
    ATL::BaseAtlThrow(v4);
  if ( v4 < 0 )
    ATL::BaseAtlThrow(v4);
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"_CameraMatrix", -1) == 2 )
  {
    if ( pvarg.vt )
      MetadataHelperFunctions::GetFloatArrayFromVariant(&pvarg, (char *)this + 152, 9);
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Saturation", -1) == 2 )
  {
    *((float *)this + 40) = (float)((float)pvarg.dblVal + 100.0) * 0.0099999998;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"EnableWhiteBalance", -1) == 2 )
  {
    *((_DWORD *)this + 49) = pvarg.iVal;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"ExposureCompensation", -1) == 2 )
  {
    *((float *)this + 44) = pvarg.dblVal;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"_BaselineExposure", -1) == 2 )
  {
    *((float *)this + 45) = pvarg.dblVal;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Gain", -1) == 2 )
  {
    *((float *)this + 46) = pvarg.dblVal;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"HighlightRecoveryCaptureOneCompliant", -1) == 2 )
  {
    *((_DWORD *)this + 48) = pvarg.iVal != 0;
  }
  else if ( CompareStringW(0x7Fu, 1u, a2, -1, L"UseLocalExposure", -1) == 2 )
  {
    *((_DWORD *)this + 67) = pvarg.iVal;
  }
  memset(&v15, 0, sizeof(v15));
  VariantInit(&v15);
  v5 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
         *((_QWORD *)this + 16),
         L"WhiteBalance",
         &v15);
  if ( v5 == -2147024882 || v5 == -2045378032 || v5 == -2045312765 || v5 == -2045247216 )
    ATL::BaseAtlThrow(v5);
  if ( v5 < 0 )
    ATL::BaseAtlThrow(v5);
  if ( *((_DWORD *)this + 49) && v15.vt )
  {
    v21 = v15;
    if ( (unsigned int)VARIANTToArray<float>(&v21, (char *)this + 164, 3) != 3 )
      ATL::BaseAtlThrow(-2147024809);
    if ( *((float *)this + 41) <= 0.0 )
      ATL::BaseAtlThrow(-2147024809);
    if ( *((float *)this + 42) <= 0.0 )
      ATL::BaseAtlThrow(-2147024809);
    if ( *((float *)this + 43) <= 0.0 )
      ATL::BaseAtlThrow(-2147024809);
  }
  else
  {
    *((_DWORD *)this + 41) = 1065353216;
    *((_DWORD *)this + 42) = 1065353216;
    *((_DWORD *)this + 43) = 1065353216;
  }
  ppsaOut = 0;
  v6 = ATL::CComSafeArray<float,4>::CopyFrom(&ppsaOut, *((SAFEARRAY **)this + 19));
  if ( v6 < 0 )
    ATL::BaseAtlThrow(v6);
  ColorMatrix::MatrixFromSafeArray9(v22, &ppsaOut);
  v17 = ColorMatrix::kIdentity;
  v18 = xmmword_1806A3250;
  v19 = xmmword_1806A3260;
  v20 = xmmword_1806A3270;
  v7 = *((float *)this + 40);
  *(float *)&v17 = (float)((float)(1.0 - v7) * 0.30860001) + v7;
  *((float *)&v17 + 1) = (float)(1.0 - v7) * 0.60939997;
  *((float *)&v17 + 2) = (float)(1.0 - v7) * 0.082000002;
  *(float *)&v18 = (float)(1.0 - v7) * 0.30860001;
  *((float *)&v18 + 1) = *((float *)&v17 + 1) + v7;
  *((float *)&v18 + 2) = *((float *)&v17 + 2);
  *(float *)&v19 = *(float *)&v18;
  *((float *)&v19 + 1) = *((float *)&v17 + 1);
  *((float *)&v19 + 2) = *((float *)&v17 + 2) + v7;
  *((float *)this + 47) = powf_0(2.0, *((float *)this + 45) + *((float *)this + 44)) * *((float *)this + 46);
  v8 = (_OWORD *)ColorMatrix::operator*(&v17, v23, v22);
  *(_OWORD *)((char *)this + 204) = *v8;
  *(_OWORD *)((char *)this + 220) = v8[1];
  *(_OWORD *)((char *)this + 236) = v8[2];
  *(_OWORD *)((char *)this + 252) = v8[3];
  memset(&v16, 0, sizeof(v16));
  VariantInit(&v16);
  v9 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
         *((_QWORD *)this + 16),
         L"Invert",
         &v16);
  if ( v9 == -2147024882 || v9 == -2045378032 || v9 == -2045312765 || v9 == -2045247216 )
    ATL::BaseAtlThrow(v9);
  if ( v9 < 0 )
    ATL::BaseAtlThrow(v9);
  if ( v16.vt == 11 && v16.iVal )
  {
    if ( *((float *)this + 47) <= 0.0 )
      ATL::BaseAtlThrow(-2147024809);
    if ( (float)((float)((float)((float)((float)(*((float *)this + 60) * *((float *)this + 55))
                                       - (float)(*((float *)this + 59) * *((float *)this + 56)))
                               * *((float *)this + 53))
                       - (float)((float)((float)(*((float *)this + 60) * *((float *)this + 51))
                                       - (float)(*((float *)this + 59) * *((float *)this + 52)))
                               * *((float *)this + 57)))
               + (float)((float)((float)(*((float *)this + 56) * *((float *)this + 51))
                               - (float)(*((float *)this + 55) * *((float *)this + 52)))
                       * *((float *)this + 61))) == 0.0 )
      ATL::BaseAtlThrow(-2147024809);
    ColorMatrix::Invert((CaptureOneRawColorEffect *)((char *)this + 204));
    *((float *)this + 41) = 1.0 / *((float *)this + 41);
    *((float *)this + 42) = 1.0 / *((float *)this + 42);
    *((float *)this + 43) = 1.0 / *((float *)this + 43);
    *((float *)this + 47) = 1.0 / *((float *)this + 47);
  }
  v10 = *((_DWORD *)this + 52);
  *((_DWORD *)this + 52) = *((_DWORD *)this + 55);
  *((_DWORD *)this + 55) = v10;
  v11 = *((_DWORD *)this + 53);
  *((_DWORD *)this + 53) = *((_DWORD *)this + 59);
  *((_DWORD *)this + 59) = v11;
  v12 = *((_DWORD *)this + 57);
  *((_DWORD *)this + 57) = *((_DWORD *)this + 60);
  *((_DWORD *)this + 60) = v12;
  VariantClear(&v16);
  VariantClear(&v15);
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x18048fe30  mov     rax, rsp
0x18048fe33  mov     [rax+8], rbx
0x18048fe37  mov     [rax+18h], rsi
0x18048fe3b  mov     [rax+20h], rdi
0x18048fe3f  push    r12
0x18048fe41  push    r14
0x18048fe43  push    r15
0x18048fe45  sub     rsp, 190h
0x18048fe4c  movaps  xmmword ptr [rax-28h], xmm6
0x18048fe50  movaps  xmmword ptr [rax-38h], xmm7
0x18048fe54  mov     rdi, rdx
0x18048fe57  mov     rbx, rcx
0x18048fe5a  xor     r14d, r14d
0x18048fe5d  test    rdx, rdx
0x18048fe60  jz      loc_18049055F
0x18048fe66  xorps   xmm0, xmm0
0x18048fe69  xor     eax, eax
0x18048fe6b  movups  xmmword ptr [rsp+1A8h+pvarg], xmm0
0x18048fe70  mov     qword ptr [rsp+1A8h+pvarg+10h], rax
0x18048fe75  lea     rcx, [rsp+1A8h+pvarg]; pvarg
0x18048fe7a  call    cs:__imp_VariantInit
0x18048fe80  mov     rcx, [rbx+80h]
0x18048fe87  mov     rax, [rcx]
0x18048fe8a  lea     r8, [rsp+1A8h+pvarg]
0x18048fe8f  mov     rdx, rdi
0x18048fe92  mov     rax, [rax+60h]
0x18048fe96  call    cs:__guard_dispatch_icall_fptr
0x18048fe9c  cmp     eax, 8007000Eh
0x18048fea1  jz      loc_1804905E5
0x18048fea7  cmp     eax, 86160210h
0x18048feac  jz      loc_1804905E5
0x18048feb2  cmp     eax, 86170103h
0x18048feb7  jz      loc_1804905E5
0x18048febd  cmp     eax, 86180110h
0x18048fec2  jz      loc_1804905E5
0x18048fec8  test    eax, eax
0x18048feca  js      loc_18049056D
0x18048fed0  or      esi, 0FFFFFFFFh
0x18048fed3  mov     [rsp+1A8h+cchCount2], esi; cchCount2
0x18048fed7  lea     rax, aCameramatrix; "_CameraMatrix"
0x18048fede  mov     [rsp+1A8h+lpString2], rax; lpString2
0x18048fee3  mov     r9d, esi; cchCount1
0x18048fee6  mov     r8, rdi; lpString1
0x18048fee9  lea     r15d, [rsi+2]
0x18048feed  mov     edx, r15d; dwCmpFlags
0x18048fef0  lea     r12d, [r15+7Eh]
0x18048fef4  mov     ecx, r12d; Locale
0x18048fef7  call    cs:__imp_CompareStringW
0x18048fefd  cmp     eax, 2
0x18048ff00  jnz     short loc_18048FF28
0x18048ff02  cmp     word ptr [rsp+1A8h+pvarg], r14w
0x18048ff08  jz      loc_1804900D1
0x18048ff0e  lea     rdx, [rbx+98h]
0x18048ff15  lea     r8d, [rsi+0Ah]
0x18048ff19  lea     rcx, [rsp+1A8h+pvarg]
0x18048ff1e  call    ?GetFloatArrayFromVariant@MetadataHelperFunctions@@SAXAEBVCComVariant@ATL@@PEAV?$CComSafeArray@M$03@3@H@Z; MetadataHelperFunctions::GetFloatArrayFromVariant(ATL::CComVariant const &,ATL::CComSafeArray<float,4> *,int)
0x18048ff23  jmp     loc_1804900D1
0x18048ff28  mov     [rsp+1A8h+cchCount2], esi; cchCount2
0x18048ff2c  lea     rax, aSaturation; "Saturation"
0x18048ff33  mov     [rsp+1A8h+lpString2], rax; lpString2
0x18048ff38  mov     r9d, esi; cchCount1
0x18048ff3b  mov     r8, rdi; lpString1
0x18048ff3e  mov     edx, r15d; dwCmpFlags
0x18048ff41  mov     ecx, r12d; Locale
0x18048ff44  call    cs:__imp_CompareStringW
0x18048ff4a  cmp     eax, 2
0x18048ff4d  jnz     short loc_18048FF76
0x18048ff4f  movsd   xmm0, qword ptr [rsp+1A8h+pvarg+8]
0x18048ff55  cvtpd2ps xmm0, xmm0
0x18048ff59  addss   xmm0, cs:__real@42c80000
0x18048ff61  mulss   xmm0, cs:__real@3c23d70a
0x18048ff69  movss   dword ptr [rbx+0A0h], xmm0
0x18048ff71  jmp     loc_1804900D1
0x18048ff76  mov     [rsp+1A8h+cchCount2], esi; cchCount2
0x18048ff7a  lea     rax, aEnablewhitebal; "EnableWhiteBalance"
0x18048ff81  mov     [rsp+1A8h+lpString2], rax; lpString2
0x18048ff86  mov     r9d, esi; cchCount1
0x18048ff89  mov     r8, rdi; lpString1
0x18048ff8c  mov     edx, r15d; dwCmpFlags
0x18048ff8f  mov     ecx, r12d; Locale
0x18048ff92  call    cs:__imp_CompareStringW
0x18048ff98  cmp     eax, 2
0x18048ff9b  jnz     short loc_18048FFAD
0x18048ff9d  movsx   eax, word ptr [rsp+1A8h+pvarg+8]
0x18048ffa2  mov     [rbx+0C4h], eax
0x18048ffa8  jmp     loc_1804900D1
0x18048ffad  mov     [rsp+1A8h+cchCount2], esi; cchCount2
0x18048ffb1  lea     rax, aExposurecompen; "ExposureCompensation"
0x18048ffb8  mov     [rsp+1A8h+lpString2], rax; lpString2
0x18048ffbd  mov     r9d, esi; cchCount1
0x18048ffc0  mov     r8, rdi; lpString1
0x18048ffc3  mov     edx, r15d; dwCmpFlags
0x18048ffc6  mov     ecx, r12d; Locale
0x18048ffc9  call    cs:__imp_CompareStringW
0x18048ffcf  cmp     eax, 2
0x18048ffd2  jnz     short loc_18048FFEB
0x18048ffd4  movsd   xmm0, qword ptr [rsp+1A8h+pvarg+8]
0x18048ffda  cvtpd2ps xmm0, xmm0
0x18048ffde  movss   dword ptr [rbx+0B0h], xmm0
0x18048ffe6  jmp     loc_1804900D1
0x18048ffeb  mov     [rsp+1A8h+cchCount2], esi; cchCount2
0x18048ffef  lea     rax, aBaselineexposu; "_BaselineExposure"
0x18048fff6  mov     [rsp+1A8h+lpString2], rax; lpString2
0x18048fffb  mov     r9d, esi; cchCount1
0x18048fffe  mov     r8, rdi; lpString1
0x180490001  mov     edx, r15d; dwCmpFlags
0x180490004  mov     ecx, r12d; Locale
0x180490007  call    cs:__imp_CompareStringW
0x18049000d  cmp     eax, 2
0x180490010  jnz     short loc_180490029
0x180490012  movsd   xmm0, qword ptr [rsp+1A8h+pvarg+8]
0x180490018  cvtpd2ps xmm0, xmm0
0x18049001c  movss   dword ptr [rbx+0B4h], xmm0
0x180490024  jmp     loc_1804900D1
0x180490029  mov     [rsp+1A8h+cchCount2], esi; cchCount2
0x18049002d  lea     rax, aGain; "Gain"
0x180490034  mov     [rsp+1A8h+lpString2], rax; lpString2
0x180490039  mov     r9d, esi; cchCount1
0x18049003c  mov     r8, rdi; lpString1
0x18049003f  mov     edx, r15d; dwCmpFlags
0x180490042  mov     ecx, r12d; Locale
0x180490045  call    cs:__imp_CompareStringW
0x18049004b  cmp     eax, 2
0x18049004e  jnz     short loc_180490064
0x180490050  movsd   xmm0, qword ptr [rsp+1A8h+pvarg+8]
0x180490056  cvtpd2ps xmm0, xmm0
0x18049005a  movss   dword ptr [rbx+0B8h], xmm0
0x180490062  jmp     short loc_1804900D1
0x180490064  mov     [rsp+1A8h+cchCount2], esi; cchCount2
0x180490068  lea     rax, aHighlightrecov; "HighlightRecoveryCaptureOneCompliant"
0x18049006f  mov     [rsp+1A8h+lpString2], rax; lpString2
0x180490074  mov     r9d, esi; cchCount1
0x180490077  mov     r8, rdi; lpString1
0x18049007a  mov     edx, r15d; dwCmpFlags
0x18049007d  mov     ecx, r12d; Locale
0x180490080  call    cs:__imp_CompareStringW
0x180490086  cmp     eax, 2
0x180490089  jnz     short loc_18049009F
0x18049008b  mov     eax, r14d
0x18049008e  cmp     word ptr [rsp+1A8h+pvarg+8], r14w
0x180490094  setnz   al
0x180490097  mov     [rbx+0C0h], eax
0x18049009d  jmp     short loc_1804900D1
0x18049009f  mov     [rsp+1A8h+cchCount2], esi; cchCount2
0x1804900a3  lea     rax, aUselocalexposu; "UseLocalExposure"
0x1804900aa  mov     [rsp+1A8h+lpString2], rax; lpString2
0x1804900af  mov     r9d, esi; cchCount1
0x1804900b2  mov     r8, rdi; lpString1
0x1804900b5  mov     edx, r15d; dwCmpFlags
0x1804900b8  mov     ecx, r12d; Locale
0x1804900bb  call    cs:__imp_CompareStringW
0x1804900c1  cmp     eax, 2
0x1804900c4  jnz     short loc_1804900D1
0x1804900c6  movsx   eax, word ptr [rsp+1A8h+pvarg+8]
0x1804900cb  mov     [rbx+10Ch], eax
0x1804900d1  xorps   xmm0, xmm0
0x1804900d4  xor     eax, eax
0x1804900d6  movups  xmmword ptr [rsp+1A8h+var_160], xmm0
0x1804900db  mov     qword ptr [rsp+1A8h+var_160+10h], rax
0x1804900e0  lea     rcx, [rsp+1A8h+var_160]; pvarg
0x1804900e5  call    cs:__imp_VariantInit
0x1804900eb  nop
0x1804900ec  mov     rcx, [rbx+80h]
0x1804900f3  mov     rax, [rcx]
0x1804900f6  lea     r8, [rsp+1A8h+var_160]
0x1804900fb  lea     rdx, aWhitebalance_0; "WhiteBalance"
0x180490102  mov     rax, [rax+60h]
0x180490106  call    cs:__guard_dispatch_icall_fptr
0x18049010c  mov     esi, 8007000Eh
0x180490111  cmp     eax, esi
0x180490113  jz      loc_1804905D9
0x180490119  mov     r15d, 86160210h
0x18049011f  cmp     eax, r15d
0x180490122  jz      loc_1804905D9
0x180490128  mov     r12d, 86170103h
0x18049012e  cmp     eax, r12d
0x180490131  jz      loc_1804905D9
0x180490137  cmp     eax, 86180110h
0x18049013c  jz      loc_1804905D9
0x180490142  test    eax, eax
0x180490144  js      loc_180490579
0x18049014a  cmp     [rbx+0C4h], r14d
0x180490151  jz      short loc_1804901D1
0x180490153  cmp     word ptr [rsp+1A8h+var_160], r14w
0x180490159  jz      short loc_1804901D1
0x18049015b  movups  xmm0, xmmword ptr [rsp+1A8h+var_160]
0x180490160  movaps  [rsp+1A8h+var_E8], xmm0
0x180490168  movsd   xmm1, qword ptr [rsp+1A8h+var_160+10h]
0x18049016e  movsd   [rsp+1A8h+var_D8], xmm1
0x180490177  lea     rdi, [rbx+0A4h]
0x18049017e  mov     r8d, 3
0x180490184  mov     rdx, rdi
0x180490187  lea     rcx, [rsp+1A8h+var_E8]
0x18049018f  call    ??$VARIANTToArray@M@@YAHUtagVARIANT@@PEAMH@Z; VARIANTToArray<float>(tagVARIANT,float *,int)
0x180490194  cmp     eax, 3
0x180490197  jnz     loc_180490580
0x18049019d  movss   xmm0, dword ptr [rdi]
0x1804901a1  xorps   xmm6, xmm6
0x1804901a4  comiss  xmm0, xmm6
0x1804901a7  jbe     loc_18049058A
0x1804901ad  movss   xmm0, dword ptr [rbx+0A8h]
0x1804901b5  comiss  xmm0, xmm6
0x1804901b8  jbe     loc_180490594
0x1804901be  movss   xmm0, dword ptr [rbx+0ACh]
0x1804901c6  comiss  xmm0, xmm6
0x1804901c9  jbe     loc_18049059E
0x1804901cf  jmp     short loc_1804901EB
0x1804901d1  mov     eax, 3F800000h
0x1804901d6  mov     [rbx+0A4h], eax
0x1804901dc  mov     [rbx+0A8h], eax
0x1804901e2  mov     [rbx+0ACh], eax
0x1804901e8  xorps   xmm6, xmm6
0x1804901eb  mov     [rsp+1A8h+ppsaOut], r14
0x1804901f3  mov     rdx, [rbx+98h]; psa
0x1804901fa  lea     rcx, [rsp+1A8h+ppsaOut]; ppsaOut
0x180490202  call    ?CopyFrom@?$CComSafeArray@M$03@ATL@@QEAAJPEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<float,4>::CopyFrom(tagSAFEARRAY const *)
0x180490207  test    eax, eax
0x180490209  js      loc_1804905A8
0x18049020f  lea     rdx, [rsp+1A8h+ppsaOut]
0x180490217  lea     rcx, [rsp+1A8h+var_B8]
0x18049021f  call    ?MatrixFromSafeArray9@ColorMatrix@@SA?BV1@V?$CComSafeArray@M$03@ATL@@@Z; ColorMatrix::MatrixFromSafeArray9(ATL::CComSafeArray<float,4>)
0x180490224  movaps  xmm0, cs:?kIdentity@ColorMatrix@@0V1@B; ColorMatrix const ColorMatrix::kIdentity
0x18049022b  movaps  [rsp+1A8h+var_128], xmm0
0x180490233  movaps  xmm1, cs:xmmword_1806A3250
0x18049023a  movaps  [rsp+1A8h+var_118], xmm1
0x180490242  movaps  xmm0, cs:xmmword_1806A3260
0x180490249  movaps  [rsp+1A8h+var_108], xmm0
0x180490251  movaps  xmm1, cs:xmmword_1806A3270
0x180490258  movaps  [rsp+1A8h+var_F8], xmm1
0x180490260  movss   xmm4, dword ptr [rbx+0A0h]
0x180490268  movss   xmm7, cs:__real@3f800000
0x180490270  movaps  xmm3, xmm7
0x180490273  subss   xmm3, xmm4
0x180490277  movaps  xmm2, xmm3
0x18049027a  mulss   xmm2, cs:__real@3e9e00d2
0x180490282  movaps  xmm0, xmm2
0x180490285  addss   xmm0, xmm4
0x180490289  movss   dword ptr [rsp+1A8h+var_128], xmm0
0x180490292  movaps  xmm1, xmm3
0x180490295  mulss   xmm1, cs:__real@3f1c01a3
0x18049029d  movss   dword ptr [rsp+1A8h+var_128+4], xmm1
0x1804902a6  mulss   xmm3, cs:__real@3da7ef9e
0x1804902ae  movss   dword ptr [rsp+1A8h+var_128+8], xmm3
0x1804902b7  movss   dword ptr [rsp+1A8h+var_118], xmm2
0x1804902c0  movaps  xmm0, xmm1
0x1804902c3  addss   xmm0, xmm4
0x1804902c7  movss   dword ptr [rsp+1A8h+var_118+4], xmm0
0x1804902d0  movss   dword ptr [rsp+1A8h+var_118+8], xmm3
0x1804902d9  movss   dword ptr [rsp+1A8h+var_108], xmm2
0x1804902e2  movss   dword ptr [rsp+1A8h+var_108+4], xmm1
0x1804902eb  addss   xmm3, xmm4
0x1804902ef  movss   dword ptr [rsp+1A8h+var_108+8], xmm3
0x1804902f8  movss   xmm1, dword ptr [rbx+0B4h]
0x180490300  addss   xmm1, dword ptr [rbx+0B0h]; Y
0x180490308  movss   xmm0, cs:__real@40000000; X
0x180490310  call    powf_0
0x180490315  mulss   xmm0, dword ptr [rbx+0B8h]
0x18049031d  movss   dword ptr [rbx+0BCh], xmm0
0x180490325  lea     rdi, [rbx+0CCh]
0x18049032c  lea     r8, [rsp+1A8h+var_B8]
0x180490334  lea     rdx, [rsp+1A8h+var_78]
0x18049033c  lea     rcx, [rsp+1A8h+var_128]
0x180490344  call    ??DColorMatrix@@QEBA?AV0@AEBV0@@Z; ColorMatrix::operator*(ColorMatrix const &)
0x180490349  movups  xmm0, xmmword ptr [rax]
0x18049034c  movups  xmmword ptr [rdi], xmm0
0x18049034f  movups  xmm1, xmmword ptr [rax+10h]
0x180490353  movups  xmmword ptr [rdi+10h], xmm1
0x180490357  movups  xmm0, xmmword ptr [rax+20h]
0x18049035b  movups  xmmword ptr [rdi+20h], xmm0
0x18049035f  movups  xmm1, xmmword ptr [rax+30h]
0x180490363  movups  xmmword ptr [rdi+30h], xmm1
0x180490367  xorps   xmm0, xmm0
0x18049036a  xor     eax, eax
0x18049036c  movups  xmmword ptr [rsp+1A8h+var_148], xmm0
0x180490371  mov     qword ptr [rsp+1A8h+var_148+10h], rax
0x180490376  lea     rcx, [rsp+1A8h+var_148]; pvarg
0x18049037b  call    cs:__imp_VariantInit
0x180490381  nop
0x180490382  mov     rcx, [rbx+80h]
0x180490389  mov     rax, [rcx]
0x18049038c  lea     r8, [rsp+1A8h+var_148]
0x180490391  lea     rdx, aInvert; "Invert"
0x180490398  mov     rax, [rax+60h]
0x18049039c  call    cs:__guard_dispatch_icall_fptr
0x1804903a2  cmp     eax, esi
0x1804903a4  jz      loc_1804905CE
0x1804903aa  cmp     eax, r15d
0x1804903ad  jz      loc_1804905CE
0x1804903b3  cmp     eax, r12d
0x1804903b6  jz      loc_1804905CE
0x1804903bc  cmp     eax, 86180110h
0x1804903c1  jz      loc_1804905CE
0x1804903c7  test    eax, eax
0x1804903c9  js      loc_1804905B3
0x1804903cf  cmp     word ptr [rsp+1A8h+var_148], 0Bh
0x1804903d5  jnz     loc_1804904AB
0x1804903db  cmp     word ptr [rsp+1A8h+var_148+8], r14w
0x1804903e1  jz      loc_1804904AB
0x1804903e7  movss   xmm0, dword ptr [rbx+0BCh]
0x1804903ef  comiss  xmm0, xmm6
  ... truncated ...
```
