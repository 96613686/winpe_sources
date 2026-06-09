# ModernDeployment::Autopilot::Core::MaaRequestor::SendToAttestationService(std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180157c34`
- end: `0x1801587f9`
- name: `?SendToAttestationService@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV56@@Z`
- size: `3013`
- prototype: ``
- caller_count: `1`
- callee_count: `53`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180157684`

## callees

- `0x18000b8f0`
- `0x18001f250`
- `0x18001f4d0`
- `0x18001f850`
- `0x180020360`
- `0x180020be0`
- `0x180020ed0`
- `0x1800297c0`
- `0x180039f40`
- `0x18003b800`
- `0x18003f680`
- `0x180041360`
- `0x180067e54`
- `0x18006bbf0`
- `0x18006e508`
- `0x180077c04`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x180081cac`
- `0x180081f38`
- `0x180084574`
- `0x18008af70`
- `0x180094ce0`
- `0x1800a1600`
- `0x1800a29ac`
- `0x1800dabf0`
- `0x18011c1e0`
- `0x180136850`
- `0x180136e28`
- `0x1801370c8`
- `0x180137284`
- `0x180137468`
- `0x18014bf88`
- `0x180150544`
- `0x180150784`
- `0x180150824`
- `0x180153588`
- `0x18015364c`
- `0x180154450`
- `0x1801548a4`
- `0x180154a00`
- `0x180154aac`
- `0x180154cb0`
- `0x18015686c`
- `0x180156bac`
- `0x180157c34`
- `0x18015d638`
- `0x18015d76c`
- `0x18015db7c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180158207`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18015821e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180158231`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180158207`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18015821e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180158231`

## string_xrefs

- `0x180157c7e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180157ebf`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180157f78`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x18015816d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x18015824f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180158509`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180158614`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=33 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::MaaRequestor::SendToAttestationService(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rsi
  __m128i si128; // xmm1
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rsi
  int v15; // eax
  unsigned int v16; // esi
  int v17; // eax
  unsigned int v18; // esi
  __int64 v19; // rax
  __int64 v20; // rsi
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // r14d
  __int64 v25; // rsi
  int ErrorDetails; // eax
  unsigned int v27; // ebx
  const WCHAR *v28; // rax
  int v29; // eax
  unsigned int v30; // ebx
  __int64 json; // rax
  const struct web::json::object *v32; // rbx
  const struct web::json::value *v33; // rax
  _QWORD *v34; // rax
  __int64 v35; // rax
  int v36; // eax
  unsigned int v37; // ebx
  int v38; // eax
  unsigned int v39; // ebx
  int v40[2]; // [rsp+20h] [rbp-508h] BYREF
  _QWORD v41[2]; // [rsp+28h] [rbp-500h] BYREF
  _BYTE v42[32]; // [rsp+38h] [rbp-4F0h] BYREF
  _BYTE v43[16]; // [rsp+58h] [rbp-4D0h] BYREF
  _BYTE v44[24]; // [rsp+68h] [rbp-4C0h] BYREF
  _BYTE v45[240]; // [rsp+80h] [rbp-4A8h] BYREF
  int v46; // [rsp+170h] [rbp-3B8h] BYREF
  _QWORD v47[2]; // [rsp+178h] [rbp-3B0h] BYREF
  _BYTE v48[8]; // [rsp+188h] [rbp-3A0h] BYREF
  _BYTE v49[8]; // [rsp+190h] [rbp-398h] BYREF
  _BYTE v50[16]; // [rsp+198h] [rbp-390h] BYREF
  _BYTE v51[24]; // [rsp+1A8h] [rbp-380h] BYREF
  std::_Ref_count_base *v52[2]; // [rsp+1C0h] [rbp-368h] BYREF
  __int64 v53; // [rsp+1D0h] [rbp-358h]
  std::_Ref_count_base **v54; // [rsp+1F8h] [rbp-330h]
  _OWORD v55[2]; // [rsp+200h] [rbp-328h] BYREF
  _OWORD v56[2]; // [rsp+220h] [rbp-308h] BYREF
  _OWORD v57[2]; // [rsp+240h] [rbp-2E8h] BYREF
  _BYTE v58[32]; // [rsp+260h] [rbp-2C8h] BYREF
  _OWORD v59[2]; // [rsp+280h] [rbp-2A8h] BYREF
  _BYTE v60[432]; // [rsp+2A0h] [rbp-288h] BYREF
  _BYTE v61[160]; // [rsp+450h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    web::http::client::http_client_config::http_client_config((web::http::client::http_client_config *)v60);
    v52[0] = (std::_Ref_count_base *)off_1802168C0;
    v54 = v52;
    std::function<void (void)>::operator=(v61, v52);
    std::_Func_class<bool,std::wstring const &>::_Tidy(v52);
    std::wstring::wstring(v58, a1 + 72);
    v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
    web::uri::uri((web::uri *)v45, v7);
    web::http::client::http_client::http_client(
      (web::http::client::http_client *)v50,
      (const struct web::uri *)v45,
      (const struct web::http::client::http_client_config *)v60);
    web::uri::~uri((web::uri *)v45);
    v8 = std::wstring::wstring(v42, &web::http::methods::POST);
    web::http::http_request::http_request(v41, v8);
    v9 = a1 + 136;
    if ( *(_QWORD *)(a1 + 152) )
    {
      v10 = v41[0];
      *(_QWORD *)v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 136);
      std::wstring::wstring(v52, L"x-ms-client-request-id");
      web::http::http_headers::add<unsigned short const *>(v10 + 88, v52, v40);
      std::wstring::_Tidy_deallocate(v52);
    }
    v56[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v56[1] = si128;
    LOWORD(v56[0]) = 0;
    if ( *(_QWORD *)(a1 + 120) )
    {
      v12 = std::wstring::wstring(v42, L"bearer ");
      v13 = std::operator+<unsigned short>(v52, v12, a1 + 104);
      std::wstring::operator=(v56, v13);
      std::wstring::_Tidy_deallocate(v52);
      std::wstring::_Tidy_deallocate(v42);
      v14 = v41[0];
      std::wstring::wstring(v52, L"authorization");
      web::http::http_headers::add<std::wstring>(v14 + 88, v52, v56);
      std::wstring::_Tidy_deallocate(v52);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    v55[0] = 0;
    v55[1] = si128;
    LOWORD(v55[0]) = 0;
    v15 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertByteArrayToUnicodeB64(a2, v55);
    v16 = v15;
    if ( v15 >= 0 )
    {
      v57[0] = 0;
      v57[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v57[0]) = 0;
      v17 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertToUriSafeB64(v55, v57);
      v18 = v17;
      if ( v17 >= 0 )
      {
        web::json::value::object(&v46, 0);
        v19 = std::wstring::wstring(v42, v57);
        v20 = web::json::value::string(v40, v19);
        std::wstring::wstring(v52, L"data");
        v21 = web::json::value::operator[](&v46, v52);
        web::json::value::operator=(v21, v20);
        std::wstring::_Tidy_deallocate(v52);
        std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v40);
        web::http::http_request::set_body((web::http::http_request *)v41, (const struct web::json::value *)&v46);
        *(_QWORD *)v40 = 0;
        std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
          v43,
          v41);
        v22 = web::http::client::http_client::request(v50, v44, v43, v40);
        pplx::task<web::http::http_response>::get(v22, v47);
        std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v44);
        pplx::cancellation_token_registration::_Clear((pplx::cancellation_token_registration *)v40);
        v23 = web::http::http_response::content_ready(v47, v52);
        pplx::task<web::http::http_response>::get(v23, v42);
        std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v42);
        std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v52);
        v24 = *(unsigned __int16 *)(v47[0] + 136LL);
        if ( (_WORD)v24 == 200 )
        {
          json = web::http::http_response::extract_json(v47, v52);
          pplx::task<web::json::value>::get(json, v49);
          if ( v52[1] )
            std::_Ref_count_base::_Decref(v52[1]);
          v32 = web::json::value::as_object((web::json::value *)v49);
          std::wstring::wstring(v42, L"data");
          v33 = (const struct web::json::value *)web::json::object::operator[](v32, v42);
          web::json::value::value((web::json::value *)v48, v33);
          std::wstring::_Tidy_deallocate(v42);
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,web::http::http_headers::_case_insensitive_cmp,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,web::http::http_headers::_case_insensitive_cmp,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(
            v51,
            v47[0] + 88LL);
          std::wstring::wstring(v52, L"x-ms-request-id");
          LOBYTE(v32) = web::http::http_headers::has(v51, v52);
          std::wstring::_Tidy_deallocate(v52);
          if ( (_BYTE)v32 )
          {
            std::wstring::wstring(v42, L"x-ms-request-id");
            v34 = (_QWORD *)std::map<std::wstring,std::wstring,web::http::http_headers::_case_insensitive_cmp,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(
                              v51,
                              v52,
                              v42);
            std::wstring::operator=(v9, *v34 + 64LL);
            std::wstring::_Tidy_deallocate(v42);
          }
          *(_OWORD *)v52 = 0;
          v53 = 0;
          v59[0] = 0;
          v59[1] = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v59[0]) = 0;
          v35 = web::json::value::as_string(v48);
          v36 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertFromUriSafeB64(v35, v59);
          v37 = v36;
          if ( v36 >= 0 )
          {
            v38 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertUnicodeB64ToByteArray(v59, v52);
            v39 = v38;
            if ( v38 >= 0 )
            {
              std::vector<unsigned char>::operator=(a3, v52);
              std::wstring::_Tidy_deallocate(v59);
              std::vector<unsigned char>::_Tidy(v52);
              std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                v51,
                v51);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v48);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v49);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v47);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v46);
              std::wstring::_Tidy_deallocate(v57);
              std::wstring::_Tidy_deallocate(v55);
              std::wstring::_Tidy_deallocate(v56);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v41);
              `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v50);
              std::wstring::_Tidy_deallocate(v58);
              web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v60);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x258,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
                (const char *)(unsigned int)v38,
                v40[0]);
              std::wstring::_Tidy_deallocate(v59);
              std::vector<unsigned char>::_Tidy(v52);
              std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                v51,
                v51);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v48);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v49);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v47);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v46);
              std::wstring::_Tidy_deallocate(v57);
              std::wstring::_Tidy_deallocate(v55);
              std::wstring::_Tidy_deallocate(v56);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v41);
              `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v50);
              std::wstring::_Tidy_deallocate(v58);
              web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v60);
              return v39;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x257,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
              (const char *)(unsigned int)v36,
              v40[0]);
            std::wstring::_Tidy_deallocate(v59);
            std::vector<unsigned char>::_Tidy(v52);
            std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
              v51,
              v51);
            std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v48);
            std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v49);
            std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v47);
            std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v46);
            std::wstring::_Tidy_deallocate(v57);
            std::wstring::_Tidy_deallocate(v55);
            std::wstring::_Tidy_deallocate(v56);
            std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v41);
            `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v50);
            std::wstring::_Tidy_deallocate(v58);
            web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v60);
            return v37;
          }
        }
        else
        {
          v25 = a1 + 200;
          ErrorDetails = ModernDeployment::Autopilot::Core::ExtractErrorDetails(v47, a1 + 168, a1 + 200, a1 + 136);
          v27 = ErrorDetails;
          if ( ErrorDetails >= 0 )
          {
            OutputDebugStringW(L"Correlation Vector: ");
            v28 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
            OutputDebugStringW(v28);
            OutputDebugStringW(L"\r\n");
            v29 = ModernDeployment::Autopilot::Core::ConvertErrorCodeToMaaHresult(v25);
            v30 = v29;
            if ( v29 >= 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x247,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
                (const char *)(v24 | 0x80190000),
                v40[0]);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v47);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v46);
              std::wstring::_Tidy_deallocate(v57);
              std::wstring::_Tidy_deallocate(v55);
              std::wstring::_Tidy_deallocate(v56);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v41);
              `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v50);
              std::wstring::_Tidy_deallocate(v58);
              web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v60);
              return v24 | 0x80190000;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x244,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
                (const char *)(unsigned int)v29,
                v40[0]);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v47);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v46);
              std::wstring::_Tidy_deallocate(v57);
              std::wstring::_Tidy_deallocate(v55);
              std::wstring::_Tidy_deallocate(v56);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v41);
              `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v50);
              std::wstring::_Tidy_deallocate(v58);
              web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v60);
              return v30;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x23D,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
              (const char *)(unsigned int)ErrorDetails,
              v40[0]);
            std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v47);
            std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v46);
            std::wstring::_Tidy_deallocate(v57);
            std::wstring::_Tidy_deallocate(v55);
            std::wstring::_Tidy_deallocate(v56);
            std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v41);
            `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v50);
            std::wstring::_Tidy_deallocate(v58);
            web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v60);
            return v27;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x22E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
          (const char *)(unsigned int)v17,
          v40[0]);
        std::wstring::_Tidy_deallocate(v57);
        std::wstring::_Tidy_deallocate(v55);
        std::wstring::_Tidy_deallocate(v56);
        std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v41);
        `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v50);
        std::wstring::_Tidy_deallocate(v58);
        web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v60);
        return v18;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
        (const char *)(unsigned int)v15,
        v40[0]);
      std::wstring::_Tidy_deallocate(v55);
      std::wstring::_Tidy_deallocate(v56);
      std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v41);
      `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v50);
      std::wstring::_Tidy_deallocate(v58);
      web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v60);
      return v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
      (const char *)0x80004001LL,
      v40[0]);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180157c34  push    rbx
0x180157c36  push    rsi
0x180157c37  push    rdi
0x180157c38  push    r14
0x180157c3a  push    r15
0x180157c3c  sub     rsp, 500h
0x180157c43  mov     rax, cs:__security_cookie
0x180157c4a  xor     rax, rsp
0x180157c4d  mov     [rsp+528h+var_38], rax
0x180157c55  mov     r15, r8
0x180157c58  mov     r14, rdx
0x180157c5b  mov     rbx, rcx
0x180157c5e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180157c65  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180157c6a  test    al, al
0x180157c6c  jnz     short loc_180157C96
0x180157c6e  mov     rcx, [rsp+528h]; this
0x180157c76  mov     ebx, 80004001h
0x180157c7b  mov     r9d, ebx; char *
0x180157c7e  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180157c85  mov     edx, 209h; void *
0x180157c8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180157c8f  mov     eax, ebx
0x180157c91  jmp     loc_1801587D9
0x180157c96  lea     rcx, [rsp+528h+var_288]; this
0x180157c9e  call    ??0http_client_config@client@http@web@@QEAA@XZ; web::http::client::http_client_config::http_client_config(void)
0x180157ca3  nop
0x180157ca4  lea     rax, off_1802168C0
0x180157cab  mov     [rsp+528h+var_368], rax
0x180157cb3  lea     rax, [rsp+528h+var_368]
0x180157cbb  mov     [rsp+528h+var_330], rax
0x180157cc3  lea     rdx, [rsp+528h+var_368]
0x180157ccb  lea     rcx, [rsp+528h+var_D8]
0x180157cd3  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> const &)
0x180157cd8  nop
0x180157cd9  lea     rcx, [rsp+528h+var_368]
0x180157ce1  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180157ce6  lea     rdx, [rbx+48h]
0x180157cea  lea     rcx, [rsp+528h+var_2C8]
0x180157cf2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180157cf7  nop
0x180157cf8  lea     rcx, [rsp+528h+var_2C8]
0x180157d00  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180157d05  mov     rdx, rax; unsigned __int16 *
0x180157d08  lea     rcx, [rsp+528h+var_4A8]; this
0x180157d10  call    ??0uri@web@@QEAA@PEBG@Z; web::uri::uri(ushort const *)
0x180157d15  nop
0x180157d16  lea     r8, [rsp+528h+var_288]; struct web::http::client::http_client_config *
0x180157d1e  lea     rdx, [rsp+528h+var_4A8]; struct web::uri *
0x180157d26  lea     rcx, [rsp+528h+var_390]; this
0x180157d2e  call    ??0http_client@client@http@web@@QEAA@AEBVuri@3@AEBVhttp_client_config@123@@Z; web::http::client::http_client::http_client(web::uri const &,web::http::client::http_client_config const &)
0x180157d33  nop
0x180157d34  lea     rcx, [rsp+528h+var_4A8]; this
0x180157d3c  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x180157d41  lea     rdx, ?POST@methods@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::methods::POST
0x180157d48  lea     rcx, [rsp+528h+var_4F0]
0x180157d4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180157d52  mov     rdx, rax
0x180157d55  lea     rcx, [rsp+528h+var_500]
0x180157d5a  call    ??0http_request@http@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::http_request::http_request(std::wstring)
0x180157d5f  nop
0x180157d60  lea     rdi, [rbx+88h]
0x180157d67  cmp     qword ptr [rdi+10h], 0
0x180157d6c  jz      short loc_180157DB9
0x180157d6e  mov     rsi, [rsp+528h+var_500]
0x180157d73  mov     rcx, rdi
0x180157d76  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180157d7b  mov     qword ptr [rsp+528h+var_508], rax; int
0x180157d80  lea     rdx, aXMsClientReque; "x-ms-client-request-id"
0x180157d87  lea     rcx, [rsp+528h+var_368]
0x180157d8f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180157d94  nop
0x180157d95  lea     r8, [rsp+528h+var_508]
0x180157d9a  lea     rdx, [rsp+528h+var_368]
0x180157da2  lea     rcx, [rsi+58h]
0x180157da6  call    ??$add@PEBG@http_headers@http@web@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEBG@Z; web::http::http_headers::add<ushort const *>(std::wstring const &,ushort const * const &)
0x180157dab  nop
0x180157dac  lea     rcx, [rsp+528h+var_368]
0x180157db4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157db9  xorps   xmm0, xmm0
0x180157dbc  movups  [rsp+528h+var_308], xmm0
0x180157dc4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180157dcc  movdqu  [rsp+528h+var_2F8], xmm1
0x180157dd5  xor     eax, eax
0x180157dd7  mov     word ptr [rsp+528h+var_308], ax
0x180157ddf  cmp     [rbx+78h], rax
0x180157de3  jz      loc_180157E80
0x180157de9  lea     rdx, aBearer_0; "bearer "
0x180157df0  lea     rcx, [rsp+528h+var_4F0]
0x180157df5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180157dfa  nop
0x180157dfb  lea     r8, [rbx+68h]
0x180157dff  mov     rdx, rax
0x180157e02  lea     rcx, [rsp+528h+var_368]
0x180157e0a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180157e0f  mov     rdx, rax
0x180157e12  lea     rcx, [rsp+528h+var_308]
0x180157e1a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180157e1f  lea     rcx, [rsp+528h+var_368]
0x180157e27  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157e2c  nop
0x180157e2d  lea     rcx, [rsp+528h+var_4F0]
0x180157e32  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157e37  mov     rsi, [rsp+528h+var_500]
0x180157e3c  lea     rdx, aAuthorization; "authorization"
0x180157e43  lea     rcx, [rsp+528h+var_368]
0x180157e4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180157e50  nop
0x180157e51  lea     r8, [rsp+528h+var_308]
0x180157e59  lea     rdx, [rsp+528h+var_368]
0x180157e61  lea     rcx, [rsi+58h]
0x180157e65  call    ??$add@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@http_headers@http@web@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; web::http::http_headers::add<std::wstring>(std::wstring const &,std::wstring const &)
0x180157e6a  nop
0x180157e6b  lea     rcx, [rsp+528h+var_368]
0x180157e73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157e78  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180157e80  xorps   xmm0, xmm0
0x180157e83  movups  [rsp+528h+var_328], xmm0
0x180157e8b  movdqu  [rsp+528h+var_318], xmm1
0x180157e94  xor     eax, eax
0x180157e96  mov     word ptr [rsp+528h+var_328], ax
0x180157e9e  lea     rdx, [rsp+528h+var_328]
0x180157ea6  mov     rcx, r14
0x180157ea9  call    ?ConvertByteArrayToUnicodeB64@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertByteArrayToUnicodeB64(std::vector<uchar> const &,std::wstring &)
0x180157eae  mov     esi, eax
0x180157eb0  test    eax, eax
0x180157eb2  jns     short loc_180157F28
0x180157eb4  mov     rcx, [rsp+528h]; this
0x180157ebc  mov     r9d, eax; char *
0x180157ebf  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180157ec6  mov     edx, 22Ch; void *
0x180157ecb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180157ed0  nop
0x180157ed1  lea     rcx, [rsp+528h+var_328]
0x180157ed9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157ede  nop
0x180157edf  lea     rcx, [rsp+528h+var_308]
0x180157ee7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157eec  nop
0x180157eed  lea     rcx, [rsp+528h+var_500]
0x180157ef2  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180157ef7  nop
0x180157ef8  lea     rcx, [rsp+528h+var_390]
0x180157f00  call    ??1_lambda_1_@?0??close@?$streambuf_state_manager@E@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@H@Z@QEAA@XZ; `Concurrency::streams::details::streambuf_state_manager<uchar>::close(int)'::`1'::_lambda_1_::~_lambda_1_(void)
0x180157f05  nop
0x180157f06  lea     rcx, [rsp+528h+var_2C8]
0x180157f0e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157f13  nop
0x180157f14  lea     rcx, [rsp+528h+var_288]; this
0x180157f1c  call    ??1http_client_config@client@http@web@@QEAA@XZ; web::http::client::http_client_config::~http_client_config(void)
0x180157f21  mov     eax, esi
0x180157f23  jmp     loc_1801587D9
0x180157f28  xorps   xmm0, xmm0
0x180157f2b  movups  [rsp+528h+var_2E8], xmm0
0x180157f33  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180157f3b  movdqu  [rsp+528h+var_2D8], xmm1
0x180157f44  xor     eax, eax
0x180157f46  mov     word ptr [rsp+528h+var_2E8], ax
0x180157f4e  lea     rdx, [rsp+528h+var_2E8]
0x180157f56  lea     rcx, [rsp+528h+var_328]
0x180157f5e  call    ?ConvertToUriSafeB64@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertToUriSafeB64(std::wstring const &,std::wstring &)
0x180157f63  mov     esi, eax
0x180157f65  test    eax, eax
0x180157f67  jns     loc_180157FEF
0x180157f6d  mov     rcx, [rsp+528h]; this
0x180157f75  mov     r9d, eax; char *
0x180157f78  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180157f7f  mov     edx, 22Eh; void *
0x180157f84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180157f89  nop
0x180157f8a  lea     rcx, [rsp+528h+var_2E8]
0x180157f92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157f97  nop
0x180157f98  lea     rcx, [rsp+528h+var_328]
0x180157fa0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157fa5  nop
0x180157fa6  lea     rcx, [rsp+528h+var_308]
0x180157fae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157fb3  nop
0x180157fb4  lea     rcx, [rsp+528h+var_500]
0x180157fb9  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180157fbe  nop
0x180157fbf  lea     rcx, [rsp+528h+var_390]
0x180157fc7  call    ??1_lambda_1_@?0??close@?$streambuf_state_manager@E@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@H@Z@QEAA@XZ; `Concurrency::streams::details::streambuf_state_manager<uchar>::close(int)'::`1'::_lambda_1_::~_lambda_1_(void)
0x180157fcc  nop
0x180157fcd  lea     rcx, [rsp+528h+var_2C8]
0x180157fd5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157fda  nop
0x180157fdb  lea     rcx, [rsp+528h+var_288]; this
0x180157fe3  call    ??1http_client_config@client@http@web@@QEAA@XZ; web::http::client::http_client_config::~http_client_config(void)
0x180157fe8  mov     eax, esi
0x180157fea  jmp     loc_1801587D9
0x180157fef  xor     edx, edx
0x180157ff1  lea     rcx, [rsp+528h+var_3B8]
0x180157ff9  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x180157ffe  nop
0x180157fff  lea     rdx, [rsp+528h+var_2E8]
0x180158007  lea     rcx, [rsp+528h+var_4F0]
0x18015800c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180158011  mov     rdx, rax
0x180158014  lea     rcx, [rsp+528h+var_508]
0x180158019  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x18015801e  mov     rsi, rax
0x180158021  lea     rdx, aData_0; "data"
0x180158028  lea     rcx, [rsp+528h+var_368]
0x180158030  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180158035  nop
0x180158036  lea     rdx, [rsp+528h+var_368]
0x18015803e  lea     rcx, [rsp+528h+var_3B8]
0x180158046  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x18015804b  mov     rdx, rsi
0x18015804e  mov     rcx, rax
0x180158051  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180158056  nop
0x180158057  lea     rcx, [rsp+528h+var_368]
0x18015805f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180158064  nop
0x180158065  lea     rcx, [rsp+528h+var_508]
0x18015806a  call    ??1?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@QEAA@XZ; std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(void)
0x18015806f  lea     rdx, [rsp+528h+var_3B8]; struct web::json::value *
0x180158077  lea     rcx, [rsp+528h+var_500]; this
0x18015807c  call    ?set_body@http_request@http@web@@QEAAXAEBVvalue@json@3@@Z; web::http::http_request::set_body(web::json::value const &)
0x180158081  mov     qword ptr [rsp+528h+var_508], 0; int
0x18015808a  lea     rdx, [rsp+528h+var_500]
0x18015808f  lea     rcx, [rsp+528h+var_4D0]
0x180158094  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x180158099  lea     r9, [rsp+528h+var_508]
0x18015809e  lea     r8, [rsp+528h+var_4D0]
0x1801580a3  lea     rdx, [rsp+528h+var_4C0]
0x1801580a8  lea     rcx, [rsp+528h+var_390]
0x1801580b0  call    ?request@http_client@client@http@web@@QEAA?AV?$task@Vhttp_response@http@web@@@pplx@@Vhttp_request@34@AEBVcancellation_token@6@@Z; web::http::client::http_client::request(web::http::http_request,pplx::cancellation_token const &)
0x1801580b5  nop
0x1801580b6  lea     rdx, [rsp+528h+var_3B0]
0x1801580be  mov     rcx, rax
0x1801580c1  call    ?get@?$task@Vhttp_response@http@web@@@pplx@@QEBA?AVhttp_response@http@web@@XZ; pplx::task<web::http::http_response>::get(void)
0x1801580c6  nop
0x1801580c7  lea     rcx, [rsp+528h+var_4C0]
0x1801580cc  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x1801580d1  nop
0x1801580d2  lea     rcx, [rsp+528h+var_508]; this
0x1801580d7  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x1801580dc  nop
0x1801580dd  lea     rdx, [rsp+528h+var_368]
0x1801580e5  lea     rcx, [rsp+528h+var_3B0]
0x1801580ed  call    ?content_ready@http_response@http@web@@QEBA?AV?$task@Vhttp_response@http@web@@@pplx@@XZ; web::http::http_response::content_ready(void)
0x1801580f2  nop
0x1801580f3  lea     rdx, [rsp+528h+var_4F0]
0x1801580f8  mov     rcx, rax
0x1801580fb  call    ?get@?$task@Vhttp_response@http@web@@@pplx@@QEBA?AVhttp_response@http@web@@XZ; pplx::task<web::http::http_response>::get(void)
0x180158100  lea     rcx, [rsp+528h+var_4F0]
0x180158105  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18015810a  nop
0x18015810b  lea     rcx, [rsp+528h+var_368]
0x180158113  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180158118  mov     rax, [rsp+528h+var_3B0]
0x180158120  movzx   r14d, word ptr [rax+88h]
0x180158128  mov     eax, 0C8h
0x18015812d  lea     rcx, [rsp+528h+var_3B0]
0x180158135  cmp     r14w, ax
0x180158139  jz      loc_180158385
0x18015813f  lea     rsi, [rbx+0C8h]
0x180158146  lea     rdx, [rbx+0A8h]
0x18015814d  mov     r9, rdi
0x180158150  mov     r8, rsi
0x180158153  call    ?ExtractErrorDetails@Core@Autopilot@ModernDeployment@@YAJAEBVhttp_response@http@web@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; ModernDeployment::Autopilot::Core::ExtractErrorDetails(web::http::http_response const &,std::wstring &,std::wstring &,std::wstring &)
0x180158158  mov     ebx, eax
0x18015815a  test    eax, eax
0x18015815c  jns     loc_180158200
0x180158162  mov     rcx, [rsp+528h]; this
0x18015816a  mov     r9d, eax; char *
0x18015816d  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180158174  mov     edx, 23Dh; void *
0x180158179  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015817e  nop
0x18015817f  lea     rcx, [rsp+528h+var_3B0]
0x180158187  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x18015818c  nop
0x18015818d  lea     rcx, [rsp+528h+var_3B8]
0x180158195  call    ??1?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@QEAA@XZ; std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(void)
0x18015819a  nop
0x18015819b  lea     rcx, [rsp+528h+var_2E8]
0x1801581a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801581a8  nop
0x1801581a9  lea     rcx, [rsp+528h+var_328]
0x1801581b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801581b6  nop
0x1801581b7  lea     rcx, [rsp+528h+var_308]
0x1801581bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801581c4  nop
0x1801581c5  lea     rcx, [rsp+528h+var_500]
0x1801581ca  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x1801581cf  nop
0x1801581d0  lea     rcx, [rsp+528h+var_390]
0x1801581d8  call    ??1_lambda_1_@?0??close@?$streambuf_state_manager@E@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@H@Z@QEAA@XZ; `Concurrency::streams::details::streambuf_state_manager<uchar>::close(int)'::`1'::_lambda_1_::~_lambda_1_(void)
0x1801581dd  nop
0x1801581de  lea     rcx, [rsp+528h+var_2C8]
0x1801581e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801581eb  nop
0x1801581ec  lea     rcx, [rsp+528h+var_288]; this
0x1801581f4  call    ??1http_client_config@client@http@web@@QEAA@XZ; web::http::client::http_client_config::~http_client_config(void)
  ... truncated ...
```
