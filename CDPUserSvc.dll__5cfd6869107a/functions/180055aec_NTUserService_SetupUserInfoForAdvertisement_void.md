# NTUserService::SetupUserInfoForAdvertisement(void)

- ea: `0x180055aec`
- end: `0x1800563b0`
- name: `?SetupUserInfoForAdvertisement@NTUserService@@IEAAJXZ`
- size: `2244`
- prototype: `__int64 __fastcall(NTUserService *__hidden this)`
- caller_count: `2`
- callee_count: `31`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180058df0`
- `0x180059280`

## callees

- `0x180002a4c`
- `0x180002e4c`
- `0x180004a58`
- `0x180013a18`
- `0x180013cac`
- `0x180013d24`
- `0x180013d9c`
- `0x180013ee4`
- `0x180015700`
- `0x180016664`
- `0x180016684`
- `0x180016788`
- `0x180017318`
- `0x1800185d8`
- `0x18001a0e4`
- `0x18001c2b0`
- `0x18001c314`
- `0x18001f3e8`
- `0x18001f874`
- `0x18002c570`
- `0x18002d204`
- `0x180042604`
- `0x180042ce0`
- `0x180043988`
- `0x180043d60`
- `0x180055aec`
- `0x180056458`
- `0x180056b5c`
- `0x18005c46c`
- `0x18005c800`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b6e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055b43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055b43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055b58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055b58`

## string_xrefs

- `0x180056219`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800562b7`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180056360`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800561d3`: `..\ntuserservice.cpp`
- `0x180056271`: `..\ntuserservice.cpp`
- `0x18005631d`: `..\ntuserservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=56
__int64 __fastcall NTUserService::SetupUserInfoForAdvertisement(NTUserService *this)
{
  bool active; // al
  HRESULT v2; // ebx
  _QWORD *v3; // rbx
  signed int LastError; // eax
  unsigned int v5; // ebx
  const struct winrt::impl::slim_source_location *v6; // rdx
  __int64 PropertyAsync; // rax
  __int64 (__fastcall ***v8)(_QWORD, __int64 *, _QWORD *); // rcx
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 (__fastcall ***v12)(_QWORD, __int64 *, __int128 *); // rcx
  unsigned int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 (__fastcall ***v16)(_QWORD, __int64 *, __int128 *); // rcx
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 (__fastcall ***v20)(_QWORD, __int64 *, __int128 *); // rcx
  unsigned int v21; // eax
  __int64 v22; // rax
  int v23; // ebx
  LPVOID v24; // rcx
  __int64 result; // rax
  cdp *v26; // rcx
  int v27; // ecx
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  cdp *v32; // rcx
  int v33; // ecx
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rax
  cdp *v38; // rcx
  int v39; // ecx
  __int64 v40; // r9
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rax
  _QWORD *v44; // rax
  int v45; // edx
  int v46; // r8d
  _QWORD v47[2]; // [rsp+30h] [rbp-1B8h] BYREF
  __int128 v48; // [rsp+40h] [rbp-1A8h] BYREF
  __int128 v49; // [rsp+50h] [rbp-198h] BYREF
  char v50[8]; // [rsp+60h] [rbp-188h] BYREF
  unsigned __int64 PlatformCurrentThreadId; // [rsp+68h] [rbp-180h] BYREF
  char v52[8]; // [rsp+70h] [rbp-178h] BYREF
  char v53[8]; // [rsp+78h] [rbp-170h] BYREF
  __int64 v54; // [rsp+80h] [rbp-168h] BYREF
  __int128 v55; // [rsp+88h] [rbp-160h]
  LPVOID ppv; // [rsp+A0h] [rbp-148h] BYREF
  unsigned __int64 v57; // [rsp+A8h] [rbp-140h] BYREF
  char v58[16]; // [rsp+B0h] [rbp-138h] BYREF
  _QWORD *v59; // [rsp+C0h] [rbp-128h] BYREF
  char v60[8]; // [rsp+C8h] [rbp-120h] BYREF
  __int64 v61; // [rsp+D0h] [rbp-118h] BYREF
  char v62[8]; // [rsp+D8h] [rbp-110h] BYREF
  __int64 v63; // [rsp+E0h] [rbp-108h] BYREF
  char v64[8]; // [rsp+E8h] [rbp-100h] BYREF
  __int64 v65; // [rsp+F0h] [rbp-F8h] BYREF
  char v66[8]; // [rsp+F8h] [rbp-F0h] BYREF
  __int64 v67; // [rsp+100h] [rbp-E8h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+108h] [rbp-E0h] BYREF
  _BYTE v69[56]; // [rsp+140h] [rbp-A8h] BYREF
  _BYTE v70[56]; // [rsp+178h] [rbp-70h] BYREF
  _QWORD v71[4]; // [rsp+1B0h] [rbp-38h] BYREF

  active = IsActiveSessionCountLimited();
  try
  {
    if ( active )
    {
      ppv = 0;
      v2 = CoCreateInstance(
             &GUID_edbb66ee_73ae_4ef7_b40d_16656c814e10,
             0,
             4u,
             &GUID_e96c4986_7a6b_4ed1_b55f_5945b735ebd0,
             &ppv);
      if ( v2 < 0 )
      {
        cdp::CDPSourceLocationInfo::CDPSourceLocationInfo(
          (cdp::CDPSourceLocationInfo *)&v59,
          "..\\ntuserservice.cpp",
          404);
        LODWORD(v47[0]) = v2;
        PlatformCurrentThreadId = cdp::GetPlatformCurrentThreadId(v26);
        Log<long &,char const * &,int &,unsigned __int64>(
          v27,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)v47,
          (unsigned int)&v59,
          (__int64)v60,
          (__int64)&PlatformCurrentThreadId);
        v28 = cdp::ExceptionStackFromSourceLocationInfo(&v54, &v59);
        v31 = cdp::ErrorCodeToString((unsigned int)v2, v29, v30, v28);
        ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v2, v31);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
      v3 = CoTaskMemAlloc(0x20u);
      v59 = v3;
      if ( v3 )
      {
        winrt::Windows::System::User::GetDefault();
        LODWORD(v54) = 0;
        v55 = 0;
        *(_QWORD *)&v49 = 0;
        if ( (unsigned __int8)winrt::Windows::Foundation::operator==(v50, &v49) )
          winrt::throw_last_error((winrt *)&v54, v6);
        v54 = *(_QWORD *)winrt::Windows::System::KnownUserProperties::AccountName();
        PropertyAsync = winrt::impl::consume_Windows_System_IUser<winrt::Windows::System::IUser>::GetPropertyAsync(
                          v50,
                          v52,
                          &v54);
        v8 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD *))winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::IInspectable>::get(
                                                                        PropertyAsync,
                                                                        &v49);
        if ( v8 )
        {
          v47[0] = 0;
          LODWORD(v54) = 0;
          v55 = 0;
          v9 = (**v8)(v8, winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>, v47);
          winrt::check_hresult(&v48, v9, &v54);
          *(_QWORD *)&v48 = v47[0];
        }
        else
        {
          *(_QWORD *)&v48 = 0;
        }
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(
          &v48,
          &PlatformCurrentThreadId);
        winrt::Windows::System::IUser::~IUser((winrt::Windows::System::IUser *)&v48);
        if ( (_QWORD)v49 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v49);
        winrt::Windows::System::IUser::~IUser((winrt::Windows::System::IUser *)v52);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v57);
        v48 = *(_OWORD *)winrt::hstring::operator std::basic_string_view<unsigned short>(&PlatformCurrentThreadId, &v54);
        v10 = winrt::to_string(v71, &v48);
        std::_String_val<std::_Simple_types<char>>::_Myptr(v10);
        wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(&v67);
        std::string::_Tidy_deallocate(v71);
        v71[0] = *(_QWORD *)winrt::Windows::System::KnownUserProperties::FirstName();
        v11 = winrt::impl::consume_Windows_System_IUser<winrt::Windows::System::IUser>::GetPropertyAsync(v50, &v57, v71);
        v12 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int128 *))winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::IInspectable>::get(
                                                                           v11,
                                                                           v47);
        if ( v12 )
        {
          *(_QWORD *)&v49 = 0;
          LODWORD(v54) = 0;
          v55 = 0;
          v13 = (**v12)(v12, winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>, &v49);
          winrt::check_hresult(&v48, v13, &v54);
          *(_QWORD *)&v48 = v49;
        }
        else
        {
          *(_QWORD *)&v48 = 0;
        }
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(
          &v48,
          v66);
        winrt::Windows::System::IUser::~IUser((winrt::Windows::System::IUser *)&v48);
        if ( v47[0] )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v47);
        winrt::Windows::System::IUser::~IUser((winrt::Windows::System::IUser *)&v57);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v52);
        v49 = *(_OWORD *)winrt::hstring::operator std::basic_string_view<unsigned short>(v66, &v54);
        v14 = winrt::to_string(v71, &v49);
        std::_String_val<std::_Simple_types<char>>::_Myptr(v14);
        wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(&v65);
        std::string::_Tidy_deallocate(v71);
        v71[0] = *(_QWORD *)winrt::Windows::System::KnownUserProperties::LastName();
        v15 = winrt::impl::consume_Windows_System_IUser<winrt::Windows::System::IUser>::GetPropertyAsync(v50, &v57, v71);
        v16 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int128 *))winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::IInspectable>::get(
                                                                           v15,
                                                                           v47);
        if ( v16 )
        {
          *(_QWORD *)&v49 = 0;
          LODWORD(v54) = 0;
          v55 = 0;
          v17 = (**v16)(v16, winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>, &v49);
          winrt::check_hresult(&v48, v17, &v54);
          *(_QWORD *)&v48 = v49;
        }
        else
        {
          *(_QWORD *)&v48 = 0;
        }
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(
          &v48,
          v64);
        winrt::Windows::System::IUser::~IUser((winrt::Windows::System::IUser *)&v48);
        if ( v47[0] )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v47);
        winrt::Windows::System::IUser::~IUser((winrt::Windows::System::IUser *)&v57);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v52);
        v49 = *(_OWORD *)winrt::hstring::operator std::basic_string_view<unsigned short>(v64, &v54);
        v18 = winrt::to_string(v71, &v49);
        std::_String_val<std::_Simple_types<char>>::_Myptr(v18);
        wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(&v63);
        std::string::_Tidy_deallocate(v71);
        v71[0] = *(_QWORD *)winrt::Windows::System::KnownUserProperties::DisplayName();
        v19 = winrt::impl::consume_Windows_System_IUser<winrt::Windows::System::IUser>::GetPropertyAsync(v50, &v57, v71);
        v20 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int128 *))winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::IInspectable>::get(
                                                                           v19,
                                                                           v47);
        if ( v20 )
        {
          *(_QWORD *)&v49 = 0;
          LODWORD(v54) = 0;
          v55 = 0;
          v21 = (**v20)(v20, winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>, &v49);
          winrt::check_hresult(&v48, v21, &v54);
          *(_QWORD *)&v48 = v49;
        }
        else
        {
          *(_QWORD *)&v48 = 0;
        }
        winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(
          &v48,
          v62);
        winrt::Windows::System::IUser::~IUser((winrt::Windows::System::IUser *)&v48);
        if ( v47[0] )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v47);
        winrt::Windows::System::IUser::~IUser((winrt::Windows::System::IUser *)&v57);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v52);
        v49 = *(_OWORD *)winrt::hstring::operator std::basic_string_view<unsigned short>(v62, &v54);
        v22 = winrt::to_string(v71, &v49);
        std::_String_val<std::_Simple_types<char>>::_Myptr(v22);
        wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(&v61);
        std::string::_Tidy_deallocate(v71);
        *v3 = v67;
        v3[1] = v65;
        v3[2] = v63;
        v3[3] = v61;
        v23 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv + 24LL))(ppv, v3);
        if ( v23 < 0 )
        {
          cdp::CDPSourceLocationInfo::CDPSourceLocationInfo(
            (cdp::CDPSourceLocationInfo *)v52,
            "..\\ntuserservice.cpp",
            455);
          LODWORD(v47[0]) = v23;
          v57 = cdp::GetPlatformCurrentThreadId(v38);
          Log<long &,char const * &,int &,unsigned __int64>(
            v39,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
            (unsigned int)v47,
            (unsigned int)v52,
            (__int64)v53,
            (__int64)&v57);
          v40 = cdp::ExceptionStackFromSourceLocationInfo(&v57, v52);
          v43 = cdp::ErrorCodeToString((unsigned int)v23, v41, v42, v40);
          ConnectedDevices::Exception::Exception(v70, (unsigned int)v23, v43);
          throw (ConnectedDevices::Exception *)v70;
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v61);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v62);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v63);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v64);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v65);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v66);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v67);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&PlatformCurrentThreadId);
        winrt::Windows::System::IUser::~IUser((winrt::Windows::System::IUser *)v50);
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( (v5 & 0x80000000) != 0 )
        {
          cdp::CDPSourceLocationInfo::CDPSourceLocationInfo(
            (cdp::CDPSourceLocationInfo *)&v57,
            "..\\ntuserservice.cpp",
            410);
          LODWORD(v47[0]) = v5;
          PlatformCurrentThreadId = cdp::GetPlatformCurrentThreadId(v32);
          Log<long &,char const * &,int &,unsigned __int64>(
            v33,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
            (unsigned int)v47,
            (unsigned int)&v57,
            (__int64)v58,
            (__int64)&PlatformCurrentThreadId);
          v34 = cdp::ExceptionStackFromSourceLocationInfo(&v54, &v57);
          v37 = cdp::ErrorCodeToString(v5, v35, v36, v34);
          ConnectedDevices::Exception::Exception(v69, v5, v37);
          throw (ConnectedDevices::Exception *)v69;
        }
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v59);
      v24 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v47[0]) = -2147418113;
    LODWORD(v44) = GetCurrentThreadId();
    v59 = v44;
    LODWORD(v48) = 462;
    cdp::CatchAllToHR<char const (&)[21],int,unsigned __int64>(
      (unsigned int)v47,
      v45,
      v46,
      (unsigned int)&v48,
      (__int64)&v59);
  }
  return result;
}

```

## disassembly

```asm
0x180055aec  mov     [rsp+arg_0], rbx
0x180055af1  push    rdi
0x180055af2  sub     rsp, 1E0h
0x180055af9  mov     rax, cs:__security_cookie
0x180055b00  xor     rax, rsp
0x180055b03  mov     [rsp+1E8h+var_18], rax
0x180055b0b  xor     edi, edi
0x180055b0d  call    ?IsActiveSessionCountLimited@@YA_NXZ; IsActiveSessionCountLimited(void)
0x180055b12  test    al, al
0x180055b14  jz      loc_1800561A4
0x180055b1a  mov     [rsp+1E8h+var_148], rdi
0x180055b22  lea     rax, [rsp+1E8h+var_148]
0x180055b2a  mov     [rsp+1E8h+ppv], rax; ppv
0x180055b2f  lea     r9, _GUID_e96c4986_7a6b_4ed1_b55f_5945b735ebd0; riid
0x180055b36  xor     edx, edx; pUnkOuter
0x180055b38  lea     r8d, [rdi+4]; dwClsContext
0x180055b3c  lea     rcx, _GUID_edbb66ee_73ae_4ef7_b40d_16656c814e10; rclsid
0x180055b43  call    cs:__imp_CoCreateInstance
0x180055b49  mov     ebx, eax
0x180055b4b  test    eax, eax
0x180055b4d  js      loc_1800561CD
0x180055b53  mov     ecx, 20h ; ' '; cb
0x180055b58  call    cs:__imp_CoTaskMemAlloc
0x180055b5e  mov     rbx, rax
0x180055b61  mov     [rsp+1E8h+var_128], rax
0x180055b69  test    rax, rax
0x180055b6c  jnz     short loc_180055B90
0x180055b6e  call    cs:__imp_GetLastError
0x180055b74  mov     ebx, eax
0x180055b76  test    eax, eax
0x180055b78  jle     short loc_180055B83
0x180055b7a  movzx   ebx, ax
0x180055b7d  or      ebx, 80070000h
0x180055b83  test    ebx, ebx
0x180055b85  js      loc_18005626B
0x180055b8b  jmp     loc_180056174
0x180055b90  lea     rcx, [rsp+1E8h+var_188]
0x180055b95  call    ?GetDefault@User@System@Windows@winrt@@SA@XZ; winrt::Windows::System::User::GetDefault(void)
0x180055b9a  nop
0x180055b9b  mov     dword ptr [rsp+1E8h+var_168], edi
0x180055ba2  xorps   xmm0, xmm0
0x180055ba5  movdqu  [rsp+1E8h+var_160], xmm0
0x180055bae  mov     qword ptr [rsp+1E8h+var_198], rdi
0x180055bb3  lea     rdx, [rsp+1E8h+var_198]
0x180055bb8  lea     rcx, [rsp+1E8h+var_188]
0x180055bbd  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180055bc2  test    al, al
0x180055bc4  jnz     loc_180056309
0x180055bca  lea     rcx, [rsp+1E8h+var_140]
0x180055bd2  call    ?AccountName@KnownUserProperties@System@Windows@winrt@@SA@XZ; winrt::Windows::System::KnownUserProperties::AccountName(void)
0x180055bd7  nop
0x180055bd8  mov     rax, [rax]
0x180055bdb  mov     [rsp+1E8h+var_168], rax
0x180055be3  lea     r8, [rsp+1E8h+var_168]
0x180055beb  lea     rdx, [rsp+1E8h+var_178]
0x180055bf0  lea     rcx, [rsp+1E8h+var_188]
0x180055bf5  call    ?GetPropertyAsync@?$consume_Windows_System_IUser@UIUser@System@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_System_IUser<winrt::Windows::System::IUser>::GetPropertyAsync(winrt::param::hstring const &)
0x180055bfa  nop
0x180055bfb  lea     rdx, [rsp+1E8h+var_198]
0x180055c00  mov     rcx, rax
0x180055c03  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@UIInspectable@234@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::IInspectable>::get(void)
0x180055c08  nop
0x180055c09  mov     rcx, [rax]
0x180055c0c  test    rcx, rcx
0x180055c0f  jnz     short loc_180055C18
0x180055c11  mov     qword ptr [rsp+1E8h+var_1A8], rdi
0x180055c16  jmp     short loc_180055C65
0x180055c18  mov     [rsp+1E8h+var_1B8], rdi
0x180055c1d  mov     dword ptr [rsp+1E8h+var_168], edi
0x180055c24  xorps   xmm0, xmm0
0x180055c27  movdqu  [rsp+1E8h+var_160], xmm0
0x180055c30  mov     rax, [rcx]
0x180055c33  lea     r8, [rsp+1E8h+var_1B8]
0x180055c38  lea     rdx, ??$guid_v@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>
0x180055c3f  mov     rax, [rax]
0x180055c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c47  lea     r8, [rsp+1E8h+var_168]
0x180055c4f  mov     edx, eax
0x180055c51  lea     rcx, [rsp+1E8h+var_1A8]
0x180055c56  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180055c5b  mov     rax, [rsp+1E8h+var_1B8]
0x180055c60  mov     qword ptr [rsp+1E8h+var_1A8], rax
0x180055c65  lea     rdx, [rsp+1E8h+var_180]
0x180055c6a  lea     rcx, [rsp+1E8h+var_1A8]
0x180055c6f  call    ?GetString@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(void)
0x180055c74  nop
0x180055c75  lea     rcx, [rsp+1E8h+var_1A8]; this
0x180055c7a  call    ??1IUser@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::IUser::~IUser(void)
0x180055c7f  nop
0x180055c80  cmp     qword ptr [rsp+1E8h+var_198], rdi
0x180055c85  jz      short loc_180055C92
0x180055c87  lea     rcx, [rsp+1E8h+var_198]
0x180055c8c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180055c91  nop
0x180055c92  lea     rcx, [rsp+1E8h+var_178]; this
0x180055c97  call    ??1IUser@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::IUser::~IUser(void)
0x180055c9c  nop
0x180055c9d  lea     rcx, [rsp+1E8h+var_140]
0x180055ca5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180055caa  lea     rdx, [rsp+1E8h+var_168]
0x180055cb2  lea     rcx, [rsp+1E8h+var_180]
0x180055cb7  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180055cbc  movups  xmm0, xmmword ptr [rax]
0x180055cbf  movdqu  [rsp+1E8h+var_1A8], xmm0
0x180055cc5  lea     rdx, [rsp+1E8h+var_1A8]
0x180055cca  lea     rcx, [rsp+1E8h+var_38]
0x180055cd2  call    ?to_string@winrt@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; winrt::to_string(std::basic_string_view<ushort>)
0x180055cd7  nop
0x180055cd8  mov     rcx, rax
0x180055cdb  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180055ce0  mov     rdx, rax
0x180055ce3  lea     rcx, [rsp+1E8h+var_E8]
0x180055ceb  call    ??$make_unique_ansistring@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z; wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)
0x180055cf0  nop
0x180055cf1  lea     rcx, [rsp+1E8h+var_38]
0x180055cf9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180055cfe  lea     rcx, [rsp+1E8h+var_178]
0x180055d03  call    ?FirstName@KnownUserProperties@System@Windows@winrt@@SA@XZ; winrt::Windows::System::KnownUserProperties::FirstName(void)
0x180055d08  nop
0x180055d09  mov     rax, [rax]
0x180055d0c  mov     [rsp+1E8h+var_38], rax
0x180055d14  lea     r8, [rsp+1E8h+var_38]
0x180055d1c  lea     rdx, [rsp+1E8h+var_140]
0x180055d24  lea     rcx, [rsp+1E8h+var_188]
0x180055d29  call    ?GetPropertyAsync@?$consume_Windows_System_IUser@UIUser@System@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_System_IUser<winrt::Windows::System::IUser>::GetPropertyAsync(winrt::param::hstring const &)
0x180055d2e  nop
0x180055d2f  lea     rdx, [rsp+1E8h+var_1B8]
0x180055d34  mov     rcx, rax
0x180055d37  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@UIInspectable@234@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::IInspectable>::get(void)
0x180055d3c  nop
0x180055d3d  mov     rcx, [rax]
0x180055d40  test    rcx, rcx
0x180055d43  jnz     short loc_180055D4C
0x180055d45  mov     qword ptr [rsp+1E8h+var_1A8], rdi
0x180055d4a  jmp     short loc_180055D99
0x180055d4c  mov     qword ptr [rsp+1E8h+var_198], rdi
0x180055d51  mov     dword ptr [rsp+1E8h+var_168], edi
0x180055d58  xorps   xmm0, xmm0
0x180055d5b  movdqu  [rsp+1E8h+var_160], xmm0
0x180055d64  mov     rax, [rcx]
0x180055d67  lea     r8, [rsp+1E8h+var_198]
0x180055d6c  lea     rdx, ??$guid_v@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>
0x180055d73  mov     rax, [rax]
0x180055d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d7b  lea     r8, [rsp+1E8h+var_168]
0x180055d83  mov     edx, eax
0x180055d85  lea     rcx, [rsp+1E8h+var_1A8]
0x180055d8a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180055d8f  mov     rax, qword ptr [rsp+1E8h+var_198]
0x180055d94  mov     qword ptr [rsp+1E8h+var_1A8], rax
0x180055d99  lea     rdx, [rsp+1E8h+var_F0]
0x180055da1  lea     rcx, [rsp+1E8h+var_1A8]
0x180055da6  call    ?GetString@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(void)
0x180055dab  nop
0x180055dac  lea     rcx, [rsp+1E8h+var_1A8]; this
0x180055db1  call    ??1IUser@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::IUser::~IUser(void)
0x180055db6  nop
0x180055db7  cmp     [rsp+1E8h+var_1B8], rdi
0x180055dbc  jz      short loc_180055DC9
0x180055dbe  lea     rcx, [rsp+1E8h+var_1B8]
0x180055dc3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180055dc8  nop
0x180055dc9  lea     rcx, [rsp+1E8h+var_140]; this
0x180055dd1  call    ??1IUser@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::IUser::~IUser(void)
0x180055dd6  nop
0x180055dd7  lea     rcx, [rsp+1E8h+var_178]
0x180055ddc  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180055de1  lea     rdx, [rsp+1E8h+var_168]
0x180055de9  lea     rcx, [rsp+1E8h+var_F0]
0x180055df1  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180055df6  movups  xmm0, xmmword ptr [rax]
0x180055df9  movdqu  [rsp+1E8h+var_198], xmm0
0x180055dff  lea     rdx, [rsp+1E8h+var_198]
0x180055e04  lea     rcx, [rsp+1E8h+var_38]
0x180055e0c  call    ?to_string@winrt@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; winrt::to_string(std::basic_string_view<ushort>)
0x180055e11  nop
0x180055e12  mov     rcx, rax
0x180055e15  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180055e1a  mov     rdx, rax
0x180055e1d  lea     rcx, [rsp+1E8h+var_F8]
0x180055e25  call    ??$make_unique_ansistring@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z; wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)
0x180055e2a  nop
0x180055e2b  lea     rcx, [rsp+1E8h+var_38]
0x180055e33  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180055e38  lea     rcx, [rsp+1E8h+var_178]
0x180055e3d  call    ?LastName@KnownUserProperties@System@Windows@winrt@@SA@XZ; winrt::Windows::System::KnownUserProperties::LastName(void)
0x180055e42  nop
0x180055e43  mov     rax, [rax]
0x180055e46  mov     [rsp+1E8h+var_38], rax
0x180055e4e  lea     r8, [rsp+1E8h+var_38]
0x180055e56  lea     rdx, [rsp+1E8h+var_140]
0x180055e5e  lea     rcx, [rsp+1E8h+var_188]
0x180055e63  call    ?GetPropertyAsync@?$consume_Windows_System_IUser@UIUser@System@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_System_IUser<winrt::Windows::System::IUser>::GetPropertyAsync(winrt::param::hstring const &)
0x180055e68  nop
0x180055e69  lea     rdx, [rsp+1E8h+var_1B8]
0x180055e6e  mov     rcx, rax
0x180055e71  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@UIInspectable@234@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::IInspectable>::get(void)
0x180055e76  nop
0x180055e77  mov     rcx, [rax]
0x180055e7a  test    rcx, rcx
0x180055e7d  jnz     short loc_180055E86
0x180055e7f  mov     qword ptr [rsp+1E8h+var_1A8], rdi
0x180055e84  jmp     short loc_180055ED3
0x180055e86  mov     qword ptr [rsp+1E8h+var_198], rdi
0x180055e8b  mov     dword ptr [rsp+1E8h+var_168], edi
0x180055e92  xorps   xmm0, xmm0
0x180055e95  movdqu  [rsp+1E8h+var_160], xmm0
0x180055e9e  mov     rax, [rcx]
0x180055ea1  lea     r8, [rsp+1E8h+var_198]
0x180055ea6  lea     rdx, ??$guid_v@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>
0x180055ead  mov     rax, [rax]
0x180055eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055eb5  lea     r8, [rsp+1E8h+var_168]
0x180055ebd  mov     edx, eax
0x180055ebf  lea     rcx, [rsp+1E8h+var_1A8]
0x180055ec4  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180055ec9  mov     rax, qword ptr [rsp+1E8h+var_198]
0x180055ece  mov     qword ptr [rsp+1E8h+var_1A8], rax
0x180055ed3  lea     rdx, [rsp+1E8h+var_100]
0x180055edb  lea     rcx, [rsp+1E8h+var_1A8]
0x180055ee0  call    ?GetString@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(void)
0x180055ee5  nop
0x180055ee6  lea     rcx, [rsp+1E8h+var_1A8]; this
0x180055eeb  call    ??1IUser@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::IUser::~IUser(void)
0x180055ef0  nop
0x180055ef1  cmp     [rsp+1E8h+var_1B8], rdi
0x180055ef6  jz      short loc_180055F03
0x180055ef8  lea     rcx, [rsp+1E8h+var_1B8]
0x180055efd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180055f02  nop
0x180055f03  lea     rcx, [rsp+1E8h+var_140]; this
0x180055f0b  call    ??1IUser@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::IUser::~IUser(void)
0x180055f10  nop
0x180055f11  lea     rcx, [rsp+1E8h+var_178]
0x180055f16  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180055f1b  lea     rdx, [rsp+1E8h+var_168]
0x180055f23  lea     rcx, [rsp+1E8h+var_100]
0x180055f2b  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180055f30  movups  xmm0, xmmword ptr [rax]
0x180055f33  movdqu  [rsp+1E8h+var_198], xmm0
0x180055f39  lea     rdx, [rsp+1E8h+var_198]
0x180055f3e  lea     rcx, [rsp+1E8h+var_38]
0x180055f46  call    ?to_string@winrt@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; winrt::to_string(std::basic_string_view<ushort>)
0x180055f4b  nop
0x180055f4c  mov     rcx, rax
0x180055f4f  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180055f54  mov     rdx, rax
0x180055f57  lea     rcx, [rsp+1E8h+var_108]
0x180055f5f  call    ??$make_unique_ansistring@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z; wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)
0x180055f64  nop
0x180055f65  lea     rcx, [rsp+1E8h+var_38]
0x180055f6d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180055f72  lea     rcx, [rsp+1E8h+var_178]
0x180055f77  call    ?DisplayName@KnownUserProperties@System@Windows@winrt@@SA@XZ; winrt::Windows::System::KnownUserProperties::DisplayName(void)
0x180055f7c  nop
0x180055f7d  mov     rax, [rax]
0x180055f80  mov     [rsp+1E8h+var_38], rax
0x180055f88  lea     r8, [rsp+1E8h+var_38]
0x180055f90  lea     rdx, [rsp+1E8h+var_140]
0x180055f98  lea     rcx, [rsp+1E8h+var_188]
0x180055f9d  call    ?GetPropertyAsync@?$consume_Windows_System_IUser@UIUser@System@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_System_IUser<winrt::Windows::System::IUser>::GetPropertyAsync(winrt::param::hstring const &)
0x180055fa2  nop
0x180055fa3  lea     rdx, [rsp+1E8h+var_1B8]
0x180055fa8  mov     rcx, rax
0x180055fab  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@UIInspectable@234@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::IInspectable>::get(void)
0x180055fb0  nop
0x180055fb1  mov     rcx, [rax]
0x180055fb4  test    rcx, rcx
0x180055fb7  jnz     short loc_180055FC0
0x180055fb9  mov     qword ptr [rsp+1E8h+var_1A8], rdi
0x180055fbe  jmp     short loc_18005600D
0x180055fc0  mov     qword ptr [rsp+1E8h+var_198], rdi
0x180055fc5  mov     dword ptr [rsp+1E8h+var_168], edi
0x180055fcc  xorps   xmm0, xmm0
0x180055fcf  movdqu  [rsp+1E8h+var_160], xmm0
0x180055fd8  mov     rax, [rcx]
0x180055fdb  lea     r8, [rsp+1E8h+var_198]
0x180055fe0  lea     rdx, ??$guid_v@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>
0x180055fe7  mov     rax, [rax]
0x180055fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fef  lea     r8, [rsp+1E8h+var_168]
0x180055ff7  mov     edx, eax
0x180055ff9  lea     rcx, [rsp+1E8h+var_1A8]
0x180055ffe  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180056003  mov     rax, qword ptr [rsp+1E8h+var_198]
0x180056008  mov     qword ptr [rsp+1E8h+var_1A8], rax
0x18005600d  lea     rdx, [rsp+1E8h+var_110]
0x180056015  lea     rcx, [rsp+1E8h+var_1A8]
0x18005601a  call    ?GetString@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(void)
0x18005601f  nop
0x180056020  lea     rcx, [rsp+1E8h+var_1A8]; this
0x180056025  call    ??1IUser@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::IUser::~IUser(void)
0x18005602a  nop
0x18005602b  cmp     [rsp+1E8h+var_1B8], rdi
0x180056030  jz      short loc_18005603D
0x180056032  lea     rcx, [rsp+1E8h+var_1B8]
0x180056037  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18005603c  nop
0x18005603d  lea     rcx, [rsp+1E8h+var_140]; this
0x180056045  call    ??1IUser@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::IUser::~IUser(void)
  ... truncated ...
```
