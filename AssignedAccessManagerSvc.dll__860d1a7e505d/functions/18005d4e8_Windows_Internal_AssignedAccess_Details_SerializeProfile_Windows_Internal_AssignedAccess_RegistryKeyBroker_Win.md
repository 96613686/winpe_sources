# Windows::Internal::AssignedAccess::Details::SerializeProfile<Windows::Internal::AssignedAccess::RegistryKeyBroker>(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessProfile *)

- ea: `0x18005d4e8`
- end: `0x18005e08a`
- name: `??$SerializeProfile@VRegistryKeyBroker@AssignedAccess@Internal@Windows@@@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKeyBroker@123@PEAUIAssignedAccessProfile@123@@Z`
- size: `2978`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800630e0`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010590`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x180022d00`
- `0x1800262e0`
- `0x1800271e4`
- `0x1800272d0`
- `0x1800272e0`
- `0x180028f14`
- `0x18002901c`
- `0x18002b190`
- `0x180037454`
- `0x18003bfac`
- `0x1800575cc`
- `0x18005bd08`
- `0x18005c43c`
- `0x18005c928`
- `0x18005d4e8`
- `0x18005e4bc`
- `0x180063b68`
- `0x180064314`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005d590`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18005d590`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d8a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005db32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005dc0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005d8a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005db32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005dc0e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005d6ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005d7f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005d9bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005da8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005d6ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005d7f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005d9bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005da8d`

## string_xrefs

- `0x18005d6df`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005d80b`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005d9d1`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005daa2`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005d552`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d5b1`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d660`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d72d`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d775`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d86e`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d946`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005da1d`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005dafd`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005dbce`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005dcd4`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005ddfe`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005dee6`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005df84`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005d97b`: `TaskbarAllowed`

## pseudocode

```c
// Hidden C++ exception states: #wind=27 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::Details::SerializeProfile<Windows::Internal::AssignedAccess::RegistryKeyBroker>(
        __int64 a1,
        __int64 *a2)
{
  int v4; // r12d
  int v5; // eax
  unsigned int v6; // ebx
  HRESULT v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  const WCHAR *v11; // rax
  unsigned int v12; // eax
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  unsigned __int8 v17; // bl
  const WCHAR *v18; // rax
  unsigned int v19; // eax
  __int64 (__fastcall *v20)(__int64 *, BYTE *); // rbx
  int v21; // eax
  unsigned int v22; // ebx
  PCWSTR StringRawBuffer; // rax
  int v24; // eax
  unsigned int v25; // ebx
  const WCHAR *v26; // rax
  unsigned int v27; // eax
  int v28; // eax
  unsigned int v29; // ebx
  const WCHAR *v30; // rax
  unsigned int v31; // eax
  __int64 (__fastcall *v32)(__int64 *, HSTRING *); // rbx
  int v33; // eax
  unsigned int v34; // ebx
  PCWSTR v35; // rax
  __int64 (__fastcall *v36)(__int64 *, HSTRING *); // rbx
  int v37; // eax
  unsigned int v38; // ebx
  PCWSTR v39; // rax
  __int64 v40; // rax
  int v41; // eax
  unsigned int v42; // ebx
  unsigned int v43; // r14d
  int v44; // r15d
  _QWORD *v45; // rbx
  int v46; // eax
  unsigned int v47; // ebx
  __int64 v48; // rax
  int v49; // eax
  unsigned int v50; // ebx
  __int64 v51; // rax
  int v52; // eax
  unsigned int v53; // ebx
  int lpData; // [rsp+20h] [rbp-158h]
  unsigned int lpDataa; // [rsp+20h] [rbp-158h]
  unsigned int lpDatab; // [rsp+20h] [rbp-158h]
  unsigned int lpDatac; // [rsp+20h] [rbp-158h]
  unsigned int lpDatad; // [rsp+20h] [rbp-158h]
  char v59; // [rsp+30h] [rbp-148h] BYREF
  char v60; // [rsp+31h] [rbp-147h] BYREF
  char v61; // [rsp+32h] [rbp-146h] BYREF
  _BYTE v62[5]; // [rsp+33h] [rbp-145h] BYREF
  __int64 v63; // [rsp+38h] [rbp-140h] BYREF
  HSTRING string; // [rsp+40h] [rbp-138h] BYREF
  BYTE v65[8]; // [rsp+48h] [rbp-130h] BYREF
  HSTRING v66; // [rsp+50h] [rbp-128h] BYREF
  __int64 v67; // [rsp+58h] [rbp-120h] BYREF
  BYTE v68[8]; // [rsp+60h] [rbp-118h] BYREF
  LPOLESTR lpsz; // [rsp+68h] [rbp-110h] BYREF
  char v70; // [rsp+70h] [rbp-108h]
  __int64 v71; // [rsp+78h] [rbp-100h] BYREF
  __int64 v72; // [rsp+80h] [rbp-F8h] BYREF
  BYTE v73[8]; // [rsp+88h] [rbp-F0h] BYREF
  BYTE Data[8]; // [rsp+90h] [rbp-E8h] BYREF
  _BYTE v75[24]; // [rsp+98h] [rbp-E0h] BYREF
  _BYTE v76[8]; // [rsp+B0h] [rbp-C8h] BYREF
  int v77; // [rsp+B8h] [rbp-C0h]
  _BYTE v78[8]; // [rsp+D0h] [rbp-A8h] BYREF
  _BYTE v79[32]; // [rsp+D8h] [rbp-A0h] BYREF
  _BYTE v80[32]; // [rsp+F8h] [rbp-80h] BYREF
  IID rclsid; // [rsp+118h] [rbp-60h] BYREF
  _BYTE v82[32]; // [rsp+128h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v4 = 0;
  *(_DWORD *)v65 = 0;
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
  v63 = 0;
  *(_QWORD *)v68 = &v63;
  lpsz = 0;
  v70 = 1;
  v8 = StringFromCLSID(&rclsid, &lpsz);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v68);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x183,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v8,
      lpData);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
    return (unsigned int)v8;
  }
  std::wstring::wstring(v80, v63);
  std::wstring::wstring(v79, L"ProfileId");
  Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(a1, v79, v80);
  std::wstring::_Tidy_deallocate(v79);
  std::wstring::_Tidy_deallocate(v80);
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
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
    return v10;
  }
  std::wstring::wstring(v79, L"Timestamp");
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v79);
  v12 = RegSetValueExW(*(HKEY *)(a1 + 16), v11, 0, 0xBu, Data, 8u);
  if ( v12 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
      (const char *)v12,
      lpDataa);
  std::wstring::_Tidy_deallocate(v79);
  v59 = 0;
  v60 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, char *))(*a2 + 72))(a2, &v59);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v13,
      lpDataa);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
    return v14;
  }
  v15 = (*(__int64 (__fastcall **)(__int64 *, char *))(*a2 + 88))(a2, &v60);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18F,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v15,
      lpDataa);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
    return v16;
  }
  if ( v59 || (v17 = 0, v60) )
    v17 = 1;
  *(_DWORD *)v68 = v17;
  std::wstring::wstring(v79, L"IsSingleAppProfile");
  v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v79);
  v19 = RegSetValueExW(*(HKEY *)(a1 + 16), v18, 0, 4u, v68, 4u);
  if ( v19 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
      (const char *)v19,
      lpDatab);
  std::wstring::_Tidy_deallocate(v79);
  if ( v17 )
  {
    *(_QWORD *)v68 = 0;
    v20 = *(__int64 (__fastcall **)(__int64 *, BYTE *))(*a2 + 232);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      v68,
      0);
    v21 = v20(a2, v68);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x197,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
        (const char *)(unsigned int)v21,
        lpDatab);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(v68);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
      return v22;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)v68, 0);
    if ( StringRawBuffer && *StringRawBuffer )
    {
      std::wstring::wstring(v80, StringRawBuffer);
      std::wstring::wstring(v79, L"BreakoutKey");
      Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(a1, v79, v80);
      std::wstring::_Tidy_deallocate(v79);
      std::wstring::_Tidy_deallocate(v80);
    }
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(v68);
  }
  v61 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64 *, char *))(*a2 + 152))(a2, &v61);
  v25 = v24;
  if ( v24 >= 0 )
  {
    *(_DWORD *)v73 = v61 != 0;
    std::wstring::wstring(v79, L"TaskbarAllowed");
    v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v79);
    v27 = RegSetValueExW(*(HKEY *)(a1 + 16), v26, 0, 4u, v73, 4u);
    if ( v27 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
        (const char *)v27,
        lpDatac);
    std::wstring::_Tidy_deallocate(v79);
    v62[0] = 0;
    v28 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*a2 + 168))(a2, v62);
    v29 = v28;
    if ( v28 >= 0 )
    {
      *(_DWORD *)v65 = v62[0] != 0;
      std::wstring::wstring(v79, L"AllAppListAllowed");
      v30 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v79);
      v31 = RegSetValueExW(*(HKEY *)(a1 + 16), v30, 0, 4u, v65, 4u);
      if ( v31 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0xCD,
          (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
          (const char *)v31,
          lpDatad);
      std::wstring::_Tidy_deallocate(v79);
      string = 0;
      v32 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a2 + 136);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v33 = v32(a2, &string);
      v34 = v33;
      if ( v33 >= 0 )
      {
        v35 = WindowsGetStringRawBuffer(string, 0);
        std::wstring::wstring(v80, v35);
        std::wstring::wstring(v79, L"StartPinsPolicy");
        Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(a1, v79, v80);
        std::wstring::_Tidy_deallocate(v79);
        std::wstring::_Tidy_deallocate(v80);
        v66 = 0;
        v36 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a2 + 248);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          &v66,
          0);
        v37 = v36(a2, &v66);
        v38 = v37;
        if ( v37 >= 0 )
        {
          v39 = WindowsGetStringRawBuffer(v66, 0);
          std::wstring::wstring(v80, v39);
          std::wstring::wstring(v79, L"StartLayoutPolicy");
          Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(a1, v79, v80);
          std::wstring::_Tidy_deallocate(v79);
          std::wstring::_Tidy_deallocate(v80);
          std::wstring::wstring(v79, L"AllowedApps");
          Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(a1, v75, v79);
          std::wstring::_Tidy_deallocate(v79);
          v40 = *a2;
          v67 = 0;
          v41 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v40 + 120))(a2, &v67);
          v42 = v41;
          if ( v41 >= 0 )
          {
            v43 = 0;
            wil::get_range_nothrow<Windows::Internal::AssignedAccess::AssignedAccessProfile *>(v76, v67);
            wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>>::begin(
              v76,
              v68);
            v44 = v77;
            while ( **(int **)(*(_QWORD *)v68 + 16LL) >= 0 && (_DWORD)lpsz != v44 )
            {
              v45 = (_QWORD *)wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessProfile *>>::vector_iterator_nothrow::operator*(v68);
              std::_Integral_to_string<unsigned short,unsigned int>(v82, v43);
              std::operator+<unsigned short>(v79, L"App", v82);
              std::wstring::_Tidy_deallocate(v82);
              Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(v75, v80, v79);
              v46 = Windows::Internal::AssignedAccess::Details::Serialize<Windows::Internal::AssignedAccess::RegistryKeyBroker>(
                      v80,
                      *v45);
              v47 = v46;
              if ( v46 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1BF,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                  (const char *)(unsigned int)v46,
                  lpDatad);
                Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v80);
                std::wstring::_Tidy_deallocate(v79);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v78);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v67);
                Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v75);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v66);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
                return v47;
              }
              ++v43;
              v4 |= 1u;
              Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v80);
              std::wstring::_Tidy_deallocate(v79);
              wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessUserInfo *>>::vector_iterator_nothrow::operator+=(v68);
            }
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v78);
            v48 = *a2;
            v71 = 0;
            v49 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v48 + 184))(a2, &v71);
            v50 = v49;
            if ( v49 >= 0 )
            {
              Windows::Internal::AssignedAccess::Details::SerializeAllowedCommonFileDialogLocations<Windows::Internal::AssignedAccess::RegistryKeyBroker>(
                a1,
                v71);
              v51 = *a2;
              v72 = 0;
              v52 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v51 + 200))(a2, &v72);
              v53 = v52;
              if ( v52 >= 0 )
              {
                if ( v72 )
                  Windows::Internal::AssignedAccess::Details::SerializeFileExplorerRestrictions<Windows::Internal::AssignedAccess::RegistryKeyBroker>(a1);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v72);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v71);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v67);
                Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v75);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v66);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
                return 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1C8,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                  (const char *)(unsigned int)v52,
                  lpDatad);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v72);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v71);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v67);
                Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v75);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v66);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
                return v53;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1C3,
                (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                (const char *)(unsigned int)v49,
                lpDatad);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v71);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v67);
              Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v75);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v66);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
              return v50;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1B8,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
              (const char *)(unsigned int)v41,
              lpDatad);
            wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v67);
            Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v75);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v66);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
            return v42;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B2,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
            (const char *)(unsigned int)v37,
            lpDatad);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v66);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
          return v38;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AD,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
          (const char *)(unsigned int)v33,
          lpDatad);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
        return v34;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A7,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
        (const char *)(unsigned int)v28,
        lpDatac);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
      return v29;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v24,
      lpDatab);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
    return v25;
  }
}

```

## disassembly

```asm
0x18005d4e8  mov     r11, rsp
0x18005d4eb  mov     [r11+18h], rbx
0x18005d4ef  mov     [r11+20h], rsi
0x18005d4f3  push    rdi
0x18005d4f4  push    r12
0x18005d4f6  push    r13
0x18005d4f8  push    r14
0x18005d4fa  push    r15
0x18005d4fc  sub     rsp, 150h
0x18005d503  mov     rax, cs:__security_cookie
0x18005d50a  xor     rax, rsp
0x18005d50d  mov     [rsp+178h+var_30], rax
0x18005d515  mov     rdi, rdx
0x18005d518  mov     rsi, rcx
0x18005d51b  xor     r13d, r13d
0x18005d51e  mov     r12d, r13d
0x18005d521  mov     dword ptr [rsp+178h+var_130], r13d
0x18005d526  xorps   xmm0, xmm0
0x18005d529  movups  xmmword ptr [r11-60h], xmm0
0x18005d52e  mov     rax, [rdx]
0x18005d531  lea     rdx, [r11-60h]
0x18005d535  mov     rcx, rdi
0x18005d538  mov     rax, [rax+38h]
0x18005d53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d541  mov     ebx, eax
0x18005d543  test    eax, eax
0x18005d545  jns     short loc_18005D56A
0x18005d547  mov     rcx, [rsp+178h]; this
0x18005d54f  mov     r9d, eax; char *
0x18005d552  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005d559  mov     edx, 181h; void *
0x18005d55e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d563  mov     eax, ebx
0x18005d565  jmp     loc_18005E05C
0x18005d56a  mov     [rsp+178h+var_140], r13
0x18005d56f  lea     rax, [rsp+178h+var_140]
0x18005d574  mov     qword ptr [rsp+178h+var_118], rax
0x18005d579  mov     [rsp+178h+lpsz], r13
0x18005d57e  mov     [rsp+178h+var_108], 1
0x18005d583  lea     rdx, [rsp+178h+lpsz]; lplpsz
0x18005d588  lea     rcx, [rsp+178h+rclsid]; rclsid
0x18005d590  call    cs:__imp_StringFromCLSID
0x18005d596  mov     ebx, eax
0x18005d598  lea     rcx, [rsp+178h+var_118]
0x18005d59d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005d5a2  test    ebx, ebx
0x18005d5a4  jns     short loc_18005D5D4
0x18005d5a6  mov     rcx, [rsp+178h]; this
0x18005d5ae  mov     r9d, ebx; char *
0x18005d5b1  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005d5b8  mov     edx, 183h; void *
0x18005d5bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d5c2  nop
0x18005d5c3  lea     rcx, [rsp+178h+var_140]
0x18005d5c8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d5cd  mov     eax, ebx
0x18005d5cf  jmp     loc_18005E05C
0x18005d5d4  mov     rdx, [rsp+178h+var_140]
0x18005d5d9  lea     rcx, [rsp+178h+var_80]
0x18005d5e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d5e6  nop
0x18005d5e7  lea     rdx, aProfileid; "ProfileId"
0x18005d5ee  lea     rcx, [rsp+178h+var_A0]
0x18005d5f6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d5fb  nop
0x18005d5fc  lea     r8, [rsp+178h+var_80]
0x18005d604  lea     rdx, [rsp+178h+var_A0]
0x18005d60c  mov     rcx, rsi
0x18005d60f  call    ?SetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(std::wstring const &,std::wstring const &)
0x18005d614  nop
0x18005d615  lea     rcx, [rsp+178h+var_A0]
0x18005d61d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d622  nop
0x18005d623  lea     rcx, [rsp+178h+var_80]
0x18005d62b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d630  mov     qword ptr [rsp+178h+Data], r13
0x18005d638  mov     rax, [rdi]
0x18005d63b  lea     rdx, [rsp+178h+Data]
0x18005d643  mov     rcx, rdi
0x18005d646  mov     rax, [rax+30h]
0x18005d64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d64f  mov     ebx, eax
0x18005d651  test    eax, eax
0x18005d653  jns     short loc_18005D683
0x18005d655  mov     rcx, [rsp+178h]; this
0x18005d65d  mov     r9d, eax; char *
0x18005d660  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005d667  mov     edx, 188h; void *
0x18005d66c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d671  nop
0x18005d672  lea     rcx, [rsp+178h+var_140]
0x18005d677  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d67c  mov     eax, ebx
0x18005d67e  jmp     loc_18005E05C
0x18005d683  lea     rdx, aTimestamp; "Timestamp"
0x18005d68a  lea     rcx, [rsp+178h+var_A0]
0x18005d692  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d697  nop
0x18005d698  lea     rcx, [rsp+178h+var_A0]
0x18005d6a0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005d6a5  mov     rdx, rax; lpValueName
0x18005d6a8  mov     [rsp+178h+cbData], 8; cbData
0x18005d6b0  lea     rax, [rsp+178h+Data]
0x18005d6b8  mov     [rsp+178h+lpData], rax; int
0x18005d6bd  mov     r9d, 0Bh; dwType
0x18005d6c3  xor     r8d, r8d; Reserved
0x18005d6c6  mov     rcx, [rsi+10h]; hKey
0x18005d6ca  call    cs:__imp_RegSetValueExW
0x18005d6d0  mov     rcx, [rsp+178h]; this
0x18005d6d8  test    eax, eax
0x18005d6da  jz      short loc_18005D6F1
0x18005d6dc  mov     r9d, eax; char *
0x18005d6df  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005d6e6  mov     edx, 0F4h; void *
0x18005d6eb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005d6f1  lea     rcx, [rsp+178h+var_A0]
0x18005d6f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d6fe  mov     [rsp+178h+var_148], r13b
0x18005d703  mov     [rsp+178h+var_147], r13b
0x18005d708  mov     rax, [rdi]
0x18005d70b  lea     rdx, [rsp+178h+var_148]
0x18005d710  mov     rcx, rdi
0x18005d713  mov     rax, [rax+48h]
0x18005d717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d71c  mov     ebx, eax
0x18005d71e  test    eax, eax
0x18005d720  jns     short loc_18005D750
0x18005d722  mov     rcx, [rsp+178h]; this
0x18005d72a  mov     r9d, eax; char *
0x18005d72d  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005d734  mov     edx, 18Eh; void *
0x18005d739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d73e  nop
0x18005d73f  lea     rcx, [rsp+178h+var_140]
0x18005d744  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d749  mov     eax, ebx
0x18005d74b  jmp     loc_18005E05C
0x18005d750  mov     rax, [rdi]
0x18005d753  lea     rdx, [rsp+178h+var_147]
0x18005d758  mov     rcx, rdi
0x18005d75b  mov     rax, [rax+58h]
0x18005d75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d764  mov     ebx, eax
0x18005d766  test    eax, eax
0x18005d768  jns     short loc_18005D798
0x18005d76a  mov     rcx, [rsp+178h]; this
0x18005d772  mov     r9d, eax; char *
0x18005d775  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005d77c  mov     edx, 18Fh; void *
0x18005d781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d786  nop
0x18005d787  lea     rcx, [rsp+178h+var_140]
0x18005d78c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d791  mov     eax, ebx
0x18005d793  jmp     loc_18005E05C
0x18005d798  cmp     [rsp+178h+var_148], r13b
0x18005d79d  jnz     short loc_18005D7A9
0x18005d79f  cmp     [rsp+178h+var_147], r13b
0x18005d7a4  mov     bl, r13b
0x18005d7a7  jz      short loc_18005D7AB
0x18005d7a9  mov     bl, 1
0x18005d7ab  movzx   eax, bl
0x18005d7ae  mov     dword ptr [rsp+178h+var_118], eax
0x18005d7b2  lea     rdx, aIssingleapppro; "IsSingleAppProfile"
0x18005d7b9  lea     rcx, [rsp+178h+var_A0]
0x18005d7c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d7c6  nop
0x18005d7c7  lea     rcx, [rsp+178h+var_A0]
0x18005d7cf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005d7d4  mov     rdx, rax; lpValueName
0x18005d7d7  mov     r14d, 4
0x18005d7dd  mov     [rsp+178h+cbData], r14d; cbData
0x18005d7e2  lea     rax, [rsp+178h+var_118]
0x18005d7e7  mov     [rsp+178h+lpData], rax; int
0x18005d7ec  mov     r9d, r14d; dwType
0x18005d7ef  xor     r8d, r8d; Reserved
0x18005d7f2  mov     rcx, [rsi+10h]; hKey
0x18005d7f6  call    cs:__imp_RegSetValueExW
0x18005d7fc  mov     rcx, [rsp+178h]; this
0x18005d804  test    eax, eax
0x18005d806  jz      short loc_18005D81D
0x18005d808  mov     r9d, eax; char *
0x18005d80b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005d812  mov     edx, 0CDh; void *
0x18005d817  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005d81d  lea     rcx, [rsp+178h+var_A0]
0x18005d825  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d82a  test    bl, bl
0x18005d82c  jz      loc_18005D919
0x18005d832  mov     qword ptr [rsp+178h+var_118], r13
0x18005d837  mov     rax, [rdi]
0x18005d83a  mov     rbx, [rax+0E8h]
0x18005d841  xor     edx, edx
0x18005d843  lea     rcx, [rsp+178h+var_118]
0x18005d848  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005d84d  lea     rdx, [rsp+178h+var_118]
0x18005d852  mov     rcx, rdi
0x18005d855  mov     rax, rbx
0x18005d858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d85d  mov     ebx, eax
0x18005d85f  test    eax, eax
0x18005d861  jns     short loc_18005D89C
0x18005d863  mov     rcx, [rsp+178h]; this
0x18005d86b  mov     r9d, eax; char *
0x18005d86e  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005d875  mov     edx, 197h; void *
0x18005d87a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d87f  nop
0x18005d880  lea     rcx, [rsp+178h+var_118]
0x18005d885  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005d88a  nop
0x18005d88b  lea     rcx, [rsp+178h+var_140]
0x18005d890  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d895  mov     eax, ebx
0x18005d897  jmp     loc_18005E05C
0x18005d89c  xor     edx, edx; length
0x18005d89e  mov     rcx, qword ptr [rsp+178h+var_118]; string
0x18005d8a3  call    cs:__imp_WindowsGetStringRawBuffer
0x18005d8a9  test    rax, rax
0x18005d8ac  jz      short loc_18005D90F
0x18005d8ae  cmp     [rax], r13w
0x18005d8b2  jz      short loc_18005D90F
0x18005d8b4  mov     rdx, rax
0x18005d8b7  lea     rcx, [rsp+178h+var_80]
0x18005d8bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d8c4  nop
0x18005d8c5  lea     rdx, aBreakoutkey; "BreakoutKey"
0x18005d8cc  lea     rcx, [rsp+178h+var_A0]
0x18005d8d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d8d9  nop
0x18005d8da  lea     r8, [rsp+178h+var_80]
0x18005d8e2  lea     rdx, [rsp+178h+var_A0]
0x18005d8ea  mov     rcx, rsi
0x18005d8ed  call    ?SetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(std::wstring const &,std::wstring const &)
0x18005d8f2  nop
0x18005d8f3  lea     rcx, [rsp+178h+var_A0]
0x18005d8fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d900  nop
0x18005d901  lea     rcx, [rsp+178h+var_80]
0x18005d909  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d90e  nop
0x18005d90f  lea     rcx, [rsp+178h+var_118]
0x18005d914  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005d919  mov     [rsp+178h+var_146], r13b
0x18005d91e  mov     rax, [rdi]
0x18005d921  lea     rdx, [rsp+178h+var_146]
0x18005d926  mov     rcx, rdi
0x18005d929  mov     rax, [rax+98h]
0x18005d930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d935  mov     ebx, eax
0x18005d937  test    eax, eax
0x18005d939  jns     short loc_18005D969
0x18005d93b  mov     rcx, [rsp+178h]; this
0x18005d943  mov     r9d, eax; char *
0x18005d946  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005d94d  mov     edx, 1A1h; void *
0x18005d952  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d957  nop
0x18005d958  lea     rcx, [rsp+178h+var_140]
0x18005d95d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d962  mov     eax, ebx
0x18005d964  jmp     loc_18005E05C
0x18005d969  mov     eax, r13d
0x18005d96c  cmp     [rsp+178h+var_146], r13b
0x18005d971  setnz   al
0x18005d974  mov     dword ptr [rsp+178h+var_F0], eax
0x18005d97b  lea     rdx, aTaskbarallowed; "TaskbarAllowed"
0x18005d982  lea     rcx, [rsp+178h+var_A0]
0x18005d98a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d98f  nop
0x18005d990  lea     rcx, [rsp+178h+var_A0]
0x18005d998  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005d99d  mov     rdx, rax; lpValueName
0x18005d9a0  mov     [rsp+178h+cbData], r14d; cbData
0x18005d9a5  lea     rax, [rsp+178h+var_F0]
0x18005d9ad  mov     [rsp+178h+lpData], rax; int
0x18005d9b2  mov     r9d, r14d; dwType
0x18005d9b5  xor     r8d, r8d; Reserved
0x18005d9b8  mov     rcx, [rsi+10h]; hKey
0x18005d9bc  call    cs:__imp_RegSetValueExW
0x18005d9c2  mov     rcx, [rsp+178h]; this
0x18005d9ca  test    eax, eax
0x18005d9cc  jz      short loc_18005D9E3
0x18005d9ce  mov     r9d, eax; char *
0x18005d9d1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005d9d8  mov     edx, 0CDh; void *
0x18005d9dd  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005d9e3  lea     rcx, [rsp+178h+var_A0]
0x18005d9eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d9f0  mov     [rsp+178h+var_145], r13b
0x18005d9f5  mov     rax, [rdi]
0x18005d9f8  lea     rdx, [rsp+178h+var_145]
0x18005d9fd  mov     rcx, rdi
0x18005da00  mov     rax, [rax+0A8h]
0x18005da07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da0c  mov     ebx, eax
0x18005da0e  test    eax, eax
0x18005da10  jns     short loc_18005DA40
0x18005da12  mov     rcx, [rsp+178h]; this
0x18005da1a  mov     r9d, eax; char *
  ... truncated ...
```
