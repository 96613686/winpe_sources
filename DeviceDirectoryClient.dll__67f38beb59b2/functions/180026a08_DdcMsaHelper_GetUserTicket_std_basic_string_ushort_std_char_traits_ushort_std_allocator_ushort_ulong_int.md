# DdcMsaHelper::GetUserTicket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong &,int &)

- ea: `0x180026a08`
- end: `0x1800273be`
- name: `?GetUserTicket@DdcMsaHelper@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAKAEAH@Z`
- size: `2486`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ca4c`

## callees

- `0x1800024c0`
- `0x1800028d4`
- `0x180004060`
- `0x180004d5c`
- `0x180004db8`
- `0x180004e10`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x1800115a8`
- `0x180025abc`
- `0x180025c58`
- `0x18002610c`
- `0x180026a08`
- `0x1800276e4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026ae9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026d58`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026ae9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026d58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800271f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800271f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180026cd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180026cd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026c63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002728c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002729c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026c63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002728c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002729c`
- `MdmCommon!MdmGetServiceTarget` at `0x180026d92`
- `MdmCommon!MdmGetServiceTarget` at `0x180026d92`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180026e14`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180026e14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002726e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002726e`

## string_xrefs

- `0x180027255`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcmsahelper.cpp`
- `0x180026dab`: `CHR(MdmGetServiceTarget(&pwszServiceTarget))`
- `0x180026b02`: `CHR(GetActivationFactory( HStringReference(RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager).Get(), pWebdAuthenticator.GetAddressOf()))`
- `0x18002723e`: `CHR(BlockOnCompletionAndGetResults(pFindProviderOperation.Get(), pProvider.GetAddressOf()))`
- `0x180026d71`: `CHR(GetActivationFactory( HStringReference(RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest).Get(), pWebTokenRequestFactory.GetAddressOf()))`
- `0x180026dec`: `CHR(CreateScope(pwszServiceTarget, LIVE_ID_SERVICE_POLICY, strScopeRequested))`
- `0x180026e2d`: `CHR(StringFromCLSID(g_ApplicationId, &strAppId))`
- `0x180026ec8`: `CHR(pWebTokenRequestFactory->Create( pProvider.Get(), HStringReference(strScopeRequested.c_str()).Get(), HStringReference(strAppId).Get(), tokenRequest.GetAddressOf()))`
- `0x180026feb`: `CHR(pWebdAuthenticator->GetTokenSilentlyAsync(tokenRequest.Get(), &pTokenRequestOperation))`
- `0x18002721f`: `CHR(BlockOnCompletionAndGetResults(pTokenRequestOperation.Get(), &pWebTokenRequestResult))`
- `0x180027062`: `CBR(pWebTokenRequestResult.Get() != 0)`
- `0x18002709f`: `CHR(pWebTokenRequestResult->get_ResponseStatus(&responseStatus))`
- `0x1800270d5`: `CBR(responseStatus == WebTokenRequestStatus_Success)`
- `0x18002712d`: `CHR(pWebTokenRequestResult->get_ResponseData(&pTokenRequestResponses))`
- `0x180027184`: `CHR(pTokenRequestResponses->GetAt(0, &pTokenRequestResponse))`
- `0x1800271dc`: `CHR(pTokenRequestResponse->get_Token(ustrToken.GetAddressOf()))`
- `0x180026ac2`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x180026d2d`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`

## pseudocode

```c
__int64 __fastcall DdcMsaHelper::GetUserTicket(__int64 a1, _DWORD *a2, _DWORD *a3)
{
  int v6; // edx
  int v7; // ecx
  int ActivationFactory; // ebx
  char v9; // r8
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, PVOID, _QWORD); // rbx
  HSTRING_HEADER *v12; // rax
  HRESULT v13; // edx
  int v14; // ecx
  __int64 v15; // r8
  int (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rdi
  int v17; // edx
  int v18; // ecx
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rdi
  int v21; // edx
  int v22; // ecx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rbx
  int v25; // edx
  int v26; // ecx
  char v27; // r8
  HSTRING_HEADER *v28; // rax
  HRESULT v29; // eax
  int v30; // edx
  int v31; // ecx
  unsigned int v32; // r8d
  int v33; // edx
  int v34; // ecx
  __int64 v35; // rdx
  int v36; // ecx
  int v37; // edx
  int v38; // ecx
  int v39; // edx
  int v40; // ecx
  char v41; // r8
  __int64 v42; // rsi
  __int64 (__fastcall *v43)(__int64, __int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), PVOID, PVOID, __int64 *); // rdi
  PVOID Reserved1; // rbx
  char v45; // r8
  HSTRING_HEADER *v46; // rax
  __int64 v47; // rdx
  int v48; // ecx
  __int64 v49; // rdi
  void (__fastcall *v50)(__int64, INT32 *); // rbx
  __int64 v51; // rsi
  void (__fastcall *v52)(__int64, __int64, __int64, __int64 *); // rdi
  __int64 v53; // rbx
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, __int64, _QWORD); // rbx
  int v56; // edx
  int v57; // ecx
  int (__fastcall ***v58)(_QWORD, GUID *, __int64 *); // rdi
  HRESULT v59; // edx
  __int64 v60; // r8
  int v61; // edx
  int v62; // ecx
  int v63; // edx
  int v64; // ecx
  int v65; // eax
  __int64 v66; // rdi
  __int64 (__fastcall *v67)(__int64, __int64 *); // rbx
  int v68; // edx
  int v69; // ecx
  __int64 v70; // rdi
  __int64 (__fastcall *v71)(__int64, _QWORD, __int64 *); // rbx
  int v72; // edx
  int v73; // ecx
  __int64 v74; // rdi
  __int64 (__fastcall *v75)(__int64, HSTRING *); // rbx
  int v76; // edx
  int v77; // ecx
  PCWSTR StringRawBuffer; // rax
  __int64 v79; // r8
  int v80; // ecx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 (__fastcall ***v83)(_QWORD, _QWORD, _QWORD); // rcx
  int (__fastcall ***v84)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v85; // rcx
  __int64 v87; // [rsp+0h] [rbp-148h] BYREF
  __int64 v88; // [rsp+20h] [rbp-128h]
  const char *v89; // [rsp+28h] [rbp-120h]
  __int64 v90; // [rsp+30h] [rbp-118h] BYREF
  INT32 result[2]; // [rsp+38h] [rbp-110h] BYREF
  HSTRING string; // [rsp+40h] [rbp-108h] BYREF
  HSTRING v93; // [rsp+48h] [rbp-100h] BYREF
  int v94; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v95; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v96; // [rsp+60h] [rbp-E8h] BYREF
  __int64 (__fastcall ***v97)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-E0h] BYREF
  __int64 v98; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v99; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v100; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v101; // [rsp+88h] [rbp-C0h] BYREF
  __int64 v102; // [rsp+90h] [rbp-B8h] BYREF
  int (__fastcall ***v103)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp-B0h] BYREF
  int (__fastcall ***v104)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp-A8h] BYREF
  LPOLESTR lpsz; // [rsp+A8h] [rbp-A0h] BYREF
  void *Block; // [rsp+B0h] [rbp-98h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-90h] BYREF
  __int64 v108; // [rsp+D0h] [rbp-78h]
  __m128i v109[2]; // [rsp+D8h] [rbp-70h] BYREF
  HSTRING_HEADER v110; // [rsp+F8h] [rbp-50h] BYREF
  __int64 v111; // [rsp+110h] [rbp-38h]

  lpsz = 0;
  Block = 0;
  v109[0] = 0;
  v109[1] = _mm_load_si128((const __m128i *)&_xmm);
  v109[0].m128i_i16[0] = 0;
  v98 = 0;
  v104 = 0;
  v103 = 0;
  v97 = 0;
  v102 = 0;
  v101 = 0;
  v96 = 0;
  v95 = 0;
  v100 = 0;
  v99 = 0;
  v93 = 0;
  string = 0;
  v94 = 0;
  *a2 = 0;
  *a3 = 0;
  v108 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  ActivationFactory = RoGetActivationFactory(v108, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v98);
  if ( ActivationFactory >= 0 )
  {
    v10 = v98;
    v11 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD))(*(_QWORD *)v98 + 88LL);
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v110, (const WCHAR **)off_18002B7D8, v9);
    ActivationFactory = v11(v10, v12[1].Reserved.Reserved1, &v104);
    if ( ActivationFactory >= 0 )
    {
      v16 = v104;
      ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
                            v104,
                            v13,
                            v15);
      if ( ActivationFactory < 0
        || (ActivationFactory = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*v16)[8])(
                                  v16,
                                  &v97),
            ActivationFactory < 0) )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          v89 = "CHR(BlockOnCompletionAndGetResults(pFindProviderOperation.Get(), pProvider.GetAddressOf()))";
          LODWORD(v88) = 126;
          McTemplateU0dsqs_EventWriteTransfer(
            v18,
            v17,
            ActivationFactory,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
            v88,
            v89,
            v90);
        }
      }
      else
      {
        v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v97;
        if ( v97 )
        {
          v20 = **v97;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
          ActivationFactory = v20(v19, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, &v102);
          if ( ActivationFactory >= 0 )
          {
            v23 = v102;
            v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v102 + 56LL);
            WindowsDeleteString(string);
            string = 0;
            ActivationFactory = v24(v23, &string);
            if ( ActivationFactory >= 0 )
            {
              v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &v110,
                      (const WCHAR **)off_18002B7D0,
                      v27);
              result[0] = 0;
              v29 = WindowsCompareStringOrdinal(string, (HSTRING)v28[1].Reserved.Reserved1, result);
              if ( v29 < 0 )
              {
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v29, v30, v32);
                JUMPOUT(0x1800273BDLL);
              }
              if ( result[0] )
              {
                *a3 = 1;
                ActivationFactory = -2147023579;
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v31,
                    v30,
                    -2147023579,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                    140,
                    "CHR(HRESULT_FROM_WIN32(1317L))",
                    v90);
              }
              else
              {
                v108 = 0;
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                  &hstringHeader,
                  L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
                  0x39u,
                  0x38u);
                ActivationFactory = RoGetActivationFactory(v108, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v101);
                if ( ActivationFactory >= 0 )
                {
                  ActivationFactory = MdmGetServiceTarget((unsigned __int16 **)&Block);
                  if ( ActivationFactory >= 0 )
                  {
                    ActivationFactory = DdcMsaHelper::CreateScope((__int64)Block, v35, (__int64)v109);
                    if ( ActivationFactory >= 0 )
                    {
                      ActivationFactory = StringFromCLSID(&rclsid, &lpsz);
                      if ( ActivationFactory >= 0 )
                      {
                        v42 = v101;
                        v43 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), PVOID, PVOID, __int64 *))(*(_QWORD *)v101 + 48LL);
                        Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                      &v110,
                                      (const WCHAR **)&lpsz,
                                      v41)[1].Reserved.Reserved1;
                        *(_QWORD *)result = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
                        v46 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                &hstringHeader,
                                (const WCHAR **)result,
                                v45);
                        ActivationFactory = v43(
                                              v42,
                                              (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v97,
                                              v46[1].Reserved.Reserved1,
                                              Reserved1,
                                              &v96);
                        if ( ActivationFactory >= 0 )
                        {
                          LOBYTE(v47) = 1;
                          wil::details::FeatureImpl<__WilFeatureTraits_Feature_47826483>::ReportUsage(
                            `wil::Feature<__WilFeatureTraits_Feature_47826483>::GetImpl'::`2'::impl,
                            v47);
                          *(_QWORD *)result = 0;
                          LOBYTE(v90) = 0;
                          v49 = v96;
                          v50 = *(void (__fastcall **)(__int64, INT32 *))(*(_QWORD *)v96 + 80LL);
                          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)result);
                          v50(v49, result);
                          v51 = *(_QWORD *)result;
                          v52 = *(void (__fastcall **)(__int64, __int64, __int64, __int64 *))(**(_QWORD **)result + 80LL);
                          v108 = 0;
                          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                            &hstringHeader,
                            L"windows",
                            8u,
                            7u);
                          v53 = v108;
                          v111 = 0;
                          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v110, L"ssoappgroup", 0xCu, 0xBu);
                          v52(v51, v111, v53, &v90);
                          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)result);
                          v54 = v98;
                          v55 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v98 + 48LL);
                          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v103);
                          ActivationFactory = v55(v54, v96, &v103);
                          if ( ActivationFactory >= 0 )
                          {
                            v58 = v103;
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
                            ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
                                                  v58,
                                                  v59,
                                                  v60);
                            if ( ActivationFactory < 0
                              || (ActivationFactory = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v58)[8])(
                                                        v58,
                                                        &v95),
                                  ActivationFactory < 0) )
                            {
                              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                McTemplateU0dsqs_EventWriteTransfer(
                                  v62,
                                  v61,
                                  ActivationFactory,
                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                                  175,
                                  "CHR(BlockOnCompletionAndGetResults(pTokenRequestOperation.Get(), &pWebTokenRequestResult))",
                                  v90);
                            }
                            else if ( v95 )
                            {
                              ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v95 + 56LL))(
                                                    v95,
                                                    &v94);
                              if ( ActivationFactory >= 0 )
                              {
                                v65 = v94;
                                *a2 = v94;
                                if ( v65 )
                                {
                                  ActivationFactory = -2147467259;
                                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                    McTemplateU0dsqs_EventWriteTransfer(
                                      v64,
                                      v63,
                                      -2147467259,
                                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                                      180,
                                      "CBR(responseStatus == WebTokenRequestStatus_Success)",
                                      v90);
                                }
                                else
                                {
                                  v66 = v95;
                                  v67 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v95 + 48LL);
                                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
                                  ActivationFactory = v67(v66, &v100);
                                  if ( ActivationFactory >= 0 )
                                  {
                                    v70 = v100;
                                    v71 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v100 + 48LL);
                                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
                                    ActivationFactory = v71(v70, 0, &v99);
                                    if ( ActivationFactory >= 0 )
                                    {
                                      v74 = v99;
                                      v75 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v99 + 48LL);
                                      WindowsDeleteString(v93);
                                      v93 = 0;
                                      ActivationFactory = v75(v74, &v93);
                                      if ( ActivationFactory >= 0 )
                                      {
                                        if ( __eh34_try(-1, 0) )
                                        {
                                          __eh34_scope_strut(0);
                                          StringRawBuffer = WindowsGetStringRawBuffer(v93, 0);
                                          std::wstring::assign(a1, (__int64)StringRawBuffer, v79);
                                        }
                                        if ( __eh34_catch(0) )
                                        {
                                          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
                                          {
                                            result[0] = -2147024882;
                                            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                                & 1) != 0 )
                                              McTemplateU0dsqs_EventWriteTransfer(
                                                v80,
                                                (unsigned int)&v87,
                                                -2147024882,
                                                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\"
                                                              "lib\\ddcmsahelper.cpp",
                                                192,
                                                "CHR(((HRESULT)0x8007000EL))");
                                            ActivationFactory = result[0];
                                            __eh34_try_continuation(
                                              0,
                                              &std::bad_alloc `RTTI Type Descriptor',
                                              &loc_18002720D);
                                          }
                                        }
                                      }
                                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits
                                               & 1) != 0 )
                                      {
                                        McTemplateU0dsqs_EventWriteTransfer(
                                          v77,
                                          v76,
                                          ActivationFactory,
                                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\"
                                                        "ddcmsahelper.cpp",
                                          184,
                                          "CHR(pTokenRequestResponse->get_Token(ustrToken.GetAddressOf()))",
                                          v90);
                                      }
                                    }
                                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                    {
                                      McTemplateU0dsqs_EventWriteTransfer(
                                        v73,
                                        v72,
                                        ActivationFactory,
                                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                                        183,
                                        "CHR(pTokenRequestResponses->GetAt(0, &pTokenRequestResponse))",
                                        v90);
                                    }
                                  }
                                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                  {
                                    McTemplateU0dsqs_EventWriteTransfer(
                                      v69,
                                      v68,
                                      ActivationFactory,
                                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                                      182,
                                      "CHR(pWebTokenRequestResult->get_ResponseData(&pTokenRequestResponses))",
                                      v90);
                                  }
                                }
                              }
                              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                              {
                                McTemplateU0dsqs_EventWriteTransfer(
                                  v64,
                                  v63,
                                  ActivationFactory,
                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                                  178,
                                  "CHR(pWebTokenRequestResult->get_ResponseStatus(&responseStatus))",
                                  v90);
                              }
                            }
                            else
                            {
                              ActivationFactory = -2147418113;
                              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                                McTemplateU0dsqs_EventWriteTransfer(
                                  v95,
                                  v61,
                                  -2147418113,
                                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                                  176,
                                  "CBR(pWebTokenRequestResult.Get() != 0)",
                                  v90);
                            }
                          }
                          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                          {
                            McTemplateU0dsqs_EventWriteTransfer(
                              v57,
                              v56,
                              ActivationFactory,
                              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                              174,
                              "CHR(pWebdAuthenticator->GetTokenSilentlyAsync(tokenRequest.Get(), &pTokenRequestOperation))",
                              v90);
                          }
                        }
                        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                        {
                          McTemplateU0dsqs_EventWriteTransfer(
                            v48,
                            v47,
                            ActivationFactory,
                            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                            159,
                            "CHR(pWebTokenRequestFactory->Create( pProvider.Get(), HStringReference(strScopeRequested.c_s"
                            "tr()).Get(), HStringReference(strAppId).Get(), tokenRequest.GetAddressOf()))",
                            v90);
                        }
                      }
                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                      {
                        McTemplateU0dsqs_EventWriteTransfer(
                          v40,
                          v39,
                          ActivationFactory,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                          153,
                          "CHR(StringFromCLSID(g_ApplicationId, &strAppId))",
                          v90);
                      }
                    }
                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    {
                      McTemplateU0dsqs_EventWriteTransfer(
                        v38,
                        v37,
                        ActivationFactory,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                        151,
                        "CHR(CreateScope(pwszServiceTarget, LIVE_ID_SERVICE_POLICY, strScopeRequested))",
                        v90);
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v36,
                      v35,
                      ActivationFactory,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                      149,
                      "CHR(MdmGetServiceTarget(&pwszServiceTarget))",
                      v90);
                  }
                }
                else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v34,
                    v33,
                    ActivationFactory,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                    147,
                    "CHR(GetActivationFactory( HStringReference(RuntimeClass_Windows_Security_Authentication_Web_Core_Web"
                    "TokenRequest).Get(), pWebTokenRequestFactory.GetAddressOf()))",
                    v90);
                }
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v26,
                v25,
                ActivationFactory,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                135,
                "CHR(pProvider2->get_Authority(providerAuthority.GetAddressOf()))",
                v90);
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v22,
              v21,
              ActivationFactory,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
              134,
              "CHR(pProvider.As(&pProvider2))",
              v90);
          }
        }
        else
        {
          *a3 = 1;
          ActivationFactory = -2147023579;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v18,
              v17,
              -2147023579,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
              131,
              "CHR(HRESULT_FROM_WIN32(1317L))",
              v90);
        }
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v14,
        v13,
        ActivationFactory,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
        125,
        "CHR(pWebdAuthenticator->FindAccountProviderAsync( HStringReference(DEFAULT_PROVIDER_ID).Get(), pFindProviderOper"
        "ation.GetAddressOf()))",
        v90);
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      v6,
      ActivationFactory,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
      116,
      "CHR(GetActivationFactory( HStringReference(RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthentication"
      "CoreManager).Get(), pWebdAuthenticator.GetAddressOf()))",
      v90);
  }
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( Block )
    operator delete(Block);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v93);
  v93 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v99);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v100);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
  v81 = v96;
  if ( v96 )
  {
    v96 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
  }
  v82 = v101;
  if ( v101 )
  {
    v101 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v102);
  v83 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v97;
  if ( v97 )
  {
    v97 = 0;
    ((void (__fastcall *)(_QWORD))(*v83)[2])(v83);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v103);
  v84 = v104;
  if ( v104 )
  {
    v104 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v84)[2])(v84);
  }
  v85 = v98;
  if ( v98 )
  {
    v98 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
  }
  std::wstring::_Tidy_deallocate((__int64)v109);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180026a08  mov     r11, rsp
0x180026a0b  mov     [r11+20h], rbx
0x180026a0f  push    rsi
0x180026a10  push    rdi
0x180026a11  push    r12
0x180026a13  push    r14
0x180026a15  push    r15
0x180026a17  sub     rsp, 120h
0x180026a1e  mov     rax, cs:__security_cookie
0x180026a25  xor     rax, rsp
0x180026a28  mov     [rsp+148h+var_30], rax
0x180026a30  mov     rsi, r8
0x180026a33  mov     r15, rdx
0x180026a36  mov     r12, rcx
0x180026a39  xor     r14d, r14d
0x180026a3c  mov     [r11-0A0h], r14
0x180026a43  mov     [r11-98h], r14
0x180026a4a  xorps   xmm0, xmm0
0x180026a4d  movups  xmmword ptr [r11-70h], xmm0
0x180026a52  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180026a5a  movdqu  xmmword ptr [r11-60h], xmm1
0x180026a60  mov     [r11-70h], r14w
0x180026a65  mov     [rsp+148h+var_D8], r14
0x180026a6a  mov     [r11-0A8h], r14
0x180026a71  mov     [r11-0B0h], r14
0x180026a78  mov     [rsp+148h+var_E0], r14
0x180026a7d  mov     [r11-0B8h], r14
0x180026a84  mov     [r11-0C0h], r14
0x180026a8b  mov     [rsp+148h+var_E8], r14
0x180026a90  mov     [rsp+148h+var_F0], r14
0x180026a95  mov     [r11-0C8h], r14
0x180026a9c  mov     [rsp+148h+var_D0], r14
0x180026aa1  mov     [rsp+148h+var_100], r14
0x180026aa6  mov     [rsp+148h+string], r14
0x180026aab  mov     [rsp+148h+var_F8], r14d
0x180026ab0  mov     [rdx], r14d
0x180026ab3  mov     [r8], r14d
0x180026ab6  mov     [r11-78h], r14
0x180026aba  lea     r9d, [r14+45h]; unsigned int
0x180026abe  lea     r8d, [r14+46h]; unsigned int
0x180026ac2  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180026ac9  lea     rcx, [r11-90h]; hstringHeader
0x180026ad0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026ad5  lea     r8, [rsp+148h+var_D8]
0x180026ada  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x180026ae1  mov     rcx, [rsp+148h+var_78]
0x180026ae9  call    cs:__imp_RoGetActivationFactory
0x180026aef  mov     ebx, eax
0x180026af1  test    eax, eax
0x180026af3  jns     short loc_180026B1B
0x180026af5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026afc  jz      loc_180027261
0x180026b02  lea     rax, aChrGetactivati; "CHR(GetActivationFactory( HStringRefere"...
0x180026b09  mov     [rsp+148h+var_120], rax
0x180026b0e  mov     dword ptr [rsp+148h+var_128], 74h ; 't'
0x180026b16  jmp     loc_180027252
0x180026b1b  mov     rdi, [rsp+148h+var_D8]
0x180026b20  mov     rax, [rdi]
0x180026b23  mov     rbx, [rax+58h]
0x180026b27  lea     rdx, off_18002B7D8; "https://login.windows.local"
0x180026b2e  lea     rcx, [rsp+148h+var_50]
0x180026b36  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180026b3b  nop
0x180026b3c  lea     r8, [rsp+148h+var_A8]
0x180026b44  mov     rdx, [rax+18h]
0x180026b48  mov     rcx, rdi
0x180026b4b  mov     rax, rbx
0x180026b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b53  mov     ebx, eax
0x180026b55  test    eax, eax
0x180026b57  jns     short loc_180026B7F
0x180026b59  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026b60  jz      loc_180027261
0x180026b66  lea     rax, aChrPwebdauthen; "CHR(pWebdAuthenticator->FindAccountProv"...
0x180026b6d  mov     [rsp+148h+var_120], rax
0x180026b72  mov     dword ptr [rsp+148h+var_128], 7Dh ; '}'
0x180026b7a  jmp     loc_180027252
0x180026b7f  mov     rdi, [rsp+148h+var_A8]
0x180026b87  mov     rcx, rdi
0x180026b8a  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)
0x180026b8f  mov     ebx, eax
0x180026b91  test    eax, eax
0x180026b93  js      loc_180027235
0x180026b99  mov     rax, [rdi]
0x180026b9c  lea     rdx, [rsp+148h+var_E0]
0x180026ba1  mov     rcx, rdi
0x180026ba4  mov     rax, [rax+40h]
0x180026ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bad  mov     ebx, eax
0x180026baf  test    eax, eax
0x180026bb1  js      loc_180027235
0x180026bb7  mov     rbx, [rsp+148h+var_E0]
0x180026bbc  test    rbx, rbx
0x180026bbf  jnz     short loc_180026BF6
0x180026bc1  mov     dword ptr [rsi], 1
0x180026bc7  mov     r8d, 80070525h
0x180026bcd  mov     ebx, r8d
0x180026bd0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026bd7  jz      loc_180027261
0x180026bdd  lea     rax, aChrHresultFrom_2; "CHR(HRESULT_FROM_WIN32(1317L))"
0x180026be4  mov     [rsp+148h+var_120], rax
0x180026be9  mov     dword ptr [rsp+148h+var_128], 83h
0x180026bf1  jmp     loc_180027255
0x180026bf6  mov     rax, [rbx]
0x180026bf9  mov     rdi, [rax]
0x180026bfc  lea     rcx, [rsp+148h+var_B8]
0x180026c04  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026c09  lea     r8, [rsp+148h+var_B8]
0x180026c11  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x180026c18  mov     rcx, rbx
0x180026c1b  mov     rax, rdi
0x180026c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c23  mov     ebx, eax
0x180026c25  test    eax, eax
0x180026c27  jns     short loc_180026C4F
0x180026c29  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026c30  jz      loc_180027261
0x180026c36  lea     rax, aChrPproviderAs; "CHR(pProvider.As(&pProvider2))"
0x180026c3d  mov     [rsp+148h+var_120], rax
0x180026c42  mov     dword ptr [rsp+148h+var_128], 86h
0x180026c4a  jmp     loc_180027252
0x180026c4f  mov     rdi, [rsp+148h+var_B8]
0x180026c57  mov     rax, [rdi]
0x180026c5a  mov     rbx, [rax+38h]
0x180026c5e  mov     rcx, [rsp+148h+string]; string
0x180026c63  call    cs:__imp_WindowsDeleteString
0x180026c69  mov     [rsp+148h+string], r14
0x180026c6e  lea     rdx, [rsp+148h+string]
0x180026c73  mov     rcx, rdi
0x180026c76  mov     rax, rbx
0x180026c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c7e  mov     ebx, eax
0x180026c80  test    eax, eax
0x180026c82  jns     short loc_180026CAA
0x180026c84  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026c8b  jz      loc_180027261
0x180026c91  lea     rax, aChrPprovider2G; "CHR(pProvider2->get_Authority(providerA"...
0x180026c98  mov     [rsp+148h+var_120], rax
0x180026c9d  mov     dword ptr [rsp+148h+var_128], 87h
0x180026ca5  jmp     loc_180027252
0x180026caa  lea     rdx, off_18002B7D0; "consumers"
0x180026cb1  lea     rcx, [rsp+148h+var_50]
0x180026cb9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180026cbe  mov     [rsp+148h+result], r14d
0x180026cc3  lea     r8, [rsp+148h+result]; result
0x180026cc8  mov     rdx, [rax+18h]; string2
0x180026ccc  mov     rcx, [rsp+148h+string]; string1
0x180026cd1  call    cs:__imp_WindowsCompareStringOrdinal
0x180026cd7  test    eax, eax
0x180026cd9  js      loc_1800273B6
0x180026cdf  cmp     [rsp+148h+result], r14d
0x180026ce4  jz      short loc_180026D1B
0x180026ce6  mov     dword ptr [rsi], 1
0x180026cec  mov     r8d, 80070525h
0x180026cf2  mov     ebx, r8d
0x180026cf5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026cfc  jz      loc_180027261
0x180026d02  lea     rax, aChrHresultFrom_2; "CHR(HRESULT_FROM_WIN32(1317L))"
0x180026d09  mov     [rsp+148h+var_120], rax
0x180026d0e  mov     dword ptr [rsp+148h+var_128], 8Ch
0x180026d16  jmp     loc_180027255
0x180026d1b  mov     [rsp+148h+var_78], r14
0x180026d23  mov     r9d, 38h ; '8'; unsigned int
0x180026d29  lea     r8d, [r9+1]; unsigned int
0x180026d2d  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180026d34  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x180026d3c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026d41  lea     r8, [rsp+148h+var_C0]
0x180026d49  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x180026d50  mov     rcx, [rsp+148h+var_78]
0x180026d58  call    cs:__imp_RoGetActivationFactory
0x180026d5e  mov     ebx, eax
0x180026d60  test    eax, eax
0x180026d62  jns     short loc_180026D8A
0x180026d64  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026d6b  jz      loc_180027261
0x180026d71  lea     rax, aChrGetactivati_5; "CHR(GetActivationFactory( HStringRefere"...
0x180026d78  mov     [rsp+148h+var_120], rax
0x180026d7d  mov     dword ptr [rsp+148h+var_128], 93h
0x180026d85  jmp     loc_180027252
0x180026d8a  lea     rcx, [rsp+148h+Block]
0x180026d92  call    cs:__imp_?MdmGetServiceTarget@@YAJPEAPEAG@Z; MdmGetServiceTarget(ushort * *)
0x180026d98  mov     ebx, eax
0x180026d9a  test    eax, eax
0x180026d9c  jns     short loc_180026DC4
0x180026d9e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026da5  jz      loc_180027261
0x180026dab  lea     rax, aChrMdmgetservi; "CHR(MdmGetServiceTarget(&pwszServiceTar"...
0x180026db2  mov     [rsp+148h+var_120], rax
0x180026db7  mov     dword ptr [rsp+148h+var_128], 95h
0x180026dbf  jmp     loc_180027252
0x180026dc4  lea     r8, [rsp+148h+var_70]
0x180026dcc  mov     rcx, [rsp+148h+Block]
0x180026dd4  call    ?CreateScope@DdcMsaHelper@@SAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcMsaHelper::CreateScope(ushort const *,ushort const *,std::wstring &)
0x180026dd9  mov     ebx, eax
0x180026ddb  test    eax, eax
0x180026ddd  jns     short loc_180026E05
0x180026ddf  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026de6  jz      loc_180027261
0x180026dec  lea     rax, aChrCreatescope; "CHR(CreateScope(pwszServiceTarget, LIVE"...
0x180026df3  mov     [rsp+148h+var_120], rax
0x180026df8  mov     dword ptr [rsp+148h+var_128], 97h
0x180026e00  jmp     loc_180027252
0x180026e05  lea     rdx, [rsp+148h+lpsz]; lplpsz
0x180026e0d  lea     rcx, rclsid; rclsid
0x180026e14  call    cs:__imp_StringFromCLSID
0x180026e1a  mov     ebx, eax
0x180026e1c  test    eax, eax
0x180026e1e  jns     short loc_180026E46
0x180026e20  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026e27  jz      loc_180027261
0x180026e2d  lea     rax, aChrStringfromc; "CHR(StringFromCLSID(g_ApplicationId, &s"...
0x180026e34  mov     [rsp+148h+var_120], rax
0x180026e39  mov     dword ptr [rsp+148h+var_128], 99h
0x180026e41  jmp     loc_180027252
0x180026e46  mov     rsi, [rsp+148h+var_C0]
0x180026e4e  mov     rax, [rsi]
0x180026e51  mov     rdi, [rax+30h]
0x180026e55  lea     rdx, [rsp+148h+lpsz]
0x180026e5d  lea     rcx, [rsp+148h+var_50]
0x180026e65  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180026e6a  nop
0x180026e6b  mov     rbx, [rax+18h]
0x180026e6f  lea     rcx, [rsp+148h+var_70]
0x180026e77  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026e7c  mov     qword ptr [rsp+148h+result], rax
0x180026e81  lea     rdx, [rsp+148h+result]
0x180026e86  lea     rcx, [rsp+148h+hstringHeader]
0x180026e8e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180026e93  nop
0x180026e94  lea     rcx, [rsp+148h+var_E8]
0x180026e99  mov     [rsp+148h+var_128], rcx
0x180026e9e  mov     r9, rbx
0x180026ea1  mov     r8, [rax+18h]
0x180026ea5  mov     rdx, [rsp+148h+var_E0]
0x180026eaa  mov     rcx, rsi
0x180026ead  mov     rax, rdi
0x180026eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026eb5  mov     ebx, eax
0x180026eb7  test    eax, eax
0x180026eb9  jns     short loc_180026EE1
0x180026ebb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026ec2  jz      loc_180027261
0x180026ec8  lea     rax, aChrPwebtokenre_0; "CHR(pWebTokenRequestFactory->Create( pP"...
0x180026ecf  mov     [rsp+148h+var_120], rax
0x180026ed4  mov     dword ptr [rsp+148h+var_128], 9Fh
0x180026edc  jmp     loc_180027252
0x180026ee1  mov     dl, 1
0x180026ee3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47826483@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47826483@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47826483> `wil::Feature<__WilFeatureTraits_Feature_47826483>::GetImpl(void)'::`2'::impl
0x180026eea  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_47826483@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47826483>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180026eef  mov     qword ptr [rsp+148h+result], r14
0x180026ef4  mov     byte ptr [rsp+148h+var_118], r14b
0x180026ef9  mov     rdi, [rsp+148h+var_E8]
0x180026efe  mov     rax, [rdi]
0x180026f01  mov     rbx, [rax+50h]
0x180026f05  lea     rcx, [rsp+148h+result]
0x180026f0a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026f0f  lea     rdx, [rsp+148h+result]
0x180026f14  mov     rcx, rdi
0x180026f17  mov     rax, rbx
0x180026f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f1f  mov     rsi, qword ptr [rsp+148h+result]
0x180026f24  mov     rax, [rsi]
0x180026f27  mov     rdi, [rax+50h]
0x180026f2b  mov     [rsp+148h+var_78], r14
0x180026f33  mov     r9d, 7; unsigned int
0x180026f39  lea     r8d, [r9+1]; unsigned int
0x180026f3d  lea     rdx, aWindows_0; "windows"
0x180026f44  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x180026f4c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026f51  nop
0x180026f52  mov     rbx, [rsp+148h+var_78]
0x180026f5a  mov     [rsp+148h+var_38], r14
0x180026f62  mov     r9d, 0Bh; unsigned int
0x180026f68  lea     r8d, [r9+1]; unsigned int
0x180026f6c  lea     rdx, aSsoappgroup; "ssoappgroup"
0x180026f73  lea     rcx, [rsp+148h+var_50]; hstringHeader
0x180026f7b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026f80  nop
0x180026f81  lea     r9, [rsp+148h+var_118]
0x180026f86  mov     r8, rbx
0x180026f89  mov     rdx, [rsp+148h+var_38]
0x180026f91  mov     rcx, rsi
0x180026f94  mov     rax, rdi
0x180026f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f9c  nop
0x180026f9d  lea     rcx, [rsp+148h+result]
0x180026fa2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026fa7  mov     rdi, [rsp+148h+var_D8]
0x180026fac  mov     rax, [rdi]
0x180026faf  mov     rbx, [rax+30h]
0x180026fb3  lea     rcx, [rsp+148h+var_B0]
0x180026fbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026fc0  lea     r8, [rsp+148h+var_B0]
0x180026fc8  mov     rdx, [rsp+148h+var_E8]
0x180026fcd  mov     rcx, rdi
0x180026fd0  mov     rax, rbx
0x180026fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fd8  mov     ebx, eax
0x180026fda  test    eax, eax
  ... truncated ...
```
