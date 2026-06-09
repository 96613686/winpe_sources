# DllRegisterServer

- ea: `0x1800556b0`
- end: `0x18005585a`
- name: `DllRegisterServer`
- size: `426`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180031298`
- `0x18004d320`
- `0x1800556b0`
- `0x180056220`

## import_xrefs

- `MFPlat!MFTRegister` at `0x1800557ac`
- `MFPlat!MFTRegister` at `0x18005581c`
- `MFPlat!MFTRegister` at `0x1800557ac`
- `MFPlat!MFTRegister` at `0x18005581c`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  int v0; // ebx
  GUID guidCategory; // [rsp+50h] [rbp-B0h] BYREF
  CLSID clsidMFT; // [rsp+60h] [rbp-A0h] BYREF
  MFT_REGISTER_TYPE_INFO pInputTypes; // [rsp+70h] [rbp-90h] BYREF
  MFT_REGISTER_TYPE_INFO pOutputTypes; // [rsp+90h] [rbp-70h] BYREF
  GUID v6; // [rsp+B0h] [rbp-50h]
  GUID v7; // [rsp+C0h] [rbp-40h]
  MFT_REGISTER_TYPE_INFO v8; // [rsp+D0h] [rbp-30h] BYREF
  GUID v9; // [rsp+F0h] [rbp-10h]
  GUID v10; // [rsp+100h] [rbp+0h]
  MFT_REGISTER_TYPE_INFO v11; // [rsp+110h] [rbp+10h] BYREF
  GUID v12; // [rsp+130h] [rbp+30h]
  __int128 v13; // [rsp+140h] [rbp+40h]
  GUID v14; // [rsp+150h] [rbp+50h]
  GUID v15; // [rsp+160h] [rbp+60h]

  pInputTypes.guidSubtype = MFAudioFormat_MPEG;
  v7 = MEDIASUBTYPE_PCM;
  v11.guidSubtype = MFAudioFormat_AAC;
  v10 = MEDIASUBTYPE_PCM;
  v13 = MEDIASUBTYPE_RAW_AAC1;
  pOutputTypes.guidMajorType = MFMediaType_Audio;
  v15 = MFAudioFormat_ADTS;
  pOutputTypes.guidSubtype = MFAudioFormat_Float;
  clsidMFT = CLSID_CMSMPEGAudDecMFT;
  v6 = MFMediaType_Audio;
  pInputTypes.guidMajorType = MFMediaType_Audio;
  v8.guidMajorType = MFMediaType_Audio;
  v8.guidSubtype = MFAudioFormat_Float;
  v9 = MFMediaType_Audio;
  v11.guidMajorType = MFMediaType_Audio;
  v12 = MFMediaType_Audio;
  v14 = MFMediaType_Audio;
  guidCategory = MFT_CATEGORY_AUDIO_DECODER;
  v0 = MFTRegister(
         &clsidMFT,
         &guidCategory,
         (LPWSTR)L"Microsoft MPEG Audio Decoder MFT",
         0,
         1u,
         &pInputTypes,
         2u,
         &pOutputTypes,
         0);
  if ( (unsigned int)IsLicensedComponentAAC_Internal() )
  {
    clsidMFT = MFT_CATEGORY_AUDIO_DECODER;
    guidCategory = CLSID_CMSAACDecMFT;
    v0 = MFTRegister(&guidCategory, &clsidMFT, (LPWSTR)L"Microsoft AAC Audio Decoder MFT", 0, 3u, &v11, 2u, &v8, 0);
  }
  if ( v0 >= 0 )
    return AMovieDllRegisterServer2(1u);
  return v0;
}

```

## disassembly

```asm
0x1800556b0  mov     [rsp-8+arg_0], rbx
0x1800556b5  push    rbp
0x1800556b6  lea     rbp, [rsp-80h]
0x1800556bb  sub     rsp, 180h
0x1800556c2  mov     rax, cs:__security_cookie
0x1800556c9  xor     rax, rsp
0x1800556cc  mov     [rbp+80h+var_10], rax
0x1800556d0  movups  xmm3, xmmword ptr cs:MFMediaType_Audio.Data1
0x1800556d7  mov     [rsp+180h+pAttributes], 0; pAttributes
0x1800556e0  lea     rax, [rbp+80h+var_F0]
0x1800556e4  movups  xmm1, xmmword ptr cs:MEDIASUBTYPE_PCM.Data1
0x1800556eb  mov     [rsp+180h+pOutputTypes], rax; pOutputTypes
0x1800556f0  lea     rax, [rsp+180h+var_110]
0x1800556f5  movups  xmm0, xmmword ptr cs:MFAudioFormat_MPEG.Data1
0x1800556fc  mov     [rsp+180h+cOutputTypes], 2; cOutputTypes
0x180055704  xor     r9d, r9d; Flags
0x180055707  movups  xmm2, xmmword ptr cs:MFAudioFormat_Float.Data1
0x18005570e  mov     [rsp+180h+pInputTypes], rax; pInputTypes
0x180055713  lea     r8, pszName; "Microsoft MPEG Audio Decoder MFT"
0x18005571a  movdqu  xmmword ptr [rbp+80h+var_110.guidSubtype.Data1], xmm0
0x18005571f  lea     rdx, [rsp+180h+guidCategory]; guidCategory
0x180055724  mov     [rsp+180h+cInputTypes], 1; cInputTypes
0x18005572c  movups  xmm0, xmmword ptr cs:MFAudioFormat_AAC.Data1
0x180055733  lea     rcx, [rsp+180h+clsidMFT]; clsidMFT
0x180055738  movdqu  [rbp+80h+var_C0], xmm1
0x18005573d  movdqu  xmmword ptr [rbp+80h+var_70.guidSubtype.Data1], xmm0
0x180055742  movups  xmm0, cs:MEDIASUBTYPE_RAW_AAC1
0x180055749  movdqu  [rbp+80h+var_80], xmm1
0x18005574e  movups  xmm1, xmmword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data1
0x180055755  movdqu  [rbp+80h+var_40], xmm0
0x18005575a  movups  xmm0, xmmword ptr cs:MFAudioFormat_ADTS.Data1
0x180055761  movdqu  xmmword ptr [rbp+80h+var_F0.guidMajorType.Data1], xmm3
0x180055766  movdqu  [rbp+80h+var_20], xmm0
0x18005576b  movups  xmm0, xmmword ptr cs:CLSID_CMSMPEGAudDecMFT.Data1
0x180055772  movdqu  xmmword ptr [rbp+80h+var_F0.guidSubtype.Data1], xmm2
0x180055777  movdqu  xmmword ptr [rsp+180h+clsidMFT.Data1], xmm0
0x18005577d  movdqu  [rbp+80h+var_D0], xmm3
0x180055782  movdqu  xmmword ptr [rsp+180h+var_110.guidMajorType.Data1], xmm3
0x180055788  movdqu  xmmword ptr [rbp+80h+var_B0.guidMajorType.Data1], xmm3
0x18005578d  movdqu  xmmword ptr [rbp+80h+var_B0.guidSubtype.Data1], xmm2
0x180055792  movdqu  [rbp+80h+var_90], xmm3
0x180055797  movdqu  xmmword ptr [rbp+80h+var_70.guidMajorType.Data1], xmm3
0x18005579c  movdqu  [rbp+80h+var_50], xmm3
0x1800557a1  movdqu  [rbp+80h+var_30], xmm3
0x1800557a6  movdqu  xmmword ptr [rsp+180h+guidCategory.Data1], xmm1
0x1800557ac  call    cs:__imp_MFTRegister
0x1800557b3  nop     dword ptr [rax+rax+00h]
0x1800557b8  mov     ebx, eax
0x1800557ba  call    ?IsLicensedComponentAAC_Internal@@YAHXZ; IsLicensedComponentAAC_Internal(void)
0x1800557bf  test    eax, eax
0x1800557c1  jz      short loc_18005582A
0x1800557c3  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data1
0x1800557ca  mov     [rsp+180h+pAttributes], 0; pAttributes
0x1800557d3  lea     rax, [rbp+80h+var_B0]
0x1800557d7  movups  xmm1, xmmword ptr cs:CLSID_CMSAACDecMFT.Data1
0x1800557de  mov     [rsp+180h+pOutputTypes], rax; pOutputTypes
0x1800557e3  lea     r8, aMicrosoftAacAu_0; "Microsoft AAC Audio Decoder MFT"
0x1800557ea  lea     rax, [rbp+80h+var_70]
0x1800557ee  mov     [rsp+180h+cOutputTypes], 2; cOutputTypes
0x1800557f6  mov     [rsp+180h+pInputTypes], rax; pInputTypes
0x1800557fb  lea     rdx, [rsp+180h+clsidMFT]; guidCategory
0x180055800  xor     r9d, r9d; Flags
0x180055803  mov     [rsp+180h+cInputTypes], 3; cInputTypes
0x18005580b  lea     rcx, [rsp+180h+guidCategory]; clsidMFT
0x180055810  movdqu  xmmword ptr [rsp+180h+clsidMFT.Data1], xmm0
0x180055816  movdqu  xmmword ptr [rsp+180h+guidCategory.Data1], xmm1
0x18005581c  call    cs:__imp_MFTRegister
0x180055823  nop     dword ptr [rax+rax+00h]
0x180055828  mov     ebx, eax
0x18005582a  test    ebx, ebx
0x18005582c  js      short loc_18005583A
0x18005582e  mov     ecx, 1
0x180055833  call    AMovieDllRegisterServer2
0x180055838  mov     ebx, eax
0x18005583a  mov     eax, ebx
0x18005583c  mov     rcx, [rbp+80h+var_10]
0x180055840  xor     rcx, rsp; StackCookie
0x180055843  call    __security_check_cookie
0x180055848  mov     rbx, [rsp+180h+arg_0]
0x180055850  add     rsp, 180h
0x180055857  pop     rbp
0x180055858  retn
```
