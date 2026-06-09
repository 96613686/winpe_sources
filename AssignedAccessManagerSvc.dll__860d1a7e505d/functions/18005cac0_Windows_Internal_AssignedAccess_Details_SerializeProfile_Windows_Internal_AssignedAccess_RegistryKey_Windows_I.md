# Windows::Internal::AssignedAccess::Details::SerializeProfile<Windows::Internal::AssignedAccess::RegistryKey>(Windows::Internal::AssignedAccess::RegistryKey &,Windows::Internal::AssignedAccess::IAssignedAccessProfile *)

- ea: `0x18005cac0`
- end: `0x18005d4e1`
- name: `??$SerializeProfile@VRegistryKey@AssignedAccess@Internal@Windows@@@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKey@123@PEAUIAssignedAccessProfile@123@@Z`
- size: `2593`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180063014`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010590`
- `0x180010c98`
- `0x180014a5c`
- `0x180022930`
- `0x180022d00`
- `0x1800262e0`
- `0x1800271e4`
- `0x1800272d0`
- `0x1800272e0`
- `0x180028f14`
- `0x18002901c`
- `0x180029598`
- `0x1800295e4`
- `0x180029c04`
- `0x18002b190`
- `0x180037454`
- `0x18003bfac`
- `0x180054894`
- `0x1800587dc`
- `0x180058808`
- `0x18005b968`
- `0x18005c82c`
- `0x18005cac0`
- `0x18005e4bc`
- `0x18005f868`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005cb74`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005cb74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cdd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cfec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d0a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cdd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cfec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d0a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005cc6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ceb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005cf55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005cc6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ceb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005cf55`

## string_xrefs

- `0x18005cc83`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005cec6`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005cf6a`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005cb2a`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005cb98`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005cc23`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005ccc3`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005cd0b`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005cda0`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005ce54`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005cf04`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005cfb7`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d064`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d124`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d25e`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d340`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d3ea`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005cea7`: `TaskbarAllowed`

## pseudocode

```c
// Hidden C++ exception states: #wind=20 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::Details::SerializeProfile<Windows::Internal::AssignedAccess::RegistryKey>(
        HKEY *a1,
        __int64 *a2)
{
  int v4; // r12d
  int v5; // eax
  unsigned int v6; // ebx
  HRESULT v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  unsigned __int8 v16; // bl
  __int64 (__fastcall *v17)(__int64 *, HSTRING *); // rbx
  int v18; // eax
  unsigned int v19; // ebx
  PCWSTR StringRawBuffer; // rax
  int v21; // eax
  unsigned int v22; // ebx
  unsigned int v23; // eax
  int v24; // eax
  unsigned int v25; // ebx
  unsigned int v26; // eax
  __int64 (__fastcall *v27)(__int64 *, HSTRING *); // rbx
  int v28; // eax
  unsigned int v29; // ebx
  PCWSTR v30; // rax
  __int64 (__fastcall *v31)(__int64 *, HSTRING *); // rbx
  int v32; // eax
  unsigned int v33; // ebx
  PCWSTR v34; // rax
  int v35; // r9d
  __int64 v36; // rax
  int v37; // eax
  unsigned int v38; // ebx
  unsigned int v39; // r14d
  int v40; // r15d
  _QWORD *v41; // rbx
  __int64 v42; // rax
  int v43; // eax
  unsigned int v44; // ebx
  __int64 v45; // rax
  int v46; // eax
  unsigned int v47; // ebx
  __int64 v48; // rax
  int v49; // eax
  unsigned int v50; // ebx
  int lpData; // [rsp+20h] [rbp-158h]
  unsigned int lpDataa; // [rsp+20h] [rbp-158h]
  unsigned int lpDatab; // [rsp+20h] [rbp-158h]
  unsigned int lpDatac; // [rsp+20h] [rbp-158h]
  int lpDatad; // [rsp+20h] [rbp-158h]
  char v56; // [rsp+30h] [rbp-148h] BYREF
  char v57; // [rsp+31h] [rbp-147h] BYREF
  char v58; // [rsp+32h] [rbp-146h] BYREF
  _BYTE v59[5]; // [rsp+33h] [rbp-145h] BYREF
  __int64 v60; // [rsp+38h] [rbp-140h] BYREF
  HSTRING string; // [rsp+40h] [rbp-138h] BYREF
  HSTRING v62; // [rsp+48h] [rbp-130h] BYREF
  BYTE v63[8]; // [rsp+50h] [rbp-128h] BYREF
  HSTRING v64; // [rsp+58h] [rbp-120h] BYREF
  __int64 v65; // [rsp+60h] [rbp-118h] BYREF
  _BYTE v66[8]; // [rsp+68h] [rbp-110h] BYREF
  __int64 v67; // [rsp+70h] [rbp-108h] BYREF
  __int64 v68; // [rsp+78h] [rbp-100h] BYREF
  BYTE v69[8]; // [rsp+80h] [rbp-F8h] BYREF
  __int64 *v70; // [rsp+88h] [rbp-F0h] BYREF
  LPOLESTR lpsz; // [rsp+90h] [rbp-E8h] BYREF
  char v72; // [rsp+98h] [rbp-E0h]
  BYTE Data[16]; // [rsp+A0h] [rbp-D8h] BYREF
  _BYTE v74[8]; // [rsp+B0h] [rbp-C8h] BYREF
  int v75; // [rsp+B8h] [rbp-C0h]
  _BYTE v76[8]; // [rsp+D0h] [rbp-A8h] BYREF
  _BYTE v77[32]; // [rsp+D8h] [rbp-A0h] BYREF
  _BYTE v78[32]; // [rsp+F8h] [rbp-80h] BYREF
  IID rclsid; // [rsp+118h] [rbp-60h] BYREF
  _BYTE v80[32]; // [rsp+128h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v4 = 0;
  *(_DWORD *)v63 = 0;
  rclsid = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, IID *))(*a2 + 56))(a2, &rclsid);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x181,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v5,
      lpData);
    return v6;
  }
  v60 = 0;
  v70 = &v60;
  lpsz = 0;
  v72 = 1;
  v8 = StringFromCLSID(&rclsid, &lpsz);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v70);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x183,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v8,
      lpData);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
    return (unsigned int)v8;
  }
  std::wstring::wstring(v78, v60);
  Windows::Internal::AssignedAccess::RegistryKey::SetString<unsigned short const *>(a1, L"ProfileId", v78);
  std::wstring::_Tidy_deallocate(v78);
  *(_QWORD *)Data = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, BYTE *))(*a2 + 48))(a2, Data);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x188,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v9,
      lpData);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
    return v10;
  }
  v11 = RegSetValueExW(*a1, L"Timestamp", 0, 0xBu, Data, 8u);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
      (const char *)v11,
      lpDataa);
  v56 = 0;
  v57 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, char *))(*a2 + 72))(a2, &v56);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v12,
      lpDataa);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
    return v13;
  }
  v14 = (*(__int64 (__fastcall **)(__int64 *, char *))(*a2 + 88))(a2, &v57);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18F,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v14,
      lpDataa);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
    return v15;
  }
  if ( v56 || (v16 = 0, v57) )
    v16 = 1;
  LODWORD(string) = v16;
  Windows::Internal::AssignedAccess::RegistryKey::SetDWORD<unsigned short const [8]>(a1, L"IsSingleAppProfile", &string);
  if ( v16 )
  {
    string = 0;
    v17 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a2 + 232);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &string,
      0);
    v18 = v17(a2, &string);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x197,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
        (const char *)(unsigned int)v18,
        lpDataa);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
      return v19;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( StringRawBuffer && *StringRawBuffer )
    {
      std::wstring::wstring(v78, StringRawBuffer);
      Windows::Internal::AssignedAccess::RegistryKey::SetString<unsigned short const *>(a1, L"BreakoutKey", v78);
      std::wstring::_Tidy_deallocate(v78);
    }
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  }
  v58 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64 *, char *))(*a2 + 152))(a2, &v58);
  v22 = v21;
  if ( v21 >= 0 )
  {
    *(_DWORD *)v69 = v58 != 0;
    v23 = RegSetValueExW(*a1, L"TaskbarAllowed", 0, 4u, v69, 4u);
    if ( v23 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
        (const char *)v23,
        lpDatab);
    v59[0] = 0;
    v24 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*a2 + 168))(a2, v59);
    v25 = v24;
    if ( v24 >= 0 )
    {
      *(_DWORD *)v63 = v59[0] != 0;
      v26 = RegSetValueExW(*a1, L"AllAppListAllowed", 0, 4u, v63, 4u);
      if ( v26 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0xCD,
          (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
          (const char *)v26,
          lpDatac);
      v62 = 0;
      v27 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a2 + 136);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v62,
        0);
      v28 = v27(a2, &v62);
      v29 = v28;
      if ( v28 >= 0 )
      {
        v30 = WindowsGetStringRawBuffer(v62, 0);
        std::wstring::wstring(v78, v30);
        Windows::Internal::AssignedAccess::RegistryKey::SetString<unsigned short const *>(a1, L"StartPinsPolicy", v78);
        std::wstring::_Tidy_deallocate(v78);
        v64 = 0;
        v31 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a2 + 248);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          &v64,
          0);
        v32 = v31(a2, &v64);
        v33 = v32;
        if ( v32 >= 0 )
        {
          v34 = WindowsGetStringRawBuffer(v64, 0);
          std::wstring::wstring(v78, v34);
          Windows::Internal::AssignedAccess::RegistryKey::SetString<unsigned short const *>(
            a1,
            L"StartLayoutPolicy",
            v78);
          std::wstring::_Tidy_deallocate(v78);
          Windows::Internal::AssignedAccess::RegistryKey::Create<unsigned short const *>(
            (_DWORD)a1,
            (unsigned int)v66,
            (unsigned int)L"AllowedApps",
            v35,
            0);
          v36 = *a2;
          v65 = 0;
          v37 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v36 + 120))(a2, &v65);
          v38 = v37;
          if ( v37 >= 0 )
          {
            v39 = 0;
            wil::get_range_nothrow<Windows::Internal::AssignedAccess::AssignedAccessProfile *>(v74, v65);
            wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>>::begin(
              v74,
              &v70);
            v40 = v75;
            while ( *(int *)v70[2] >= 0 && (_DWORD)lpsz != v40 )
            {
              v41 = (_QWORD *)wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessProfile *>>::vector_iterator_nothrow::operator*(&v70);
              std::_Integral_to_string<unsigned short,unsigned int>(v80, v39);
              std::operator+<unsigned short>(v78, L"App", v80);
              std::wstring::_Tidy_deallocate(v80);
              v42 = std::wstring::wstring(v77, v78);
              Windows::Internal::AssignedAccess::RegistryKey::Create<std::wstring>(v66, &string, v42);
              v43 = Windows::Internal::AssignedAccess::Details::Serialize<Windows::Internal::AssignedAccess::RegistryKey>(
                      &string,
                      *v41);
              v44 = v43;
              if ( v43 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1BF,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                  (const char *)(unsigned int)v43,
                  lpDatad);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&string);
                std::wstring::_Tidy_deallocate(v78);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v76);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v65);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v66);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v64);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v62);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
                return v44;
              }
              ++v39;
              v4 |= 1u;
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&string);
              std::wstring::_Tidy_deallocate(v78);
              wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessUserInfo *>>::vector_iterator_nothrow::operator+=(&v70);
            }
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v76);
            v45 = *a2;
            v67 = 0;
            v46 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v45 + 184))(a2, &v67);
            v47 = v46;
            if ( v46 >= 0 )
            {
              LODWORD(string) = Windows::Internal::AssignedAccess::Details::CommonFileDialogLocationsConverter::ConvertFromLocationsToBitset(v67);
              Windows::Internal::AssignedAccess::RegistryKey::SetDWORD<unsigned short const *>(
                a1,
                off_18009E5C8,
                &string);
              v48 = *a2;
              v68 = 0;
              v49 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v48 + 200))(a2, &v68);
              v50 = v49;
              if ( v49 >= 0 )
              {
                if ( v68 )
                  Windows::Internal::AssignedAccess::Details::SerializeFileExplorerRestrictions<Windows::Internal::AssignedAccess::RegistryKey>(a1);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v68);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v67);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v65);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v66);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v64);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v62);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
                return 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1C8,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                  (const char *)(unsigned int)v49,
                  lpDatad);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v68);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v67);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v65);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v66);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v64);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v62);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
                return v50;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1C3,
                (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                (const char *)(unsigned int)v46,
                lpDatad);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v67);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v65);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v66);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v64);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v62);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
              return v47;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1B8,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
              (const char *)(unsigned int)v37,
              lpDatad);
            wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v65);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v66);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v64);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v62);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
            return v38;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B2,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
            (const char *)(unsigned int)v32,
            lpDatac);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v64);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v62);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
          return v33;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AD,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
          (const char *)(unsigned int)v28,
          lpDatac);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v62);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
        return v29;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A7,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
        (const char *)(unsigned int)v24,
        lpDatab);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
      return v25;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v21,
      lpDataa);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
    return v22;
  }
}

```

## disassembly

```asm
0x18005cac0  mov     r11, rsp
0x18005cac3  mov     [r11+18h], rbx
0x18005cac7  mov     [r11+20h], rsi
0x18005cacb  push    rdi
0x18005cacc  push    r12
0x18005cace  push    r13
0x18005cad0  push    r14
0x18005cad2  push    r15
0x18005cad4  sub     rsp, 150h
0x18005cadb  mov     rax, cs:__security_cookie
0x18005cae2  xor     rax, rsp
0x18005cae5  mov     [rsp+178h+var_30], rax
0x18005caed  mov     rdi, rdx
0x18005caf0  mov     rsi, rcx
0x18005caf3  xor     r13d, r13d
0x18005caf6  mov     r12d, r13d
0x18005caf9  mov     dword ptr [rsp+178h+var_128], r13d
0x18005cafe  xorps   xmm0, xmm0
0x18005cb01  movups  xmmword ptr [r11-60h], xmm0
0x18005cb06  mov     rax, [rdx]
0x18005cb09  lea     rdx, [r11-60h]
0x18005cb0d  mov     rcx, rdi
0x18005cb10  mov     rax, [rax+38h]
0x18005cb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb19  mov     ebx, eax
0x18005cb1b  test    eax, eax
0x18005cb1d  jns     short loc_18005CB42
0x18005cb1f  mov     rcx, [rsp+178h]; this
0x18005cb27  mov     r9d, eax; char *
0x18005cb2a  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005cb31  mov     edx, 181h; void *
0x18005cb36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cb3b  mov     eax, ebx
0x18005cb3d  jmp     loc_18005D4B3
0x18005cb42  mov     [rsp+178h+var_140], r13
0x18005cb47  lea     rax, [rsp+178h+var_140]
0x18005cb4c  mov     [rsp+178h+var_F0], rax
0x18005cb54  mov     [rsp+178h+lpsz], r13
0x18005cb5c  mov     [rsp+178h+var_E0], 1
0x18005cb64  lea     rdx, [rsp+178h+lpsz]; lplpsz
0x18005cb6c  lea     rcx, [rsp+178h+rclsid]; rclsid
0x18005cb74  call    cs:__imp_StringFromCLSID
0x18005cb7a  mov     ebx, eax
0x18005cb7c  lea     rcx, [rsp+178h+var_F0]
0x18005cb84  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005cb89  test    ebx, ebx
0x18005cb8b  jns     short loc_18005CBBB
0x18005cb8d  mov     rcx, [rsp+178h]; this
0x18005cb95  mov     r9d, ebx; char *
0x18005cb98  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005cb9f  mov     edx, 183h; void *
0x18005cba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cba9  nop
0x18005cbaa  lea     rcx, [rsp+178h+var_140]
0x18005cbaf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005cbb4  mov     eax, ebx
0x18005cbb6  jmp     loc_18005D4B3
0x18005cbbb  mov     rdx, [rsp+178h+var_140]
0x18005cbc0  lea     rcx, [rsp+178h+var_80]
0x18005cbc8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005cbcd  nop
0x18005cbce  lea     r8, [rsp+178h+var_80]
0x18005cbd6  lea     rdx, aProfileid; "ProfileId"
0x18005cbdd  mov     rcx, rsi
0x18005cbe0  call    ??$SetString@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEBAXPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::AssignedAccess::RegistryKey::SetString<ushort const *>(ushort const *,std::wstring const &)
0x18005cbe5  nop
0x18005cbe6  lea     rcx, [rsp+178h+var_80]
0x18005cbee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005cbf3  mov     qword ptr [rsp+178h+Data], r13
0x18005cbfb  mov     rax, [rdi]
0x18005cbfe  lea     rdx, [rsp+178h+Data]
0x18005cc06  mov     rcx, rdi
0x18005cc09  mov     rax, [rax+30h]
0x18005cc0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc12  mov     ebx, eax
0x18005cc14  test    eax, eax
0x18005cc16  jns     short loc_18005CC46
0x18005cc18  mov     rcx, [rsp+178h]; this
0x18005cc20  mov     r9d, eax; char *
0x18005cc23  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005cc2a  mov     edx, 188h; void *
0x18005cc2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cc34  nop
0x18005cc35  lea     rcx, [rsp+178h+var_140]
0x18005cc3a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005cc3f  mov     eax, ebx
0x18005cc41  jmp     loc_18005D4B3
0x18005cc46  mov     [rsp+178h+cbData], 8; cbData
0x18005cc4e  lea     rax, [rsp+178h+Data]
0x18005cc56  mov     [rsp+178h+lpData], rax; int
0x18005cc5b  mov     r9d, 0Bh; dwType
0x18005cc61  xor     r8d, r8d; Reserved
0x18005cc64  lea     rdx, aTimestamp; "Timestamp"
0x18005cc6b  mov     rcx, [rsi]; hKey
0x18005cc6e  call    cs:__imp_RegSetValueExW
0x18005cc74  mov     rcx, [rsp+178h]; this
0x18005cc7c  test    eax, eax
0x18005cc7e  jz      short loc_18005CC94
0x18005cc80  mov     r9d, eax; char *
0x18005cc83  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005cc8a  mov     edx, 0F4h; void *
0x18005cc8f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005cc94  mov     [rsp+178h+var_148], r13b
0x18005cc99  mov     [rsp+178h+var_147], r13b
0x18005cc9e  mov     rax, [rdi]
0x18005cca1  lea     rdx, [rsp+178h+var_148]
0x18005cca6  mov     rcx, rdi
0x18005cca9  mov     rax, [rax+48h]
0x18005ccad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ccb2  mov     ebx, eax
0x18005ccb4  test    eax, eax
0x18005ccb6  jns     short loc_18005CCE6
0x18005ccb8  mov     rcx, [rsp+178h]; this
0x18005ccc0  mov     r9d, eax; char *
0x18005ccc3  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005ccca  mov     edx, 18Eh; void *
0x18005cccf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ccd4  nop
0x18005ccd5  lea     rcx, [rsp+178h+var_140]
0x18005ccda  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005ccdf  mov     eax, ebx
0x18005cce1  jmp     loc_18005D4B3
0x18005cce6  mov     rax, [rdi]
0x18005cce9  lea     rdx, [rsp+178h+var_147]
0x18005ccee  mov     rcx, rdi
0x18005ccf1  mov     rax, [rax+58h]
0x18005ccf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ccfa  mov     ebx, eax
0x18005ccfc  test    eax, eax
0x18005ccfe  jns     short loc_18005CD2E
0x18005cd00  mov     rcx, [rsp+178h]; this
0x18005cd08  mov     r9d, eax; char *
0x18005cd0b  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005cd12  mov     edx, 18Fh; void *
0x18005cd17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cd1c  nop
0x18005cd1d  lea     rcx, [rsp+178h+var_140]
0x18005cd22  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005cd27  mov     eax, ebx
0x18005cd29  jmp     loc_18005D4B3
0x18005cd2e  cmp     [rsp+178h+var_148], r13b
0x18005cd33  jnz     short loc_18005CD3F
0x18005cd35  cmp     [rsp+178h+var_147], r13b
0x18005cd3a  mov     bl, r13b
0x18005cd3d  jz      short loc_18005CD41
0x18005cd3f  mov     bl, 1
0x18005cd41  movzx   eax, bl
0x18005cd44  mov     dword ptr [rsp+178h+string], eax
0x18005cd48  lea     r8, [rsp+178h+string]
0x18005cd4d  lea     rdx, aIssingleapppro; "IsSingleAppProfile"
0x18005cd54  mov     rcx, rsi
0x18005cd57  call    ??$SetDWORD@$$BY07$$CBG@RegistryKey@AssignedAccess@Internal@Windows@@QEBAXAEAY07$$CBGAEBK@Z; Windows::Internal::AssignedAccess::RegistryKey::SetDWORD<ushort const [8]>(ushort const (&)[8],ulong const &)
0x18005cd5c  test    bl, bl
0x18005cd5e  jz      loc_18005CE27
0x18005cd64  mov     [rsp+178h+string], r13
0x18005cd69  mov     rax, [rdi]
0x18005cd6c  mov     rbx, [rax+0E8h]
0x18005cd73  xor     edx, edx
0x18005cd75  lea     rcx, [rsp+178h+string]
0x18005cd7a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005cd7f  lea     rdx, [rsp+178h+string]
0x18005cd84  mov     rcx, rdi
0x18005cd87  mov     rax, rbx
0x18005cd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd8f  mov     ebx, eax
0x18005cd91  test    eax, eax
0x18005cd93  jns     short loc_18005CDCE
0x18005cd95  mov     rcx, [rsp+178h]; this
0x18005cd9d  mov     r9d, eax; char *
0x18005cda0  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005cda7  mov     edx, 197h; void *
0x18005cdac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cdb1  nop
0x18005cdb2  lea     rcx, [rsp+178h+string]
0x18005cdb7  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005cdbc  nop
0x18005cdbd  lea     rcx, [rsp+178h+var_140]
0x18005cdc2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005cdc7  mov     eax, ebx
0x18005cdc9  jmp     loc_18005D4B3
0x18005cdce  xor     edx, edx; length
0x18005cdd0  mov     rcx, [rsp+178h+string]; string
0x18005cdd5  call    cs:__imp_WindowsGetStringRawBuffer
0x18005cddb  test    rax, rax
0x18005cdde  jz      short loc_18005CE1D
0x18005cde0  cmp     [rax], r13w
0x18005cde4  jz      short loc_18005CE1D
0x18005cde6  mov     rdx, rax
0x18005cde9  lea     rcx, [rsp+178h+var_80]
0x18005cdf1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005cdf6  nop
0x18005cdf7  lea     r8, [rsp+178h+var_80]
0x18005cdff  lea     rdx, aBreakoutkey; "BreakoutKey"
0x18005ce06  mov     rcx, rsi
0x18005ce09  call    ??$SetString@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEBAXPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::AssignedAccess::RegistryKey::SetString<ushort const *>(ushort const *,std::wstring const &)
0x18005ce0e  nop
0x18005ce0f  lea     rcx, [rsp+178h+var_80]
0x18005ce17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ce1c  nop
0x18005ce1d  lea     rcx, [rsp+178h+string]
0x18005ce22  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005ce27  mov     [rsp+178h+var_146], r13b
0x18005ce2c  mov     rax, [rdi]
0x18005ce2f  lea     rdx, [rsp+178h+var_146]
0x18005ce34  mov     rcx, rdi
0x18005ce37  mov     rax, [rax+98h]
0x18005ce3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce43  mov     ebx, eax
0x18005ce45  test    eax, eax
0x18005ce47  jns     short loc_18005CE77
0x18005ce49  mov     rcx, [rsp+178h]; this
0x18005ce51  mov     r9d, eax; char *
0x18005ce54  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005ce5b  mov     edx, 1A1h; void *
0x18005ce60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ce65  nop
0x18005ce66  lea     rcx, [rsp+178h+var_140]
0x18005ce6b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005ce70  mov     eax, ebx
0x18005ce72  jmp     loc_18005D4B3
0x18005ce77  mov     eax, r13d
0x18005ce7a  cmp     [rsp+178h+var_146], r13b
0x18005ce7f  setnz   al
0x18005ce82  mov     dword ptr [rsp+178h+var_F8], eax
0x18005ce89  mov     r14d, 4
0x18005ce8f  mov     [rsp+178h+cbData], r14d; cbData
0x18005ce94  lea     rax, [rsp+178h+var_F8]
0x18005ce9c  mov     [rsp+178h+lpData], rax; int
0x18005cea1  mov     r9d, r14d; dwType
0x18005cea4  xor     r8d, r8d; Reserved
0x18005cea7  lea     rdx, aTaskbarallowed; "TaskbarAllowed"
0x18005ceae  mov     rcx, [rsi]; hKey
0x18005ceb1  call    cs:__imp_RegSetValueExW
0x18005ceb7  mov     rcx, [rsp+178h]; this
0x18005cebf  test    eax, eax
0x18005cec1  jz      short loc_18005CED7
0x18005cec3  mov     r9d, eax; char *
0x18005cec6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005cecd  mov     edx, 0CDh; void *
0x18005ced2  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005ced7  mov     [rsp+178h+var_145], r13b
0x18005cedc  mov     rax, [rdi]
0x18005cedf  lea     rdx, [rsp+178h+var_145]
0x18005cee4  mov     rcx, rdi
0x18005cee7  mov     rax, [rax+0A8h]
0x18005ceee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cef3  mov     ebx, eax
0x18005cef5  test    eax, eax
0x18005cef7  jns     short loc_18005CF27
0x18005cef9  mov     rcx, [rsp+178h]; this
0x18005cf01  mov     r9d, eax; char *
0x18005cf04  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005cf0b  mov     edx, 1A7h; void *
0x18005cf10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cf15  nop
0x18005cf16  lea     rcx, [rsp+178h+var_140]
0x18005cf1b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005cf20  mov     eax, ebx
0x18005cf22  jmp     loc_18005D4B3
0x18005cf27  mov     eax, r13d
0x18005cf2a  cmp     [rsp+178h+var_145], r13b
0x18005cf2f  setnz   al
0x18005cf32  mov     dword ptr [rsp+178h+var_128], eax
0x18005cf36  mov     [rsp+178h+cbData], r14d; cbData
0x18005cf3b  lea     rax, [rsp+178h+var_128]
0x18005cf40  mov     [rsp+178h+lpData], rax; int
0x18005cf45  mov     r9d, r14d; dwType
0x18005cf48  xor     r8d, r8d; Reserved
0x18005cf4b  lea     rdx, aAllapplistallo; "AllAppListAllowed"
0x18005cf52  mov     rcx, [rsi]; hKey
0x18005cf55  call    cs:__imp_RegSetValueExW
0x18005cf5b  mov     rcx, [rsp+178h]; this
0x18005cf63  test    eax, eax
0x18005cf65  jz      short loc_18005CF7B
0x18005cf67  mov     r9d, eax; char *
0x18005cf6a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005cf71  mov     edx, 0CDh; void *
0x18005cf76  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005cf7b  mov     [rsp+178h+var_130], r13
0x18005cf80  mov     rax, [rdi]
0x18005cf83  mov     rbx, [rax+88h]
0x18005cf8a  xor     edx, edx
0x18005cf8c  lea     rcx, [rsp+178h+var_130]
0x18005cf91  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005cf96  lea     rdx, [rsp+178h+var_130]
0x18005cf9b  mov     rcx, rdi
0x18005cf9e  mov     rax, rbx
0x18005cfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfa6  mov     ebx, eax
0x18005cfa8  test    eax, eax
0x18005cfaa  jns     short loc_18005CFE5
0x18005cfac  mov     rcx, [rsp+178h]; this
0x18005cfb4  mov     r9d, eax; char *
0x18005cfb7  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005cfbe  mov     edx, 1ADh; void *
0x18005cfc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cfc8  nop
0x18005cfc9  lea     rcx, [rsp+178h+var_130]
0x18005cfce  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005cfd3  nop
  ... truncated ...
```
