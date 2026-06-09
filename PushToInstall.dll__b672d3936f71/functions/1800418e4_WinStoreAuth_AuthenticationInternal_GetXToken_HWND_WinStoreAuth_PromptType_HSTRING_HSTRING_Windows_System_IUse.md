# WinStoreAuth::AuthenticationInternal::GetXToken(HWND__ *,WinStoreAuth::PromptType,HSTRING__ *,HSTRING__ *,Windows::System::IUser *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800418e4`
- end: `0x180042154`
- name: `?GetXToken@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@PEAUHSTRING__@@2PEAUIUser@System@Windows@@PEAPEAU5@4@Z`
- size: `2160`
- prototype: `int __high(HWND, enum WinStoreAuth::PromptType, HSTRING, HSTRING, struct Windows::System::IUser *, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003ef6c`

## callees

- `0x180010b84`
- `0x1800380ac`
- `0x180039bb4`
- `0x180040e90`
- `0x1800418e4`
- `0x180042640`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041b94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041bba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041b94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041bca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041bd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041cdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041ceb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041d16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041bca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041bd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041cdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041ceb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041d16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800419ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800419ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041923`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004195c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004196a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004199e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800419c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041ca7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041cb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042107`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041923`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004195c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004196a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004199e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800419c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041ca7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041cb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042107`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180041fa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180042071`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180041fa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180042071`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041a12`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041a12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004197d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004198d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041b8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004197d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004198d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041b8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042138`

## string_xrefs

- `0x180041c17`: `x-xbl-contract-version:2\nAccept:application/json`
- `0x180041d37`: `x-xbl-contract-version:2\nAccept:application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=155
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetXToken(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        __int64 a4,
        __int64 a5,
        HSTRING *a6,
        HSTRING *a7)
{
  HRESULT SlsValue; // ebx
  __int64 v9; // rdx
  HRESULT v11; // eax
  LPVOID v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  LPVOID v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  LPVOID v18; // rcx
  LPVOID v19; // rsi
  __int64 (__fastcall *v20)(LPVOID, const wchar_t *, PCWSTR, const wchar_t *); // r14
  void *v21; // rdi
  DWORD LastError; // ebx
  wchar_t *v23; // rdi
  DWORD v24; // ebx
  PCWSTR v25; // rdi
  WinStoreAuth::AuthenticationInternal *v26; // rcx
  bool v27; // al
  const wchar_t *v28; // rcx
  int v29; // eax
  size_t v30; // rdx
  __int64 v31; // rcx
  LPVOID v32; // rcx
  LPVOID v33; // r14
  __int64 (__fastcall *v34)(LPVOID, _QWORD, PCWSTR, const wchar_t *); // rsi
  int StringRawBuffer; // edi
  WinStoreAuth::AuthenticationInternal *v36; // rcx
  bool IsPlatformXbox; // al
  const wchar_t *v38; // rcx
  PCWSTR v39; // rax
  int v40; // eax
  size_t v41; // rcx
  __int64 v42; // rcx
  LPVOID v43; // rcx
  size_t v44; // rdi
  __int64 (__fastcall *v45)(size_t, void **); // rbx
  void **v46; // rax
  int v47; // eax
  size_t v48; // rcx
  __int64 v49; // rcx
  LPVOID v50; // rcx
  size_t v51; // rdi
  __int64 (__fastcall *v52)(size_t, void **); // rbx
  void **v53; // rax
  int v54; // eax
  size_t v55; // rcx
  __int64 v56; // rcx
  LPVOID v57; // rcx
  size_t v58; // rcx
  HRESULT v59; // eax
  __int64 v60; // rcx
  LPVOID v61; // rcx
  HRESULT v62; // eax
  size_t v63; // rdx
  __int64 v64; // rcx
  LPVOID v65; // rcx
  HRESULT v66; // eax
  __int64 v67; // rcx
  LPVOID v68; // rcx
  HRESULT v69; // eax
  __int64 v70; // rcx
  LPVOID v71; // rcx
  __int64 v72; // rcx
  LPVOID v73; // rcx
  int ppv; // [rsp+20h] [rbp-91h]
  int ppva; // [rsp+20h] [rbp-91h]
  LPVOID *ppvb; // [rsp+20h] [rbp-91h]
  HSTRING string; // [rsp+70h] [rbp-41h] BYREF
  HSTRING v78; // [rsp+78h] [rbp-39h] BYREF
  LPVOID v79; // [rsp+80h] [rbp-31h] BYREF
  __int64 v80; // [rsp+88h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-21h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+98h] [rbp-19h] BYREF
  size_t pcchLength; // [rsp+A0h] [rbp-11h] BYREF
  const wchar_t *v84; // [rsp+A8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+47h]

  psz = 0;
  pv = 0;
  *a6 = 0;
  *a7 = 0;
  string = 0;
  WindowsDeleteString(0);
  v78 = 0;
  SlsValue = WinStoreAuth::GetSlsValue(5, &v78);
  if ( SlsValue < 0 )
  {
    v9 = 975;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)SlsValue,
      ppv);
LABEL_4:
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v78);
    v78 = 0;
    if ( pv )
      CoTaskMemFree(pv);
    if ( psz )
      CoTaskMemFree((LPVOID)psz);
    return (unsigned int)SlsValue;
  }
  WindowsDeleteString(string);
  string = 0;
  SlsValue = WindowsDuplicateString(0, &string);
  if ( SlsValue < 0 )
  {
    v9 = 977;
    goto LABEL_3;
  }
  if ( !string )
  {
    WindowsDeleteString(0);
    string = 0;
    SlsValue = WinStoreAuth::GetSlsValue(6, &string);
    if ( SlsValue < 0 )
    {
      v9 = 980;
      goto LABEL_3;
    }
  }
  v79 = 0;
  v11 = CoCreateInstance(
          &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
          0,
          0x17u,
          &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
          &v79);
  SlsValue = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v11,
      ppva);
    v12 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_4;
  }
  v80 = 0;
  v13 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v79)(
          v79,
          &GUID_0000013d_0000_0000_c000_000000000046,
          &v80);
  SlsValue = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v13,
      ppva);
    v14 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_4;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64, __int64))(*(_QWORD *)v80 + 32LL))(
          v80,
          v79,
          0xFFFFFFFFLL,
          0xFFFFFFFFLL);
  SlsValue = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v16,
      -1);
    v17 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
    }
    goto LABEL_4;
  }
  if ( a3 )
  {
    pcchLength = 0;
    v33 = v79;
    v34 = *(__int64 (__fastcall **)(LPVOID, _QWORD, PCWSTR, const wchar_t *))(*(_QWORD *)v79 + 456LL);
    WindowsGetStringRawBuffer(string, 0);
    StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(v78, 0);
    IsPlatformXbox = WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v36);
    v38 = L"S-1-15-2-903380885-3144618533-3326689759-1293738580-1356288723-3824823557-3342340653";
    if ( !IsPlatformXbox )
      v38 = L"S-1-15-2-1609473798-1231923017-684268153-4268514328-882773646-2760585773-1760938157";
    v84 = v38;
    v39 = WindowsGetStringRawBuffer(a3, 0);
    LODWORD(ppvb) = StringRawBuffer;
    v40 = v34(v33, 0, v39, v84);
    SlsValue = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x458,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v40,
        StringRawBuffer);
      v41 = pcchLength;
      if ( pcchLength )
      {
        pcchLength = 0;
        (*(void (__fastcall **)(size_t))(*(_QWORD *)v41 + 16LL))(v41);
      }
      v42 = v80;
      if ( v80 )
      {
        v80 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      v43 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v43 + 16LL))(v43);
      }
      goto LABEL_4;
    }
    v44 = pcchLength;
    v45 = *(__int64 (__fastcall **)(size_t, void **))(*(_QWORD *)pcchLength + 40LL);
    v46 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&((void **)&psz);
    v47 = v45(v44, v46);
    SlsValue = v47;
    if ( v47 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v47,
        (int)ppvb);
      v48 = pcchLength;
      if ( pcchLength )
      {
        pcchLength = 0;
        (*(void (__fastcall **)(size_t))(*(_QWORD *)v48 + 16LL))(v48);
      }
      v49 = v80;
      if ( v80 )
      {
        v80 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      v50 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v50 + 16LL))(v50);
      }
      goto LABEL_4;
    }
    v51 = pcchLength;
    v52 = *(__int64 (__fastcall **)(size_t, void **))(*(_QWORD *)pcchLength + 48LL);
    v53 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(&pv);
    v54 = v52(v51, v53);
    SlsValue = v54;
    if ( v54 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45B,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v54,
        (int)ppvb);
      v55 = pcchLength;
      if ( pcchLength )
      {
        pcchLength = 0;
        (*(void (__fastcall **)(size_t))(*(_QWORD *)v55 + 16LL))(v55);
      }
      v56 = v80;
      if ( v80 )
      {
        v80 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      }
      v57 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v57 + 16LL))(v57);
      }
      goto LABEL_4;
    }
    v58 = pcchLength;
    if ( pcchLength )
    {
      pcchLength = 0;
      (*(void (__fastcall **)(size_t))(*(_QWORD *)v58 + 16LL))(v58);
    }
  }
  else
  {
    v19 = v79;
    v20 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, PCWSTR, const wchar_t *))(*(_QWORD *)v79 + 504LL);
    v21 = pv;
    if ( pv )
    {
      LastError = GetLastError();
      CoTaskMemFree(v21);
      SetLastError(LastError);
    }
    pv = 0;
    v23 = (wchar_t *)psz;
    if ( psz )
    {
      v24 = GetLastError();
      CoTaskMemFree(v23);
      SetLastError(v24);
    }
    psz = 0;
    WindowsGetStringRawBuffer(string, 0);
    v25 = WindowsGetStringRawBuffer(v78, 0);
    v27 = WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v26);
    v28 = L"S-1-15-2-903380885-3144618533-3326689759-1293738580-1356288723-3824823557-3342340653";
    if ( !v27 )
      v28 = L"S-1-15-2-1609473798-1231923017-684268153-4268514328-882773646-2760585773-1760938157";
    ppvb = (LPVOID *)L"GET";
    v29 = v20(v19, v28, v25, L"MBI_SSL");
    SlsValue = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40F,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v29,
        (int)L"GET");
      v31 = v80;
      if ( v80 )
      {
        v80 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      v32 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
      }
      goto LABEL_4;
    }
  }
  pcchLength = 0;
  v59 = StringCchLengthW(psz, v30, &pcchLength);
  SlsValue = v59;
  if ( v59 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45F,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v59,
      (int)ppvb);
    v60 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    }
    v61 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v61 + 16LL))(v61);
    }
    goto LABEL_4;
  }
  v62 = WindowsCreateString(psz, pcchLength, a6);
  SlsValue = v62;
  if ( v62 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x460,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v62,
      (int)ppvb);
    v64 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    }
    v65 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v65 + 16LL))(v65);
    }
    goto LABEL_4;
  }
  pcchLength = 0;
  v66 = StringCchLengthW((STRSAFE_PCNZWCH)pv, v63, &pcchLength);
  SlsValue = v66;
  if ( v66 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x463,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v66,
      (int)ppvb);
    v67 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    }
    v68 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v68 + 16LL))(v68);
    }
    goto LABEL_4;
  }
  v69 = WindowsCreateString((PCNZWCH)pv, pcchLength, a7);
  SlsValue = v69;
  if ( v69 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x464,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v69,
      (int)ppvb);
    v70 = v80;
    if ( v80 )
    {
      v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    }
    v71 = v79;
    if ( v79 )
    {
      v79 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v71 + 16LL))(v71);
    }
    goto LABEL_4;
  }
  v72 = v80;
  if ( v80 )
  {
    v80 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
  }
  v73 = v79;
  if ( v79 )
  {
    v79 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v73 + 16LL))(v73);
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v78);
  v78 = 0;
  if ( pv )
    CoTaskMemFree(pv);
  if ( psz )
    CoTaskMemFree((LPVOID)psz);
  return 0;
}

```

## disassembly

```asm
0x1800418e4  push    rbp
0x1800418e6  push    rbx
0x1800418e7  push    rsi
0x1800418e8  push    rdi
0x1800418e9  push    r12
0x1800418eb  push    r13
0x1800418ed  push    r14
0x1800418ef  push    r15
0x1800418f1  lea     rbp, [rsp-7]
0x1800418f6  sub     rsp, 0B8h
0x1800418fd  mov     r13, r8
0x180041900  mov     r15, [rbp+3Fh+arg_28]
0x180041904  mov     r12, [rbp+3Fh+arg_30]
0x180041908  xor     edi, edi
0x18004190a  mov     [rbp+3Fh+psz], rdi
0x18004190e  mov     [rbp+3Fh+pv], rdi
0x180041912  mov     [r15], rdi
0x180041915  mov     [r12], rdi
0x180041919  mov     [rbp+3Fh+var_78], rdi
0x18004191d  mov     [rbp+3Fh+string], rdi
0x180041921  xor     ecx, ecx; string
0x180041923  call    cs:__imp_WindowsDeleteString
0x180041929  mov     [rbp+3Fh+var_78], rdi
0x18004192d  lea     rdx, [rbp+3Fh+var_78]
0x180041931  lea     ecx, [rdi+5]
0x180041934  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x180041939  mov     ebx, eax
0x18004193b  test    eax, eax
0x18004193d  jns     short loc_18004199A
0x18004193f  mov     edx, 3CFh; void *
0x180041944  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18004194b  mov     r9d, ebx; char *
0x18004194e  mov     rcx, [rbp+47h]; this
0x180041952  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041957  nop
0x180041958  mov     rcx, [rbp+3Fh+string]; string
0x18004195c  call    cs:__imp_WindowsDeleteString
0x180041962  mov     [rbp+3Fh+string], rdi
0x180041966  mov     rcx, [rbp+3Fh+var_78]; string
0x18004196a  call    cs:__imp_WindowsDeleteString
0x180041970  mov     [rbp+3Fh+var_78], rdi
0x180041974  mov     rcx, [rbp+3Fh+pv]; pv
0x180041978  test    rcx, rcx
0x18004197b  jz      short loc_180041984
0x18004197d  call    cs:__imp_CoTaskMemFree
0x180041983  nop
0x180041984  mov     rcx, [rbp+3Fh+psz]; pv
0x180041988  test    rcx, rcx
0x18004198b  jz      short loc_180041993
0x18004198d  call    cs:__imp_CoTaskMemFree
0x180041993  mov     eax, ebx
0x180041995  jmp     loc_180042140
0x18004199a  mov     rcx, [rbp+3Fh+string]; string
0x18004199e  call    cs:__imp_WindowsDeleteString
0x1800419a4  mov     [rbp+3Fh+string], rdi
0x1800419a8  lea     rdx, [rbp+3Fh+string]; newString
0x1800419ac  xor     ecx, ecx; string
0x1800419ae  call    cs:__imp_WindowsDuplicateString
0x1800419b4  mov     ebx, eax
0x1800419b6  test    eax, eax
0x1800419b8  jns     short loc_1800419C1
0x1800419ba  mov     edx, 3D1h
0x1800419bf  jmp     short loc_180041944
0x1800419c1  cmp     [rbp+3Fh+string], rdi
0x1800419c5  jnz     short loc_1800419F1
0x1800419c7  xor     ecx, ecx; string
0x1800419c9  call    cs:__imp_WindowsDeleteString
0x1800419cf  mov     [rbp+3Fh+string], rdi
0x1800419d3  lea     rdx, [rbp+3Fh+string]
0x1800419d7  mov     ecx, 6
0x1800419dc  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x1800419e1  mov     ebx, eax
0x1800419e3  test    eax, eax
0x1800419e5  jns     short loc_1800419F1
0x1800419e7  mov     edx, 3D4h
0x1800419ec  jmp     loc_180041944
0x1800419f1  mov     [rbp+3Fh+var_70], rdi
0x1800419f5  lea     rax, [rbp+3Fh+var_70]
0x1800419f9  mov     [rsp+0F0h+ppv], rax; int
0x1800419fe  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x180041a05  xor     edx, edx; pUnkOuter
0x180041a07  lea     r8d, [rdx+17h]; dwClsContext
0x180041a0b  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x180041a12  call    cs:__imp_CoCreateInstance
0x180041a18  mov     ebx, eax
0x180041a1a  test    eax, eax
0x180041a1c  jns     short loc_180041A56
0x180041a1e  mov     rcx, [rbp+47h]; this
0x180041a22  mov     r9d, eax; char *
0x180041a25  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180041a2c  mov     edx, 3D8h; void *
0x180041a31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041a36  nop
0x180041a37  mov     rcx, [rbp+3Fh+var_70]
0x180041a3b  test    rcx, rcx
0x180041a3e  jz      short loc_180041A51
0x180041a40  mov     [rbp+3Fh+var_70], rdi
0x180041a44  mov     rax, [rcx]
0x180041a47  mov     rax, [rax+10h]
0x180041a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a50  nop
0x180041a51  jmp     loc_180041958
0x180041a56  mov     [rbp+3Fh+var_68], rdi
0x180041a5a  mov     rcx, [rbp+3Fh+var_70]
0x180041a5e  mov     rax, [rcx]
0x180041a61  lea     r8, [rbp+3Fh+var_68]
0x180041a65  lea     rdx, _GUID_0000013d_0000_0000_c000_000000000046
0x180041a6c  mov     rax, [rax]
0x180041a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a74  mov     ebx, eax
0x180041a76  test    eax, eax
0x180041a78  jns     short loc_180041ACC
0x180041a7a  mov     rcx, [rbp+47h]; this
0x180041a7e  mov     r9d, eax; char *
0x180041a81  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180041a88  mov     edx, 3FDh; void *
0x180041a8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041a92  nop
0x180041a93  mov     rcx, [rbp+3Fh+var_68]
0x180041a97  test    rcx, rcx
0x180041a9a  jz      short loc_180041AAD
0x180041a9c  mov     [rbp+3Fh+var_68], rdi
0x180041aa0  mov     rax, [rcx]
0x180041aa3  mov     rax, [rax+10h]
0x180041aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041aac  nop
0x180041aad  mov     rcx, [rbp+3Fh+var_70]
0x180041ab1  test    rcx, rcx
0x180041ab4  jz      short loc_180041AC7
0x180041ab6  mov     [rbp+3Fh+var_70], rdi
0x180041aba  mov     rax, [rcx]
0x180041abd  mov     rax, [rax+10h]
0x180041ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ac6  nop
0x180041ac7  jmp     loc_180041958
0x180041acc  mov     rcx, [rbp+3Fh+var_68]
0x180041ad0  mov     rax, [rcx]
0x180041ad3  mov     dword ptr [rsp+0F0h+var_B0], 40h ; '@'
0x180041adb  mov     [rsp+0F0h+var_B8], rdi
0x180041ae0  mov     dword ptr [rsp+0F0h+var_C0], 3
0x180041ae8  mov     dword ptr [rsp+0F0h+var_C8], edi
0x180041aec  mov     [rsp+0F0h+ppv], 0FFFFFFFFFFFFFFFFh; int
0x180041af5  or      r8d, 0FFFFFFFFh
0x180041af9  mov     r9d, r8d
0x180041afc  mov     rdx, [rbp+3Fh+var_70]
0x180041b00  mov     rax, [rax+20h]
0x180041b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b09  mov     ebx, eax
0x180041b0b  test    eax, eax
0x180041b0d  jns     short loc_180041B61
0x180041b0f  mov     rcx, [rbp+47h]; this
0x180041b13  mov     r9d, eax; char *
0x180041b16  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180041b1d  mov     edx, 3FEh; void *
0x180041b22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041b27  nop
0x180041b28  mov     rcx, [rbp+3Fh+var_68]
0x180041b2c  test    rcx, rcx
0x180041b2f  jz      short loc_180041B42
0x180041b31  mov     [rbp+3Fh+var_68], rdi
0x180041b35  mov     rax, [rcx]
0x180041b38  mov     rax, [rax+10h]
0x180041b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b41  nop
0x180041b42  mov     rcx, [rbp+3Fh+var_70]
0x180041b46  test    rcx, rcx
0x180041b49  jz      short loc_180041B5C
0x180041b4b  mov     [rbp+3Fh+var_70], rdi
0x180041b4f  mov     rax, [rcx]
0x180041b52  mov     rax, [rax+10h]
0x180041b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b5b  nop
0x180041b5c  jmp     loc_180041958
0x180041b61  test    r13, r13
0x180041b64  jnz     loc_180041CC4
0x180041b6a  mov     rsi, [rbp+3Fh+var_70]
0x180041b6e  mov     rax, [rsi]
0x180041b71  mov     r14, [rax+1F8h]
0x180041b78  mov     rdi, [rbp+3Fh+pv]
0x180041b7c  test    rdi, rdi
0x180041b7f  jz      short loc_180041B9A
0x180041b81  call    cs:__imp_GetLastError
0x180041b87  mov     ebx, eax
0x180041b89  mov     rcx, rdi; pv
0x180041b8c  call    cs:__imp_CoTaskMemFree
0x180041b92  mov     ecx, ebx; dwErrCode
0x180041b94  call    cs:__imp_SetLastError
0x180041b9a  mov     [rbp+3Fh+pv], r13
0x180041b9e  mov     rdi, [rbp+3Fh+psz]
0x180041ba2  test    rdi, rdi
0x180041ba5  jz      short loc_180041BC0
0x180041ba7  call    cs:__imp_GetLastError
0x180041bad  mov     ebx, eax
0x180041baf  mov     rcx, rdi; pv
0x180041bb2  call    cs:__imp_CoTaskMemFree
0x180041bb8  mov     ecx, ebx; dwErrCode
0x180041bba  call    cs:__imp_SetLastError
0x180041bc0  mov     [rbp+3Fh+psz], r13
0x180041bc4  xor     edx, edx; length
0x180041bc6  mov     rcx, [rbp+3Fh+string]; string
0x180041bca  call    cs:__imp_WindowsGetStringRawBuffer
0x180041bd0  mov     rbx, rax
0x180041bd3  xor     edx, edx; length
0x180041bd5  mov     rcx, [rbp+3Fh+var_78]; string
0x180041bd9  call    cs:__imp_WindowsGetStringRawBuffer
0x180041bdf  mov     rdi, rax
0x180041be2  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x180041be7  lea     rdx, aS1152160947379; "S-1-15-2-1609473798-1231923017-68426815"...
0x180041bee  lea     rcx, aS1152903380885; "S-1-15-2-903380885-3144618533-332668975"...
0x180041bf5  test    al, al
0x180041bf7  cmovz   rcx, rdx
0x180041bfb  lea     rax, [rbp+3Fh+pv]
0x180041bff  mov     [rsp+0F0h+var_A0], rax
0x180041c04  lea     rax, [rbp+3Fh+psz]
0x180041c08  mov     [rsp+0F0h+var_A8], rax
0x180041c0d  mov     dword ptr [rsp+0F0h+var_B0], r13d
0x180041c12  mov     [rsp+0F0h+var_B8], r13
0x180041c17  lea     rdx, aXXblContractVe; "x-xbl-contract-version:2\r\nAccept:appl"...
0x180041c1e  mov     [rsp+0F0h+var_C0], rdx
0x180041c23  mov     [rsp+0F0h+var_C8], rbx
0x180041c28  lea     rdx, aGet; "GET"
0x180041c2f  mov     [rsp+0F0h+ppv], rdx; int
0x180041c34  lea     r9, aMbiSsl; "MBI_SSL"
0x180041c3b  mov     r8, rdi
0x180041c3e  mov     rdx, rcx
0x180041c41  mov     rcx, rsi
0x180041c44  mov     rax, r14
0x180041c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c4c  mov     ebx, eax
0x180041c4e  test    eax, eax
0x180041c50  jns     loc_180041F2D
0x180041c56  mov     rcx, [rbp+47h]; this
0x180041c5a  mov     r9d, eax; char *
0x180041c5d  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180041c64  mov     edx, 40Fh; void *
0x180041c69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041c6e  nop
0x180041c6f  mov     rcx, [rbp+3Fh+var_68]
0x180041c73  test    rcx, rcx
0x180041c76  jz      short loc_180041C89
0x180041c78  mov     [rbp+3Fh+var_68], r13
0x180041c7c  mov     rax, [rcx]
0x180041c7f  mov     rax, [rax+10h]
0x180041c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c88  nop
0x180041c89  mov     rcx, [rbp+3Fh+var_70]
0x180041c8d  test    rcx, rcx
0x180041c90  jz      short loc_180041CA3
0x180041c92  mov     [rbp+3Fh+var_70], r13
0x180041c96  mov     rax, [rcx]
0x180041c99  mov     rax, [rax+10h]
0x180041c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ca2  nop
0x180041ca3  mov     rcx, [rbp+3Fh+string]; string
0x180041ca7  call    cs:__imp_WindowsDeleteString
0x180041cad  mov     [rbp+3Fh+string], r13
0x180041cb1  mov     rcx, [rbp+3Fh+var_78]; string
0x180041cb5  call    cs:__imp_WindowsDeleteString
0x180041cbb  mov     [rbp+3Fh+var_78], r13
0x180041cbf  jmp     loc_180041974
0x180041cc4  mov     [rbp+3Fh+pcchLength], rdi
0x180041cc8  mov     r14, [rbp+3Fh+var_70]
0x180041ccc  mov     rax, [r14]
0x180041ccf  mov     rsi, [rax+1C8h]
0x180041cd6  xor     edx, edx; length
0x180041cd8  mov     rcx, [rbp+3Fh+string]; string
0x180041cdc  call    cs:__imp_WindowsGetStringRawBuffer
0x180041ce2  mov     rbx, rax
0x180041ce5  xor     edx, edx; length
0x180041ce7  mov     rcx, [rbp+3Fh+var_78]; string
0x180041ceb  call    cs:__imp_WindowsGetStringRawBuffer
0x180041cf1  mov     rdi, rax
0x180041cf4  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x180041cf9  lea     rdx, aS1152160947379; "S-1-15-2-1609473798-1231923017-68426815"...
0x180041d00  lea     rcx, aS1152903380885; "S-1-15-2-903380885-3144618533-332668975"...
0x180041d07  test    al, al
0x180041d09  cmovz   rcx, rdx
0x180041d0d  mov     [rbp+3Fh+var_48], rcx
0x180041d11  xor     edx, edx; length
0x180041d13  mov     rcx, r13; string
0x180041d16  call    cs:__imp_WindowsGetStringRawBuffer
0x180041d1c  lea     rcx, [rbp+3Fh+pcchLength]
0x180041d20  mov     [rsp+0F0h+var_90], rcx
0x180041d25  xor     r13d, r13d
0x180041d28  mov     [rsp+0F0h+var_98], r13d
0x180041d2d  mov     dword ptr [rsp+0F0h+var_A0], r13d
0x180041d32  mov     [rsp+0F0h+var_A8], r13
0x180041d37  lea     rdx, aXXblContractVe; "x-xbl-contract-version:2\r\nAccept:appl"...
0x180041d3e  mov     [rsp+0F0h+var_B0], rdx
0x180041d43  mov     [rsp+0F0h+var_B8], rbx
0x180041d48  lea     rdx, aGet; "GET"
0x180041d4f  mov     [rsp+0F0h+var_C0], rdx
0x180041d54  lea     rdx, aMbiSsl; "MBI_SSL"
0x180041d5b  mov     [rsp+0F0h+var_C8], rdx
0x180041d60  mov     [rsp+0F0h+ppv], rdi; int
0x180041d65  mov     r9, [rbp+3Fh+var_48]
0x180041d69  mov     r8, rax
0x180041d6c  xor     edx, edx
0x180041d6e  mov     rcx, r14
0x180041d71  mov     rax, rsi
  ... truncated ...
```
