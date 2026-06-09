# WinStoreAuth::AuthenticationInternal::CreateTokenRequestHelper(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AuthenticationEndpoint,WinStoreAuth::PromptType,Windows::System::IUser *,Windows::Security::Authentication::Web::Core::IWebTokenRequest * *)

- ea: `0x18003b010`
- end: `0x18003bbae`
- name: `?CreateTokenRequestHelper@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@W4AuthenticationEndpoint@2@W4PromptType@2@PEAUIUser@System@Windows@@PEAPEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@Z`
- size: `2974`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, IUnknown **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003e828`
- `0x180040ef8`

## callees

- `0x1800026b0`
- `0x180010b84`
- `0x1800115fc`
- `0x18002fbb4`
- `0x180038550`
- `0x18003b010`
- `0x18003bd7c`
- `0x180040e90`
- `0x18004bab0`
- `0x18004bb04`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b2d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b3ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b64f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b8bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b9a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b2d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b3ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b64f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b8bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b9a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b0d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b101`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b195`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b1e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b24a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b730`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b7df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b821`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b90d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b91c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b9f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003babe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bacd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b0d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b101`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b195`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b1e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b24a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b730`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b7df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b821`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b90d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b91c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b9f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003babe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bacd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b0eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b11b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b17f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b1af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b0eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b11b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b17f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003b1af`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003b315`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003b315`

## string_xrefs

- `0x18003b2d1`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x18003b296`: `service::%s::%s`

## pseudocode

```c
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CreateTokenRequestHelper(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        IUnknown **a5)
{
  int v6; // eax
  int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  const WCHAR *v10; // r14
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rbx
  HRESULT v13; // eax
  const WCHAR *v14; // r14
  unsigned __int64 v15; // rbx
  HRESULT v16; // eax
  int SlsValue; // eax
  __int64 v18; // rdx
  unsigned int StringRawBuffer; // ebx
  PCWSTR v20; // rax
  HRESULT v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  HSTRING v24; // rbx
  IUnknown *v25; // rcx
  int ActivationFactory; // eax
  IUnknown *v27; // rcx
  int v28; // eax
  int v29; // edx
  unsigned int v30; // r8d
  IUnknown *v31; // rcx
  IUnknown *v32; // rbx
  struct IUnknownVtbl *lpVtbl; // rsi
  HSTRING v34; // r14
  HRESULT v35; // eax
  int v36; // edx
  unsigned int v37; // r8d
  int v38; // eax
  IUnknown *v39; // rcx
  IUnknown *v40; // rcx
  int v41; // eax
  IUnknown *v42; // rcx
  IUnknown *v43; // rcx
  int v44; // eax
  IUnknown *v45; // rcx
  IUnknown *v46; // rcx
  IUnknown *v47; // rcx
  int v48; // eax
  IUnknown *v49; // rcx
  IUnknown *v50; // rcx
  IUnknown *v51; // rcx
  IUnknown *v52; // rbx
  struct IUnknownVtbl *v53; // rsi
  HRESULT v54; // eax
  int v55; // edx
  unsigned int v56; // r8d
  HSTRING v57; // rdi
  HRESULT v58; // eax
  int v59; // edx
  unsigned int v60; // r8d
  int v61; // eax
  IUnknown *v62; // rcx
  IUnknown *v63; // rcx
  IUnknown *v64; // rcx
  int v65; // eax
  IUnknown *v66; // rcx
  IUnknown *v67; // rcx
  IUnknown *v68; // rcx
  int v69; // eax
  IUnknown *v70; // rcx
  IUnknown *v71; // rcx
  IUnknown *v72; // rcx
  IUnknown *v73; // rbx
  struct IUnknownVtbl *v74; // rdi
  HSTRING v75; // rsi
  HRESULT v76; // eax
  int v77; // edx
  unsigned int v78; // r8d
  int v79; // eax
  IUnknown *v80; // rcx
  IUnknown *v81; // rcx
  IUnknown *v82; // rcx
  IUnknown *v83; // rbx
  struct IUnknownVtbl *v84; // rdi
  HSTRING v85; // rsi
  HRESULT v86; // eax
  int v87; // edx
  unsigned int v88; // r8d
  int v89; // eax
  IUnknown *v90; // rcx
  IUnknown *v91; // rcx
  IUnknown *v92; // rcx
  IUnknown *v94; // rax
  IUnknown *v95; // rcx
  IUnknown *v96; // rdx
  IUnknown *v97; // rcx
  int v98; // [rsp+20h] [rbp-E0h]
  HSTRING v99; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v100; // [rsp+48h] [rbp-B8h] BYREF
  IUnknown *v101; // [rsp+50h] [rbp-B0h] BYREF
  IUnknown *v102; // [rsp+58h] [rbp-A8h]
  char v103[8]; // [rsp+60h] [rbp-A0h] BYREF
  IUnknown *v104; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v105; // [rsp+70h] [rbp-90h] BYREF
  char v106[8]; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v108; // [rsp+88h] [rbp-78h] BYREF
  IUnknown **v109; // [rsp+90h] [rbp-70h]
  HSTRING_HEADER v110; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v111; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING v113[2]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR sourceString[2088]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1168h] [rbp+1068h]

  v109 = a5;
  *a5 = 0;
  string = 0;
  LODWORD(v105) = 0;
  v6 = WinStoreAuth::AuthenticationInternal::ExtractProviderType(a1, &v105);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (unsigned int)v6;
    v9 = 1913;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)v8,
      v98);
LABEL_126:
    WindowsDeleteString(string);
    return (unsigned int)v7;
  }
  if ( (_DWORD)v105 == 1 )
  {
    v14 = WinStoreAuth::g_msaClientId;
    v11 = -1;
    if ( WinStoreAuth::g_msaClientId )
    {
      v15 = -1;
      do
        ++v15;
      while ( WinStoreAuth::g_msaClientId[v15] );
      if ( v15 > 0xFFFFFFFF )
      {
        v7 = -2147024362;
        goto LABEL_24;
      }
      WindowsDeleteString(string);
      string = 0;
      v16 = WindowsCreateString(v14, v15, &string);
    }
    else
    {
      WindowsDeleteString(string);
      string = 0;
      v16 = WindowsCreateString(&ApplicationName, 0, &string);
    }
    v7 = v16;
LABEL_24:
    if ( v7 < 0 )
    {
      v9 = 1918;
      goto LABEL_26;
    }
    goto LABEL_28;
  }
  if ( (_DWORD)v105 != 2 )
  {
    v7 = -2147024809;
    v9 = 1924;
LABEL_26:
    v8 = (unsigned int)v7;
    goto LABEL_27;
  }
  v10 = WinStoreAuth::g_pszAadClientId;
  v11 = -1;
  if ( WinStoreAuth::g_pszAadClientId )
  {
    v12 = -1;
    do
      ++v12;
    while ( WinStoreAuth::g_pszAadClientId[v12] );
    if ( v12 > 0xFFFFFFFF )
    {
      v7 = -2147024362;
      goto LABEL_14;
    }
    WindowsDeleteString(string);
    string = 0;
    v13 = WindowsCreateString(v10, v12, &string);
  }
  else
  {
    WindowsDeleteString(string);
    string = 0;
    v13 = WindowsCreateString(&ApplicationName, 0, &string);
  }
  v7 = v13;
LABEL_14:
  if ( v7 < 0 )
  {
    v9 = 1921;
    goto LABEL_26;
  }
LABEL_28:
  v99 = 0;
  WindowsDeleteString(0);
  v100 = 0;
  SlsValue = WinStoreAuth::GetSlsValue(0, &v100);
  v7 = SlsValue;
  if ( SlsValue < 0 )
  {
    v18 = 1933;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)SlsValue,
      v98);
LABEL_125:
    WindowsDeleteString(v99);
    v99 = 0;
    WindowsDeleteString(v100);
    v100 = 0;
    goto LABEL_126;
  }
  WindowsDeleteString(v99);
  v99 = 0;
  SlsValue = WinStoreAuth::GetSlsValue(1, &v99);
  v7 = SlsValue;
  if ( SlsValue < 0 )
  {
    v18 = 1934;
    goto LABEL_30;
  }
  StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(v99, 0);
  v20 = WindowsGetStringRawBuffer(v100, 0);
  v98 = StringRawBuffer;
  SlsValue = StringCchPrintfW(sourceString, 0x824u, L"service::%s::%s", v20);
  v7 = SlsValue;
  if ( SlsValue < 0 )
  {
    v18 = 1948;
    goto LABEL_30;
  }
  v101 = 0;
  v113[0] = 0;
  v21 = WindowsCreateStringReference(
          L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
          0x38u,
          &hstringHeader,
          v113);
  if ( v21 < 0 )
    goto LABEL_137;
  v24 = v113[0];
  v25 = v101;
  if ( v101 )
  {
    v101 = 0;
    ((void (__fastcall *)(IUnknown *))v25->lpVtbl->Release)(v25);
  }
  ActivationFactory = RoGetActivationFactory(v24, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v101);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v98);
    v27 = v101;
    if ( v101 )
    {
      v101 = 0;
      ((void (__fastcall *)(IUnknown *))v27->lpVtbl->Release)(v27);
    }
    goto LABEL_125;
  }
  v28 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v101);
  v7 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v28,
      v98);
    v31 = v101;
    if ( v101 )
    {
      v101 = 0;
      ((void (__fastcall *)(IUnknown *))v31->lpVtbl->Release)(v31);
    }
    goto LABEL_125;
  }
  v102 = 0;
  do
    ++v11;
  while ( sourceString[v11] );
  if ( v11 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v29, v30);
LABEL_137:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
LABEL_138:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v35, v36, v37);
LABEL_139:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v54, v55, v56);
    goto LABEL_140;
  }
  if ( (int)v11 + 1 < (unsigned int)v11 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v29, v30);
    __debugbreak();
  }
  v32 = v101;
  lpVtbl = v101->lpVtbl;
  v34 = string;
  v35 = WindowsCreateStringReference(sourceString, v11, &v110, &v111);
  if ( v35 < 0 )
    goto LABEL_138;
  v38 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, HSTRING, HSTRING))lpVtbl[2].AddRef)(v32, *a1, v111, v34);
  v7 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v38,
      0);
    v39 = v102;
    if ( v102 )
    {
      v102 = 0;
      ((void (__fastcall *)(IUnknown *))v39->lpVtbl->Release)(v39);
    }
    v40 = v101;
    if ( v101 )
    {
      v101 = 0;
      ((void (__fastcall *)(IUnknown *))v40->lpVtbl->Release)(v40);
    }
    goto LABEL_125;
  }
  v41 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v102);
  v7 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B1,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v41,
      0);
    v42 = v102;
    if ( v102 )
    {
      v102 = 0;
      ((void (__fastcall *)(IUnknown *))v42->lpVtbl->Release)(v42);
    }
    v43 = v101;
    if ( v101 )
    {
      v101 = 0;
      ((void (__fastcall *)(IUnknown *))v43->lpVtbl->Release)(v43);
    }
    goto LABEL_125;
  }
  v104 = 0;
  v44 = ((__int64 (__fastcall *)(IUnknown *, IUnknown **))v102->lpVtbl[3].AddRef)(v102, &v104);
  v7 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v44,
      0);
    v45 = v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(IUnknown *))v45->lpVtbl->Release)(v45);
    }
    v46 = v102;
    if ( v102 )
    {
      v102 = 0;
      ((void (__fastcall *)(IUnknown *))v46->lpVtbl->Release)(v46);
    }
    v47 = v101;
    if ( v101 )
    {
      v101 = 0;
      ((void (__fastcall *)(IUnknown *))v47->lpVtbl->Release)(v47);
    }
    goto LABEL_125;
  }
  v48 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v104);
  v7 = v48;
  if ( v48 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B5,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v48,
      0);
    v49 = v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(IUnknown *))v49->lpVtbl->Release)(v49);
    }
    v50 = v102;
    if ( v102 )
    {
      v102 = 0;
      ((void (__fastcall *)(IUnknown *))v50->lpVtbl->Release)(v50);
    }
    v51 = v101;
    if ( v101 )
    {
      v101 = 0;
      ((void (__fastcall *)(IUnknown *))v51->lpVtbl->Release)(v51);
    }
    goto LABEL_125;
  }
  if ( (_DWORD)v105 != 1 )
  {
    if ( (_DWORD)v105 != 2 )
      goto LABEL_128;
    v105 = 0;
    WindowsDeleteString(0);
    v105 = 0;
    v65 = WinStoreAuth::GetSlsValue(2, &v105);
    v7 = v65;
    if ( v65 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D2,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v65,
        0);
      WindowsDeleteString(v105);
      v105 = 0;
      v66 = v104;
      if ( v104 )
      {
        v104 = 0;
        ((void (__fastcall *)(IUnknown *))v66->lpVtbl->Release)(v66);
      }
      v67 = v102;
      if ( v102 )
      {
        v102 = 0;
        ((void (__fastcall *)(IUnknown *))v67->lpVtbl->Release)(v67);
      }
      v68 = v101;
      if ( v101 )
      {
        v101 = 0;
        ((void (__fastcall *)(IUnknown *))v68->lpVtbl->Release)(v68);
      }
      goto LABEL_125;
    }
    v108 = 0;
    WindowsDeleteString(0);
    v108 = 0;
    v69 = WinStoreAuth::GetSlsValue(3, &v108);
    v7 = v69;
    if ( v69 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D5,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v69,
        0);
      WindowsDeleteString(v108);
      v108 = 0;
      WindowsDeleteString(v105);
      v105 = 0;
      v70 = v104;
      if ( v104 )
      {
        v104 = 0;
        ((void (__fastcall *)(IUnknown *))v70->lpVtbl->Release)(v70);
      }
      v71 = v102;
      if ( v102 )
      {
        v102 = 0;
        ((void (__fastcall *)(IUnknown *))v71->lpVtbl->Release)(v71);
      }
      v72 = v101;
      if ( v101 )
      {
        v101 = 0;
        ((void (__fastcall *)(IUnknown *))v72->lpVtbl->Release)(v72);
      }
      goto LABEL_125;
    }
    v103[0] = 0;
    v73 = v104;
    v74 = v104->lpVtbl;
    v75 = v108;
    v111 = 0;
    v76 = WindowsCreateStringReference(L"resource", 8u, &v110, &v111);
    if ( v76 >= 0 )
    {
      v79 = ((__int64 (__fastcall *)(IUnknown *, HSTRING, HSTRING, char *))v74[3].AddRef)(v73, v111, v75, v103);
      v7 = v79;
      if ( v79 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7DB,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v79,
          0);
        WindowsDeleteString(v108);
        v108 = 0;
        WindowsDeleteString(v105);
        v105 = 0;
        v80 = v104;
        if ( v104 )
        {
          v104 = 0;
          ((void (__fastcall *)(IUnknown *))v80->lpVtbl->Release)(v80);
        }
        v81 = v102;
        if ( v102 )
        {
          v102 = 0;
          ((void (__fastcall *)(IUnknown *))v81->lpVtbl->Release)(v81);
        }
        v82 = v101;
        if ( v101 )
        {
          v101 = 0;
          ((void (__fastcall *)(IUnknown *))v82->lpVtbl->Release)(v82);
        }
        goto LABEL_125;
      }
      v83 = v104;
      v84 = v104->lpVtbl;
      v85 = v105;
      v111 = 0;
      v86 = WindowsCreateStringReference(L"authority", 9u, &v110, &v111);
      if ( v86 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v86, v87, v88);
        JUMPOUT(0x18003BBADLL);
      }
      v89 = ((__int64 (__fastcall *)(IUnknown *, HSTRING, HSTRING, char *))v84[3].AddRef)(v83, v111, v85, v103);
      v7 = v89;
      if ( v89 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7E0,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v89,
          0);
        WindowsDeleteString(v108);
        v108 = 0;
        WindowsDeleteString(v105);
        v105 = 0;
        v90 = v104;
        if ( v104 )
        {
          v104 = 0;
          ((void (__fastcall *)(IUnknown *))v90->lpVtbl->Release)(v90);
        }
        v91 = v102;
        if ( v102 )
        {
          v102 = 0;
          ((void (__fastcall *)(IUnknown *))v91->lpVtbl->Release)(v91);
        }
        v92 = v101;
        if ( v101 )
        {
          v101 = 0;
          ((void (__fastcall *)(IUnknown *))v92->lpVtbl->Release)(v92);
        }
        goto LABEL_125;
      }
      WindowsDeleteString(v108);
      v108 = 0;
      WindowsDeleteString(v105);
      goto LABEL_128;
    }
LABEL_141:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v76, v77, v78);
    __debugbreak();
  }
  v106[0] = 0;
  if ( wcscmp_0(WinStoreAuth::g_msaClientId, L"{f0c62012-2cef-4831-b1f7-930682874c86}") )
    goto LABEL_128;
  v52 = v104;
  v53 = v104->lpVtbl;
  v113[0] = 0;
  v54 = WindowsCreateStringReference(L"none", 4u, &hstringHeader, v113);
  if ( v54 < 0 )
    goto LABEL_139;
  v57 = v113[0];
  v111 = 0;
  v58 = WindowsCreateStringReference(L"ssoappgroup", 0xBu, &v110, &v111);
  if ( v58 < 0 )
  {
LABEL_140:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v58, v59, v60);
    goto LABEL_141;
  }
  v61 = ((__int64 (__fastcall *)(IUnknown *, HSTRING, HSTRING, char *))v53[3].AddRef)(v52, v111, v57, v106);
  v7 = v61;
  if ( v61 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C2,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v61,
      0);
    v62 = v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(IUnknown *))v62->lpVtbl->Release)(v62);
    }
    v63 = v102;
    if ( v102 )
    {
      v102 = 0;
      ((void (__fastcall *)(IUnknown *))v63->lpVtbl->Release)(v63);
    }
    v64 = v101;
    if ( v101 )
    {
      v101 = 0;
      ((void (__fastcall *)(IUnknown *))v64->lpVtbl->Release)(v64);
    }
    goto LABEL_125;
  }
LABEL_128:
  v94 = v102;
  v95 = 0;
  v102 = 0;
  *v109 = v94;
  v96 = v104;
  if ( v104 )
  {
    v104 = 0;
    ((void (__fastcall *)(IUnknown *))v96->lpVtbl->Release)(v96);
    v95 = v102;
  }
  if ( v95 )
  {
    v102 = 0;
    ((void (__fastcall *)(IUnknown *))v95->lpVtbl->Release)(v95);
  }
  v97 = v101;
  if ( v101 )
  {
    v101 = 0;
    ((void (__fastcall *)(IUnknown *))v97->lpVtbl->Release)(v97);
  }
  WindowsDeleteString(v99);
  v99 = 0;
  WindowsDeleteString(v100);
  v100 = 0;
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x18003b010  mov     [rsp-8+arg_8], rbx
0x18003b015  mov     [rsp-8+arg_10], rsi
0x18003b01a  push    rbp
0x18003b01b  push    rdi
0x18003b01c  push    r12
0x18003b01e  push    r13
0x18003b020  push    r14
0x18003b022  lea     rbp, [rsp-1040h]
0x18003b02a  mov     eax, 1140h
0x18003b02f  call    _alloca_probe
0x18003b034  sub     rsp, rax
0x18003b037  mov     rax, cs:__security_cookie
0x18003b03e  xor     rax, rsp
0x18003b041  mov     [rbp+1060h+var_30], rax
0x18003b048  mov     r13, rcx
0x18003b04b  mov     rax, [rbp+1060h+arg_20]
0x18003b052  mov     [rbp+1060h+var_10D0], rax
0x18003b056  xor     edi, edi
0x18003b058  mov     [rax], rdi
0x18003b05b  mov     [rbp+1060h+string], rdi
0x18003b05f  mov     dword ptr [rsp+1160h+var_10F0], edi
0x18003b063  lea     rdx, [rsp+1160h+var_10F0]
0x18003b068  call    ?ExtractProviderType@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@AEAW4AccountProviderType@2@@Z; WinStoreAuth::AuthenticationInternal::ExtractProviderType(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AccountProviderType &)
0x18003b06d  mov     ebx, eax
0x18003b06f  test    eax, eax
0x18003b071  jns     short loc_18003B080
0x18003b073  mov     r9d, eax
0x18003b076  mov     edx, 779h
0x18003b07b  jmp     loc_18003B1C3
0x18003b080  mov     ecx, dword ptr [rsp+1160h+var_10F0]
0x18003b084  sub     ecx, 1
0x18003b087  jz      loc_18003B135
0x18003b08d  cmp     ecx, 1
0x18003b090  jz      short loc_18003B0A1
0x18003b092  mov     ebx, 80070057h
0x18003b097  mov     edx, 784h
0x18003b09c  jmp     loc_18003B1C0
0x18003b0a1  mov     r14, cs:?g_pszAadClientId@WinStoreAuth@@3PEBGEB; ushort const * const WinStoreAuth::g_pszAadClientId
0x18003b0a8  mov     esi, 80070216h
0x18003b0ad  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003b0b1  xor     eax, eax
0x18003b0b3  mov     r12d, 0FFFFFFFFh
0x18003b0b9  test    r14, r14
0x18003b0bc  jz      short loc_18003B0FD
0x18003b0be  mov     rbx, rdi
0x18003b0c1  inc     rbx
0x18003b0c4  cmp     [r14+rbx*2], ax
0x18003b0c9  jnz     short loc_18003B0C1
0x18003b0cb  cmp     rbx, r12
0x18003b0ce  ja      short loc_18003B0F6
0x18003b0d0  mov     rcx, [rbp+1060h+string]; string
0x18003b0d4  call    cs:__imp_WindowsDeleteString
0x18003b0da  mov     [rbp+1060h+string], 0
0x18003b0e2  mov     edx, ebx; length
0x18003b0e4  lea     r8, [rbp+1060h+string]; string
0x18003b0e8  mov     rcx, r14; sourceString
0x18003b0eb  call    cs:__imp_WindowsCreateString
0x18003b0f1  xor     r14d, r14d
0x18003b0f4  jmp     short loc_18003B121
0x18003b0f6  mov     ebx, esi
0x18003b0f8  xor     r14d, r14d
0x18003b0fb  jmp     short loc_18003B123
0x18003b0fd  mov     rcx, [rbp+1060h+string]; string
0x18003b101  call    cs:__imp_WindowsDeleteString
0x18003b107  xor     r14d, r14d
0x18003b10a  mov     [rbp+1060h+string], r14
0x18003b10e  lea     r8, [rbp+1060h+string]; string
0x18003b112  xor     edx, edx; length
0x18003b114  lea     rcx, ApplicationName; sourceString
0x18003b11b  call    cs:__imp_WindowsCreateString
0x18003b121  mov     ebx, eax
0x18003b123  test    ebx, ebx
0x18003b125  jns     loc_18003B1DB
0x18003b12b  mov     edx, 781h
0x18003b130  jmp     loc_18003B1C0
0x18003b135  mov     r14, cs:?g_msaClientId@WinStoreAuth@@3PEBGEB; ushort const * const WinStoreAuth::g_msaClientId
0x18003b13c  mov     esi, 80070216h
0x18003b141  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003b145  xor     eax, eax
0x18003b147  mov     r12d, 0FFFFFFFFh
0x18003b14d  test    r14, r14
0x18003b150  jz      short loc_18003B191
0x18003b152  mov     rbx, rdi
0x18003b155  inc     rbx
0x18003b158  cmp     [r14+rbx*2], ax
0x18003b15d  jnz     short loc_18003B155
0x18003b15f  cmp     rbx, r12
0x18003b162  ja      short loc_18003B18A
0x18003b164  mov     rcx, [rbp+1060h+string]; string
0x18003b168  call    cs:__imp_WindowsDeleteString
0x18003b16e  mov     [rbp+1060h+string], 0
0x18003b176  mov     edx, ebx; length
0x18003b178  lea     r8, [rbp+1060h+string]; string
0x18003b17c  mov     rcx, r14; sourceString
0x18003b17f  call    cs:__imp_WindowsCreateString
0x18003b185  xor     r14d, r14d
0x18003b188  jmp     short loc_18003B1B5
0x18003b18a  mov     ebx, esi
0x18003b18c  xor     r14d, r14d
0x18003b18f  jmp     short loc_18003B1B7
0x18003b191  mov     rcx, [rbp+1060h+string]; string
0x18003b195  call    cs:__imp_WindowsDeleteString
0x18003b19b  xor     r14d, r14d
0x18003b19e  mov     [rbp+1060h+string], r14
0x18003b1a2  lea     r8, [rbp+1060h+string]; string
0x18003b1a6  xor     edx, edx; length
0x18003b1a8  lea     rcx, ApplicationName; sourceString
0x18003b1af  call    cs:__imp_WindowsCreateString
0x18003b1b5  mov     ebx, eax
0x18003b1b7  test    ebx, ebx
0x18003b1b9  jns     short loc_18003B1DB
0x18003b1bb  mov     edx, 77Eh; void *
0x18003b1c0  mov     r9d, ebx; char *
0x18003b1c3  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003b1ca  mov     rcx, [rbp+1068h]; this
0x18003b1d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b1d6  jmp     loc_18003BA83
0x18003b1db  mov     [rsp+1160h+var_1118], r14
0x18003b1e0  mov     [rsp+1160h+var_1120], r14
0x18003b1e5  xor     ecx, ecx; string
0x18003b1e7  call    cs:__imp_WindowsDeleteString
0x18003b1ed  mov     [rsp+1160h+var_1118], r14
0x18003b1f2  lea     rdx, [rsp+1160h+var_1118]
0x18003b1f7  xor     ecx, ecx
0x18003b1f9  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x18003b1fe  mov     ebx, eax
0x18003b200  test    eax, eax
0x18003b202  jns     short loc_18003B245
0x18003b204  mov     edx, 78Dh; void *
0x18003b209  mov     rcx, [rbp+1068h]; this
0x18003b210  mov     r9d, eax; char *
0x18003b213  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003b21a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b21f  nop
0x18003b220  mov     rcx, [rsp+1160h+var_1120]; string
0x18003b225  call    cs:__imp_WindowsDeleteString
0x18003b22b  mov     [rsp+1160h+var_1120], r14
0x18003b230  mov     rcx, [rsp+1160h+var_1118]; string
0x18003b235  call    cs:__imp_WindowsDeleteString
0x18003b23b  mov     [rsp+1160h+var_1118], r14
0x18003b240  jmp     loc_18003BA83
0x18003b245  mov     rcx, [rsp+1160h+var_1120]; string
0x18003b24a  call    cs:__imp_WindowsDeleteString
0x18003b250  mov     [rsp+1160h+var_1120], r14
0x18003b255  lea     rdx, [rsp+1160h+var_1120]
0x18003b25a  mov     ecx, 1
0x18003b25f  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x18003b264  mov     ebx, eax
0x18003b266  test    eax, eax
0x18003b268  jns     short loc_18003B271
0x18003b26a  mov     edx, 78Eh
0x18003b26f  jmp     short loc_18003B209
0x18003b271  xor     edx, edx; length
0x18003b273  mov     rcx, [rsp+1160h+var_1120]; string
0x18003b278  call    cs:__imp_WindowsGetStringRawBuffer
0x18003b27e  mov     rbx, rax
0x18003b281  xor     edx, edx; length
0x18003b283  mov     rcx, [rsp+1160h+var_1118]; string
0x18003b288  call    cs:__imp_WindowsGetStringRawBuffer
0x18003b28e  mov     qword ptr [rsp+1160h+var_1140], rbx; int
0x18003b293  mov     r9, rax
0x18003b296  lea     r8, aServiceSS; "service::%s::%s"
0x18003b29d  mov     edx, 824h; unsigned __int64
0x18003b2a2  lea     rcx, [rbp+1060h+sourceString]; unsigned __int16 *
0x18003b2a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b2ab  mov     ebx, eax
0x18003b2ad  test    eax, eax
0x18003b2af  jns     short loc_18003B2BB
0x18003b2b1  mov     edx, 79Ch
0x18003b2b6  jmp     loc_18003B209
0x18003b2bb  mov     [rsp+1160h+var_1110], r14
0x18003b2c0  mov     [rbp+1060h+var_1090], r14
0x18003b2c4  lea     r9, [rbp+1060h+var_1090]; string
0x18003b2c8  lea     r8, [rbp+1060h+hstringHeader]; hstringHeader
0x18003b2cc  mov     edx, 38h ; '8'; length
0x18003b2d1  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18003b2d8  call    cs:__imp_WindowsCreateStringReference
0x18003b2de  test    eax, eax
0x18003b2e0  js      loc_18003BB7E
0x18003b2e6  mov     rbx, [rbp+1060h+var_1090]
0x18003b2ea  mov     rcx, [rsp+1160h+var_1110]
0x18003b2ef  test    rcx, rcx
0x18003b2f2  jz      short loc_18003B306
0x18003b2f4  mov     [rsp+1160h+var_1110], r14
0x18003b2f9  mov     rax, [rcx]
0x18003b2fc  mov     rax, [rax+10h]
0x18003b300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b305  nop
0x18003b306  lea     r8, [rsp+1160h+var_1110]
0x18003b30b  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x18003b312  mov     rcx, rbx
0x18003b315  call    cs:__imp_RoGetActivationFactory
0x18003b31b  mov     ebx, eax
0x18003b31d  test    eax, eax
0x18003b31f  jns     short loc_18003B35E
0x18003b321  mov     rcx, [rbp+1068h]; this
0x18003b328  mov     r9d, eax; char *
0x18003b32b  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003b332  mov     edx, 7A7h; void *
0x18003b337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b33c  nop
0x18003b33d  mov     rcx, [rsp+1160h+var_1110]
0x18003b342  test    rcx, rcx
0x18003b345  jz      short loc_18003B359
0x18003b347  mov     [rsp+1160h+var_1110], r14
0x18003b34c  mov     rax, [rcx]
0x18003b34f  mov     rax, [rax+10h]
0x18003b353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b358  nop
0x18003b359  jmp     loc_18003B220
0x18003b35e  mov     rcx, [rsp+1160h+var_1110]
0x18003b363  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18003b368  mov     ebx, eax
0x18003b36a  test    eax, eax
0x18003b36c  jns     short loc_18003B3AB
0x18003b36e  mov     rcx, [rbp+1068h]; this
0x18003b375  mov     r9d, eax; char *
0x18003b378  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003b37f  mov     edx, 7A8h; void *
0x18003b384  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b389  nop
0x18003b38a  mov     rcx, [rsp+1160h+var_1110]
0x18003b38f  test    rcx, rcx
0x18003b392  jz      short loc_18003B3A6
0x18003b394  mov     [rsp+1160h+var_1110], r14
0x18003b399  mov     rax, [rcx]
0x18003b39c  mov     rax, [rax+10h]
0x18003b3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3a5  nop
0x18003b3a6  jmp     loc_18003B220
0x18003b3ab  mov     [rsp+1160h+var_1108], r14
0x18003b3b0  lea     rax, [rbp+1060h+sourceString]
0x18003b3b4  inc     rdi
0x18003b3b7  cmp     [rax+rdi*2], r14w
0x18003b3bc  jnz     short loc_18003B3B4
0x18003b3be  cmp     rdi, r12
0x18003b3c1  ja      loc_18003BB76
0x18003b3c7  lea     eax, [rdi+1]
0x18003b3ca  cmp     eax, edi
0x18003b3cc  jb      loc_18003BB6E
0x18003b3d2  mov     rbx, [rsp+1160h+var_1110]
0x18003b3d7  mov     rsi, [rbx]
0x18003b3da  mov     r14, [rbp+1060h+string]
0x18003b3de  lea     r9, [rbp+1060h+var_10B0]; string
0x18003b3e2  lea     r8, [rbp+1060h+var_10C8]; hstringHeader
0x18003b3e6  mov     edx, edi; length
0x18003b3e8  lea     rcx, [rbp+1060h+sourceString]; sourceString
0x18003b3ec  call    cs:__imp_WindowsCreateStringReference
0x18003b3f2  xor     r12d, r12d
0x18003b3f5  test    eax, eax
0x18003b3f7  js      loc_18003BB86
0x18003b3fd  lea     rax, [rsp+1160h+var_1108]
0x18003b402  mov     [rsp+1160h+var_1138], rax
0x18003b407  mov     [rsp+1160h+var_1140], r12d; int
0x18003b40c  mov     r9, r14
0x18003b40f  mov     r8, [rbp+1060h+var_10B0]
0x18003b413  mov     rdx, [r13+0]
0x18003b417  mov     rcx, rbx
0x18003b41a  mov     rax, [rsi+38h]
0x18003b41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b423  mov     ebx, eax
0x18003b425  test    eax, eax
0x18003b427  jns     short loc_18003B482
0x18003b429  mov     rcx, [rbp+1068h]; this
0x18003b430  mov     r9d, eax; char *
0x18003b433  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003b43a  mov     edx, 7B0h; void *
0x18003b43f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b444  nop
0x18003b445  mov     rcx, [rsp+1160h+var_1108]
0x18003b44a  test    rcx, rcx
0x18003b44d  jz      short loc_18003B461
0x18003b44f  mov     [rsp+1160h+var_1108], r12
0x18003b454  mov     rax, [rcx]
0x18003b457  mov     rax, [rax+10h]
0x18003b45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b460  nop
0x18003b461  mov     rcx, [rsp+1160h+var_1110]
0x18003b466  test    rcx, rcx
0x18003b469  jz      short loc_18003B47D
0x18003b46b  mov     [rsp+1160h+var_1110], r12
0x18003b470  mov     rax, [rcx]
0x18003b473  mov     rax, [rax+10h]
0x18003b477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b47c  nop
0x18003b47d  jmp     loc_18003BA63
0x18003b482  mov     rcx, [rsp+1160h+var_1108]
0x18003b487  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18003b48c  mov     ebx, eax
0x18003b48e  test    eax, eax
0x18003b490  jns     short loc_18003B4EB
0x18003b492  mov     rcx, [rbp+1068h]; this
0x18003b499  mov     r9d, eax; char *
0x18003b49c  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003b4a3  mov     edx, 7B1h; void *
0x18003b4a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b4ad  nop
0x18003b4ae  mov     rcx, [rsp+1160h+var_1108]
0x18003b4b3  test    rcx, rcx
0x18003b4b6  jz      short loc_18003B4CA
  ... truncated ...
```
