# WinStoreAuth::AuthenticationInternal::GetXToken(HWND__ *,WinStoreAuth::PromptType,HSTRING__ *,HSTRING__ *,Windows::System::IUser *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1801e90a0`
- end: `0x1801ea336`
- name: `?GetXToken@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@PEAUHSTRING__@@2PEAUIUser@System@Windows@@PEAPEAU5@4@Z`
- size: `4758`
- prototype: `int __high(HWND, enum WinStoreAuth::PromptType, HSTRING, HSTRING, struct Windows::System::IUser *, HSTRING *, HSTRING *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801e6688`
- `0x1801e8768`
- `0x1801e8b14`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x1800252e8`
- `0x18002c310`
- `0x1800374d0`
- `0x180046ad4`
- `0x18008abbc`
- `0x1800ff76c`
- `0x18012e884`
- `0x1801df000`
- `0x1801e8500`
- `0x1801e90a0`
- `0x1801eaa04`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801e9423`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801e9423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801ea1ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801ea26c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801ea1ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801ea26c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9162`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e93d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9527`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e95bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e96ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e97b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e987a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e98ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9911`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9a02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9a43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9b6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9bad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9c50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9d34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9d75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9dcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9e0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ea2e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ea2f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9162`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e93d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9527`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e95bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e96ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e97b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e987a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e98ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9911`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9a02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9a43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9b6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9bad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9c50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9d34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9d75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9dcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e9e0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ea2e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ea2f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e941a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e99b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9aa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9ab4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9e61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9f4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9f5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9f84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e941a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e99b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9aa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9ab4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9e61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9f4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9f5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e9f84`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801e91aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801e91aa`

## string_xrefs

- `0x1801e9aee`: `x-xbl-contract-version:2\nAccept:application/json`
- `0x1801e9ea6`: `x-xbl-contract-version:2\nAccept:application/json`
- `0x1801e9fa2`: `x-xbl-contract-version:2\nAccept:application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetXToken(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        __int64 a4,
        __int64 a5,
        HSTRING *a6,
        HSTRING *a7)
{
  int SlsValue; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  HRESULT v11; // eax
  LPVOID v12; // rcx
  int v13; // eax
  LPVOID v14; // rcx
  int v15; // eax
  WinStoreAuth::AuthenticationInternal *v16; // rcx
  LPVOID v17; // rcx
  int v18; // eax
  LPVOID v19; // rcx
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  LPVOID v22; // rcx
  PCWSTR StringRawBuffer; // rax
  unsigned int v24; // esi
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64 *); // rbx
  int v27; // eax
  LPVOID v28; // rcx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64 *); // rbx
  int v31; // eax
  LPVOID v32; // rcx
  int v33; // eax
  LPVOID v34; // rcx
  int v35; // eax
  LPVOID v36; // rcx
  LPVOID v37; // rcx
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, __int64, _QWORD); // rbx
  int v40; // eax
  LPVOID v41; // rcx
  __int64 (__fastcall ***v42)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v43)(_QWORD, GUID *, __int64 *); // rdi
  int v44; // eax
  LPVOID v45; // rcx
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, HSTRING *); // rbx
  int v48; // eax
  LPVOID v49; // rcx
  LPVOID v50; // rdi
  __int64 (__fastcall *v51)(LPVOID, PCWSTR, __int64 *); // rbx
  PCWSTR v52; // rax
  int v53; // eax
  LPVOID v54; // rcx
  LPVOID v55; // r14
  __int64 (__fastcall *v56)(LPVOID, _QWORD, __int64, const wchar_t *); // rsi
  int v57; // edi
  WinStoreAuth::AuthenticationInternal *v58; // rcx
  bool IsPlatformXbox; // al
  const wchar_t *v60; // r9
  int v61; // eax
  LPVOID v62; // rcx
  __int64 v63; // rdi
  __int64 (__fastcall *v64)(__int64, PCNZWCH *); // rbx
  int v65; // eax
  LPVOID v66; // rcx
  __int64 v67; // rdi
  __int64 (__fastcall *v68)(__int64, PCNZWCH *); // rbx
  int v69; // eax
  LPVOID v70; // rcx
  LPVOID v71; // r14
  __int64 (__fastcall *v72)(LPVOID, const wchar_t *, PCWSTR, const wchar_t *); // rsi
  PCWSTR v73; // rdi
  WinStoreAuth::AuthenticationInternal *v74; // rcx
  bool v75; // al
  const wchar_t *v76; // rdx
  int v77; // eax
  LPVOID v78; // rcx
  LPVOID v79; // r14
  __int64 (__fastcall *v80)(LPVOID, _QWORD, PCWSTR, const wchar_t *); // rsi
  int v81; // edi
  WinStoreAuth::AuthenticationInternal *v82; // rcx
  const wchar_t *v83; // r15
  PCWSTR v84; // rax
  int v85; // eax
  LPVOID v86; // rcx
  __int64 v87; // rdi
  __int64 (__fastcall *v88)(__int64, PCNZWCH *); // rbx
  int v89; // eax
  LPVOID v90; // rcx
  __int64 v91; // rdi
  __int64 (__fastcall *v92)(__int64, PCNZWCH *); // rbx
  int v93; // eax
  LPVOID v94; // rcx
  int v95; // eax
  LPVOID v96; // rcx
  HRESULT v97; // eax
  LPVOID v98; // rcx
  int v99; // eax
  LPVOID v100; // rcx
  HRESULT v101; // eax
  LPVOID v102; // rcx
  LPVOID v103; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  LPVOID *ppvb; // [rsp+20h] [rbp-E0h]
  LPVOID v108; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  __int64 v110; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v111[8]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v112; // [rsp+90h] [rbp-70h] BYREF
  __int64 v113; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v114; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v115; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v116; // [rsp+B0h] [rbp-50h] BYREF
  __int64 (__fastcall ***v117)(_QWORD, GUID *, __int64 *); // [rsp+B8h] [rbp-48h] BYREF
  __int64 v118; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING newString; // [rsp+C8h] [rbp-38h] BYREF
  PCNZWCH v120; // [rsp+D0h] [rbp-30h] BYREF
  PCNZWCH sourceString; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v122; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v123; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v124; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING v125; // [rsp+F8h] [rbp-8h] BYREF
  UINT32 length[2]; // [rsp+100h] [rbp+0h] BYREF
  HSTRING *v127; // [rsp+110h] [rbp+10h]
  HSTRING_HEADER hstringHeader; // [rsp+118h] [rbp+18h] BYREF
  __int64 v129; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v127 = a7;
  *(_QWORD *)length = 0;
  sourceString = 0;
  v120 = 0;
  *a6 = 0;
  *a7 = 0;
  newString = 0;
  WindowsDeleteString(0);
  v125 = 0;
  SlsValue = WinStoreAuth::GetSlsValue(5, &v125);
  v9 = SlsValue;
  if ( SlsValue < 0 )
  {
    v10 = 975;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)SlsValue,
      ppv);
    goto LABEL_123;
  }
  SlsValue = Microsoft::WRL::Wrappers::HString::Set(&newString, (HSTRING *)length);
  v9 = SlsValue;
  if ( SlsValue < 0 )
  {
    v10 = 977;
    goto LABEL_5;
  }
  if ( !newString )
  {
    WindowsDeleteString(0);
    newString = 0;
    SlsValue = WinStoreAuth::GetSlsValue(6, &newString);
    v9 = SlsValue;
    if ( SlsValue < 0 )
    {
      v10 = 980;
      goto LABEL_5;
    }
  }
  v108 = 0;
  v11 = CoCreateInstance(
          &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
          0,
          0x17u,
          &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
          &v108);
  v9 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v11,
      ppva);
    v12 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_123;
  }
  v110 = 0;
  v13 = Microsoft::WRL::ComPtr<IXblAuthManager>::As<IClientSecurity>(&v108, &v110);
  v9 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v13,
      ppva);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
    v14 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_123;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64, __int64))(*(_QWORD *)v110 + 32LL))(
          v110,
          v108,
          0xFFFFFFFFLL,
          0xFFFFFFFFLL);
  v9 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v15,
      -1);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
    v17 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_123;
  }
  if ( !a3 )
  {
    if ( a5 && WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v16) )
    {
      v112 = 0;
      v129 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.System.Internal.UserManager",
        0x24u,
        0x23u);
      v18 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(
              v129,
              &v112);
      v9 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x414,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v18,
          -1);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v19 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
        }
        goto LABEL_123;
      }
      string = 0;
      v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a5 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v21 = v20(a5, &string);
      v9 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x417,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v21,
          -1);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v22 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
        }
        goto LABEL_123;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v24 = _o__wtoi(StringRawBuffer);
      v113 = 0;
      v25 = v112;
      v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v112 + 96LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
      v27 = v26(v25, v24, &v113);
      v9 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x41B,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v27,
          -1);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v28 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
        }
        goto LABEL_123;
      }
      v115 = 0;
      v29 = v113;
      v30 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v113 + 88LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
      v31 = v30(v29, &v115);
      v9 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x41E,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v31,
          -1);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v32 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
        }
        goto LABEL_123;
      }
      v116 = 0;
      v33 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
              &v115,
              &v116);
      v9 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x421,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v33,
          -1);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v116);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v34 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
        }
        goto LABEL_123;
      }
      v111[0] = 0;
      v35 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v116 + 64LL))(v116, qword_1802CB2E8, v111);
      v9 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x424,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v35,
          -1);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v116);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v36 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
        }
        goto LABEL_123;
      }
      if ( !v111[0] )
      {
        v9 = -2147023579;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x427,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)0x80070525LL,
          -1);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v116);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v37 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v37 + 16LL))(v37);
        }
        goto LABEL_123;
      }
      v117 = 0;
      v38 = v116;
      v39 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v116 + 48LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v117);
      v40 = v39(v38, qword_1802CB2E8, &v117);
      v9 = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x42B,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v40,
          -1);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v117);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v116);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v41 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v41 + 16LL))(v41);
        }
        goto LABEL_123;
      }
      v118 = 0;
      v42 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v117;
      v43 = **v117;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v118);
      v44 = v43(v42, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v118);
      v9 = v44;
      if ( v44 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x42E,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v44,
          -1);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v118);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v117);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v116);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v45 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v45 + 16LL))(v45);
        }
        goto LABEL_123;
      }
      v114 = 0;
      v46 = v118;
      v47 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v118 + 152LL);
      WindowsDeleteString(0);
      v114 = 0;
      v48 = v47(v46, &v114);
      v9 = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x431,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v48,
          -1);
        WindowsDeleteString(v114);
        v114 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v118);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v117);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v116);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v49 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v49 + 16LL))(v49);
        }
        goto LABEL_123;
      }
      v123 = 0;
      v50 = v108;
      v51 = *(__int64 (__fastcall **)(LPVOID, PCWSTR, __int64 *))(*(_QWORD *)v108 + 552LL);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v123,
        0);
      v52 = WindowsGetStringRawBuffer(v114, 0);
      v53 = v51(v50, v52, &v123);
      v9 = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x434,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v53,
          -1);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v123);
        WindowsDeleteString(v114);
        v114 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v118);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v117);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v116);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v54 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v54 + 16LL))(v54);
        }
        goto LABEL_123;
      }
      v122 = 0;
      v55 = v108;
      v56 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, const wchar_t *))(*(_QWORD *)v108 + 456LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v122);
      WindowsGetStringRawBuffer(newString, 0);
      v57 = (unsigned int)WindowsGetStringRawBuffer(v125, 0);
      IsPlatformXbox = WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v58);
      v60 = L"S-1-15-2-903380885-3144618533-3326689759-1293738580-1356288723-3824823557-3342340653";
      if ( !IsPlatformXbox )
        v60 = L"S-1-15-2-1609473798-1231923017-684268153-4268514328-882773646-2760585773-1760938157";
      LODWORD(ppvb) = v57;
      v61 = v56(v55, 0, v123, v60);
      v9 = v61;
      if ( v61 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x443,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v61,
          v57);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v122);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v123);
        WindowsDeleteString(v114);
        v114 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v118);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v117);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v116);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v62 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v62 + 16LL))(v62);
        }
        goto LABEL_123;
      }
      v63 = v122;
      v64 = *(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v122 + 40LL);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &sourceString,
        0);
      v65 = v64(v63, &sourceString);
      v9 = v65;
      if ( v65 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x445,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v65,
          (int)ppvb);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v122);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v123);
        WindowsDeleteString(v114);
        v114 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v118);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v117);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v116);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v66 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
        }
        goto LABEL_123;
      }
      v67 = v122;
      v68 = *(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v122 + 48LL);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v120,
        0);
      v69 = v68(v67, &v120);
      v9 = v69;
      if ( v69 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x446,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v69,
          (int)ppvb);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v122);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v123);
        WindowsDeleteString(v114);
        v114 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v118);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v117);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v116);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v70 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v70 + 16LL))(v70);
        }
        goto LABEL_123;
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v122);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v123);
      WindowsDeleteString(v114);
      v114 = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v118);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v117);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v116);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v112);
      goto LABEL_104;
    }
    v71 = v108;
    v72 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, PCWSTR, const wchar_t *))(*(_QWORD *)v108 + 504LL);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v120,
      0);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &sourceString,
      0);
    WindowsGetStringRawBuffer(newString, 0);
    v73 = WindowsGetStringRawBuffer(v125, 0);
    v75 = WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v74);
    v76 = L"S-1-15-2-903380885-3144618533-3326689759-1293738580-1356288723-3824823557-3342340653";
    if ( !v75 )
      v76 = L"S-1-15-2-1609473798-1231923017-684268153-4268514328-882773646-2760585773-1760938157";
    ppvb = (LPVOID *)L"GET";
    v77 = v72(v71, v76, v73, L"MBI_SSL");
    v9 = v77;
    if ( v77 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40F,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v77,
        (int)L"GET");
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
      v78 = v108;
      if ( v108 )
      {
        v108 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v78 + 16LL))(v78);
      }
      goto LABEL_123;
    }
LABEL_104:
    *(_QWORD *)length = 0;
    v95 = StringCchLengthW(sourceString, 0x7FFFFFFFu, (unsigned __int64 *)length);
    v9 = v95;
    if ( v95 >= 0 )
    {
      v97 = WindowsCreateString(sourceString, length[0], a6);
      v9 = v97;
      if ( v97 >= 0 )
      {
        *(_QWORD *)length = 0;
        v99 = StringCchLengthW(v120, 0x7FFFFFFFu, (unsigned __int64 *)length);
        v9 = v99;
        if ( v99 >= 0 )
        {
          v101 = WindowsCreateString(v120, length[0], v127);
          v9 = v101;
          if ( v101 >= 0 )
          {
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
            v103 = v108;
            if ( v108 )
            {
              v108 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v103 + 16LL))(v103);
            }
            v9 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x464,
              (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
              (const char *)(unsigned int)v101,
              (int)ppvb);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
            v102 = v108;
            if ( v108 )
            {
              v108 = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v102 + 16LL))(v102);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x463,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)v99,
            (int)ppvb);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
          v100 = v108;
          if ( v108 )
          {
            v108 = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v100 + 16LL))(v100);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x460,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v97,
          (int)ppvb);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
        v98 = v108;
        if ( v108 )
        {
          v108 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v98 + 16LL))(v98);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45F,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v95,
        (int)ppvb);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
      v96 = v108;
      if ( v108 )
      {
        v108 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v96 + 16LL))(v96);
      }
    }
    goto LABEL_123;
  }
  v124 = 0;
  v79 = v108;
  v80 = *(__int64 (__fastcall **)(LPVOID, _QWORD, PCWSTR, const wchar_t *))(*(_QWORD *)v108 + 456LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v124);
  WindowsGetStringRawBuffer(newString, 0);
  v81 = (unsigned int)WindowsGetStringRawBuffer(v125, 0);
  v83 = L"S-1-15-2-903380885-3144618533-3326689759-1293738580-1356288723-3824823557-3342340653";
  if ( !WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v82) )
    v83 = L"S-1-15-2-1609473798-1231923017-684268153-4268514328-882773646-2760585773-1760938157";
  v84 = WindowsGetStringRawBuffer(a3, 0);
  LODWORD(ppvb) = v81;
  v85 = v80(v79, 0, v84, v83);
  v9 = v85;
  if ( v85 >= 0 )
  {
    v87 = v124;
    v88 = *(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v124 + 40LL);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &sourceString,
      0);
    v89 = v88(v87, &sourceString);
    v9 = v89;
    if ( v89 >= 0 )
    {
      v91 = v124;
      v92 = *(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v124 + 48LL);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v120,
        0);
      v93 = v92(v91, &v120);
      v9 = v93;
      if ( v93 >= 0 )
      {
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v124);
        goto LABEL_104;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45B,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v93,
        (int)ppvb);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v124);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
      v94 = v108;
      if ( v108 )
      {
        v108 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v94 + 16LL))(v94);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v89,
        (int)ppvb);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v124);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
      v90 = v108;
      if ( v108 )
      {
        v108 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v90 + 16LL))(v90);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x458,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v85,
      v81);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v124);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
    v86 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v86 + 16LL))(v86);
    }
  }
LABEL_123:
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(v125);
  v125 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v120);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
  return v9;
}

```

## disassembly

```asm
0x1801e90a0  push    rbp
0x1801e90a2  push    rbx
0x1801e90a3  push    rsi
0x1801e90a4  push    rdi
0x1801e90a5  push    r12
0x1801e90a7  push    r13
0x1801e90a9  push    r14
0x1801e90ab  push    r15
0x1801e90ad  lea     rbp, [rsp-48h]
0x1801e90b2  sub     rsp, 148h
0x1801e90b9  mov     rax, cs:__security_cookie
0x1801e90c0  xor     rax, rsp
0x1801e90c3  mov     [rbp+80h+var_48], rax
0x1801e90c7  mov     r12, r8
0x1801e90ca  mov     rdi, [rbp+80h+arg_20]
0x1801e90d1  mov     r13, [rbp+80h+arg_28]
0x1801e90d8  mov     rax, [rbp+80h+arg_30]
0x1801e90df  mov     [rbp+80h+var_70], rax
0x1801e90e3  xor     r14d, r14d
0x1801e90e6  mov     qword ptr [rbp+80h+length], r14
0x1801e90ea  mov     [rbp+80h+sourceString], r14
0x1801e90ee  mov     [rbp+80h+var_B0], r14
0x1801e90f2  mov     [r13+0], r14
0x1801e90f6  mov     [rax], r14
0x1801e90f9  mov     [rbp+80h+var_88], r14
0x1801e90fd  mov     [rbp+80h+newString], r14
0x1801e9101  xor     ecx, ecx; string
0x1801e9103  call    cs:__imp_WindowsDeleteString
0x1801e9109  mov     [rbp+80h+var_88], r14
0x1801e910d  lea     rdx, [rbp+80h+var_88]
0x1801e9111  lea     ecx, [r14+5]
0x1801e9115  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x1801e911a  mov     ebx, eax
0x1801e911c  test    eax, eax
0x1801e911e  jns     short loc_1801E9127
0x1801e9120  mov     edx, 3CFh
0x1801e9125  jmp     short loc_1801E913F
0x1801e9127  lea     rdx, [rbp+80h+length]; HSTRING *
0x1801e912b  lea     rcx, [rbp+80h+newString]; newString
0x1801e912f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1801e9134  mov     ebx, eax
0x1801e9136  test    eax, eax
0x1801e9138  jns     short loc_1801E915A
0x1801e913a  mov     edx, 3D1h; void *
0x1801e913f  mov     rcx, [rbp+88h]; this
0x1801e9146  mov     r9d, eax; char *
0x1801e9149  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e9150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e9155  jmp     loc_1801EA2E5
0x1801e915a  cmp     [rbp+80h+newString], r14
0x1801e915e  jnz     short loc_1801E9187
0x1801e9160  xor     ecx, ecx; string
0x1801e9162  call    cs:__imp_WindowsDeleteString
0x1801e9168  mov     [rbp+80h+newString], r14
0x1801e916c  lea     rdx, [rbp+80h+newString]
0x1801e9170  mov     ecx, 6
0x1801e9175  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x1801e917a  mov     ebx, eax
0x1801e917c  test    eax, eax
0x1801e917e  jns     short loc_1801E9187
0x1801e9180  mov     edx, 3D4h
0x1801e9185  jmp     short loc_1801E913F
0x1801e9187  mov     [rsp+180h+var_110], r14
0x1801e918c  lea     rax, [rsp+180h+var_110]
0x1801e9191  mov     [rsp+180h+ppv], rax; int
0x1801e9196  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x1801e919d  xor     edx, edx; pUnkOuter
0x1801e919f  lea     r8d, [rdx+17h]; dwClsContext
0x1801e91a3  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x1801e91aa  call    cs:__imp_CoCreateInstance
0x1801e91b0  mov     ebx, eax
0x1801e91b2  test    eax, eax
0x1801e91b4  jns     short loc_1801E91F3
0x1801e91b6  mov     rcx, [rbp+88h]; this
0x1801e91bd  mov     r9d, eax; char *
0x1801e91c0  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e91c7  mov     edx, 3D8h; void *
0x1801e91cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e91d1  nop
0x1801e91d2  mov     rcx, [rsp+180h+var_110]
0x1801e91d7  test    rcx, rcx
0x1801e91da  jz      short loc_1801E91EE
0x1801e91dc  mov     [rsp+180h+var_110], r14
0x1801e91e1  mov     rax, [rcx]
0x1801e91e4  mov     rax, [rax+10h]
0x1801e91e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e91ed  nop
0x1801e91ee  jmp     loc_1801EA2E5
0x1801e91f3  mov     [rbp+80h+var_100], r14
0x1801e91f7  lea     rdx, [rbp+80h+var_100]
0x1801e91fb  lea     rcx, [rsp+180h+var_110]
0x1801e9200  call    ??$As@UIClientSecurity@@@?$ComPtr@UIXblAuthManager@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIClientSecurity@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXblAuthManager>::As<IClientSecurity>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IClientSecurity>>)
0x1801e9205  mov     ebx, eax
0x1801e9207  test    eax, eax
0x1801e9209  jns     short loc_1801E9252
0x1801e920b  mov     rcx, [rbp+88h]; this
0x1801e9212  mov     r9d, eax; char *
0x1801e9215  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e921c  mov     edx, 3FDh; void *
0x1801e9221  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e9226  nop
0x1801e9227  lea     rcx, [rbp+80h+var_100]
0x1801e922b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e9230  nop
0x1801e9231  mov     rcx, [rsp+180h+var_110]
0x1801e9236  test    rcx, rcx
0x1801e9239  jz      short loc_1801E924D
0x1801e923b  mov     [rsp+180h+var_110], r14
0x1801e9240  mov     rax, [rcx]
0x1801e9243  mov     rax, [rax+10h]
0x1801e9247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e924c  nop
0x1801e924d  jmp     loc_1801EA2E5
0x1801e9252  mov     rcx, [rbp+80h+var_100]
0x1801e9256  mov     rax, [rcx]
0x1801e9259  mov     dword ptr [rsp+180h+var_140], 40h ; '@'
0x1801e9261  mov     [rsp+180h+var_148], r14
0x1801e9266  mov     dword ptr [rsp+180h+var_150], 3
0x1801e926e  mov     dword ptr [rsp+180h+var_158], r14d
0x1801e9273  mov     [rsp+180h+ppv], 0FFFFFFFFFFFFFFFFh; int
0x1801e927c  or      r8d, 0FFFFFFFFh
0x1801e9280  mov     r9d, r8d
0x1801e9283  mov     rdx, [rsp+180h+var_110]
0x1801e9288  mov     rax, [rax+20h]
0x1801e928c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9291  mov     ebx, eax
0x1801e9293  test    eax, eax
0x1801e9295  jns     short loc_1801E92DE
0x1801e9297  mov     rcx, [rbp+88h]; this
0x1801e929e  mov     r9d, eax; char *
0x1801e92a1  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e92a8  mov     edx, 3FEh; void *
0x1801e92ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e92b2  nop
0x1801e92b3  lea     rcx, [rbp+80h+var_100]
0x1801e92b7  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e92bc  nop
0x1801e92bd  mov     rcx, [rsp+180h+var_110]
0x1801e92c2  test    rcx, rcx
0x1801e92c5  jz      short loc_1801E92D9
0x1801e92c7  mov     [rsp+180h+var_110], r14
0x1801e92cc  mov     rax, [rcx]
0x1801e92cf  mov     rax, [rax+10h]
0x1801e92d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e92d8  nop
0x1801e92d9  jmp     loc_1801EA2E5
0x1801e92de  test    r12, r12
0x1801e92e1  jnz     loc_1801E9F2C
0x1801e92e7  test    rdi, rdi
0x1801e92ea  jz      loc_1801E9E27
0x1801e92f0  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x1801e92f5  test    al, al
0x1801e92f7  jz      loc_1801E9E27
0x1801e92fd  mov     [rbp+80h+var_F0], r14
0x1801e9301  mov     [rbp+80h+var_50], r14
0x1801e9305  lea     r9d, [r12+23h]; unsigned int
0x1801e930a  lea     r8d, [r12+24h]; unsigned int
0x1801e930f  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x1801e9316  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x1801e931a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801e931f  lea     rdx, [rbp+80h+var_F0]
0x1801e9323  mov     rcx, [rbp+80h+var_50]
0x1801e9327  call    ??$GetActivationFactory@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>)
0x1801e932c  mov     ebx, eax
0x1801e932e  test    eax, eax
0x1801e9330  jns     short loc_1801E9383
0x1801e9332  mov     rcx, [rbp+88h]; this
0x1801e9339  mov     r9d, eax; char *
0x1801e933c  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e9343  mov     edx, 414h; void *
0x1801e9348  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e934d  nop
0x1801e934e  lea     rcx, [rbp+80h+var_F0]
0x1801e9352  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e9357  nop
0x1801e9358  lea     rcx, [rbp+80h+var_100]
0x1801e935c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e9361  nop
0x1801e9362  mov     rcx, [rsp+180h+var_110]
0x1801e9367  test    rcx, rcx
0x1801e936a  jz      short loc_1801E937E
0x1801e936c  mov     [rsp+180h+var_110], r14
0x1801e9371  mov     rax, [rcx]
0x1801e9374  mov     rax, [rax+10h]
0x1801e9378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e937d  nop
0x1801e937e  jmp     loc_1801EA2E5
0x1801e9383  mov     [rsp+180h+string], r14
0x1801e9388  mov     rax, [rdi]
0x1801e938b  mov     rbx, [rax+30h]
0x1801e938f  xor     ecx, ecx; string
0x1801e9391  call    cs:__imp_WindowsDeleteString
0x1801e9397  mov     [rsp+180h+string], r14
0x1801e939c  lea     rdx, [rsp+180h+string]
0x1801e93a1  mov     rcx, rdi
0x1801e93a4  mov     rax, rbx
0x1801e93a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e93ac  mov     ebx, eax
0x1801e93ae  test    eax, eax
0x1801e93b0  jns     short loc_1801E9413
0x1801e93b2  mov     rcx, [rbp+88h]; this
0x1801e93b9  mov     r9d, eax; char *
0x1801e93bc  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e93c3  mov     edx, 417h; void *
0x1801e93c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e93cd  nop
0x1801e93ce  mov     rcx, [rsp+180h+string]; string
0x1801e93d3  call    cs:__imp_WindowsDeleteString
0x1801e93d9  mov     [rsp+180h+string], r14
0x1801e93de  lea     rcx, [rbp+80h+var_F0]
0x1801e93e2  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e93e7  nop
0x1801e93e8  lea     rcx, [rbp+80h+var_100]
0x1801e93ec  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e93f1  nop
0x1801e93f2  mov     rcx, [rsp+180h+var_110]
0x1801e93f7  test    rcx, rcx
0x1801e93fa  jz      short loc_1801E940E
0x1801e93fc  mov     [rsp+180h+var_110], r14
0x1801e9401  mov     rax, [rcx]
0x1801e9404  mov     rax, [rax+10h]
0x1801e9408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e940d  nop
0x1801e940e  jmp     loc_1801EA2E5
0x1801e9413  xor     edx, edx; length
0x1801e9415  mov     rcx, [rsp+180h+string]; string
0x1801e941a  call    cs:__imp_WindowsGetStringRawBuffer
0x1801e9420  mov     rcx, rax
0x1801e9423  call    cs:__imp__o__wtoi
0x1801e9429  mov     esi, eax
0x1801e942b  mov     [rbp+80h+var_E8], r14
0x1801e942f  mov     rdi, [rbp+80h+var_F0]
0x1801e9433  mov     rcx, [rdi]
0x1801e9436  mov     rbx, [rcx+60h]
0x1801e943a  lea     rcx, [rbp+80h+var_E8]
0x1801e943e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e9443  lea     r8, [rbp+80h+var_E8]
0x1801e9447  mov     edx, esi
0x1801e9449  mov     rcx, rdi
0x1801e944c  mov     rax, rbx
0x1801e944f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9454  mov     ebx, eax
0x1801e9456  test    eax, eax
0x1801e9458  jns     short loc_1801E94C5
0x1801e945a  mov     rcx, [rbp+88h]; this
0x1801e9461  mov     r9d, eax; char *
0x1801e9464  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e946b  mov     edx, 41Bh; void *
0x1801e9470  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e9475  nop
0x1801e9476  lea     rcx, [rbp+80h+var_E8]
0x1801e947a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e947f  nop
0x1801e9480  mov     rcx, [rsp+180h+string]; string
0x1801e9485  call    cs:__imp_WindowsDeleteString
0x1801e948b  mov     [rsp+180h+string], r14
0x1801e9490  lea     rcx, [rbp+80h+var_F0]
0x1801e9494  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e9499  nop
0x1801e949a  lea     rcx, [rbp+80h+var_100]
0x1801e949e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e94a3  nop
0x1801e94a4  mov     rcx, [rsp+180h+var_110]
0x1801e94a9  test    rcx, rcx
0x1801e94ac  jz      short loc_1801E94C0
0x1801e94ae  mov     [rsp+180h+var_110], r14
0x1801e94b3  mov     rax, [rcx]
0x1801e94b6  mov     rax, [rax+10h]
0x1801e94ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e94bf  nop
0x1801e94c0  jmp     loc_1801EA2E5
0x1801e94c5  mov     [rbp+80h+var_D8], r14
0x1801e94c9  mov     rdi, [rbp+80h+var_E8]
0x1801e94cd  mov     rax, [rdi]
0x1801e94d0  mov     rbx, [rax+58h]
0x1801e94d4  lea     rcx, [rbp+80h+var_D8]
0x1801e94d8  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e94dd  lea     rdx, [rbp+80h+var_D8]
0x1801e94e1  mov     rcx, rdi
0x1801e94e4  mov     rax, rbx
0x1801e94e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e94ec  mov     ebx, eax
0x1801e94ee  test    eax, eax
0x1801e94f0  jns     short loc_1801E9567
0x1801e94f2  mov     rcx, [rbp+88h]; this
0x1801e94f9  mov     r9d, eax; char *
0x1801e94fc  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e9503  mov     edx, 41Eh; void *
0x1801e9508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e950d  nop
0x1801e950e  lea     rcx, [rbp+80h+var_D8]
0x1801e9512  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e9517  nop
0x1801e9518  lea     rcx, [rbp+80h+var_E8]
0x1801e951c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e9521  nop
0x1801e9522  mov     rcx, [rsp+180h+string]; string
0x1801e9527  call    cs:__imp_WindowsDeleteString
0x1801e952d  mov     [rsp+180h+string], r14
0x1801e9532  lea     rcx, [rbp+80h+var_F0]
  ... truncated ...
```
