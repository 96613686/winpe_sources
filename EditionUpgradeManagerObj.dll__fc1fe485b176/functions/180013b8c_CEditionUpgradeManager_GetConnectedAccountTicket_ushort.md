# CEditionUpgradeManager::GetConnectedAccountTicket(ushort * *)

- ea: `0x180013b8c`
- end: `0x1800142ef`
- name: `?GetConnectedAccountTicket@CEditionUpgradeManager@@AEAAJPEAPEAG@Z`
- size: `1891`
- prototype: `__int64 __fastcall(CEditionUpgradeManager *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800117b0`

## callees

- `0x180001ac0`
- `0x1800026b4`
- `0x180007970`
- `0x1800090dc`
- `0x180009480`
- `0x18000974c`
- `0x18000d10c`
- `0x18000e78c`
- `0x18000ea14`
- `0x180012238`
- `0x180013a10`
- `0x180013b8c`
- `0x1800228f0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013da8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013ea9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013da8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013ea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013c35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013d8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013dda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013e04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013e8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013f53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001406b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013d8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013dda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013e04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013e8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013f53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001406b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014095`

## string_xrefs

- `0x180013e85`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x180013d84`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x180013ec5`: `www.microsoft.com`
- `0x180013ed1`: `service::%s::%s`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeManager::GetConnectedAccountTicket(
        CEditionUpgradeManager *this,
        unsigned __int16 **a2)
{
  int v3; // ebx
  int v4; // ecx
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int ActivationFactory; // eax
  __int64 *v10; // rbx
  __int64 v11; // rsi
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  HSTRING v15; // rdi
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  HRESULT v19; // edx
  __int64 v20; // r8
  int (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rdi
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  __int64 *v25; // rbx
  __int64 v26; // rsi
  HRESULT v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  unsigned __int64 v30; // rdx
  HSTRING v31; // rdi
  HRESULT v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  wil::details *v35; // rcx
  unsigned int v36; // r8d
  int v37; // eax
  __int64 *v38; // rbx
  __int64 v39; // rsi
  HRESULT v40; // eax
  int v41; // edx
  unsigned int v42; // r8d
  HSTRING v43; // rdi
  HRESULT v44; // eax
  int v45; // edx
  unsigned int v46; // r8d
  HRESULT v47; // edx
  __int64 v48; // r8
  int (__fastcall ***v49)(_QWORD, GUID *, __int64 *); // rdi
  bool v50; // zf
  bool v51; // zf
  PCWSTR StringRawBuffer; // rax
  _BYTE v53[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v54; // [rsp+48h] [rbp-B8h] BYREF
  int v55; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+58h] [rbp-A8h] BYREF
  int v57; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v58; // [rsp+68h] [rbp-98h] BYREF
  __int64 v59; // [rsp+70h] [rbp-90h] BYREF
  __int64 v60; // [rsp+78h] [rbp-88h] BYREF
  __int64 v61; // [rsp+80h] [rbp-80h] BYREF
  __int64 v62; // [rsp+88h] [rbp-78h] BYREF
  __int64 v63; // [rsp+90h] [rbp-70h] BYREF
  int (__fastcall ***v64)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp-68h] BYREF
  __int64 *v65; // [rsp+A0h] [rbp-60h] BYREF
  int (__fastcall ***v66)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp-58h] BYREF
  __int64 *v67; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v69; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER v70; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v71; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING v73[2]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR sourceString[2088]; // [rsp+110h] [rbp+10h] BYREF

  v67 = 0;
  v66 = 0;
  v65 = 0;
  v64 = 0;
  v60 = 0;
  v59 = 0;
  v56 = 0;
  v58 = 0;
  v63 = 0;
  v62 = 0;
  v61 = 0;
  v55 = 0;
  v57 = 0;
  memset_0(sourceString, 0, 0x1048u);
  string = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
LABEL_3:
    v4 = v3;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_5;
  }
  v73[0] = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
         0x45u,
         &hstringHeader,
         v73);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v73[0], &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v67);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
  v10 = v67;
  v11 = *v67;
  v73[0] = 0;
  v12 = WindowsCreateStringReference(L"consumers", 9u, &hstringHeader, v73);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
    __debugbreak();
  }
  v15 = v73[0];
  v71 = 0;
  v16 = WindowsCreateStringReference(L"https://login.windows.local", 0x1Bu, &v70, &v71);
  if ( v16 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
    __debugbreak();
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v11 + 96))(
                        v10,
                        v71,
                        v15,
                        &v66);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
  v21 = v66;
  v3 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
         v66,
         v19,
         v20);
  if ( v3 < 0 )
    goto LABEL_3;
  v3 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v21)[8])(v21, &v60);
  if ( v3 < 0 )
    goto LABEL_3;
  if ( !v60 )
  {
    v3 = -2147023692;
    goto LABEL_3;
  }
  v71 = 0;
  v22 = WindowsCreateStringReference(L"Windows.Security.Authentication.Web.Core.WebTokenRequest", 0x38u, &v70, &v71);
  if ( v22 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v71, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v65);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
  ActivationFactory = StringCchPrintfW(sourceString, 0x824u, L"service::%s::%s", L"www.microsoft.com", L"MBI_SSL");
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
  v25 = v65;
  v26 = *v65;
  v71 = 0;
  v27 = WindowsCreateStringReference(L"{28c08266-f973-4ae6-ffe4-409b249f138f}", 0x26u, &v70, &v71);
  if ( v27 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
    __debugbreak();
  }
  v30 = -1;
  do
    ++v30;
  while ( sourceString[v30] );
  if ( v30 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v30, v29);
    __debugbreak();
  }
  if ( (int)v30 + 1 < (unsigned int)v30 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v30, v29);
    __debugbreak();
  }
  v31 = v71;
  v32 = WindowsCreateStringReference(sourceString, v30, &hstringHeader, v73);
  if ( v32 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
    __debugbreak();
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, __int64, HSTRING, HSTRING, _DWORD, __int64 *))(v26 + 56))(
                        v25,
                        v60,
                        v73[0],
                        v31,
                        0,
                        &v59);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
  v36 = *(_DWORD *)Feature_48005687__descriptor;
  if ( (*(_DWORD *)Feature_48005687__descriptor & 4) == 0 )
  {
    v69 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_48005687>::GetCachedFeatureEnabledState(v35, &v69);
    v36 = v69;
  }
  LODWORD(v54) = 0;
  WORD2(v54) = 3;
  wil::details::ReportUsageToService(&qword_18002FCA0, 48005687, (v36 >> 10) & 1, (v36 >> 11) & 1, &v54, 1, 3);
  v54 = 0;
  v53[0] = 0;
  v37 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v59 + 80LL))(v59, &v54);
  v3 = v37;
  if ( v37 < 0 )
    goto LABEL_53;
  v38 = v54;
  v39 = *v54;
  v71 = 0;
  v40 = WindowsCreateStringReference(L"windows", 7u, &v70, &v71);
  if ( v40 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v40, v41, v42);
    JUMPOUT(0x1800142EELL);
  }
  v43 = v71;
  v73[0] = 0;
  v44 = WindowsCreateStringReference(L"ssoappgroup", 0xBu, &hstringHeader, v73);
  if ( v44 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v44, v45, v46);
    __debugbreak();
  }
  v37 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING, _BYTE *))(v39 + 80))(v38, v73[0], v43, v53);
  v3 = v37;
  if ( v37 < 0 )
  {
LABEL_53:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v37);
    if ( v54 )
      (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
    goto LABEL_5;
  }
  if ( v54 )
    (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
  ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(*v67 + 48))(v67, v59, &v64);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
  v49 = v64;
  v3 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
         v64,
         v47,
         v48);
  if ( v3 < 0 )
    goto LABEL_3;
  v3 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v49)[8])(v49, &v56);
  if ( v3 < 0 )
    goto LABEL_3;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v56 + 56LL))(v56, &v57);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
  if ( ((v57 - 3) & 0xFFFFFFFD) == 0 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 64LL))(v56, &v61);
    v3 = ActivationFactory;
    if ( ActivationFactory < 0 )
      goto LABEL_32;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v61 + 48LL))(v61, &v55);
    v3 = ActivationFactory;
    if ( ActivationFactory < 0 )
      goto LABEL_32;
    v3 = v55;
    v50 = v55 == 0;
    if ( v55 )
    {
      if ( v55 > 0 )
      {
        v3 = (unsigned __int16)v55 | 0x80070000;
        v50 = 0;
      }
      if ( !v50 )
        goto LABEL_3;
    }
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 48LL))(v56, &v62);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v62 + 48LL))(v62, 0, &v58);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 56LL))(v58, &v63);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
  if ( !v63 )
    goto LABEL_80;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v63 + 48LL))(v63, &v55);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
LABEL_32:
    v4 = ActivationFactory;
    goto LABEL_4;
  }
  v3 = v55;
  v51 = v55 == 0;
  if ( v55 )
  {
    if ( v55 > 0 )
    {
      v3 = (unsigned __int16)v55 | 0x80070000;
      v51 = 0;
    }
    if ( !v51 )
      goto LABEL_3;
  }
LABEL_80:
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v58 + 48LL))(v58, &string);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  ActivationFactory = CMiscHelpersT<CEmptyType>::AssignString(StringRawBuffer, a2);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_32;
LABEL_5:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
  if ( string )
    WindowsDeleteString(string);
  if ( v61 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    v61 = 0;
  }
  if ( v62 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    v62 = 0;
  }
  if ( v63 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    v63 = 0;
  }
  if ( v58 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
  }
  if ( v56 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
  if ( v59 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( v60 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    v60 = 0;
  }
  if ( v64 )
  {
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v64)[2])(v64);
    v64 = 0;
  }
  if ( v65 )
  {
    (*(void (__fastcall **)(__int64 *))(*v65 + 16))(v65);
    v65 = 0;
  }
  if ( v66 )
  {
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v66)[2])(v66);
    v66 = 0;
  }
  if ( v67 )
    (*(void (__fastcall **)(__int64 *))(*v67 + 16))(v67);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013b8c  push    rbp
0x180013b8e  push    rbx
0x180013b8f  push    rsi
0x180013b90  push    rdi
0x180013b91  push    r14
0x180013b93  push    r15
0x180013b95  lea     rbp, [rsp-1078h]
0x180013b9d  mov     eax, 1178h
0x180013ba2  call    _alloca_probe
0x180013ba7  sub     rsp, rax
0x180013baa  mov     rax, cs:__security_cookie
0x180013bb1  xor     rax, rsp
0x180013bb4  mov     [rbp+10A0h+var_40], rax
0x180013bbb  xor     r15d, r15d
0x180013bbe  lea     rcx, [rbp+10A0h+sourceString]; void *
0x180013bc2  mov     r14, rdx
0x180013bc5  mov     [rbp+10A0h+var_10F0], r15
0x180013bc9  xor     edx, edx; Val
0x180013bcb  mov     [rbp+10A0h+var_10F8], r15
0x180013bcf  mov     r8d, 1048h; Size
0x180013bd5  mov     [rbp+10A0h+var_1100], r15
0x180013bd9  mov     [rbp+10A0h+var_1108], r15
0x180013bdd  mov     [rsp+11A0h+var_1128], r15
0x180013be2  mov     [rsp+11A0h+var_1130], r15
0x180013be7  mov     [rsp+11A0h+var_1148], r15
0x180013bec  mov     [rsp+11A0h+var_1138], r15
0x180013bf1  mov     [rbp+10A0h+var_1110], r15
0x180013bf5  mov     [rbp+10A0h+var_1118], r15
0x180013bf9  mov     [rbp+10A0h+var_1120], r15
0x180013bfd  mov     [rsp+11A0h+var_1150], r15d
0x180013c02  mov     [rsp+11A0h+var_1140], r15d
0x180013c07  call    memset_0
0x180013c0c  mov     [rbp+10A0h+string], r15
0x180013c10  test    r14, r14
0x180013c13  jnz     loc_180013D73
0x180013c19  mov     ebx, 80070057h
0x180013c1e  mov     ecx, ebx
0x180013c20  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180013c25  mov     ecx, ebx
0x180013c27  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013c2c  mov     rcx, [rbp+10A0h+string]; string
0x180013c30  test    rcx, rcx
0x180013c33  jz      short loc_180013C3B
0x180013c35  call    cs:__imp_WindowsDeleteString
0x180013c3b  mov     rcx, [rbp+10A0h+var_1120]
0x180013c3f  test    rcx, rcx
0x180013c42  jz      short loc_180013C54
0x180013c44  mov     rax, [rcx]
0x180013c47  mov     rax, [rax+10h]
0x180013c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c50  mov     [rbp+10A0h+var_1120], r15
0x180013c54  mov     rcx, [rbp+10A0h+var_1118]
0x180013c58  test    rcx, rcx
0x180013c5b  jz      short loc_180013C6D
0x180013c5d  mov     rax, [rcx]
0x180013c60  mov     rax, [rax+10h]
0x180013c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c69  mov     [rbp+10A0h+var_1118], r15
0x180013c6d  mov     rcx, [rbp+10A0h+var_1110]
0x180013c71  test    rcx, rcx
0x180013c74  jz      short loc_180013C86
0x180013c76  mov     rax, [rcx]
0x180013c79  mov     rax, [rax+10h]
0x180013c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c82  mov     [rbp+10A0h+var_1110], r15
0x180013c86  mov     rcx, [rsp+11A0h+var_1138]
0x180013c8b  test    rcx, rcx
0x180013c8e  jz      short loc_180013CA1
0x180013c90  mov     rax, [rcx]
0x180013c93  mov     rax, [rax+10h]
0x180013c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c9c  mov     [rsp+11A0h+var_1138], r15
0x180013ca1  mov     rcx, [rsp+11A0h+var_1148]
0x180013ca6  test    rcx, rcx
0x180013ca9  jz      short loc_180013CBC
0x180013cab  mov     rax, [rcx]
0x180013cae  mov     rax, [rax+10h]
0x180013cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cb7  mov     [rsp+11A0h+var_1148], r15
0x180013cbc  mov     rcx, [rsp+11A0h+var_1130]
0x180013cc1  test    rcx, rcx
0x180013cc4  jz      short loc_180013CD7
0x180013cc6  mov     rax, [rcx]
0x180013cc9  mov     rax, [rax+10h]
0x180013ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cd2  mov     [rsp+11A0h+var_1130], r15
0x180013cd7  mov     rcx, [rsp+11A0h+var_1128]
0x180013cdc  test    rcx, rcx
0x180013cdf  jz      short loc_180013CF2
0x180013ce1  mov     rax, [rcx]
0x180013ce4  mov     rax, [rax+10h]
0x180013ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ced  mov     [rsp+11A0h+var_1128], r15
0x180013cf2  mov     rcx, [rbp+10A0h+var_1108]
0x180013cf6  test    rcx, rcx
0x180013cf9  jz      short loc_180013D0B
0x180013cfb  mov     rax, [rcx]
0x180013cfe  mov     rax, [rax+10h]
0x180013d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d07  mov     [rbp+10A0h+var_1108], r15
0x180013d0b  mov     rcx, [rbp+10A0h+var_1100]
0x180013d0f  test    rcx, rcx
0x180013d12  jz      short loc_180013D24
0x180013d14  mov     rax, [rcx]
0x180013d17  mov     rax, [rax+10h]
0x180013d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d20  mov     [rbp+10A0h+var_1100], r15
0x180013d24  mov     rcx, [rbp+10A0h+var_10F8]
0x180013d28  test    rcx, rcx
0x180013d2b  jz      short loc_180013D3D
0x180013d2d  mov     rax, [rcx]
0x180013d30  mov     rax, [rax+10h]
0x180013d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d39  mov     [rbp+10A0h+var_10F8], r15
0x180013d3d  mov     rcx, [rbp+10A0h+var_10F0]
0x180013d41  test    rcx, rcx
0x180013d44  jz      short loc_180013D52
0x180013d46  mov     rax, [rcx]
0x180013d49  mov     rax, [rax+10h]
0x180013d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d52  mov     eax, ebx
0x180013d54  mov     rcx, [rbp+10A0h+var_40]
0x180013d5b  xor     rcx, rsp; StackCookie
0x180013d5e  call    __security_check_cookie
0x180013d63  add     rsp, 1178h
0x180013d6a  pop     r15
0x180013d6c  pop     r14
0x180013d6e  pop     rdi
0x180013d6f  pop     rsi
0x180013d70  pop     rbx
0x180013d71  pop     rbp
0x180013d72  retn
0x180013d73  lea     r9, [rbp+10A0h+var_10A0]; string
0x180013d77  mov     [rbp+10A0h+var_10A0], r15
0x180013d7b  lea     r8, [rbp+10A0h+hstringHeader]; hstringHeader
0x180013d7f  mov     edx, 45h ; 'E'; length
0x180013d84  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180013d8b  call    cs:__imp_WindowsCreateStringReference
0x180013d91  test    eax, eax
0x180013d93  js      loc_1800142AC
0x180013d99  mov     rcx, [rbp+10A0h+var_10A0]
0x180013d9d  lea     r8, [rbp+10A0h+var_10F0]
0x180013da1  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x180013da8  call    cs:__imp_RoGetActivationFactory
0x180013dae  mov     ebx, eax
0x180013db0  test    eax, eax
0x180013db2  jns     short loc_180013DBB
0x180013db4  mov     ecx, eax
0x180013db6  jmp     loc_180013C20
0x180013dbb  mov     rbx, [rbp+10A0h+var_10F0]
0x180013dbf  lea     r9, [rbp+10A0h+var_10A0]; string
0x180013dc3  lea     r8, [rbp+10A0h+hstringHeader]; hstringHeader
0x180013dc7  mov     edx, 9; length
0x180013dcc  lea     rcx, aConsumers; "consumers"
0x180013dd3  mov     rsi, [rbx]
0x180013dd6  mov     [rbp+10A0h+var_10A0], r15
0x180013dda  call    cs:__imp_WindowsCreateStringReference
0x180013de0  test    eax, eax
0x180013de2  js      loc_1800142B4
0x180013de8  mov     rdi, [rbp+10A0h+var_10A0]
0x180013dec  lea     r9, [rbp+10A0h+var_10C0]; string
0x180013df0  lea     r8, [rbp+10A0h+var_10D8]; hstringHeader
0x180013df4  mov     [rbp+10A0h+var_10C0], r15
0x180013df8  mov     edx, 1Bh; length
0x180013dfd  lea     rcx, aHttpsLoginWind; "https://login.windows.local"
0x180013e04  call    cs:__imp_WindowsCreateStringReference
0x180013e0a  test    eax, eax
0x180013e0c  js      loc_1800142BC
0x180013e12  mov     rdx, [rbp+10A0h+var_10C0]
0x180013e16  lea     r9, [rbp+10A0h+var_10F8]
0x180013e1a  mov     rax, [rsi+60h]
0x180013e1e  mov     r8, rdi
0x180013e21  mov     rcx, rbx
0x180013e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e29  mov     ebx, eax
0x180013e2b  test    eax, eax
0x180013e2d  js      short loc_180013DB4
0x180013e2f  mov     rdi, [rbp+10A0h+var_10F8]
0x180013e33  mov     rcx, rdi
0x180013e36  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)
0x180013e3b  mov     ebx, eax
0x180013e3d  test    eax, eax
0x180013e3f  js      loc_180013C1E
0x180013e45  mov     rax, [rdi]
0x180013e48  lea     rdx, [rsp+11A0h+var_1128]
0x180013e4d  mov     rcx, rdi
0x180013e50  mov     rax, [rax+40h]
0x180013e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e59  mov     ebx, eax
0x180013e5b  test    eax, eax
0x180013e5d  js      loc_180013C1E
0x180013e63  cmp     [rsp+11A0h+var_1128], r15
0x180013e68  jnz     short loc_180013E74
0x180013e6a  mov     ebx, 800704B4h
0x180013e6f  jmp     loc_180013C1E
0x180013e74  lea     r9, [rbp+10A0h+var_10C0]; string
0x180013e78  mov     [rbp+10A0h+var_10C0], r15
0x180013e7c  lea     r8, [rbp+10A0h+var_10D8]; hstringHeader
0x180013e80  mov     edx, 38h ; '8'; length
0x180013e85  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180013e8c  call    cs:__imp_WindowsCreateStringReference
0x180013e92  test    eax, eax
0x180013e94  js      loc_1800142C4
0x180013e9a  mov     rcx, [rbp+10A0h+var_10C0]
0x180013e9e  lea     r8, [rbp+10A0h+var_1100]
0x180013ea2  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x180013ea9  call    cs:__imp_RoGetActivationFactory
0x180013eaf  mov     ebx, eax
0x180013eb1  test    eax, eax
0x180013eb3  js      loc_180013DB4
0x180013eb9  lea     rax, aMbiSsl; "MBI_SSL"
0x180013ec0  mov     edx, 824h; unsigned __int64
0x180013ec5  lea     r9, aWwwMicrosoftCo; "www.microsoft.com"
0x180013ecc  mov     [rsp+11A0h+var_1180], rax
0x180013ed1  lea     r8, aServiceSS; "service::%s::%s"
0x180013ed8  lea     rcx, [rbp+10A0h+sourceString]; unsigned __int16 *
0x180013edc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013ee1  mov     ebx, eax
0x180013ee3  test    eax, eax
0x180013ee5  js      loc_180013DB4
0x180013eeb  mov     rbx, [rbp+10A0h+var_1100]
0x180013eef  lea     r9, [rbp+10A0h+var_10C0]; string
0x180013ef3  lea     r8, [rbp+10A0h+var_10D8]; hstringHeader
0x180013ef7  mov     edx, 26h ; '&'; length
0x180013efc  lea     rcx, a28c08266F9734a; "{28c08266-f973-4ae6-ffe4-409b249f138f}"
0x180013f03  mov     rsi, [rbx]
0x180013f06  mov     [rbp+10A0h+var_10C0], r15
0x180013f0a  call    cs:__imp_WindowsCreateStringReference
0x180013f10  test    eax, eax
0x180013f12  js      loc_1800142CC
0x180013f18  lea     rax, [rbp+10A0h+sourceString]
0x180013f1c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180013f20  inc     rdx; int
0x180013f23  cmp     [rax+rdx*2], r15w
0x180013f28  jnz     short loc_180013F20
0x180013f2a  mov     eax, 0FFFFFFFFh
0x180013f2f  cmp     rdx, rax
0x180013f32  ja      loc_1800142A1
0x180013f38  lea     eax, [rdx+1]
0x180013f3b  cmp     eax, edx
0x180013f3d  jb      loc_1800142D4
0x180013f43  mov     rdi, [rbp+10A0h+var_10C0]
0x180013f47  lea     r9, [rbp+10A0h+var_10A0]; string
0x180013f4b  lea     r8, [rbp+10A0h+hstringHeader]; hstringHeader
0x180013f4f  lea     rcx, [rbp+10A0h+sourceString]; sourceString
0x180013f53  call    cs:__imp_WindowsCreateStringReference
0x180013f59  test    eax, eax
0x180013f5b  js      loc_1800142DF
0x180013f61  mov     r8, [rbp+10A0h+var_10A0]
0x180013f65  lea     rax, [rsp+11A0h+var_1130]
0x180013f6a  mov     rdx, [rsp+11A0h+var_1128]
0x180013f6f  mov     r9, rdi
0x180013f72  mov     [rsp+11A0h+var_1178], rax
0x180013f77  mov     rcx, rbx
0x180013f7a  mov     rax, [rsi+38h]
0x180013f7e  mov     dword ptr [rsp+11A0h+var_1180], r15d
0x180013f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f88  mov     ebx, eax
0x180013f8a  test    eax, eax
0x180013f8c  js      loc_180013DB4
0x180013f92  mov     rax, cs:Feature_48005687__descriptor
0x180013f99  mov     r8d, [rax]
0x180013f9c  test    r8b, 4
0x180013fa0  jnz     short loc_180013FB5
0x180013fa2  lea     rdx, [rbp+10A0h+var_10E0]
0x180013fa6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_48005687@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48005687>::GetCachedFeatureEnabledState(void)
0x180013fab  mov     rcx, [rax]
0x180013fae  mov     [rbp+10A0h+var_10E0], rcx
0x180013fb2  mov     r8d, ecx
0x180013fb5  mov     r9d, r8d
0x180013fb8  mov     [rsp+11A0h+var_1170], 3
0x180013fc0  shr     r9d, 0Bh
0x180013fc4  lea     rax, [rsp+11A0h+var_1158]
0x180013fc9  shr     r8d, 0Ah
0x180013fcd  lea     rcx, qword_18002FCA0
0x180013fd4  and     r9d, 1
0x180013fd8  mov     dword ptr [rsp+11A0h+var_1178], 1
0x180013fe0  and     r8d, 1
0x180013fe4  mov     dword ptr [rsp+11A0h+var_1158], r15d
0x180013fe9  mov     edx, 2DC8237h
0x180013fee  mov     word ptr [rsp+11A0h+var_1158+4], 3
0x180013ff5  mov     [rsp+11A0h+var_1180], rax
0x180013ffa  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180013fff  mov     rcx, [rsp+11A0h+var_1130]
0x180014004  lea     rdx, [rsp+11A0h+var_1158]
0x180014009  mov     [rsp+11A0h+var_1158], r15
0x18001400e  mov     [rsp+11A0h+var_1160], r15b
0x180014013  mov     rax, [rcx]
0x180014016  mov     rax, [rax+50h]
0x18001401a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001401f  mov     ebx, eax
0x180014021  test    eax, eax
0x180014023  jns     short loc_18001404B
0x180014025  mov     ecx, eax
0x180014027  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001402c  mov     rcx, [rsp+11A0h+var_1158]
0x180014031  test    rcx, rcx
0x180014034  jz      loc_180013C25
0x18001403a  mov     rax, [rcx]
0x18001403d  mov     rax, [rax+10h]
  ... truncated ...
```
