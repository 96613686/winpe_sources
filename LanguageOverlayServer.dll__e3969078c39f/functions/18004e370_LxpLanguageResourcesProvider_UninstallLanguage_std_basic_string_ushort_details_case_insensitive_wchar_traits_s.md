# LxpLanguageResourcesProvider::UninstallLanguage(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)

- ea: `0x18004e370`
- end: `0x18004e85f`
- name: `?UninstallLanguage@LxpLanguageResourcesProvider@@UEBAJAEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@Z`
- size: `1263`
- prototype: `__int64 __fastcall(LxpLanguageResourcesProvider *this, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003a00`
- `0x1800044b8`
- `0x180004a44`
- `0x180012a98`
- `0x180014ca0`
- `0x180015a00`
- `0x180016e1c`
- `0x18003771c`
- `0x18004b0bc`
- `0x18004d4cc`
- `0x18004dc3c`
- `0x18004e370`
- `0x18004f528`
- `0x1800610ec`
- `0x180062f00`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e54b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e5c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e54b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e5c6`
- `ext-ms-win-resources-languageoverlay-l1-1-0!GetLanguageOverlayPackageFamilyName` at `0x18004e515`
- `ext-ms-win-resources-languageoverlay-l1-1-0!GetLanguageOverlayPackageFamilyName` at `0x18004e515`

## string_xrefs

- `0x18004e3ca`: `UninstallLxpActivity`
- `0x18004e79e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004e7b5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004e7d2`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004e7ef`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004e804`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004e818`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004e82d`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004e841`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall LxpLanguageResourcesProvider::UninstallLanguage(LxpLanguageResourcesProvider *this, __int64 a2)
{
  void **v2; // rbx
  const unsigned __int16 *v4; // rdi
  void *v5; // rax
  int LanguageOverlayPackageFamilyName; // eax
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int v10; // eax
  unsigned int v11; // r8d
  wil::details::in1diag3 *v12; // rcx
  unsigned __int64 v13; // rdx
  struct Windows::Management::Deployment::IPackageManager *v14; // rbx
  __int64 v15; // rdi
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  int v19; // eax
  wil::details::in1diag3 *v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  PVOID Reserved1; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  struct Windows::Management::Deployment::IPackageManager *v28; // rcx
  const char *v29; // r9
  __int64 result; // rax
  int v31; // [rsp+20h] [rbp-258h]
  _BYTE v32[8]; // [rsp+30h] [rbp-248h] BYREF
  __int64 v33; // [rsp+38h] [rbp-240h] BYREF
  struct Windows::Management::Deployment::IPackageManager *v34; // [rsp+40h] [rbp-238h] BYREF
  __int64 v35; // [rsp+48h] [rbp-230h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-228h] BYREF
  HSTRING string; // [rsp+68h] [rbp-210h] BYREF
  void **v38; // [rsp+70h] [rbp-208h] BYREF
  int v39; // [rsp+78h] [rbp-200h] BYREF
  char v40; // [rsp+7Ch] [rbp-1FCh]
  int v41; // [rsp+A0h] [rbp-1D8h] BYREF
  const char *v42; // [rsp+A8h] [rbp-1D0h]
  __int64 v43; // [rsp+B0h] [rbp-1C8h]
  char v44; // [rsp+B8h] [rbp-1C0h]
  int v45; // [rsp+C0h] [rbp-1B8h]
  _BYTE v46[152]; // [rsp+C8h] [rbp-1B0h] BYREF
  __int128 v47; // [rsp+160h] [rbp-118h]
  int v48; // [rsp+170h] [rbp-108h]
  __int64 v49; // [rsp+178h] [rbp-100h]
  int *v50; // [rsp+180h] [rbp-F8h]
  __int64 v51; // [rsp+188h] [rbp-F0h]
  __int64 v52; // [rsp+190h] [rbp-E8h]
  void ***v53; // [rsp+198h] [rbp-E0h]
  __int64 v54; // [rsp+1A0h] [rbp-D8h]
  int v55; // [rsp+1A8h] [rbp-D0h]
  int *v56; // [rsp+1B0h] [rbp-C8h]
  char v57; // [rsp+1B8h] [rbp-C0h]
  WCHAR sourceString[72]; // [rsp+1C0h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v2 = (void **)a2;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v4 = (const unsigned __int16 *)a2;
  else
    v4 = *(const unsigned __int16 **)a2;
  v39 = 0;
  v40 = 0;
  v44 = 0;
  v41 = 0;
  v42 = "UninstallLxpActivity";
  v43 = 0;
  v45 = 0;
  v47 = 0;
  memset_0(v46, 0, sizeof(v46));
  v48 = 1;
  v49 = 0;
  v50 = &v39;
  v51 = 0;
  v52 = 0;
  v53 = &v38;
  v54 = 0;
  v55 = 0;
  v56 = &v41;
  v57 = 0;
  v38 = &LanguageOverlayTraceProvider::UninstallLxpActivity::`vftable';
  try
  {
    LanguageOverlayTraceProvider::UninstallLxpActivity::StartActivity(
      (LanguageOverlayTraceProvider::UninstallLxpActivity *)&v38,
      v4);
    if ( (unsigned __int64)v2[3] <= 7 )
      v5 = v2;
    else
      v5 = *v2;
    hstringHeader.Reserved.Reserved1 = v5;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v2[2];
    if ( !(unsigned __int8)bcp47::IsMuiForm(&hstringHeader) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !IsValidUserContext() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !(unsigned __int8)IsGetLanguageOverlayPackageFamilyNamePresent() )
      goto LABEL_40;
    memset_0(sourceString, 0, 0x82u);
    if ( (unsigned __int64)v2[3] > 7 )
      v2 = (void **)*v2;
    LanguageOverlayPackageFamilyName = GetLanguageOverlayPackageFamilyName(v2, &qword_180070100, sourceString, 64);
    if ( LanguageOverlayPackageFamilyName < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19B,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
        (const char *)(unsigned int)LanguageOverlayPackageFamilyName,
        v31);
    v34 = 0;
    string = 0;
    v7 = WindowsCreateStringReference(L"Windows.Management.Deployment.PackageManager", 0x2Cu, &hstringHeader, &string);
    if ( v7 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    }
    else
    {
      v10 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
              string,
              &v34);
      v12 = retaddr;
      if ( v10 >= 0 )
      {
        v35 = 0;
        v13 = -1;
        do
          ++v13;
        while ( sourceString[v13] );
        if ( v13 <= 0xFFFFFFFF )
        {
          if ( (int)v13 + 1 < (unsigned int)v13 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v13, v11);
            JUMPOUT(0x18004E85DLL);
          }
          v14 = v34;
          v15 = *(_QWORD *)v34;
          v16 = WindowsCreateStringReference(sourceString, v13, &hstringHeader, &string);
          if ( v16 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
          }
          else
          {
            v19 = (*(__int64 (__fastcall **)(struct Windows::Management::Deployment::IPackageManager *, _QWORD, HSTRING, __int64 *))(v15 + 160))(
                    v14,
                    0,
                    string,
                    &v35);
            v20 = retaddr;
            if ( v19 >= 0 )
            {
              v33 = 0;
              v32[0] = 0;
              v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 48LL))(v35, &v33);
              if ( v21 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1AA,
                  (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
                  (const char *)(unsigned int)v21,
                  v31);
              v22 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v33 + 56LL))(v33, v32);
              if ( v22 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1AB,
                  (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
                  (const char *)(unsigned int)v22,
                  v31);
              while ( v32[0] )
              {
                hstringHeader.Reserved.Reserved1 = 0;
                v23 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v33 + 48LL))(
                        v33,
                        &hstringHeader);
                if ( v23 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1AF,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguagereso"
                                  "urcesprovider.cpp",
                    (const char *)(unsigned int)v23,
                    v31);
                LxpLanguageResourcesProvider::_UninstallPackage(
                  this,
                  v34,
                  (struct Windows::ApplicationModel::IPackage *)hstringHeader.Reserved.Reserved1);
                v24 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v33 + 64LL))(v33, v32);
                if ( v24 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1B1,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguagereso"
                                  "urcesprovider.cpp",
                    (const char *)(unsigned int)v24,
                    v31);
                Reserved1 = hstringHeader.Reserved.Reserved1;
                if ( hstringHeader.Reserved.Reserved1 )
                {
                  hstringHeader.Reserved.Reserved1 = 0;
                  (*(void (__fastcall **)(PVOID))(*(_QWORD *)Reserved1 + 16LL))(Reserved1);
                }
              }
              wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v38);
              v26 = v33;
              if ( v33 )
              {
                v33 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              }
              v27 = v35;
              if ( v35 )
              {
                v35 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
              }
              v28 = v34;
              if ( v34 )
              {
                v34 = 0;
                (*(void (__fastcall **)(struct Windows::Management::Deployment::IPackageManager *))(*(_QWORD *)v28 + 16LL))(v28);
              }
              v38 = &LanguageOverlayTraceProvider::UninstallLxpActivity::`vftable';
              wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v38);
              wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v38);
              return 0;
            }
          }
          wil::details::in1diag3::Throw_Hr(
            v20,
            (void *)0x1A6,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
            (const char *)(unsigned int)v19,
            v31);
        }
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v13, v11);
LABEL_40:
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x195,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
          (const char *)0x80004001LL,
          v31);
      }
    }
    wil::details::in1diag3::Throw_Hr(
      v12,
      (void *)0x1A0,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v10,
      v31);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1B6,
                           (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplangu"
                                         "ageresourcesprovider.cpp",
                           v29);
  }
  return result;
}

```

## disassembly

```asm
0x18004e370  mov     [rsp+arg_10], rbx
0x18004e375  mov     [rsp+arg_18], rsi
0x18004e37a  push    rdi
0x18004e37b  push    r14
0x18004e37d  push    r15
0x18004e37f  sub     rsp, 260h
0x18004e386  mov     rax, cs:__security_cookie
0x18004e38d  xor     rax, rsp
0x18004e390  mov     [rsp+278h+var_28], rax
0x18004e398  mov     rbx, rdx
0x18004e39b  mov     rsi, rcx
0x18004e39e  cmp     qword ptr [rdx+18h], 7
0x18004e3a3  jbe     short loc_18004E3AA
0x18004e3a5  mov     rdi, [rdx]
0x18004e3a8  jmp     short loc_18004E3AD
0x18004e3aa  mov     rdi, rbx
0x18004e3ad  xor     r14d, r14d
0x18004e3b0  mov     [rsp+278h+var_200], r14d
0x18004e3b5  mov     [rsp+278h+var_1FC], r14b
0x18004e3ba  mov     [rsp+278h+var_1C0], r14b
0x18004e3c2  mov     [rsp+278h+var_1D8], r14d
0x18004e3ca  lea     rax, aUninstalllxpac; "UninstallLxpActivity"
0x18004e3d1  mov     [rsp+278h+var_1D0], rax
0x18004e3d9  mov     [rsp+278h+var_1C8], r14
0x18004e3e1  mov     [rsp+278h+var_1B8], r14d
0x18004e3e9  xorps   xmm0, xmm0
0x18004e3ec  movdqa  [rsp+278h+var_118], xmm0
0x18004e3f5  xor     edx, edx; Val
0x18004e3f7  mov     r8d, 98h; Size
0x18004e3fd  lea     rcx, [rsp+278h+var_1B0]; void *
0x18004e405  call    memset_0
0x18004e40a  mov     [rsp+278h+var_108], 1
0x18004e415  xor     eax, eax
0x18004e417  mov     [rsp+278h+var_100], rax
0x18004e41f  lea     rax, [rsp+278h+var_200]
0x18004e424  mov     [rsp+278h+var_F8], rax
0x18004e42c  mov     [rsp+278h+var_F0], r14
0x18004e434  mov     [rsp+278h+var_E8], r14
0x18004e43c  lea     rax, [rsp+278h+var_208]
0x18004e441  mov     [rsp+278h+var_E0], rax
0x18004e449  mov     [rsp+278h+var_D8], r14
0x18004e451  mov     [rsp+278h+var_D0], r14d
0x18004e459  lea     rax, [rsp+278h+var_1D8]
0x18004e461  mov     [rsp+278h+var_C8], rax
0x18004e469  mov     [rsp+278h+var_C0], r14b
0x18004e471  lea     r15, ??_7UninstallLxpActivity@LanguageOverlayTraceProvider@@6B@; const LanguageOverlayTraceProvider::UninstallLxpActivity::`vftable'
0x18004e478  mov     [rsp+278h+var_208], r15
0x18004e47d  mov     rdx, rdi; unsigned __int16 *
0x18004e480  lea     rcx, [rsp+278h+var_208]; this
0x18004e485  call    ?StartActivity@UninstallLxpActivity@LanguageOverlayTraceProvider@@QEAAXPEBG@Z; LanguageOverlayTraceProvider::UninstallLxpActivity::StartActivity(ushort const *)
0x18004e48a  nop
0x18004e48b  cmp     qword ptr [rbx+18h], 7
0x18004e490  jbe     short loc_18004E497
0x18004e492  mov     rax, [rbx]
0x18004e495  jmp     short loc_18004E49A
0x18004e497  mov     rax, rbx
0x18004e49a  mov     qword ptr [rsp+278h+hstringHeader.Reserved], rax
0x18004e49f  mov     rax, [rbx+10h]
0x18004e4a3  mov     qword ptr [rsp+278h+hstringHeader.Reserved+8], rax
0x18004e4a8  lea     rcx, [rsp+278h+hstringHeader]
0x18004e4ad  call    ?IsMuiForm@bcp47@@YA_NAEBV?$basic_string_view@GUcase_insensitive_wchar_traits@details@@@std@@@Z; bcp47::IsMuiForm(std::basic_string_view<ushort,details::case_insensitive_wchar_traits> const &)
0x18004e4b2  test    al, al
0x18004e4b4  jnz     short loc_18004E4BB
0x18004e4b6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004e4bb  call    ?IsValidUserContext@@YA_NXZ; IsValidUserContext(void)
0x18004e4c0  test    al, al
0x18004e4c2  jnz     short loc_18004E4C9
0x18004e4c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004e4c9  mov     rdi, [rsp+278h]
0x18004e4d1  call    IsGetLanguageOverlayPackageFamilyNamePresent
0x18004e4d6  test    al, al
0x18004e4d8  jz      loc_18004E798
0x18004e4de  xor     edx, edx; Val
0x18004e4e0  mov     r8d, 82h; Size
0x18004e4e6  lea     rcx, [rsp+278h+sourceString]; void *
0x18004e4ee  call    memset_0
0x18004e4f3  cmp     qword ptr [rbx+18h], 7
0x18004e4f8  jbe     short loc_18004E4FD
0x18004e4fa  mov     rbx, [rbx]
0x18004e4fd  mov     r9d, 40h ; '@'
0x18004e503  lea     r8, [rsp+278h+sourceString]
0x18004e50b  lea     rdx, qword_180070100
0x18004e512  mov     rcx, rbx
0x18004e515  call    cs:__imp_GetLanguageOverlayPackageFamilyName
0x18004e51b  mov     rcx, [rsp+278h]; this
0x18004e523  test    eax, eax
0x18004e525  js      loc_18004E7B2
0x18004e52b  mov     [rsp+278h+var_238], r14
0x18004e530  mov     [rsp+278h+string], r14
0x18004e535  lea     r9, [rsp+278h+string]; string
0x18004e53a  lea     r8, [rsp+278h+hstringHeader]; hstringHeader
0x18004e53f  mov     edx, 2Ch ; ','; length
0x18004e544  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x18004e54b  call    cs:__imp_WindowsCreateStringReference
0x18004e551  test    eax, eax
0x18004e553  js      loc_18004E7C7
0x18004e559  lea     rdx, [rsp+278h+var_238]
0x18004e55e  mov     rcx, [rsp+278h+string]
0x18004e563  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x18004e568  mov     rcx, [rsp+278h]
0x18004e570  test    eax, eax
0x18004e572  js      loc_18004E7CF
0x18004e578  mov     [rsp+278h+var_230], r14
0x18004e57d  lea     rax, [rsp+278h+sourceString]
0x18004e585  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004e589  inc     rdx; int
0x18004e58c  cmp     [rax+rdx*2], r14w
0x18004e591  jnz     short loc_18004E589
0x18004e593  mov     eax, 0FFFFFFFFh
0x18004e598  cmp     rdx, rax
0x18004e59b  ja      loc_18004E78D
0x18004e5a1  lea     eax, [rdx+1]
0x18004e5a4  cmp     eax, edx
0x18004e5a6  jb      loc_18004E853
0x18004e5ac  mov     rbx, [rsp+278h+var_238]
0x18004e5b1  mov     rdi, [rbx]
0x18004e5b4  lea     r9, [rsp+278h+string]; string
0x18004e5b9  lea     r8, [rsp+278h+hstringHeader]; hstringHeader
0x18004e5be  lea     rcx, [rsp+278h+sourceString]; sourceString
0x18004e5c6  call    cs:__imp_WindowsCreateStringReference
0x18004e5cc  test    eax, eax
0x18004e5ce  js      loc_18004E7E4
0x18004e5d4  lea     r9, [rsp+278h+var_230]
0x18004e5d9  mov     r8, [rsp+278h+string]
0x18004e5de  xor     edx, edx
0x18004e5e0  mov     rcx, rbx
0x18004e5e3  mov     rax, [rdi+0A0h]
0x18004e5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5ef  mov     rcx, [rsp+278h]
0x18004e5f7  test    eax, eax
0x18004e5f9  js      loc_18004E7EC
0x18004e5ff  mov     [rsp+278h+var_240], r14
0x18004e604  mov     [rsp+278h+var_248], r14b
0x18004e609  mov     rcx, [rsp+278h+var_230]
0x18004e60e  mov     rax, [rcx]
0x18004e611  lea     rdx, [rsp+278h+var_240]
0x18004e616  mov     rax, [rax+30h]
0x18004e61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e61f  mov     rcx, [rsp+278h]; this
0x18004e627  test    eax, eax
0x18004e629  js      loc_18004E801
0x18004e62f  mov     rcx, [rsp+278h+var_240]
0x18004e634  mov     rax, [rcx]
0x18004e637  lea     rdx, [rsp+278h+var_248]
0x18004e63c  mov     rax, [rax+38h]
0x18004e640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e645  mov     rcx, [rsp+278h]; this
0x18004e64d  test    eax, eax
0x18004e64f  js      loc_18004E815
0x18004e655  cmp     [rsp+278h+var_248], r14b
0x18004e65a  jz      loc_18004E6E4
0x18004e660  mov     qword ptr [rsp+278h+hstringHeader.Reserved], r14
0x18004e665  mov     rcx, [rsp+278h+var_240]
0x18004e66a  mov     rax, [rcx]
0x18004e66d  lea     rdx, [rsp+278h+hstringHeader]
0x18004e672  mov     rax, [rax+30h]
0x18004e676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e67b  mov     rcx, [rsp+278h]; this
0x18004e683  test    eax, eax
0x18004e685  js      loc_18004E82A
0x18004e68b  mov     r8, qword ptr [rsp+278h+hstringHeader.Reserved]; struct Windows::ApplicationModel::IPackage *
0x18004e690  mov     rdx, [rsp+278h+var_238]; struct Windows::Management::Deployment::IPackageManager *
0x18004e695  mov     rcx, rsi; this
0x18004e698  call    ?_UninstallPackage@LxpLanguageResourcesProvider@@AEBAXPEAUIPackageManager@Deployment@Management@Windows@@PEAUIPackage@ApplicationModel@5@@Z; LxpLanguageResourcesProvider::_UninstallPackage(Windows::Management::Deployment::IPackageManager *,Windows::ApplicationModel::IPackage *)
0x18004e69d  mov     rcx, [rsp+278h+var_240]
0x18004e6a2  mov     rax, [rcx]
0x18004e6a5  lea     rdx, [rsp+278h+var_248]
0x18004e6aa  mov     rax, [rax+40h]
0x18004e6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6b3  mov     rcx, [rsp+278h]; this
0x18004e6bb  test    eax, eax
0x18004e6bd  js      loc_18004E83E
0x18004e6c3  mov     rcx, qword ptr [rsp+278h+hstringHeader.Reserved]
0x18004e6c8  test    rcx, rcx
0x18004e6cb  jz      short loc_18004E6DF
0x18004e6cd  mov     qword ptr [rsp+278h+hstringHeader.Reserved], r14
0x18004e6d2  mov     rax, [rcx]
0x18004e6d5  mov     rax, [rax+10h]
0x18004e6d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6de  nop
0x18004e6df  jmp     loc_18004E655
0x18004e6e4  lea     rcx, [rsp+278h+var_208]
0x18004e6e9  call    ?Stop@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004e6ee  nop
0x18004e6ef  mov     rcx, [rsp+278h+var_240]
0x18004e6f4  test    rcx, rcx
0x18004e6f7  jz      short loc_18004E70B
0x18004e6f9  mov     [rsp+278h+var_240], r14
0x18004e6fe  mov     rax, [rcx]
0x18004e701  mov     rax, [rax+10h]
0x18004e705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e70a  nop
0x18004e70b  mov     rcx, [rsp+278h+var_230]
0x18004e710  test    rcx, rcx
0x18004e713  jz      short loc_18004E727
0x18004e715  mov     [rsp+278h+var_230], r14
0x18004e71a  mov     rax, [rcx]
0x18004e71d  mov     rax, [rax+10h]
0x18004e721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e726  nop
0x18004e727  mov     rcx, [rsp+278h+var_238]
0x18004e72c  test    rcx, rcx
0x18004e72f  jz      short loc_18004E743
0x18004e731  mov     [rsp+278h+var_238], r14
0x18004e736  mov     rax, [rcx]
0x18004e739  mov     rax, [rax+10h]
0x18004e73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e742  nop
0x18004e743  mov     [rsp+278h+var_208], r15
0x18004e748  lea     rcx, [rsp+278h+var_208]
0x18004e74d  call    ?Destroy@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18004e752  lea     rcx, [rsp+278h+var_208]
0x18004e757  call    ??1?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18004e75c  xor     eax, eax
0x18004e75e  jmp     short loc_18004E764
0x18004e760  mov     eax, dword ptr [rsp+278h+var_240]
0x18004e764  mov     rcx, [rsp+278h+var_28]
0x18004e76c  xor     rcx, rsp; StackCookie
0x18004e76f  call    __security_check_cookie
0x18004e774  lea     r11, [rsp+278h+var_18]
0x18004e77c  mov     rbx, [r11+30h]
0x18004e780  mov     rsi, [r11+38h]
0x18004e784  mov     rsp, r11
0x18004e787  pop     r15
0x18004e789  pop     r14
0x18004e78b  pop     rdi
0x18004e78c  retn
0x18004e78d  mov     ecx, 80070216h; this
0x18004e792  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004e797  nop
0x18004e798  mov     r9d, 80004001h; char *
0x18004e79e  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004e7a5  mov     edx, 195h; void *
0x18004e7aa  mov     rcx, rdi; this
0x18004e7ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e7b2  mov     r9d, eax; char *
0x18004e7b5  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004e7bc  mov     edx, 19Bh; void *
0x18004e7c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e7c7  mov     ecx, eax; this
0x18004e7c9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004e7ce  nop
0x18004e7cf  mov     r9d, eax; char *
0x18004e7d2  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004e7d9  mov     edx, 1A0h; void *
0x18004e7de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e7e4  mov     ecx, eax; this
0x18004e7e6  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004e7eb  nop
0x18004e7ec  mov     r9d, eax; char *
0x18004e7ef  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004e7f6  mov     edx, 1A6h; void *
0x18004e7fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e801  mov     r9d, eax; char *
0x18004e804  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004e80b  mov     edx, 1AAh; void *
0x18004e810  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e815  mov     r9d, eax; char *
0x18004e818  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004e81f  mov     edx, 1ABh; void *
0x18004e824  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e82a  mov     r9d, eax; char *
0x18004e82d  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004e834  mov     edx, 1AFh; void *
0x18004e839  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e83e  mov     r9d, eax; char *
0x18004e841  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004e848  mov     edx, 1B1h; void *
0x18004e84d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e853  mov     ecx, 80070216h; this
0x18004e858  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
