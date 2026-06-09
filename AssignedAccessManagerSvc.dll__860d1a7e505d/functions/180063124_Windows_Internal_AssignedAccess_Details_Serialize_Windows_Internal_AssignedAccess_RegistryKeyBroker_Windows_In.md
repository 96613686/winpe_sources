# Windows::Internal::AssignedAccess::Details::Serialize(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *)

- ea: `0x180063124`
- end: `0x1800637f1`
- name: `?Serialize@Details@AssignedAccess@Internal@Windows@@YAJAEAVRegistryKeyBroker@234@PEAUIAssignedAccessUserInfo@234@@Z`
- size: `1741`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::Details *__hidden this, struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180066928`
- `0x180066d38`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x180022d00`
- `0x1800271e4`
- `0x18002901c`
- `0x18002b190`
- `0x180037454`
- `0x1800575cc`
- `0x18005af78`
- `0x180063058`
- `0x180063124`
- `0x180063b68`
- `0x180064314`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006322f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006322f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180063372`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180063372`

## string_xrefs

- `0x180063387`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x180063337`: `ConfigSource`
- `0x18006317a`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x1800631d2`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x180063253`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x180063301`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x1800633c8`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18006343e`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x1800634ac`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18006352d`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x1800635a1`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18006361d`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x180063690`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18006372c`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::Details::Serialize(
        HKEY *this,
        struct Windows::Internal::AssignedAccess::RegistryKeyBroker *a2,
        struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *a3)
{
  __int64 v5; // rax
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  HRESULT v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  const WCHAR *v14; // rax
  unsigned int v15; // eax
  int v16; // eax
  unsigned int v17; // ebx
  __int64 (__fastcall *v18)(struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, __int64 *); // rbx
  int v19; // eax
  unsigned int v20; // ebx
  struct Windows::Internal::AssignedAccess::RegistryKeyBroker *v21; // rbx
  int v22; // eax
  unsigned int v23; // edi
  __int64 (__fastcall *v24)(struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, __int64 *); // rdi
  int v25; // eax
  unsigned int v26; // edi
  int v27; // eax
  unsigned int v28; // edi
  int v29; // eax
  unsigned int v30; // edi
  int v31; // eax
  unsigned int v32; // edi
  struct Windows::Internal::AssignedAccess::IAssignedAccessAccount *v33; // r8
  int v34; // eax
  unsigned int v35; // ebx
  int lpData; // [rsp+20h] [rbp-C8h]
  unsigned int lpDataa; // [rsp+20h] [rbp-C8h]
  BYTE Data[8]; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+50h] [rbp-98h] BYREF
  int v43; // [rsp+58h] [rbp-90h] BYREF
  unsigned int v44; // [rsp+5Ch] [rbp-8Ch] BYREF
  _BYTE v45[24]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v46[32]; // [rsp+78h] [rbp-70h] BYREF
  __int64 *v47; // [rsp+98h] [rbp-50h] BYREF
  LPOLESTR lpsz; // [rsp+A0h] [rbp-48h] BYREF
  char v49; // [rsp+A8h] [rbp-40h]
  IID rclsid; // [rsp+B8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v5 = *(_QWORD *)a2;
  v39 = 0;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, __int64 *))(v5 + 64))(
         a2,
         &v39);
  v7 = v6;
  if ( v6 >= 0 )
  {
    rclsid = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, IID *))(*(_QWORD *)v39 + 56LL))(v39, &rclsid);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v40 = 0;
      v47 = &v40;
      lpsz = 0;
      v49 = 1;
      v11 = StringFromCLSID(&rclsid, &lpsz);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v47);
      if ( v11 >= 0 )
      {
        std::wstring::wstring(v46, v40);
        std::wstring::wstring(&v47, L"DefaultProfileId");
        Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(this, &v47, v46);
        std::wstring::_Tidy_deallocate(&v47);
        std::wstring::_Tidy_deallocate(v46);
        v43 = 0;
        v12 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, int *))(*(_QWORD *)a2 + 72LL))(
                a2,
                &v43);
        v13 = v12;
        if ( v12 >= 0 )
        {
          *(_DWORD *)Data = v43;
          std::wstring::wstring(v46, L"ConfigSource");
          v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
          v15 = RegSetValueExW(this[2], v14, 0, 4u, Data, 4u);
          if ( v15 )
            wil::details::in1diag3::_Throw_Win32(
              retaddr,
              (void *)0xCD,
              (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
              (const char *)v15,
              lpDataa);
          std::wstring::_Tidy_deallocate(v46);
          *(_QWORD *)Data = 0;
          v16 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessAccount,Windows::Internal::AssignedAccess::IAssignedAccessAccount,>(Data);
          v17 = v16;
          if ( v16 >= 0 )
          {
            v41 = 0;
            v18 = *(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, __int64 *))(*(_QWORD *)a2 + 48LL);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
              &v41,
              0);
            v19 = v18(a2, &v41);
            v20 = v19;
            if ( v19 >= 0 )
            {
              v21 = *(struct Windows::Internal::AssignedAccess::RegistryKeyBroker **)Data;
              v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)Data + 56LL))(*(_QWORD *)Data, v41);
              v23 = v22;
              if ( v22 >= 0 )
              {
                v42 = 0;
                v24 = *(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, __int64 *))(*(_QWORD *)a2 + 56LL);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
                  &v42,
                  0);
                v25 = v24(a2, &v42);
                v26 = v25;
                if ( v25 >= 0 )
                {
                  v27 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, __int64))(*(_QWORD *)v21 + 72LL))(
                          v21,
                          v42);
                  v28 = v27;
                  if ( v27 >= 0 )
                  {
                    v44 = 0;
                    v29 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, unsigned int *))(*(_QWORD *)a2 + 88LL))(
                            a2,
                            &v44);
                    v30 = v29;
                    if ( v29 >= 0 )
                    {
                      v31 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::RegistryKeyBroker *, _QWORD))(*(_QWORD *)v21 + 88LL))(
                              v21,
                              v44);
                      v32 = v31;
                      if ( v31 >= 0 )
                      {
                        std::wstring::wstring(v46, L"Account");
                        Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(this, v45, v46);
                        std::wstring::_Tidy_deallocate(v46);
                        v34 = Windows::Internal::AssignedAccess::Details::Serialize(
                                (Windows::Internal::AssignedAccess::Details *)v45,
                                v21,
                                v33);
                        v35 = v34;
                        if ( v34 >= 0 )
                        {
                          Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v45);
                          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v42);
                          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v41);
                          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(Data);
                          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
                          return 0;
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0xE7,
                            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                            (const char *)(unsigned int)v34,
                            lpDataa);
                          Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v45);
                          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v42);
                          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v41);
                          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(Data);
                          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
                          return v35;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xE4,
                          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                          (const char *)(unsigned int)v31,
                          lpDataa);
                        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v42);
                        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v41);
                        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(Data);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
                        return v32;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xE3,
                        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                        (const char *)(unsigned int)v29,
                        lpDataa);
                      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v42);
                      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v41);
                      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(Data);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
                      return v30;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xE1,
                      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                      (const char *)(unsigned int)v27,
                      lpDataa);
                    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v42);
                    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v41);
                    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(Data);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
                    return v28;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xE0,
                    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                    (const char *)(unsigned int)v25,
                    lpDataa);
                  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v42);
                  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v41);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(Data);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
                  return v26;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xDE,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                  (const char *)(unsigned int)v22,
                  lpDataa);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v41);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(Data);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
                return v23;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xDD,
                (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                (const char *)(unsigned int)v19,
                lpDataa);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v41);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(Data);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
              return v20;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xDB,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
              (const char *)(unsigned int)v16,
              lpDataa);
            wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(Data);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
            wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
            return v17;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD7,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
            (const char *)(unsigned int)v12,
            lpData);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
          return v13;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD4,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
          (const char *)(unsigned int)v11,
          lpData);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
        return (unsigned int)v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
        (const char *)(unsigned int)v9,
        lpData);
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v6,
      lpData);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
    return v7;
  }
}

```

## disassembly

```asm
0x180063124  mov     [rsp+arg_10], rbx
0x180063129  push    rsi
0x18006312a  push    rdi
0x18006312b  push    r14
0x18006312d  sub     rsp, 0D0h
0x180063134  mov     rax, cs:__security_cookie
0x18006313b  xor     rax, rsp
0x18006313e  mov     [rsp+0E8h+var_20], rax
0x180063146  mov     rsi, rdx
0x180063149  mov     r14, rcx
0x18006314c  mov     rax, [rdx]
0x18006314f  mov     [rsp+0E8h+var_B0], 0
0x180063158  lea     rdx, [rsp+0E8h+var_B0]
0x18006315d  mov     rcx, rsi
0x180063160  mov     rax, [rax+40h]
0x180063164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063169  mov     ebx, eax
0x18006316b  test    eax, eax
0x18006316d  jns     short loc_18006319D
0x18006316f  mov     rcx, [rsp+0E8h]; this
0x180063177  mov     r9d, eax; char *
0x18006317a  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180063181  mov     edx, 0D0h; void *
0x180063186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006318b  nop
0x18006318c  lea     rcx, [rsp+0E8h+var_B0]
0x180063191  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180063196  mov     eax, ebx
0x180063198  jmp     loc_1800637CC
0x18006319d  xorps   xmm0, xmm0
0x1800631a0  movups  xmmword ptr [rsp+0E8h+rclsid.Data1], xmm0
0x1800631a8  mov     rcx, [rsp+0E8h+var_B0]
0x1800631ad  mov     rax, [rcx]
0x1800631b0  lea     rdx, [rsp+0E8h+rclsid]
0x1800631b8  mov     rax, [rax+38h]
0x1800631bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631c1  mov     ebx, eax
0x1800631c3  test    eax, eax
0x1800631c5  jns     short loc_1800631F5
0x1800631c7  mov     rcx, [rsp+0E8h]; this
0x1800631cf  mov     r9d, eax; char *
0x1800631d2  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800631d9  mov     edx, 0D2h; void *
0x1800631de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800631e3  nop
0x1800631e4  lea     rcx, [rsp+0E8h+var_B0]
0x1800631e9  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800631ee  mov     eax, ebx
0x1800631f0  jmp     loc_1800637CC
0x1800631f5  mov     [rsp+0E8h+var_A8], 0
0x1800631fe  lea     rax, [rsp+0E8h+var_A8]
0x180063203  mov     [rsp+0E8h+var_50], rax
0x18006320b  mov     [rsp+0E8h+lpsz], 0
0x180063217  mov     [rsp+0E8h+var_40], 1
0x18006321f  lea     rdx, [rsp+0E8h+lpsz]; lplpsz
0x180063227  lea     rcx, [rsp+0E8h+rclsid]; rclsid
0x18006322f  call    cs:__imp_StringFromCLSID
0x180063235  mov     ebx, eax
0x180063237  lea     rcx, [rsp+0E8h+var_50]
0x18006323f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180063244  test    ebx, ebx
0x180063246  jns     short loc_180063281
0x180063248  mov     rcx, [rsp+0E8h]; this
0x180063250  mov     r9d, ebx; char *
0x180063253  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18006325a  mov     edx, 0D4h; void *
0x18006325f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063264  nop
0x180063265  lea     rcx, [rsp+0E8h+var_A8]
0x18006326a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006326f  nop
0x180063270  lea     rcx, [rsp+0E8h+var_B0]
0x180063275  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18006327a  mov     eax, ebx
0x18006327c  jmp     loc_1800637CC
0x180063281  mov     rdx, [rsp+0E8h+var_A8]
0x180063286  lea     rcx, [rsp+0E8h+var_70]
0x18006328b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180063290  nop
0x180063291  lea     rdx, aDefaultprofile; "DefaultProfileId"
0x180063298  lea     rcx, [rsp+0E8h+var_50]
0x1800632a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800632a5  nop
0x1800632a6  lea     r8, [rsp+0E8h+var_70]
0x1800632ab  lea     rdx, [rsp+0E8h+var_50]
0x1800632b3  mov     rcx, r14
0x1800632b6  call    ?SetString@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::SetString(std::wstring const &,std::wstring const &)
0x1800632bb  nop
0x1800632bc  lea     rcx, [rsp+0E8h+var_50]
0x1800632c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800632c9  nop
0x1800632ca  lea     rcx, [rsp+0E8h+var_70]
0x1800632cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800632d4  mov     [rsp+0E8h+var_90], 0
0x1800632dc  mov     rax, [rsi]
0x1800632df  lea     rdx, [rsp+0E8h+var_90]
0x1800632e4  mov     rcx, rsi
0x1800632e7  mov     rax, [rax+48h]
0x1800632eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632f0  mov     ebx, eax
0x1800632f2  test    eax, eax
0x1800632f4  jns     short loc_18006332F
0x1800632f6  mov     rcx, [rsp+0E8h]; this
0x1800632fe  mov     r9d, eax; char *
0x180063301  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180063308  mov     edx, 0D7h; void *
0x18006330d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063312  nop
0x180063313  lea     rcx, [rsp+0E8h+var_A8]
0x180063318  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006331d  nop
0x18006331e  lea     rcx, [rsp+0E8h+var_B0]
0x180063323  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180063328  mov     eax, ebx
0x18006332a  jmp     loc_1800637CC
0x18006332f  mov     eax, [rsp+0E8h+var_90]
0x180063333  mov     dword ptr [rsp+0E8h+Data], eax
0x180063337  lea     rdx, aConfigsource; "ConfigSource"
0x18006333e  lea     rcx, [rsp+0E8h+var_70]
0x180063343  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180063348  nop
0x180063349  lea     rcx, [rsp+0E8h+var_70]
0x18006334e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063353  mov     rdx, rax; lpValueName
0x180063356  mov     r9d, 4; dwType
0x18006335c  mov     [rsp+0E8h+cbData], r9d; cbData
0x180063361  lea     rax, [rsp+0E8h+Data]
0x180063366  mov     [rsp+0E8h+lpData], rax; int
0x18006336b  xor     r8d, r8d; Reserved
0x18006336e  mov     rcx, [r14+10h]; hKey
0x180063372  call    cs:__imp_RegSetValueExW
0x180063378  mov     rcx, [rsp+0E8h]; this
0x180063380  test    eax, eax
0x180063382  jz      short loc_180063399
0x180063384  mov     r9d, eax; char *
0x180063387  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18006338e  mov     edx, 0CDh; void *
0x180063393  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180063399  lea     rcx, [rsp+0E8h+var_70]
0x18006339e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800633a3  nop
0x1800633a4  mov     qword ptr [rsp+0E8h+Data], 0
0x1800633ad  lea     rcx, [rsp+0E8h+Data]
0x1800633b2  call    ??$MakeAndInitialize@VAssignedAccessAccount@AssignedAccess@Internal@Windows@@UIAssignedAccessAccount@234@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIAssignedAccessAccount@AssignedAccess@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessAccount,Windows::Internal::AssignedAccess::IAssignedAccessAccount,>(Windows::Internal::AssignedAccess::IAssignedAccessAccount * *)
0x1800633b7  mov     ebx, eax
0x1800633b9  test    eax, eax
0x1800633bb  jns     short loc_180063401
0x1800633bd  mov     rcx, [rsp+0E8h]; this
0x1800633c5  mov     r9d, eax; char *
0x1800633c8  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800633cf  mov     edx, 0DBh; void *
0x1800633d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800633d9  nop
0x1800633da  lea     rcx, [rsp+0E8h+Data]
0x1800633df  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800633e4  nop
0x1800633e5  lea     rcx, [rsp+0E8h+var_A8]
0x1800633ea  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800633ef  nop
0x1800633f0  lea     rcx, [rsp+0E8h+var_B0]
0x1800633f5  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800633fa  mov     eax, ebx
0x1800633fc  jmp     loc_1800637CC
0x180063401  mov     [rsp+0E8h+var_A0], 0
0x18006340a  mov     rax, [rsi]
0x18006340d  mov     rbx, [rax+30h]
0x180063411  xor     edx, edx
0x180063413  lea     rcx, [rsp+0E8h+var_A0]
0x180063418  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18006341d  lea     rdx, [rsp+0E8h+var_A0]
0x180063422  mov     rcx, rsi
0x180063425  mov     rax, rbx
0x180063428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006342d  mov     ebx, eax
0x18006342f  test    eax, eax
0x180063431  jns     short loc_180063482
0x180063433  mov     rcx, [rsp+0E8h]; this
0x18006343b  mov     r9d, eax; char *
0x18006343e  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180063445  mov     edx, 0DDh; void *
0x18006344a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006344f  nop
0x180063450  lea     rcx, [rsp+0E8h+var_A0]
0x180063455  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18006345a  nop
0x18006345b  lea     rcx, [rsp+0E8h+Data]
0x180063460  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180063465  nop
0x180063466  lea     rcx, [rsp+0E8h+var_A8]
0x18006346b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180063470  nop
0x180063471  lea     rcx, [rsp+0E8h+var_B0]
0x180063476  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18006347b  mov     eax, ebx
0x18006347d  jmp     loc_1800637CC
0x180063482  mov     rbx, qword ptr [rsp+0E8h+Data]
0x180063487  mov     rax, [rbx]
0x18006348a  mov     rdx, [rsp+0E8h+var_A0]
0x18006348f  mov     rcx, rbx
0x180063492  mov     rax, [rax+38h]
0x180063496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006349b  mov     edi, eax
0x18006349d  test    eax, eax
0x18006349f  jns     short loc_1800634F0
0x1800634a1  mov     rcx, [rsp+0E8h]; this
0x1800634a9  mov     r9d, eax; char *
0x1800634ac  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800634b3  mov     edx, 0DEh; void *
0x1800634b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800634bd  nop
0x1800634be  lea     rcx, [rsp+0E8h+var_A0]
0x1800634c3  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800634c8  nop
0x1800634c9  lea     rcx, [rsp+0E8h+Data]
0x1800634ce  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800634d3  nop
0x1800634d4  lea     rcx, [rsp+0E8h+var_A8]
0x1800634d9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800634de  nop
0x1800634df  lea     rcx, [rsp+0E8h+var_B0]
0x1800634e4  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800634e9  mov     eax, edi
0x1800634eb  jmp     loc_1800637CC
0x1800634f0  mov     [rsp+0E8h+var_98], 0
0x1800634f9  mov     rax, [rsi]
0x1800634fc  mov     rdi, [rax+38h]
0x180063500  xor     edx, edx
0x180063502  lea     rcx, [rsp+0E8h+var_98]
0x180063507  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18006350c  lea     rdx, [rsp+0E8h+var_98]
0x180063511  mov     rcx, rsi
0x180063514  mov     rax, rdi
0x180063517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006351c  mov     edi, eax
0x18006351e  test    eax, eax
0x180063520  jns     short loc_18006357C
0x180063522  mov     rcx, [rsp+0E8h]; this
0x18006352a  mov     r9d, eax; char *
0x18006352d  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180063534  mov     edx, 0E0h; void *
0x180063539  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006353e  nop
0x18006353f  lea     rcx, [rsp+0E8h+var_98]
0x180063544  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180063549  nop
0x18006354a  lea     rcx, [rsp+0E8h+var_A0]
0x18006354f  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180063554  nop
0x180063555  lea     rcx, [rsp+0E8h+Data]
0x18006355a  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18006355f  nop
0x180063560  lea     rcx, [rsp+0E8h+var_A8]
0x180063565  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006356a  nop
0x18006356b  lea     rcx, [rsp+0E8h+var_B0]
0x180063570  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180063575  mov     eax, edi
0x180063577  jmp     loc_1800637CC
0x18006357c  mov     rax, [rbx]
0x18006357f  mov     rdx, [rsp+0E8h+var_98]
0x180063584  mov     rcx, rbx
0x180063587  mov     rax, [rax+48h]
0x18006358b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063590  mov     edi, eax
0x180063592  test    eax, eax
0x180063594  jns     short loc_1800635F0
0x180063596  mov     rcx, [rsp+0E8h]; this
0x18006359e  mov     r9d, eax; char *
0x1800635a1  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800635a8  mov     edx, 0E1h; void *
0x1800635ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800635b2  nop
0x1800635b3  lea     rcx, [rsp+0E8h+var_98]
0x1800635b8  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800635bd  nop
0x1800635be  lea     rcx, [rsp+0E8h+var_A0]
0x1800635c3  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800635c8  nop
0x1800635c9  lea     rcx, [rsp+0E8h+Data]
0x1800635ce  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800635d3  nop
0x1800635d4  lea     rcx, [rsp+0E8h+var_A8]
0x1800635d9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800635de  nop
0x1800635df  lea     rcx, [rsp+0E8h+var_B0]
0x1800635e4  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800635e9  mov     eax, edi
0x1800635eb  jmp     loc_1800637CC
0x1800635f0  mov     [rsp+0E8h+var_8C], 0
0x1800635f8  mov     rax, [rsi]
0x1800635fb  lea     rdx, [rsp+0E8h+var_8C]
0x180063600  mov     rcx, rsi
0x180063603  mov     rax, [rax+58h]
0x180063607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006360c  mov     edi, eax
0x18006360e  test    eax, eax
0x180063610  jns     short loc_18006366C
0x180063612  mov     rcx, [rsp+0E8h]; this
0x18006361a  mov     r9d, eax; char *
0x18006361d  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
  ... truncated ...
```
