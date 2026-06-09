# Windows::Internal::AssignedAccess::Details::DeserializeV0(Windows::Internal::AssignedAccess::IAssignedAccessProfile * *,Windows::Internal::AssignedAccess::IAssignedAccessConfig * *)

- ea: `0x18005fad0`
- end: `0x1800601a2`
- name: `?DeserializeV0@Details@AssignedAccess@Internal@Windows@@YAJPEAPEAUIAssignedAccessProfile@234@PEAPEAUIAssignedAccessConfig@234@@Z`
- size: `1746`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::Details *__hidden this, struct Windows::Internal::AssignedAccess::IAssignedAccessProfile **, struct Windows::Internal::AssignedAccess::IAssignedAccessConfig **)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005716c`

## callees

- `0x180006640`
- `0x1800088bc`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x18000f8dc`
- `0x180010c98`
- `0x180015300`
- `0x18002249c`
- `0x180022930`
- `0x180029c04`
- `0x18004b730`
- `0x18005ac34`
- `0x18005ac7c`
- `0x18005b0d4`
- `0x18005b274`
- `0x18005b470`
- `0x18005b5c8`
- `0x18005b848`
- `0x18005eb70`
- `0x18005f0e0`
- `0x18005f5b4`
- `0x18005fad0`
- `0x180060244`
- `0x180061cf0`

## string_xrefs

- `0x18005fb59`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005fcad`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005fd76`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005fe07`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005fed1`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005ff83`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x180060048`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005fc35`: `ConfigLevel`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::Details::DeserializeV0(
        Windows::Internal::AssignedAccess::Details *this,
        struct Windows::Internal::AssignedAccess::IAssignedAccessProfile **a2,
        struct Windows::Internal::AssignedAccess::IAssignedAccessConfig **a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  _DWORD *v8; // rax
  bool v9; // bl
  __int64 v10; // rax
  int v11; // eax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rbx
  void *v18; // rax
  __int64 v19; // rsi
  __int64 v20; // r9
  int v21; // edi
  int v22; // eax
  int v23; // edx
  unsigned int v24; // edi
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // eax
  __int64 v28; // r8
  unsigned int v29; // ebx
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // [rsp+20h] [rbp-1A8h]
  int v33; // [rsp+20h] [rbp-1A8h]
  char v34; // [rsp+40h] [rbp-188h] BYREF
  char v35; // [rsp+41h] [rbp-187h] BYREF
  char v36; // [rsp+42h] [rbp-186h] BYREF
  int v37[2]; // [rsp+48h] [rbp-180h] BYREF
  __int64 v38; // [rsp+50h] [rbp-178h] BYREF
  __int64 v39; // [rsp+58h] [rbp-170h] BYREF
  char v40[8]; // [rsp+60h] [rbp-168h] BYREF
  int v41[2]; // [rsp+68h] [rbp-160h] BYREF
  int v42; // [rsp+70h] [rbp-158h] BYREF
  __int64 v43; // [rsp+78h] [rbp-150h] BYREF
  __int64 v44; // [rsp+80h] [rbp-148h] BYREF
  __int64 v45; // [rsp+88h] [rbp-140h] BYREF
  char v46[32]; // [rsp+90h] [rbp-138h] BYREF
  _BYTE v47[32]; // [rsp+B0h] [rbp-118h] BYREF
  _BYTE v48[32]; // [rsp+D0h] [rbp-F8h] BYREF
  int v49; // [rsp+F0h] [rbp-D8h] BYREF
  char v50[72]; // [rsp+F8h] [rbp-D0h] BYREF
  _BYTE v51[80]; // [rsp+140h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  *(_QWORD *)this = 0;
  *a2 = 0;
  *(_QWORD *)v37 = 0;
  v5 = Windows::Internal::AssignedAccess::RegistryKey::TryOpen<unsigned short const *>(
         -2147483646,
         L"SOFTWARE\\Microsoft\\Windows Embedded\\Lockdown",
         131097,
         0);
  v6 = v5;
  if ( v5 == -2147024894 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
    return 0;
  }
  else if ( v5 >= 0 )
  {
    Windows::Internal::AssignedAccess::RegistryKey::BeginSubKeys(v37, &v49);
    v8 = (_DWORD *)Windows::Internal::AssignedAccess::RegistryKey::EndSubKeys(v37, v51);
    v9 = v49 == *v8;
    Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(v51);
    if ( v9 )
    {
      Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(&v49);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
      return 0;
    }
    else
    {
      std::wstring::wstring(v47, v50);
      v10 = std::wstring::wstring(v46, v47);
      Windows::Internal::AssignedAccess::RegistryKey::Open<std::wstring>(v37, v40, v10);
      Windows::Internal::AssignedAccess::RegistryKey::GetString<unsigned short const *>(v40, v48, L"AppUserModelId");
      v11 = Windows::Internal::AssignedAccess::RegistryKey::GetDWORD<unsigned short const *>(v40, L"ConfigLevel");
      if ( v11 )
      {
        if ( v11 == 1 )
          v14 = 3;
        else
          v14 = 0;
      }
      else
      {
        v14 = 1;
      }
      v42 = v14;
      v34 = 0;
      v41[0] = 1;
      v39 = 0;
      v15 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessApplication,Windows::Internal::AssignedAccess::IAssignedAccessApplication,std::wstring &,unsigned short const (&)[2],unsigned short const (&)[1],enum Windows::Internal::AssignedAccess::AppType,bool>(
              (unsigned int)&v39,
              (unsigned int)v48,
              v12,
              v13,
              (__int64)v41,
              (__int64)&v34);
      v16 = v15;
      if ( v15 >= 0 )
      {
        v17 = 0;
        v43 = 0;
        v18 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
        v38 = (__int64)v18;
        v19 = 0;
        if ( v18 )
        {
          v19 = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessApplication *,1,1,0>>::Vector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessApplication *,1,1,0>>(v18);
          v38 = 0;
        }
        Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>::~MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>(&v38);
        if ( v19 )
        {
          v21 = 0;
          v17 = v19;
          v43 = v19;
        }
        else
        {
          v21 = -2147024882;
        }
        if ( v21 >= 0 )
        {
          LOBYTE(v20) = 1;
          v22 = Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessApplication *,1,1,0>>::InsertAtInternal(
                  v17,
                  0,
                  v39,
                  v20);
          v24 = v22;
          if ( v22 >= 0 )
          {
            v34 = 0;
            v35 = 0;
            v38 = v17;
            v36 = 1;
            v44 = 0;
            v25 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessProfile,Windows::Internal::AssignedAccess::IAssignedAccessProfile,_GUID const &,bool,Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>> *,unsigned short const (&)[1],bool,bool>(
                    (unsigned int)&v44,
                    v23,
                    (unsigned int)&v36,
                    (unsigned int)&v38,
                    v32,
                    (__int64)&v35,
                    (__int64)&v34);
            v26 = v25;
            if ( v25 >= 0 )
            {
              v41[0] = 0;
              v38 = 0;
              v27 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessAccount,Windows::Internal::AssignedAccess::IAssignedAccessAccount,enum Windows::Internal::AssignedAccess::AccountType,std::wstring &>(
                      &v38,
                      v41,
                      v47);
              v29 = v27;
              if ( v27 >= 0 )
              {
                v45 = v38;
                *(_QWORD *)v41 = 0;
                v30 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessConfig,Windows::Internal::AssignedAccess::IAssignedAccessConfig,Windows::Internal::AssignedAccess::IAssignedAccessAccount *,_GUID const &,enum Windows::Internal::AssignedAccess::ConfigSource &>(
                        v41,
                        &v45,
                        v28,
                        &v42);
                v31 = v30;
                if ( v30 >= 0 )
                {
                  wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(
                    &v44,
                    this);
                  wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(
                    v41,
                    a2);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v41);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v38);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v44);
                  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(&v43);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
                  std::wstring::_Tidy_deallocate(v48);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v40);
                  std::wstring::_Tidy_deallocate(v47);
                  Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(&v49);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
                  return 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x11A,
                    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                    (const char *)(unsigned int)v30,
                    v33);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v41);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v38);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v44);
                  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(&v43);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
                  std::wstring::_Tidy_deallocate(v48);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v40);
                  std::wstring::_Tidy_deallocate(v47);
                  Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(&v49);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
                  return v31;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x118,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                  (const char *)(unsigned int)v27,
                  v33);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v38);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v44);
                wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(&v43);
                wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
                std::wstring::_Tidy_deallocate(v48);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v40);
                std::wstring::_Tidy_deallocate(v47);
                Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(&v49);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
                return v29;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x115,
                (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
                (const char *)(unsigned int)v25,
                v33);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v44);
              wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(&v43);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
              std::wstring::_Tidy_deallocate(v48);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v40);
              std::wstring::_Tidy_deallocate(v47);
              Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(&v49);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
              return v26;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x10A,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
              (const char *)(unsigned int)v22,
              v32);
            wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(&v43);
            wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
            std::wstring::_Tidy_deallocate(v48);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v40);
            std::wstring::_Tidy_deallocate(v47);
            Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(&v49);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
            return v24;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x109,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
            (const char *)(unsigned int)v21,
            v32);
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(&v43);
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
          std::wstring::_Tidy_deallocate(v48);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v40);
          std::wstring::_Tidy_deallocate(v47);
          Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(&v49);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
          return (unsigned int)v21;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
          (const char *)(unsigned int)v15,
          v32);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
        std::wstring::_Tidy_deallocate(v48);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v40);
        std::wstring::_Tidy_deallocate(v47);
        Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(&v49);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
        return v16;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v5,
      (int)v37);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v37);
    return v6;
  }
}

```

## disassembly

```asm
0x18005fad0  mov     [rsp+arg_10], rbx
0x18005fad5  push    rsi
0x18005fad6  push    rdi
0x18005fad7  push    r12
0x18005fad9  push    r14
0x18005fadb  push    r15
0x18005fadd  sub     rsp, 1A0h
0x18005fae4  mov     rax, cs:__security_cookie
0x18005faeb  xor     rax, rsp
0x18005faee  mov     [rsp+1C8h+var_38], rax
0x18005faf6  mov     r14, rdx
0x18005faf9  mov     r15, rcx
0x18005fafc  xor     r12d, r12d
0x18005faff  mov     [rcx], r12
0x18005fb02  mov     [rdx], r12
0x18005fb05  mov     qword ptr [rsp+1C8h+var_180], r12
0x18005fb0a  lea     rax, [rsp+1C8h+var_180]
0x18005fb0f  mov     qword ptr [rsp+1C8h+var_1A8], rax; int
0x18005fb14  xor     r9d, r9d
0x18005fb17  mov     r8d, 20019h
0x18005fb1d  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Embedded\\"...
0x18005fb24  mov     rcx, 0FFFFFFFF80000002h
0x18005fb2b  call    ??$TryOpen@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@SAJPEAUHKEY__@@PEBGKKAEAV0123@@Z; Windows::Internal::AssignedAccess::RegistryKey::TryOpen<ushort const *>(HKEY__ *,ushort const *,ulong,ulong,Windows::Internal::AssignedAccess::RegistryKey &)
0x18005fb30  mov     ebx, eax
0x18005fb32  cmp     eax, 80070002h
0x18005fb37  jnz     short loc_18005FB4A
0x18005fb39  lea     rcx, [rsp+1C8h+var_180]
0x18005fb3e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fb43  xor     eax, eax
0x18005fb45  jmp     loc_180060179
0x18005fb4a  test    ebx, ebx
0x18005fb4c  jns     short loc_18005FB7C
0x18005fb4e  mov     rcx, [rsp+1C8h]; this
0x18005fb56  mov     r9d, ebx; char *
0x18005fb59  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005fb60  mov     edx, 0F9h; void *
0x18005fb65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fb6a  nop
0x18005fb6b  lea     rcx, [rsp+1C8h+var_180]
0x18005fb70  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fb75  mov     eax, ebx
0x18005fb77  jmp     loc_180060179
0x18005fb7c  lea     rdx, [rsp+1C8h+var_D8]
0x18005fb84  lea     rcx, [rsp+1C8h+var_180]
0x18005fb89  call    ?BeginSubKeys@RegistryKey@AssignedAccess@Internal@Windows@@QEBA?AV?$Iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyDereferenceTrait@RegistryKey@AssignedAccess@Internal@Windows@@@1234@XZ; Windows::Internal::AssignedAccess::RegistryKey::BeginSubKeys(void)
0x18005fb8e  nop
0x18005fb8f  lea     rdx, [rsp+1C8h+var_88]
0x18005fb97  lea     rcx, [rsp+1C8h+var_180]
0x18005fb9c  call    ?EndSubKeys@RegistryKey@AssignedAccess@Internal@Windows@@QEBA?AV?$Iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyDereferenceTrait@RegistryKey@AssignedAccess@Internal@Windows@@@1234@XZ; Windows::Internal::AssignedAccess::RegistryKey::EndSubKeys(void)
0x18005fba1  mov     eax, [rax]
0x18005fba3  cmp     [rsp+1C8h+var_D8], eax
0x18005fbaa  setz    bl
0x18005fbad  lea     rcx, [rsp+1C8h+var_88]
0x18005fbb5  call    ??1?$Iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyDereferenceTrait@RegistryKey@AssignedAccess@Internal@Windows@@@RegistryKey@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(void)
0x18005fbba  test    bl, bl
0x18005fbbc  jz      short loc_18005FBDD
0x18005fbbe  lea     rcx, [rsp+1C8h+var_D8]
0x18005fbc6  call    ??1?$Iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyDereferenceTrait@RegistryKey@AssignedAccess@Internal@Windows@@@RegistryKey@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(void)
0x18005fbcb  nop
0x18005fbcc  lea     rcx, [rsp+1C8h+var_180]
0x18005fbd1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fbd6  xor     eax, eax
0x18005fbd8  jmp     loc_180060179
0x18005fbdd  lea     rdx, [rsp+1C8h+var_D0]
0x18005fbe5  lea     rcx, [rsp+1C8h+var_118]
0x18005fbed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005fbf2  nop
0x18005fbf3  lea     rdx, [rsp+1C8h+var_118]
0x18005fbfb  lea     rcx, [rsp+1C8h+var_138]
0x18005fc03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005fc08  mov     r8, rax
0x18005fc0b  lea     rdx, [rsp+1C8h+var_168]
0x18005fc10  lea     rcx, [rsp+1C8h+var_180]
0x18005fc15  call    ??$Open@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@RegistryKey@AssignedAccess@Internal@Windows@@QEAA?AV0123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK@Z; Windows::Internal::AssignedAccess::RegistryKey::Open<std::wstring>(std::wstring,ulong,ulong)
0x18005fc1a  nop
0x18005fc1b  lea     r8, aAppusermodelid; "AppUserModelId"
0x18005fc22  lea     rdx, [rsp+1C8h+var_F8]
0x18005fc2a  lea     rcx, [rsp+1C8h+var_168]
0x18005fc2f  call    ??$GetString@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_N@Z; Windows::Internal::AssignedAccess::RegistryKey::GetString<ushort const *>(ushort const *,bool)
0x18005fc34  nop
0x18005fc35  lea     rdx, aConfiglevel; "ConfigLevel"
0x18005fc3c  lea     rcx, [rsp+1C8h+var_168]
0x18005fc41  call    ??$GetDWORD@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEBA?BKPEBG_N@Z; Windows::Internal::AssignedAccess::RegistryKey::GetDWORD<ushort const *>(ushort const *,bool)
0x18005fc46  test    eax, eax
0x18005fc48  jz      short loc_18005FC5B
0x18005fc4a  cmp     eax, 1
0x18005fc4d  jz      short loc_18005FC54
0x18005fc4f  mov     ecx, r12d
0x18005fc52  jmp     short loc_18005FC60
0x18005fc54  mov     ecx, 3
0x18005fc59  jmp     short loc_18005FC60
0x18005fc5b  mov     ecx, 1
0x18005fc60  mov     [rsp+1C8h+var_158], ecx
0x18005fc64  mov     [rsp+1C8h+var_188], r12b
0x18005fc69  mov     [rsp+1C8h+var_160], 1
0x18005fc71  mov     [rsp+1C8h+var_170], r12
0x18005fc76  lea     rax, [rsp+1C8h+var_188]
0x18005fc7b  mov     [rsp+1C8h+var_1A0], rax
0x18005fc80  lea     rax, [rsp+1C8h+var_160]
0x18005fc85  mov     qword ptr [rsp+1C8h+var_1A8], rax; int
0x18005fc8a  lea     rdx, [rsp+1C8h+var_F8]
0x18005fc92  lea     rcx, [rsp+1C8h+var_170]
0x18005fc97  call    ??$MakeAndInitialize@VAssignedAccessApplication@AssignedAccess@Internal@Windows@@UIAssignedAccessApplication@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY01$$CBGAEAY00$$CBGW4AppType@234@_N@Details@WRL@Microsoft@@YAJPEAPEAUIAssignedAccessApplication@AssignedAccess@Internal@Windows@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY01$$CBGAEAY00$$CBG$$QEAW4AppType@456@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessApplication,Windows::Internal::AssignedAccess::IAssignedAccessApplication,std::wstring &,ushort const (&)[2],ushort const (&)[1],Windows::Internal::AssignedAccess::AppType,bool>(Windows::Internal::AssignedAccess::IAssignedAccessApplication * *,std::wstring &,ushort const (&)[2],ushort const (&)[1],Windows::Internal::AssignedAccess::AppType &&,bool &&)
0x18005fc9c  mov     ebx, eax
0x18005fc9e  test    eax, eax
0x18005fca0  jns     short loc_18005FD10
0x18005fca2  mov     rcx, [rsp+1C8h]; this
0x18005fcaa  mov     r9d, eax; char *
0x18005fcad  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005fcb4  mov     edx, 107h; void *
0x18005fcb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fcbe  nop
0x18005fcbf  lea     rcx, [rsp+1C8h+var_170]
0x18005fcc4  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005fcc9  nop
0x18005fcca  lea     rcx, [rsp+1C8h+var_F8]
0x18005fcd2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fcd7  nop
0x18005fcd8  lea     rcx, [rsp+1C8h+var_168]
0x18005fcdd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fce2  nop
0x18005fce3  lea     rcx, [rsp+1C8h+var_118]
0x18005fceb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fcf0  nop
0x18005fcf1  lea     rcx, [rsp+1C8h+var_D8]
0x18005fcf9  call    ??1?$Iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyDereferenceTrait@RegistryKey@AssignedAccess@Internal@Windows@@@RegistryKey@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(void)
0x18005fcfe  nop
0x18005fcff  lea     rcx, [rsp+1C8h+var_180]
0x18005fd04  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fd09  mov     eax, ebx
0x18005fd0b  jmp     loc_180060179
0x18005fd10  mov     rbx, r12
0x18005fd13  mov     [rsp+1C8h+var_150], rbx
0x18005fd18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005fd1f  mov     ecx, 0B8h; unsigned __int64
0x18005fd24  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005fd29  mov     [rsp+1C8h+var_178], rax
0x18005fd2e  mov     rsi, r12
0x18005fd31  test    rax, rax
0x18005fd34  jz      short loc_18005FD46
0x18005fd36  mov     rcx, rax
0x18005fd39  call    ??0?$Vector@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3674@U?$VectorOptions@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@$00$00$0A@@3674@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessApplication *,1,1,0>>::Vector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessApplication *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *> const &,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessApplication *,1,1,0>>::permission)
0x18005fd3e  mov     rsi, rax
0x18005fd41  mov     [rsp+1C8h+var_178], r12
0x18005fd46  lea     rcx, [rsp+1C8h+var_178]
0x18005fd4b  call    ??1?$MakeAllocator@U?$GitInvokeHelper@U?$VectorChangedEventHandler@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@VGitPtr@Internal@4@$01@Details@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>::~MakeAllocator<Windows::Internal::Details::GitInvokeHelper<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Internal::GitPtr,2>>(void)
0x18005fd50  test    rsi, rsi
0x18005fd53  jnz     short loc_18005FD5C
0x18005fd55  mov     edi, 8007000Eh
0x18005fd5a  jmp     short loc_18005FD67
0x18005fd5c  mov     edi, r12d
0x18005fd5f  mov     rbx, rsi
0x18005fd62  mov     [rsp+1C8h+var_150], rbx
0x18005fd67  test    edi, edi
0x18005fd69  jns     short loc_18005FDE4
0x18005fd6b  mov     rcx, [rsp+1C8h]; this
0x18005fd73  mov     r9d, edi; char *
0x18005fd76  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005fd7d  mov     edx, 109h; void *
0x18005fd82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fd87  nop
0x18005fd88  lea     rcx, [rsp+1C8h+var_150]
0x18005fd8d  call    ??1?$com_ptr_t@V?$AgileObservableVector@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3674@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(void)
0x18005fd92  nop
0x18005fd93  lea     rcx, [rsp+1C8h+var_170]
0x18005fd98  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005fd9d  nop
0x18005fd9e  lea     rcx, [rsp+1C8h+var_F8]
0x18005fda6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fdab  nop
0x18005fdac  lea     rcx, [rsp+1C8h+var_168]
0x18005fdb1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fdb6  nop
0x18005fdb7  lea     rcx, [rsp+1C8h+var_118]
0x18005fdbf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fdc4  nop
0x18005fdc5  lea     rcx, [rsp+1C8h+var_D8]
0x18005fdcd  call    ??1?$Iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyDereferenceTrait@RegistryKey@AssignedAccess@Internal@Windows@@@RegistryKey@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(void)
0x18005fdd2  nop
0x18005fdd3  lea     rcx, [rsp+1C8h+var_180]
0x18005fdd8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fddd  mov     eax, edi
0x18005fddf  jmp     loc_180060179
0x18005fde4  mov     r9b, 1
0x18005fde7  mov     r8, [rsp+1C8h+var_170]
0x18005fdec  xor     edx, edx
0x18005fdee  mov     rcx, rbx
0x18005fdf1  call    ?InsertAtInternal@?$Vector@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3674@U?$VectorOptions@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@$00$00$0A@@3674@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIAssignedAccessApplication@AssignedAccess@25@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Internal::AssignedAccess::AssignedAccessApplication *,1,1,0>>::InsertAtInternal(uint,Windows::Internal::AssignedAccess::IAssignedAccessApplication *,bool)
0x18005fdf6  mov     edi, eax
0x18005fdf8  test    eax, eax
0x18005fdfa  jns     short loc_18005FE75
0x18005fdfc  mov     rcx, [rsp+1C8h]; this
0x18005fe04  mov     r9d, eax; char *
0x18005fe07  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005fe0e  mov     edx, 10Ah; void *
0x18005fe13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fe18  nop
0x18005fe19  lea     rcx, [rsp+1C8h+var_150]
0x18005fe1e  call    ??1?$com_ptr_t@V?$AgileObservableVector@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3674@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(void)
0x18005fe23  nop
0x18005fe24  lea     rcx, [rsp+1C8h+var_170]
0x18005fe29  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005fe2e  nop
0x18005fe2f  lea     rcx, [rsp+1C8h+var_F8]
0x18005fe37  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fe3c  nop
0x18005fe3d  lea     rcx, [rsp+1C8h+var_168]
0x18005fe42  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fe47  nop
0x18005fe48  lea     rcx, [rsp+1C8h+var_118]
0x18005fe50  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fe55  nop
0x18005fe56  lea     rcx, [rsp+1C8h+var_D8]
0x18005fe5e  call    ??1?$Iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyDereferenceTrait@RegistryKey@AssignedAccess@Internal@Windows@@@RegistryKey@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(void)
0x18005fe63  nop
0x18005fe64  lea     rcx, [rsp+1C8h+var_180]
0x18005fe69  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fe6e  mov     eax, edi
0x18005fe70  jmp     loc_180060179
0x18005fe75  mov     [rsp+1C8h+var_188], r12b
0x18005fe7a  mov     [rsp+1C8h+var_187], r12b
0x18005fe7f  mov     [rsp+1C8h+var_178], rbx
0x18005fe84  mov     [rsp+1C8h+var_186], 1
0x18005fe89  mov     [rsp+1C8h+var_148], r12
0x18005fe91  lea     rax, [rsp+1C8h+var_188]
0x18005fe96  mov     [rsp+1C8h+var_198], rax
0x18005fe9b  lea     rax, [rsp+1C8h+var_187]
0x18005fea0  mov     [rsp+1C8h+var_1A0], rax
0x18005fea5  lea     r9, [rsp+1C8h+var_178]
0x18005feaa  lea     r8, [rsp+1C8h+var_186]
0x18005feaf  lea     rcx, [rsp+1C8h+var_148]
0x18005feb7  call    ??$MakeAndInitialize@VAssignedAccessProfile@AssignedAccess@Internal@Windows@@UIAssignedAccessProfile@234@AEBU_GUID@@_NPEAV?$AgileObservableVector@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3674@@3Collections@Foundation@4@AEAY00$$CBG_N_N@Details@WRL@Microsoft@@YAJPEAPEAUIAssignedAccessProfile@AssignedAccess@Internal@Windows@@AEBU_GUID@@$$QEA_N$$QEAPEAV?$AgileObservableVector@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3674@@5Collections@Foundation@6@AEAY00$$CBG22@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessProfile,Windows::Internal::AssignedAccess::IAssignedAccessProfile,_GUID const &,bool,Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>> *,ushort const (&)[1],bool,bool>(Windows::Internal::AssignedAccess::IAssignedAccessProfile * *,_GUID const &,bool &&,Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>> * &&,ushort const (&)[1],bool &&,bool &&)
0x18005febc  mov     ebx, eax
0x18005febe  test    eax, eax
0x18005fec0  jns     loc_18005FF4D
0x18005fec6  mov     rcx, [rsp+1C8h]; this
0x18005fece  mov     r9d, eax; char *
0x18005fed1  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005fed8  mov     edx, 115h; void *
0x18005fedd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fee2  nop
0x18005fee3  lea     rcx, [rsp+1C8h+var_148]
0x18005feeb  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005fef0  nop
0x18005fef1  lea     rcx, [rsp+1C8h+var_150]
0x18005fef6  call    ??1?$com_ptr_t@V?$AgileObservableVector@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3674@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(void)
0x18005fefb  nop
0x18005fefc  lea     rcx, [rsp+1C8h+var_170]
0x18005ff01  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005ff06  nop
0x18005ff07  lea     rcx, [rsp+1C8h+var_F8]
0x18005ff0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ff14  nop
0x18005ff15  lea     rcx, [rsp+1C8h+var_168]
0x18005ff1a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005ff1f  nop
0x18005ff20  lea     rcx, [rsp+1C8h+var_118]
0x18005ff28  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ff2d  nop
0x18005ff2e  lea     rcx, [rsp+1C8h+var_D8]
0x18005ff36  call    ??1?$Iterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyDereferenceTrait@RegistryKey@AssignedAccess@Internal@Windows@@@RegistryKey@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKey::Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>::~Iterator<std::wstring,Windows::Internal::AssignedAccess::RegistryKey::KeyDereferenceTrait>(void)
0x18005ff3b  nop
0x18005ff3c  lea     rcx, [rsp+1C8h+var_180]
0x18005ff41  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005ff46  mov     eax, ebx
0x18005ff48  jmp     loc_180060179
0x18005ff4d  mov     [rsp+1C8h+var_160], r12d
0x18005ff52  mov     [rsp+1C8h+var_178], r12
0x18005ff57  lea     r8, [rsp+1C8h+var_118]
0x18005ff5f  lea     rdx, [rsp+1C8h+var_160]
0x18005ff64  lea     rcx, [rsp+1C8h+var_178]
0x18005ff69  call    ??$MakeAndInitialize@VAssignedAccessAccount@AssignedAccess@Internal@Windows@@UIAssignedAccessAccount@234@W4AccountType@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUIAssignedAccessAccount@AssignedAccess@Internal@Windows@@$$QEAW4AccountType@456@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AssignedAccessAccount,Windows::Internal::AssignedAccess::IAssignedAccessAccount,Windows::Internal::AssignedAccess::AccountType,std::wstring &>(Windows::Internal::AssignedAccess::IAssignedAccessAccount * *,Windows::Internal::AssignedAccess::AccountType &&,std::wstring &)
0x18005ff6e  mov     ebx, eax
0x18005ff70  test    eax, eax
0x18005ff72  jns     loc_18006000A
0x18005ff78  mov     rcx, [rsp+1C8h]; this
0x18005ff80  mov     r9d, eax; char *
0x18005ff83  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005ff8a  mov     edx, 118h; void *
0x18005ff8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ff94  nop
0x18005ff95  lea     rcx, [rsp+1C8h+var_178]
0x18005ff9a  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005ff9f  nop
0x18005ffa0  lea     rcx, [rsp+1C8h+var_148]
0x18005ffa8  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005ffad  nop
0x18005ffae  lea     rcx, [rsp+1C8h+var_150]
0x18005ffb3  call    ??1?$com_ptr_t@V?$AgileObservableVector@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessOperationStatus@AssignedAccess@Internal@Windows@@@3674@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessOperationStatus *>>,wil::err_exception_policy>(void)
0x18005ffb8  nop
0x18005ffb9  lea     rcx, [rsp+1C8h+var_170]
0x18005ffbe  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18005ffc3  nop
0x18005ffc4  lea     rcx, [rsp+1C8h+var_F8]
0x18005ffcc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ffd1  nop
0x18005ffd2  lea     rcx, [rsp+1C8h+var_168]
0x18005ffd7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005ffdc  nop
0x18005ffdd  lea     rcx, [rsp+1C8h+var_118]
  ... truncated ...
```
