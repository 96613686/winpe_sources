# LocationDeviceTokenAuth::FetchBearerTokenImp(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,AcquireTicketStats &)

- ea: `0x18013d7c4`
- end: `0x18013e15c`
- name: `?FetchBearerTokenImp@LocationDeviceTokenAuth@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUAcquireTicketStats@@@Z`
- size: `2456`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18013d048`

## callees

- `0x180014340`
- `0x180020880`
- `0x180020994`
- `0x180020c64`
- `0x18008f490`
- `0x180098a2c`
- `0x18009c344`
- `0x1800a98c0`
- `0x1800c5180`
- `0x1800f2a2c`
- `0x18013c5c0`
- `0x18013c91c`
- `0x18013d7c4`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013df5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013df5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18013da50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18013da50`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18013d873`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18013d99d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18013d873`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18013d99d`

## string_xrefs

- `0x18013d97b`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`
- `0x18013d851`: `Windows.Security.Authentication.OnlineId.OnlineIdSystemAuthenticator`
- `0x18013d88a`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`
- `0x18013d8de`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`
- `0x18013d939`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`
- `0x18013d9b4`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`
- `0x18013da67`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`
- `0x18013daef`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`
- `0x18013db79`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`
- `0x18013dc13`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`
- `0x18013dd4c`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`
- `0x18013ddfd`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`
- `0x18013dec5`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`
- `0x18013df7d`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationdevicetokenauth.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 __fastcall LocationDeviceTokenAuth::FetchBearerTokenImp(__int64 a1, _DWORD *a2)
{
  __int128 v4; // xmm6
  const wchar_t *v5; // rdi
  const wchar_t *v6; // r14
  int ActivationFactory; // eax
  unsigned int v8; // ebx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdx
  const WCHAR *v18; // rax
  HRESULT v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // eax
  int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rax
  int v32; // eax
  unsigned int v33; // ebx
  __int64 v34; // rax
  int v35; // eax
  unsigned int v36; // ebx
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64); // rbx
  __int64 v39; // rdx
  int v40; // eax
  unsigned int v41; // ebx
  PCWSTR StringRawBuffer; // rax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-E8h] BYREF
  __int64 v44; // [rsp+38h] [rbp-D0h]
  const wchar_t *v45; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v46; // [rsp+48h] [rbp-C0h] BYREF
  __int64 *v47; // [rsp+50h] [rbp-B8h] BYREF
  __int64 *v48; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v49; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v50; // [rsp+68h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+70h] [rbp-98h] BYREF
  __int64 *v52; // [rsp+78h] [rbp-90h] BYREF
  __int64 v53; // [rsp+80h] [rbp-88h] BYREF
  const wchar_t *v54; // [rsp+88h] [rbp-80h] BYREF
  HSTRING v55; // [rsp+90h] [rbp-78h] BYREF
  int v56; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v57[16]; // [rsp+A0h] [rbp-68h] BYREF
  UINT32 length; // [rsp+B0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v4 = xmmword_1801AA070;
  v5 = L"bd058a95-0fcf-405c-a523-61bc113d6519";
  v6 = L"8949a8c3-3bdd-43d9-ae02-d54f547ef2db";
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OrionEndpointFirstPartyAppRouting>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Location_OrionEndpointFirstPartyAppRouting>::GetImpl'::`2'::impl)
    && LocationDeviceTokenAuth::s_useSecondaryAppPath )
  {
    v4 = xmmword_1801AA050;
    v5 = L"d51b5e92-b708-41cb-bf6e-4c0868c1faa8";
    v6 = L"da09035e-2886-4d6f-833d-b1ba12683da8";
  }
  v47 = 0;
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.OnlineId.OnlineIdSystemAuthenticator",
    0x45u,
    0x44u);
  ActivationFactory = RoGetActivationFactory(v44, &GUID_85047792_f634_41e3_96a4_5164e902c740, &v47);
  v8 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v46 = 0;
    v10 = *v47;
    v46 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v10 + 48))(v47, &v46);
    v12 = v11;
    if ( v11 >= 0 )
    {
      *(_OWORD *)&hstringHeader.Reserved.Reserved1 = v4;
      v13 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v46 + 56LL))(v46, &hstringHeader);
      v14 = v13;
      if ( v13 >= 0 )
      {
        v48 = 0;
        v44 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
          0x46u,
          0x45u);
        v15 = RoGetActivationFactory(v44, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v48);
        v16 = v15;
        if ( v15 >= 0 )
        {
          v54 = v5;
          v45 = v6;
          hstringHeader.Reserved.Reserved1 = (PVOID)L"{}/.default&clientid={}&api-version=2.0";
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 39;
          std::format<unsigned short const *,unsigned short const *>(v57, &hstringHeader, &v45, &v54);
          string = 0;
          v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57, v17);
          v19 = WindowsCreateString(v18, length, &string);
          v20 = v19;
          if ( v19 >= 0 )
          {
            v50 = 0;
            v21 = *v48;
            v50 = 0;
            v22 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v21 + 56))(v48, string, &v50);
            v23 = v22;
            if ( v22 >= 0 )
            {
              v49 = 0;
              v24 = LocationDeviceTokenAuth::AcquireTicketWithTimeout(&v46, &v50, &v49, a2);
              v25 = v24;
              if ( v24 >= 0 )
              {
                v56 = 0;
                v26 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v49 + 56))(v49, &v56);
                v27 = v26;
                if ( v26 >= 0 )
                {
                  v28 = v56;
                  a2[20] = v56;
                  if ( v28 )
                  {
                    LODWORD(v54) = 0;
                    (*(void (__fastcall **)(__int64 *, const wchar_t **))(*v49 + 64))(v49, &v54);
                    v29 = (int)v54;
                    a2[4] = (_DWORD)v54;
                    v30 = -2147188976;
                    if ( v29 < 0 )
                      v30 = v29;
                    a2[3] = v30;
                    wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v49);
                    wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v50);
                    Windows::Internal::String::~String((Windows::Internal::String *)&string);
                    std::wstring::_Tidy_deallocate(v57);
                    wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
                    wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
                    wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
                    return v30;
                  }
                  else
                  {
                    v52 = 0;
                    v31 = *v49;
                    v52 = 0;
                    v32 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v31 + 48))(v49, &v52);
                    v33 = v32;
                    if ( v32 >= 0 )
                    {
                      v53 = 0;
                      v34 = *v52;
                      v53 = 0;
                      v35 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v34 + 48))(v52, &v53);
                      v36 = v35;
                      if ( v35 >= 0 )
                      {
                        v55 = 0;
                        v37 = v53;
                        v38 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 48LL);
                        v39 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(&v55);
                        v40 = v38(v37, v39);
                        v41 = v40;
                        if ( v40 >= 0 )
                        {
                          StringRawBuffer = WindowsGetStringRawBuffer(v55, 0);
                          if ( StringRawBuffer )
                          {
                            std::wstring::assign(a1, StringRawBuffer);
                            if ( *(_QWORD *)(a1 + 16) )
                            {
                              *(_QWORD *)(a2 + 3) = 0;
                              Windows::Internal::String::~String((Windows::Internal::String *)&v55);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v53);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v52);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v49);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v50);
                              Windows::Internal::String::~String((Windows::Internal::String *)&string);
                              std::wstring::_Tidy_deallocate(v57);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
                              return 0;
                            }
                            else
                            {
                              a2[4] = -2147418113;
                              a2[3] = -2147418113;
                              Windows::Internal::String::~String((Windows::Internal::String *)&v55);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v53);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v52);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v49);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v50);
                              Windows::Internal::String::~String((Windows::Internal::String *)&string);
                              std::wstring::_Tidy_deallocate(v57);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
                              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
                              return 2147549183LL;
                            }
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x100,
                              (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\l"
                                            "ocationdevicetokenauth.cpp",
                              (const char *)0x8000FFFFLL,
                              (int)hstringHeader.Reserved.Reserved1);
                            Windows::Internal::String::~String((Windows::Internal::String *)&v55);
                            wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v53);
                            wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v52);
                            wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v49);
                            wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v50);
                            Windows::Internal::String::~String((Windows::Internal::String *)&string);
                            std::wstring::_Tidy_deallocate(v57);
                            wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
                            wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
                            wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
                            return 2147549183LL;
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0xFE,
                            (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\loc"
                                          "ationdevicetokenauth.cpp",
                            (const char *)(unsigned int)v40,
                            (int)hstringHeader.Reserved.Reserved1);
                          Windows::Internal::String::~String((Windows::Internal::String *)&v55);
                          wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v53);
                          wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v52);
                          wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v49);
                          wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v50);
                          Windows::Internal::String::~String((Windows::Internal::String *)&string);
                          std::wstring::_Tidy_deallocate(v57);
                          wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
                          wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
                          wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
                          return v41;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xFB,
                          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locat"
                                        "iondevicetokenauth.cpp",
                          (const char *)(unsigned int)v35,
                          (int)hstringHeader.Reserved.Reserved1);
                        wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v53);
                        wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v52);
                        wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v49);
                        wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v50);
                        Windows::Internal::String::~String((Windows::Internal::String *)&string);
                        std::wstring::_Tidy_deallocate(v57);
                        wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
                        wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
                        wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
                        return v36;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xF8,
                        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locatio"
                                      "ndevicetokenauth.cpp",
                        (const char *)(unsigned int)v32,
                        (int)hstringHeader.Reserved.Reserved1);
                      wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v52);
                      wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v49);
                      wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v50);
                      Windows::Internal::String::~String((Windows::Internal::String *)&string);
                      std::wstring::_Tidy_deallocate(v57);
                      wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
                      wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
                      wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
                      return v33;
                    }
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xEA,
                    (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locationdev"
                                  "icetokenauth.cpp",
                    (const char *)(unsigned int)v26,
                    (int)hstringHeader.Reserved.Reserved1);
                  wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v49);
                  wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v50);
                  Windows::Internal::String::~String((Windows::Internal::String *)&string);
                  std::wstring::_Tidy_deallocate(v57);
                  wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
                  wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
                  wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
                  return v27;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xE7,
                  (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locationdevicetokenauth.cpp",
                  (const char *)(unsigned int)v24,
                  (int)hstringHeader.Reserved.Reserved1);
                wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v49);
                wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v50);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                std::wstring::_Tidy_deallocate(v57);
                wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
                wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
                wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
                return v25;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE4,
                (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locationdevicetokenauth.cpp",
                (const char *)(unsigned int)v22,
                (int)hstringHeader.Reserved.Reserved1);
              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v50);
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              std::wstring::_Tidy_deallocate(v57);
              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
              wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
              return v23;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE1,
              (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locationdevicetokenauth.cpp",
              (const char *)(unsigned int)v19,
              (int)hstringHeader.Reserved.Reserved1);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            std::wstring::_Tidy_deallocate(v57);
            wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
            wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
            wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
            return v20;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDA,
            (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locationdevicetokenauth.cpp",
            (const char *)(unsigned int)v15,
            (int)hstringHeader.Reserved.Reserved1);
          wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v48);
          wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
          wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
          return v16;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD6,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locationdevicetokenauth.cpp",
          (const char *)(unsigned int)v13,
          (int)hstringHeader.Reserved.Reserved1);
        wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
        wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
        return v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locationdevicetokenauth.cpp",
        (const char *)(unsigned int)v11,
        (int)hstringHeader.Reserved.Reserved1);
      wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v46);
      wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
      return v12;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locationdevicetokenauth.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)hstringHeader.Reserved.Reserved1);
    wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&v47);
    return v8;
  }
}

```

## disassembly

```asm
0x18013d7c4  mov     rax, rsp
0x18013d7c7  mov     [rax+18h], rbx
0x18013d7cb  push    rsi
0x18013d7cc  push    rdi
0x18013d7cd  push    r12
0x18013d7cf  push    r14
0x18013d7d1  push    r15
0x18013d7d3  sub     rsp, 0E0h
0x18013d7da  movaps  xmmword ptr [rax-38h], xmm6
0x18013d7de  mov     rax, cs:__security_cookie
0x18013d7e5  xor     rax, rsp
0x18013d7e8  mov     [rsp+108h+var_48], rax
0x18013d7f0  mov     rsi, rdx
0x18013d7f3  mov     r15, rcx
0x18013d7f6  movups  xmm6, cs:xmmword_1801AA070
0x18013d7fd  mov     rdi, cs:off_180169E90; "bd058a95-0fcf-405c-a523-61bc113d6519"
0x18013d804  mov     r14, cs:off_180169E60; "8949a8c3-3bdd-43d9-ae02-d54f547ef2db"
0x18013d80b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Location_OrionEndpointFirstPartyAppRouting@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Location_OrionEndpointFirstPartyAppRouting@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OrionEndpointFirstPartyAppRouting> `wil::Feature<__WilFeatureTraits_Feature_Location_OrionEndpointFirstPartyAppRouting>::GetImpl(void)'::`2'::impl
0x18013d812  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Location_OrionEndpointFirstPartyAppRouting@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OrionEndpointFirstPartyAppRouting>::__private_IsEnabled(void)
0x18013d817  xor     r12d, r12d
0x18013d81a  test    al, al
0x18013d81c  jz      short loc_18013D83D
0x18013d81e  mov     al, cs:?s_useSecondaryAppPath@LocationDeviceTokenAuth@@0U?$atomic@_N@std@@A; std::atomic<bool> LocationDeviceTokenAuth::s_useSecondaryAppPath
0x18013d824  test    al, al
0x18013d826  jz      short loc_18013D83D
0x18013d828  movups  xmm6, cs:xmmword_1801AA050
0x18013d82f  mov     rdi, cs:off_180169E70; "d51b5e92-b708-41cb-bf6e-4c0868c1faa8"
0x18013d836  mov     r14, cs:off_180169E80; "da09035e-2886-4d6f-833d-b1ba12683da8"
0x18013d83d  mov     [rsp+108h+var_B8], r12
0x18013d842  mov     [rsp+108h+var_D0], r12
0x18013d847  mov     r9d, 44h ; 'D'; unsigned int
0x18013d84d  lea     r8d, [r9+1]; unsigned int
0x18013d851  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdSystemAuthenticator@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x18013d858  lea     rcx, [rsp+108h+hstringHeader]; hstringHeader
0x18013d85d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18013d862  lea     r8, [rsp+108h+var_B8]
0x18013d867  lea     rdx, _GUID_85047792_f634_41e3_96a4_5164e902c740
0x18013d86e  mov     rcx, [rsp+108h+var_D0]
0x18013d873  call    cs:__imp_RoGetActivationFactory
0x18013d879  mov     ebx, eax
0x18013d87b  test    eax, eax
0x18013d87d  jns     short loc_18013D8AD
0x18013d87f  mov     rcx, [rsp+108h]; this
0x18013d887  mov     r9d, eax; char *
0x18013d88a  lea     r8, aOnecoreuapDriv_86; "onecoreuap\\drivers\\mobilepc\\location"...
0x18013d891  mov     edx, 0D1h; void *
0x18013d896  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d89b  nop
0x18013d89c  lea     rcx, [rsp+108h+var_B8]
0x18013d8a1  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013d8a6  mov     eax, ebx
0x18013d8a8  jmp     loc_18013E12E
0x18013d8ad  mov     [rsp+108h+var_C0], r12
0x18013d8b2  mov     rcx, [rsp+108h+var_B8]
0x18013d8b7  mov     rax, [rcx]
0x18013d8ba  mov     [rsp+108h+var_C0], r12
0x18013d8bf  lea     rdx, [rsp+108h+var_C0]
0x18013d8c4  mov     rax, [rax+30h]
0x18013d8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d8cd  mov     ebx, eax
0x18013d8cf  test    eax, eax
0x18013d8d1  jns     short loc_18013D90C
0x18013d8d3  mov     rcx, [rsp+108h]; this
0x18013d8db  mov     r9d, eax; char *
0x18013d8de  lea     r8, aOnecoreuapDriv_86; "onecoreuap\\drivers\\mobilepc\\location"...
0x18013d8e5  mov     edx, 0D4h; void *
0x18013d8ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d8ef  nop
0x18013d8f0  lea     rcx, [rsp+108h+var_C0]
0x18013d8f5  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013d8fa  nop
0x18013d8fb  lea     rcx, [rsp+108h+var_B8]
0x18013d900  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013d905  mov     eax, ebx
0x18013d907  jmp     loc_18013E12E
0x18013d90c  mov     rcx, [rsp+108h+var_C0]
0x18013d911  movdqa  xmmword ptr [rsp+108h+hstringHeader.Reserved], xmm6; int
0x18013d917  mov     rax, [rcx]
0x18013d91a  lea     rdx, [rsp+108h+hstringHeader]
0x18013d91f  mov     rax, [rax+38h]
0x18013d923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013d928  mov     ebx, eax
0x18013d92a  test    eax, eax
0x18013d92c  jns     short loc_18013D967
0x18013d92e  mov     rcx, [rsp+108h]; this
0x18013d936  mov     r9d, eax; char *
0x18013d939  lea     r8, aOnecoreuapDriv_86; "onecoreuap\\drivers\\mobilepc\\location"...
0x18013d940  mov     edx, 0D6h; void *
0x18013d945  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d94a  nop
0x18013d94b  lea     rcx, [rsp+108h+var_C0]
0x18013d950  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013d955  nop
0x18013d956  lea     rcx, [rsp+108h+var_B8]
0x18013d95b  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013d960  mov     eax, ebx
0x18013d962  jmp     loc_18013E12E
0x18013d967  mov     [rsp+108h+var_B0], r12
0x18013d96c  mov     [rsp+108h+var_D0], r12
0x18013d971  mov     r9d, 45h ; 'E'; unsigned int
0x18013d977  lea     r8d, [r9+1]; unsigned int
0x18013d97b  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x18013d982  lea     rcx, [rsp+108h+hstringHeader]; hstringHeader
0x18013d987  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18013d98c  lea     r8, [rsp+108h+var_B0]
0x18013d991  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x18013d998  mov     rcx, [rsp+108h+var_D0]
0x18013d99d  call    cs:__imp_RoGetActivationFactory
0x18013d9a3  mov     ebx, eax
0x18013d9a5  test    eax, eax
0x18013d9a7  jns     short loc_18013D9ED
0x18013d9a9  mov     rcx, [rsp+108h]; this
0x18013d9b1  mov     r9d, eax; char *
0x18013d9b4  lea     r8, aOnecoreuapDriv_86; "onecoreuap\\drivers\\mobilepc\\location"...
0x18013d9bb  mov     edx, 0DAh; void *
0x18013d9c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d9c5  nop
0x18013d9c6  lea     rcx, [rsp+108h+var_B0]
0x18013d9cb  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013d9d0  nop
0x18013d9d1  lea     rcx, [rsp+108h+var_C0]
0x18013d9d6  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013d9db  nop
0x18013d9dc  lea     rcx, [rsp+108h+var_B8]
0x18013d9e1  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013d9e6  mov     eax, ebx
0x18013d9e8  jmp     loc_18013E12E
0x18013d9ed  mov     [rsp+108h+var_80], rdi
0x18013d9f5  mov     [rsp+108h+var_C8], r14
0x18013d9fa  lea     rax, aDefaultClienti; "{}/.default&clientid={}&api-version=2.0"
0x18013da01  mov     qword ptr [rsp+108h+hstringHeader.Reserved], rax; int
0x18013da06  mov     qword ptr [rsp+108h+hstringHeader.Reserved+8], 27h ; '''
0x18013da0f  lea     r9, [rsp+108h+var_80]
0x18013da17  lea     r8, [rsp+108h+var_C8]
0x18013da1c  lea     rdx, [rsp+108h+hstringHeader]
0x18013da21  lea     rcx, [rsp+108h+var_68]
0x18013da29  call    ??$format@PEBGPEBG@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GPEBGPEBG@0@$$QEAPEBG1@Z; std::format<ushort const *,ushort const *>(std::basic_format_string<ushort,ushort const *,ushort const *>,ushort const * &&,ushort const * &&)
0x18013da2e  nop
0x18013da2f  mov     [rsp+108h+string], r12
0x18013da34  lea     rcx, [rsp+108h+var_68]
0x18013da3c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013da41  mov     rcx, rax; sourceString
0x18013da44  lea     r8, [rsp+108h+string]; string
0x18013da49  mov     edx, [rsp+108h+length]; length
0x18013da50  call    cs:__imp_WindowsCreateString
0x18013da56  mov     ebx, eax
0x18013da58  test    eax, eax
0x18013da5a  jns     short loc_18013DAB9
0x18013da5c  mov     rcx, [rsp+108h]; this
0x18013da64  mov     r9d, eax; char *
0x18013da67  lea     r8, aOnecoreuapDriv_86; "onecoreuap\\drivers\\mobilepc\\location"...
0x18013da6e  mov     edx, 0E1h; void *
0x18013da73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013da78  nop
0x18013da79  lea     rcx, [rsp+108h+string]; this
0x18013da7e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18013da83  nop
0x18013da84  lea     rcx, [rsp+108h+var_68]
0x18013da8c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013da91  nop
0x18013da92  lea     rcx, [rsp+108h+var_B0]
0x18013da97  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013da9c  nop
0x18013da9d  lea     rcx, [rsp+108h+var_C0]
0x18013daa2  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013daa7  nop
0x18013daa8  lea     rcx, [rsp+108h+var_B8]
0x18013daad  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013dab2  mov     eax, ebx
0x18013dab4  jmp     loc_18013E12E
0x18013dab9  mov     [rsp+108h+var_A0], r12
0x18013dabe  mov     rcx, [rsp+108h+var_B0]
0x18013dac3  mov     rax, [rcx]
0x18013dac6  mov     [rsp+108h+var_A0], r12
0x18013dacb  lea     r8, [rsp+108h+var_A0]
0x18013dad0  mov     rdx, [rsp+108h+string]
0x18013dad5  mov     rax, [rax+38h]
0x18013dad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013dade  mov     ebx, eax
0x18013dae0  test    eax, eax
0x18013dae2  jns     short loc_18013DB4C
0x18013dae4  mov     rcx, [rsp+108h]; this
0x18013daec  mov     r9d, eax; char *
0x18013daef  lea     r8, aOnecoreuapDriv_86; "onecoreuap\\drivers\\mobilepc\\location"...
0x18013daf6  mov     edx, 0E4h; void *
0x18013dafb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013db00  nop
0x18013db01  lea     rcx, [rsp+108h+var_A0]
0x18013db06  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013db0b  nop
0x18013db0c  lea     rcx, [rsp+108h+string]; this
0x18013db11  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18013db16  nop
0x18013db17  lea     rcx, [rsp+108h+var_68]
0x18013db1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013db24  nop
0x18013db25  lea     rcx, [rsp+108h+var_B0]
0x18013db2a  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013db2f  nop
0x18013db30  lea     rcx, [rsp+108h+var_C0]
0x18013db35  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013db3a  nop
0x18013db3b  lea     rcx, [rsp+108h+var_B8]
0x18013db40  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013db45  mov     eax, ebx
0x18013db47  jmp     loc_18013E12E
0x18013db4c  mov     [rsp+108h+var_A8], r12
0x18013db51  mov     r9, rsi
0x18013db54  lea     r8, [rsp+108h+var_A8]
0x18013db59  lea     rdx, [rsp+108h+var_A0]
0x18013db5e  lea     rcx, [rsp+108h+var_C0]
0x18013db63  call    ?AcquireTicketWithTimeout@LocationDeviceTokenAuth@@CAJAEBV?$com_ptr_t@UIOnlineIdSystemAuthenticatorForUser@OnlineId@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@AEBV?$com_ptr_t@UIOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@3@AEAV?$com_ptr_t@UIOnlineIdSystemTicketResult@OnlineId@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@3@AEAUAcquireTicketStats@@@Z; LocationDeviceTokenAuth::AcquireTicketWithTimeout(wil::com_ptr_t<Windows::Security::Authentication::OnlineId::IOnlineIdSystemAuthenticatorForUser,wil::err_exception_policy> const &,wil::com_ptr_t<Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest,wil::err_exception_policy> const &,wil::com_ptr_t<Windows::Security::Authentication::OnlineId::IOnlineIdSystemTicketResult,wil::err_exception_policy> &,AcquireTicketStats &)
0x18013db68  mov     ebx, eax
0x18013db6a  test    eax, eax
0x18013db6c  jns     short loc_18013DBE1
0x18013db6e  mov     rcx, [rsp+108h]; this
0x18013db76  mov     r9d, eax; char *
0x18013db79  lea     r8, aOnecoreuapDriv_86; "onecoreuap\\drivers\\mobilepc\\location"...
0x18013db80  mov     edx, 0E7h; void *
0x18013db85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013db8a  nop
0x18013db8b  lea     rcx, [rsp+108h+var_A8]
0x18013db90  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013db95  nop
0x18013db96  lea     rcx, [rsp+108h+var_A0]
0x18013db9b  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013dba0  nop
0x18013dba1  lea     rcx, [rsp+108h+string]; this
0x18013dba6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18013dbab  nop
0x18013dbac  lea     rcx, [rsp+108h+var_68]
0x18013dbb4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013dbb9  nop
0x18013dbba  lea     rcx, [rsp+108h+var_B0]
0x18013dbbf  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013dbc4  nop
0x18013dbc5  lea     rcx, [rsp+108h+var_C0]
0x18013dbca  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013dbcf  nop
0x18013dbd0  lea     rcx, [rsp+108h+var_B8]
0x18013dbd5  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013dbda  mov     eax, ebx
0x18013dbdc  jmp     loc_18013E12E
0x18013dbe1  mov     [rsp+108h+var_70], r12d
0x18013dbe9  mov     rcx, [rsp+108h+var_A8]
0x18013dbee  mov     rax, [rcx]
0x18013dbf1  lea     rdx, [rsp+108h+var_70]
0x18013dbf9  mov     rax, [rax+38h]
0x18013dbfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013dc02  mov     ebx, eax
0x18013dc04  test    eax, eax
0x18013dc06  jns     short loc_18013DC7B
0x18013dc08  mov     rcx, [rsp+108h]; this
0x18013dc10  mov     r9d, eax; char *
0x18013dc13  lea     r8, aOnecoreuapDriv_86; "onecoreuap\\drivers\\mobilepc\\location"...
0x18013dc1a  mov     edx, 0EAh; void *
0x18013dc1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013dc24  nop
0x18013dc25  lea     rcx, [rsp+108h+var_A8]
0x18013dc2a  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013dc2f  nop
0x18013dc30  lea     rcx, [rsp+108h+var_A0]
0x18013dc35  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013dc3a  nop
0x18013dc3b  lea     rcx, [rsp+108h+string]; this
0x18013dc40  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18013dc45  nop
0x18013dc46  lea     rcx, [rsp+108h+var_68]
0x18013dc4e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013dc53  nop
0x18013dc54  lea     rcx, [rsp+108h+var_B0]
0x18013dc59  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013dc5e  nop
0x18013dc5f  lea     rcx, [rsp+108h+var_C0]
0x18013dc64  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013dc69  nop
0x18013dc6a  lea     rcx, [rsp+108h+var_B8]
0x18013dc6f  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013dc74  mov     eax, ebx
0x18013dc76  jmp     loc_18013E12E
0x18013dc7b  mov     eax, [rsp+108h+var_70]
0x18013dc82  mov     [rsi+50h], eax
0x18013dc85  test    eax, eax
0x18013dc87  jz      loc_18013DD1B
0x18013dc8d  mov     dword ptr [rsp+108h+var_80], r12d
0x18013dc95  mov     rcx, [rsp+108h+var_A8]
0x18013dc9a  mov     rax, [rcx]
0x18013dc9d  lea     rdx, [rsp+108h+var_80]
0x18013dca5  mov     rax, [rax+40h]
0x18013dca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013dcae  mov     eax, dword ptr [rsp+108h+var_80]
0x18013dcb5  mov     [rsi+10h], eax
0x18013dcb8  mov     ebx, 80047F10h
0x18013dcbd  test    eax, eax
0x18013dcbf  cmovs   ebx, eax
0x18013dcc2  mov     [rsi+0Ch], ebx
0x18013dcc5  lea     rcx, [rsp+108h+var_A8]
0x18013dcca  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18013dccf  nop
0x18013dcd0  lea     rcx, [rsp+108h+var_A0]
  ... truncated ...
```
