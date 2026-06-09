# ModernDeployment::Autopilot::Core::MaaRequestor::SendToAttestationService(std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180153ad0`
- end: `0x1801546b8`
- name: `?SendToAttestationService@MaaRequestor@Core@Autopilot@ModernDeployment@@IEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV56@@Z`
- size: `3048`
- prototype: ``
- caller_count: `1`
- callee_count: `53`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18015352c`

## callees

- `0x18000b820`
- `0x18001f1e0`
- `0x18001f460`
- `0x18001f7e0`
- `0x1800202e0`
- `0x180020b50`
- `0x180020e30`
- `0x1800296e0`
- `0x180039d90`
- `0x18003b650`
- `0x18003f4d0`
- `0x1800411b0`
- `0x180067a54`
- `0x18006b708`
- `0x18006dfb8`
- `0x180077384`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x18008122c`
- `0x1800814a8`
- `0x1800839bc`
- `0x18008a0a8`
- `0x180093a28`
- `0x1800a0084`
- `0x1800a13a4`
- `0x1800d84e0`
- `0x180118938`
- `0x180132a00`
- `0x180132fb8`
- `0x180133258`
- `0x180133408`
- `0x1801335e0`
- `0x18014804c`
- `0x18014c5a0`
- `0x18014c7e0`
- `0x18014c87c`
- `0x18014d828`
- `0x18014f5d8`
- `0x1801503f8`
- `0x180150824`
- `0x180150980`
- `0x180150a2c`
- `0x180150c28`
- `0x18015278c`
- `0x180152a98`
- `0x180153ad0`
- `0x180159438`
- `0x180159564`
- `0x180159960`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801540c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801540d1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801540de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801540c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801540d1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801540de`

## string_xrefs

- `0x180153b1f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180153d69`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180153e25`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x180154023`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x1801540f6`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x1801543b6`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`
- `0x1801544c4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\maarequestor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=34 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::MaaRequestor::SendToAttestationService(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rbx
  __m128i si128; // xmm1
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // r15d
  int ErrorDetails; // eax
  unsigned int v23; // ebx
  const WCHAR *v24; // rax
  int v25; // eax
  unsigned int v26; // ebx
  __int64 json; // rax
  const struct web::json::object *v28; // rbx
  const struct web::json::value *v29; // rax
  _QWORD *v30; // rax
  __int64 v31; // rax
  int v32; // eax
  unsigned int v33; // ebx
  int v34; // eax
  unsigned int v35; // ebx
  int v36[2]; // [rsp+20h] [rbp-508h] BYREF
  _BYTE v37[32]; // [rsp+28h] [rbp-500h] BYREF
  _BYTE v38[16]; // [rsp+48h] [rbp-4E0h] BYREF
  _BYTE v39[24]; // [rsp+58h] [rbp-4D0h] BYREF
  _BYTE v40[240]; // [rsp+70h] [rbp-4B8h] BYREF
  int v41; // [rsp+160h] [rbp-3C8h] BYREF
  _QWORD v42[2]; // [rsp+168h] [rbp-3C0h] BYREF
  _QWORD v43[2]; // [rsp+178h] [rbp-3B0h] BYREF
  _BYTE v44[8]; // [rsp+188h] [rbp-3A0h] BYREF
  _BYTE v45[8]; // [rsp+190h] [rbp-398h] BYREF
  _BYTE v46[16]; // [rsp+198h] [rbp-390h] BYREF
  _BYTE v47[24]; // [rsp+1A8h] [rbp-380h] BYREF
  std::_Ref_count_base *v48[2]; // [rsp+1C0h] [rbp-368h] BYREF
  __int64 v49; // [rsp+1D0h] [rbp-358h]
  std::_Ref_count_base **v50; // [rsp+1F8h] [rbp-330h]
  _OWORD v51[2]; // [rsp+200h] [rbp-328h] BYREF
  _OWORD v52[2]; // [rsp+220h] [rbp-308h] BYREF
  _OWORD v53[2]; // [rsp+240h] [rbp-2E8h] BYREF
  _BYTE v54[32]; // [rsp+260h] [rbp-2C8h] BYREF
  _OWORD v55[2]; // [rsp+280h] [rbp-2A8h] BYREF
  _BYTE v56[432]; // [rsp+2A0h] [rbp-288h] BYREF
  _BYTE v57[160]; // [rsp+450h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    web::http::client::http_client_config::http_client_config((web::http::client::http_client_config *)v56);
    v48[0] = (std::_Ref_count_base *)off_1802108C0;
    v50 = v48;
    std::function<void (void)>::operator=(v57, v48);
    std::_Func_class<bool,std::wstring const &>::_Tidy(v48);
    std::wstring::wstring(v54, a1 + 72);
    v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
    web::uri::uri((web::uri *)v40, v7);
    web::http::client::http_client::http_client(
      (web::http::client::http_client *)v46,
      (const struct web::uri *)v40,
      (const struct web::http::client::http_client_config *)v56);
    web::uri::~uri((web::uri *)v40);
    *(_QWORD *)v36 = std::wstring::wstring(v37, &web::http::methods::POST);
    std::make_shared<web::http::details::_http_request,std::wstring>(v42, *(_QWORD *)v36);
    std::wstring::_Tidy_deallocate(*(_QWORD *)v36);
    v8 = v42[0];
    if ( *(_QWORD *)(a1 + 152) )
    {
      *(_QWORD *)v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 136);
      std::wstring::wstring(v48, L"x-ms-client-request-id");
      web::http::http_headers::add<unsigned short const *>(v8 + 88, v48, v36);
      std::wstring::_Tidy_deallocate(v48);
    }
    v52[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v52[1] = si128;
    LOWORD(v52[0]) = 0;
    if ( *(_QWORD *)(a1 + 120) )
    {
      v10 = std::wstring::wstring(v37, L"bearer ");
      v11 = std::operator+<unsigned short>(v48, v10, a1 + 104);
      std::wstring::operator=(v52, v11);
      std::wstring::_Tidy_deallocate(v48);
      std::wstring::_Tidy_deallocate(v37);
      std::wstring::wstring(v48, L"authorization");
      web::http::http_headers::add<std::wstring>(v8 + 88, v48, v52);
      std::wstring::_Tidy_deallocate(v48);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    v51[0] = 0;
    v51[1] = si128;
    LOWORD(v51[0]) = 0;
    v12 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertByteArrayToUnicodeB64(a2, v51);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v53[0] = 0;
      v53[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v53[0]) = 0;
      v14 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertToUriSafeB64(v51, v53);
      v15 = v14;
      if ( v14 >= 0 )
      {
        web::json::value::object(&v41, 0);
        v16 = std::wstring::wstring(v37, v53);
        v17 = web::json::value::string(v36, v16);
        std::wstring::wstring(v48, L"data");
        v18 = web::json::value::operator[](&v41, v48);
        web::json::value::operator=(v18, v17);
        std::wstring::_Tidy_deallocate(v48);
        std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v36);
        web::http::http_request::set_body((web::http::http_request *)v42, (const struct web::json::value *)&v41);
        *(_QWORD *)v36 = 0;
        std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
          v38,
          v42);
        v19 = web::http::client::http_client::request(v46, v39, v38, v36);
        pplx::task<web::http::http_response>::get(v19, v43);
        std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v39);
        pplx::cancellation_token_registration::_Clear((pplx::cancellation_token_registration *)v36);
        v20 = web::http::http_response::content_ready(v43, v48);
        pplx::task<web::http::http_response>::get(v20, v37);
        std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v37);
        std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v48);
        v21 = *(unsigned __int16 *)(v43[0] + 136LL);
        if ( (_WORD)v21 == 200 )
        {
          json = web::http::http_response::extract_json(v43, v48);
          pplx::task<web::json::value>::get(json, v45);
          if ( v48[1] )
            std::_Ref_count_base::_Decref(v48[1]);
          v28 = web::json::value::as_object((web::json::value *)v45);
          std::wstring::wstring(v37, L"data");
          v29 = (const struct web::json::value *)web::json::object::operator[](v28, v37);
          web::json::value::value((web::json::value *)v44, v29);
          std::wstring::_Tidy_deallocate(v37);
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,web::http::http_headers::_case_insensitive_cmp,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,web::http::http_headers::_case_insensitive_cmp,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(
            v47,
            v43[0] + 88LL);
          std::wstring::wstring(v48, L"x-ms-request-id");
          LOBYTE(v28) = web::http::http_headers::has(v47, v48);
          std::wstring::_Tidy_deallocate(v48);
          if ( (_BYTE)v28 )
          {
            std::wstring::wstring(v37, L"x-ms-request-id");
            v30 = (_QWORD *)std::map<std::wstring,std::wstring,web::http::http_headers::_case_insensitive_cmp,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(
                              v47,
                              v48,
                              v37);
            std::wstring::operator=(a1 + 136, *v30 + 64LL);
            std::wstring::_Tidy_deallocate(v37);
          }
          *(_OWORD *)v48 = 0;
          v49 = 0;
          v55[0] = 0;
          v55[1] = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v55[0]) = 0;
          v31 = web::json::value::as_string(v44);
          v32 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertFromUriSafeB64(v31, v55);
          v33 = v32;
          if ( v32 >= 0 )
          {
            v34 = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertUnicodeB64ToByteArray(v55, v48);
            v35 = v34;
            if ( v34 >= 0 )
            {
              std::vector<unsigned char>::operator=(a3, v48);
              std::wstring::_Tidy_deallocate(v55);
              std::vector<unsigned char>::_Tidy(v48);
              std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                v47,
                v47);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v44);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v45);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v43);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v41);
              std::wstring::_Tidy_deallocate(v53);
              std::wstring::_Tidy_deallocate(v51);
              std::wstring::_Tidy_deallocate(v52);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v42);
              `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v46);
              std::wstring::_Tidy_deallocate(v54);
              web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v56);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x258,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
                (const char *)(unsigned int)v34,
                v36[0]);
              std::wstring::_Tidy_deallocate(v55);
              std::vector<unsigned char>::_Tidy(v48);
              std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                v47,
                v47);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v44);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v45);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v43);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v41);
              std::wstring::_Tidy_deallocate(v53);
              std::wstring::_Tidy_deallocate(v51);
              std::wstring::_Tidy_deallocate(v52);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v42);
              `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v46);
              std::wstring::_Tidy_deallocate(v54);
              web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v56);
              return v35;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x257,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
              (const char *)(unsigned int)v32,
              v36[0]);
            std::wstring::_Tidy_deallocate(v55);
            std::vector<unsigned char>::_Tidy(v48);
            std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
              v47,
              v47);
            std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v44);
            std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(v45);
            std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v43);
            std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v41);
            std::wstring::_Tidy_deallocate(v53);
            std::wstring::_Tidy_deallocate(v51);
            std::wstring::_Tidy_deallocate(v52);
            std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v42);
            `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v46);
            std::wstring::_Tidy_deallocate(v54);
            web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v56);
            return v33;
          }
        }
        else
        {
          ErrorDetails = ModernDeployment::Autopilot::Core::ExtractErrorDetails(v43, a1 + 168, a1 + 200, a1 + 136);
          v23 = ErrorDetails;
          if ( ErrorDetails >= 0 )
          {
            OutputDebugStringW(L"Correlation Vector: ");
            v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 136);
            OutputDebugStringW(v24);
            OutputDebugStringW(L"\r\n");
            v25 = ModernDeployment::Autopilot::Core::ConvertErrorCodeToMaaHresult(a1 + 200);
            v26 = v25;
            if ( v25 >= 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x247,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
                (const char *)(v21 | 0x80190000),
                v36[0]);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v43);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v41);
              std::wstring::_Tidy_deallocate(v53);
              std::wstring::_Tidy_deallocate(v51);
              std::wstring::_Tidy_deallocate(v52);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v42);
              `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v46);
              std::wstring::_Tidy_deallocate(v54);
              web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v56);
              return v21 | 0x80190000;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x244,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
                (const char *)(unsigned int)v25,
                v36[0]);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v43);
              std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v41);
              std::wstring::_Tidy_deallocate(v53);
              std::wstring::_Tidy_deallocate(v51);
              std::wstring::_Tidy_deallocate(v52);
              std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v42);
              `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v46);
              std::wstring::_Tidy_deallocate(v54);
              web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v56);
              return v26;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x23D,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
              (const char *)(unsigned int)ErrorDetails,
              v36[0]);
            std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v43);
            std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(&v41);
            std::wstring::_Tidy_deallocate(v53);
            std::wstring::_Tidy_deallocate(v51);
            std::wstring::_Tidy_deallocate(v52);
            std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v42);
            `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v46);
            std::wstring::_Tidy_deallocate(v54);
            web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v56);
            return v23;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x22E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
          (const char *)(unsigned int)v14,
          v36[0]);
        std::wstring::_Tidy_deallocate(v53);
        std::wstring::_Tidy_deallocate(v51);
        std::wstring::_Tidy_deallocate(v52);
        std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v42);
        `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v46);
        std::wstring::_Tidy_deallocate(v54);
        web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v56);
        return v15;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
        (const char *)(unsigned int)v12,
        v36[0]);
      std::wstring::_Tidy_deallocate(v51);
      std::wstring::_Tidy_deallocate(v52);
      std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(v42);
      `Concurrency::streams::details::streambuf_state_manager<unsigned char>::close'::`1'::_lambda_1_::~_lambda_1_(v46);
      std::wstring::_Tidy_deallocate(v54);
      web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v56);
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\maarequestor.cpp",
      (const char *)0x80004001LL,
      v36[0]);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180153ad0  mov     [rsp+arg_18], rbx
0x180153ad5  push    rsi
0x180153ad6  push    rdi
0x180153ad7  push    r12
0x180153ad9  push    r14
0x180153adb  push    r15
0x180153add  sub     rsp, 500h
0x180153ae4  mov     rax, cs:__security_cookie
0x180153aeb  xor     rax, rsp
0x180153aee  mov     [rsp+528h+var_38], rax
0x180153af6  mov     r12, r8
0x180153af9  mov     r15, rdx
0x180153afc  mov     rdi, rcx
0x180153aff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180153b06  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180153b0b  test    al, al
0x180153b0d  jnz     short loc_180153B37
0x180153b0f  mov     rcx, [rsp+528h]; this
0x180153b17  mov     ebx, 80004001h
0x180153b1c  mov     r9d, ebx; char *
0x180153b1f  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180153b26  mov     edx, 209h; void *
0x180153b2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180153b30  mov     eax, ebx
0x180153b32  jmp     loc_18015468F
0x180153b37  lea     rcx, [rsp+528h+var_288]; this
0x180153b3f  call    ??0http_client_config@client@http@web@@QEAA@XZ; web::http::client::http_client_config::http_client_config(void)
0x180153b44  nop
0x180153b45  lea     rax, off_1802108C0
0x180153b4c  mov     [rsp+528h+var_368], rax
0x180153b54  lea     rax, [rsp+528h+var_368]
0x180153b5c  mov     [rsp+528h+var_330], rax
0x180153b64  lea     rdx, [rsp+528h+var_368]
0x180153b6c  lea     rcx, [rsp+528h+var_D8]
0x180153b74  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> const &)
0x180153b79  nop
0x180153b7a  lea     rcx, [rsp+528h+var_368]
0x180153b82  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180153b87  lea     rdx, [rdi+48h]
0x180153b8b  lea     rcx, [rsp+528h+var_2C8]
0x180153b93  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180153b98  nop
0x180153b99  lea     rcx, [rsp+528h+var_2C8]
0x180153ba1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180153ba6  mov     rdx, rax; unsigned __int16 *
0x180153ba9  lea     rcx, [rsp+528h+var_4B8]; this
0x180153bae  call    ??0uri@web@@QEAA@PEBG@Z; web::uri::uri(ushort const *)
0x180153bb3  nop
0x180153bb4  lea     r8, [rsp+528h+var_288]; struct web::http::client::http_client_config *
0x180153bbc  lea     rdx, [rsp+528h+var_4B8]; struct web::uri *
0x180153bc1  lea     rcx, [rsp+528h+var_390]; this
0x180153bc9  call    ??0http_client@client@http@web@@QEAA@AEBVuri@3@AEBVhttp_client_config@123@@Z; web::http::client::http_client::http_client(web::uri const &,web::http::client::http_client_config const &)
0x180153bce  nop
0x180153bcf  lea     rcx, [rsp+528h+var_4B8]; this
0x180153bd4  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x180153bd9  lea     rdx, ?POST@methods@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::methods::POST
0x180153be0  lea     rcx, [rsp+528h+var_500]
0x180153be5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180153bea  mov     rbx, rax
0x180153bed  mov     qword ptr [rsp+528h+var_508], rax
0x180153bf2  mov     rdx, rax
0x180153bf5  lea     rcx, [rsp+528h+var_3C0]
0x180153bfd  call    ??$make_shared@V_http_request@details@http@web@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@YA?AV?$shared_ptr@V_http_request@details@http@web@@@0@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::make_shared<web::http::details::_http_request,std::wstring>(std::wstring &&)
0x180153c02  nop
0x180153c03  mov     rcx, rbx
0x180153c06  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153c0b  nop
0x180153c0c  lea     rsi, [rdi+88h]
0x180153c13  mov     rbx, [rsp+528h+var_3C0]
0x180153c1b  cmp     qword ptr [rsi+10h], 0
0x180153c20  jz      short loc_180153C68
0x180153c22  mov     rcx, rsi
0x180153c25  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180153c2a  mov     qword ptr [rsp+528h+var_508], rax; int
0x180153c2f  lea     rdx, aXMsClientReque; "x-ms-client-request-id"
0x180153c36  lea     rcx, [rsp+528h+var_368]
0x180153c3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180153c43  nop
0x180153c44  lea     r8, [rsp+528h+var_508]
0x180153c49  lea     rdx, [rsp+528h+var_368]
0x180153c51  lea     rcx, [rbx+58h]
0x180153c55  call    ??$add@PEBG@http_headers@http@web@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEBG@Z; web::http::http_headers::add<ushort const *>(std::wstring const &,ushort const * const &)
0x180153c5a  nop
0x180153c5b  lea     rcx, [rsp+528h+var_368]
0x180153c63  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153c68  xorps   xmm0, xmm0
0x180153c6b  movups  [rsp+528h+var_308], xmm0
0x180153c73  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180153c7b  movdqu  [rsp+528h+var_2F8], xmm1
0x180153c84  xor     eax, eax
0x180153c86  mov     word ptr [rsp+528h+var_308], ax
0x180153c8e  cmp     [rdi+78h], rax
0x180153c92  jz      loc_180153D2A
0x180153c98  lea     rdx, aBearer_0; "bearer "
0x180153c9f  lea     rcx, [rsp+528h+var_500]
0x180153ca4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180153ca9  nop
0x180153caa  lea     r8, [rdi+68h]
0x180153cae  mov     rdx, rax
0x180153cb1  lea     rcx, [rsp+528h+var_368]
0x180153cb9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180153cbe  mov     rdx, rax
0x180153cc1  lea     rcx, [rsp+528h+var_308]
0x180153cc9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180153cce  lea     rcx, [rsp+528h+var_368]
0x180153cd6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153cdb  nop
0x180153cdc  lea     rcx, [rsp+528h+var_500]
0x180153ce1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153ce6  lea     rdx, aAuthorization; "authorization"
0x180153ced  lea     rcx, [rsp+528h+var_368]
0x180153cf5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180153cfa  nop
0x180153cfb  lea     r8, [rsp+528h+var_308]
0x180153d03  lea     rdx, [rsp+528h+var_368]
0x180153d0b  lea     rcx, [rbx+58h]
0x180153d0f  call    ??$add@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@http_headers@http@web@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; web::http::http_headers::add<std::wstring>(std::wstring const &,std::wstring const &)
0x180153d14  nop
0x180153d15  lea     rcx, [rsp+528h+var_368]
0x180153d1d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153d22  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180153d2a  xorps   xmm0, xmm0
0x180153d2d  movups  [rsp+528h+var_328], xmm0
0x180153d35  movdqu  [rsp+528h+var_318], xmm1
0x180153d3e  xor     eax, eax
0x180153d40  mov     word ptr [rsp+528h+var_328], ax
0x180153d48  lea     rdx, [rsp+528h+var_328]
0x180153d50  mov     rcx, r15
0x180153d53  call    ?ConvertByteArrayToUnicodeB64@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertByteArrayToUnicodeB64(std::vector<uchar> const &,std::wstring &)
0x180153d58  mov     ebx, eax
0x180153d5a  test    eax, eax
0x180153d5c  jns     short loc_180153DD5
0x180153d5e  mov     rcx, [rsp+528h]; this
0x180153d66  mov     r9d, eax; char *
0x180153d69  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180153d70  mov     edx, 22Ch; void *
0x180153d75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180153d7a  nop
0x180153d7b  lea     rcx, [rsp+528h+var_328]
0x180153d83  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153d88  nop
0x180153d89  lea     rcx, [rsp+528h+var_308]
0x180153d91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153d96  nop
0x180153d97  lea     rcx, [rsp+528h+var_3C0]
0x180153d9f  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180153da4  nop
0x180153da5  lea     rcx, [rsp+528h+var_390]
0x180153dad  call    ??1_lambda_1_@?0??close@?$streambuf_state_manager@E@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@H@Z@QEAA@XZ; `Concurrency::streams::details::streambuf_state_manager<uchar>::close(int)'::`1'::_lambda_1_::~_lambda_1_(void)
0x180153db2  nop
0x180153db3  lea     rcx, [rsp+528h+var_2C8]
0x180153dbb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153dc0  nop
0x180153dc1  lea     rcx, [rsp+528h+var_288]; this
0x180153dc9  call    ??1http_client_config@client@http@web@@QEAA@XZ; web::http::client::http_client_config::~http_client_config(void)
0x180153dce  mov     eax, ebx
0x180153dd0  jmp     loc_18015468F
0x180153dd5  xorps   xmm0, xmm0
0x180153dd8  movups  [rsp+528h+var_2E8], xmm0
0x180153de0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180153de8  movdqu  [rsp+528h+var_2D8], xmm1
0x180153df1  xor     eax, eax
0x180153df3  mov     word ptr [rsp+528h+var_2E8], ax
0x180153dfb  lea     rdx, [rsp+528h+var_2E8]
0x180153e03  lea     rcx, [rsp+528h+var_328]
0x180153e0b  call    ?ConvertToUriSafeB64@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::ConvertToUriSafeB64(std::wstring const &,std::wstring &)
0x180153e10  mov     ebx, eax
0x180153e12  test    eax, eax
0x180153e14  jns     loc_180153E9F
0x180153e1a  mov     rcx, [rsp+528h]; this
0x180153e22  mov     r9d, eax; char *
0x180153e25  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x180153e2c  mov     edx, 22Eh; void *
0x180153e31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180153e36  nop
0x180153e37  lea     rcx, [rsp+528h+var_2E8]
0x180153e3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153e44  nop
0x180153e45  lea     rcx, [rsp+528h+var_328]
0x180153e4d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153e52  nop
0x180153e53  lea     rcx, [rsp+528h+var_308]
0x180153e5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153e60  nop
0x180153e61  lea     rcx, [rsp+528h+var_3C0]
0x180153e69  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180153e6e  nop
0x180153e6f  lea     rcx, [rsp+528h+var_390]
0x180153e77  call    ??1_lambda_1_@?0??close@?$streambuf_state_manager@E@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@H@Z@QEAA@XZ; `Concurrency::streams::details::streambuf_state_manager<uchar>::close(int)'::`1'::_lambda_1_::~_lambda_1_(void)
0x180153e7c  nop
0x180153e7d  lea     rcx, [rsp+528h+var_2C8]
0x180153e85  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153e8a  nop
0x180153e8b  lea     rcx, [rsp+528h+var_288]; this
0x180153e93  call    ??1http_client_config@client@http@web@@QEAA@XZ; web::http::client::http_client_config::~http_client_config(void)
0x180153e98  mov     eax, ebx
0x180153e9a  jmp     loc_18015468F
0x180153e9f  xor     edx, edx
0x180153ea1  lea     rcx, [rsp+528h+var_3C8]
0x180153ea9  call    ?object@value@json@web@@SA?AV123@_N@Z; web::json::value::object(bool)
0x180153eae  nop
0x180153eaf  lea     rdx, [rsp+528h+var_2E8]
0x180153eb7  lea     rcx, [rsp+528h+var_500]
0x180153ebc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180153ec1  mov     rdx, rax
0x180153ec4  lea     rcx, [rsp+528h+var_508]
0x180153ec9  call    ?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::string(std::wstring)
0x180153ece  mov     rbx, rax
0x180153ed1  lea     rdx, aData_0; "data"
0x180153ed8  lea     rcx, [rsp+528h+var_368]
0x180153ee0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180153ee5  nop
0x180153ee6  lea     rdx, [rsp+528h+var_368]
0x180153eee  lea     rcx, [rsp+528h+var_3C8]
0x180153ef6  call    ??Avalue@json@web@@QEAAAEAV012@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::operator[](std::wstring const &)
0x180153efb  mov     rdx, rbx
0x180153efe  mov     rcx, rax
0x180153f01  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180153f06  nop
0x180153f07  lea     rcx, [rsp+528h+var_368]
0x180153f0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180153f14  nop
0x180153f15  lea     rcx, [rsp+528h+var_508]
0x180153f1a  call    ??1?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@QEAA@XZ; std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(void)
0x180153f1f  lea     rdx, [rsp+528h+var_3C8]; struct web::json::value *
0x180153f27  lea     rcx, [rsp+528h+var_3C0]; this
0x180153f2f  call    ?set_body@http_request@http@web@@QEAAXAEBVvalue@json@3@@Z; web::http::http_request::set_body(web::json::value const &)
0x180153f34  mov     qword ptr [rsp+528h+var_508], 0; int
0x180153f3d  lea     rdx, [rsp+528h+var_3C0]
0x180153f45  lea     rcx, [rsp+528h+var_4E0]
0x180153f4a  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x180153f4f  lea     r9, [rsp+528h+var_508]
0x180153f54  lea     r8, [rsp+528h+var_4E0]
0x180153f59  lea     rdx, [rsp+528h+var_4D0]
0x180153f5e  lea     rcx, [rsp+528h+var_390]
0x180153f66  call    ?request@http_client@client@http@web@@QEAA?AV?$task@Vhttp_response@http@web@@@pplx@@Vhttp_request@34@AEBVcancellation_token@6@@Z; web::http::client::http_client::request(web::http::http_request,pplx::cancellation_token const &)
0x180153f6b  nop
0x180153f6c  lea     rdx, [rsp+528h+var_3B0]
0x180153f74  mov     rcx, rax
0x180153f77  call    ?get@?$task@Vhttp_response@http@web@@@pplx@@QEBA?AVhttp_response@http@web@@XZ; pplx::task<web::http::http_response>::get(void)
0x180153f7c  nop
0x180153f7d  lea     rcx, [rsp+528h+var_4D0]
0x180153f82  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180153f87  nop
0x180153f88  lea     rcx, [rsp+528h+var_508]; this
0x180153f8d  call    ?_Clear@cancellation_token_registration@pplx@@AEAAXXZ; pplx::cancellation_token_registration::_Clear(void)
0x180153f92  nop
0x180153f93  lea     rdx, [rsp+528h+var_368]
0x180153f9b  lea     rcx, [rsp+528h+var_3B0]
0x180153fa3  call    ?content_ready@http_response@http@web@@QEBA?AV?$task@Vhttp_response@http@web@@@pplx@@XZ; web::http::http_response::content_ready(void)
0x180153fa8  nop
0x180153fa9  lea     rdx, [rsp+528h+var_500]
0x180153fae  mov     rcx, rax
0x180153fb1  call    ?get@?$task@Vhttp_response@http@web@@@pplx@@QEBA?AVhttp_response@http@web@@XZ; pplx::task<web::http::http_response>::get(void)
0x180153fb6  lea     rcx, [rsp+528h+var_500]
0x180153fbb  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180153fc0  nop
0x180153fc1  lea     rcx, [rsp+528h+var_368]
0x180153fc9  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180153fce  mov     rax, [rsp+528h+var_3B0]
0x180153fd6  movzx   r15d, word ptr [rax+88h]
0x180153fde  mov     eax, 0C8h
0x180153fe3  lea     rcx, [rsp+528h+var_3B0]
0x180153feb  cmp     r15w, ax
0x180153fef  jz      loc_180154232
0x180153ff5  lea     r14, [rdi+0C8h]
0x180153ffc  lea     rdx, [rdi+0A8h]
0x180154003  mov     r9, rsi
0x180154006  mov     r8, r14
0x180154009  call    ?ExtractErrorDetails@Core@Autopilot@ModernDeployment@@YAJAEBVhttp_response@http@web@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; ModernDeployment::Autopilot::Core::ExtractErrorDetails(web::http::http_response const &,std::wstring &,std::wstring &,std::wstring &)
0x18015400e  mov     ebx, eax
0x180154010  test    eax, eax
0x180154012  jns     loc_1801540B9
0x180154018  mov     rcx, [rsp+528h]; this
0x180154020  mov     r9d, eax; char *
0x180154023  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015402a  mov     edx, 23Dh; void *
0x18015402f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154034  nop
0x180154035  lea     rcx, [rsp+528h+var_3B0]
0x18015403d  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180154042  nop
0x180154043  lea     rcx, [rsp+528h+var_3C8]
0x18015404b  call    ??1?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@QEAA@XZ; std::unique_ptr<web::json::details::_Value>::~unique_ptr<web::json::details::_Value>(void)
0x180154050  nop
0x180154051  lea     rcx, [rsp+528h+var_2E8]
0x180154059  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015405e  nop
0x18015405f  lea     rcx, [rsp+528h+var_328]
0x180154067  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015406c  nop
0x18015406d  lea     rcx, [rsp+528h+var_308]
0x180154075  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015407a  nop
0x18015407b  lea     rcx, [rsp+528h+var_3C0]
0x180154083  call    ??1?$shared_ptr@V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>::~shared_ptr<std::vector<std::pair<std::wstring,std::wstring>>>(void)
0x180154088  nop
0x180154089  lea     rcx, [rsp+528h+var_390]
0x180154091  call    ??1_lambda_1_@?0??close@?$streambuf_state_manager@E@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@H@Z@QEAA@XZ; `Concurrency::streams::details::streambuf_state_manager<uchar>::close(int)'::`1'::_lambda_1_::~_lambda_1_(void)
0x180154096  nop
  ... truncated ...
```
