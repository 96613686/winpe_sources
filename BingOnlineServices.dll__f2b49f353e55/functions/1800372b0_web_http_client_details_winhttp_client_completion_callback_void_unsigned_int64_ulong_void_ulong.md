# web::http::client::details::winhttp_client::completion_callback(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x1800372b0`
- end: `0x180037d25`
- name: `?completion_callback@winhttp_client@details@client@http@web@@CAXPEAX_KK0K@Z`
- size: `2677`
- prototype: `void __stdcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, LPVOID lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `37`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002c2c`
- `0x180002ca8`
- `0x180004fa0`
- `0x180005e6c`
- `0x180007330`
- `0x1800086b0`
- `0x180009698`
- `0x18000979c`
- `0x18000e5a8`
- `0x18000eca4`
- `0x18000fa74`
- `0x180012430`
- `0x1800148ac`
- `0x18001ad68`
- `0x18001f380`
- `0x180025488`
- `0x18002bd70`
- `0x18002c7f0`
- `0x18002f2a0`
- `0x18002fe40`
- `0x180033014`
- `0x1800337f0`
- `0x180034984`
- `0x180036144`
- `0x1800362a8`
- `0x180036860`
- `0x180036a50`
- `0x180036bf0`
- `0x180036cdc`
- `0x180037214`
- `0x1800372b0`
- `0x180038250`
- `0x180038f58`
- `0x180039418`
- `0x1800395a0`
- `0x18003a10c`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003772a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003772a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b6c`
- `WINHTTP!WinHttpQueryHeaders` at `0x180037adb`
- `WINHTTP!WinHttpQueryHeaders` at `0x180037b62`
- `WINHTTP!WinHttpQueryHeaders` at `0x180037adb`
- `WINHTTP!WinHttpQueryHeaders` at `0x180037b62`
- `WINHTTP!WinHttpQueryOption` at `0x180037870`
- `WINHTTP!WinHttpQueryOption` at `0x180037870`
- `WINHTTP!WinHttpReadData` at `0x180037720`
- `WINHTTP!WinHttpReadData` at `0x180037720`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800373e2`
- `WINHTTP!WinHttpReceiveResponse` at `0x18003756a`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800373e2`
- `WINHTTP!WinHttpReceiveResponse` at `0x18003756a`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800379bb`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800379bb`
- `CRYPT32!CertFreeCertificateChain` at `0x180037a8d`
- `CRYPT32!CertFreeCertificateChain` at `0x180037a8d`
- `CRYPT32!CertFreeCertificateContext` at `0x180037aa5`
- `CRYPT32!CertFreeCertificateContext` at `0x180037aa5`
- `CRYPT32!CertGetCertificateChain` at `0x180037927`
- `CRYPT32!CertGetCertificateChain` at `0x180037927`

## string_xrefs

- `0x180037732`: `WinHttpReadData`
- `0x180037931`: `Failed to create certificate chain.`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall web::http::client::details::winhttp_client::completion_callback(
        HINTERNET hInternet,
        DWORD_PTR dwContext,
        DWORD dwInternetStatus,
        DWORD *lpvStatusInformation,
        DWORD dwStatusInformationLength)
{
  char v8; // bl
  DWORD v9; // ebx
  __int64 v10; // r8
  struct _CERT_CHAIN_PARA *p_hRequest; // rcx
  unsigned int v12; // r15d
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  DWORD v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rax
  DWORD v21; // r15d
  __int64 v22; // rax
  __int64 *v23; // rbx
  void *v24; // rdx
  DWORD v25; // ebx
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // r8
  __int64 v29; // r8
  int v30; // ebx
  __int64 v31; // r8
  char *v32; // r15
  char *v33; // rax
  size_t v34; // rbx
  DWORD LastError; // ebx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r10
  __int64 v40; // rdi
  void (__fastcall *v41)(__int64, __int64); // rbx
  __int64 v42; // rax
  __int64 v43; // rdi
  __int64 v44; // rax
  __int64 v45; // rdi
  __int64 v46; // rax
  __int64 v47; // rdi
  __int64 v48; // rax
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+40h] [rbp-308h] BYREF
  PCCERT_CONTEXT Buffer[2]; // [rsp+50h] [rbp-2F8h] BYREF
  void *lpBuffer[2]; // [rsp+60h] [rbp-2E8h] BYREF
  __int64 v52; // [rsp+70h] [rbp-2D8h]
  DWORD v53; // [rsp+78h] [rbp-2D0h] BYREF
  DWORD dwBufferLength[2]; // [rsp+80h] [rbp-2C8h] BYREF
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+88h] [rbp-2C0h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+A0h] [rbp-2A8h] BYREF
  std::_Ref_count_base *v57; // [rsp+A8h] [rbp-2A0h]
  _BYTE v58[32]; // [rsp+B0h] [rbp-298h] BYREF
  struct _CERT_CHAIN_PARA hRequest; // [rsp+D0h] [rbp-278h] BYREF
  _BYTE v60[32]; // [rsp+F0h] [rbp-258h] BYREF
  _BYTE v61[512]; // [rsp+110h] [rbp-238h] BYREF

  if ( dwInternetStatus == 2048 )
    return;
  *(_QWORD *)dwBufferLength = dwContext;
  if ( !dwContext )
    return;
  switch ( dwInternetStatus )
  {
    case 0x20000u:
      web::http::client::http_client_config::http_client_config(
        (web::http::client::http_client_config *)v61,
        (const struct web::http::client::http_client_config *)(*(_QWORD *)(dwContext + 8) + 240LL));
      if ( !v61[424] )
        goto LABEL_76;
      Buffer[0] = 0;
      dwBufferLength[0] = 8;
      memset(&hRequest, 0, sizeof(hRequest));
      pPolicyPara = 0;
      memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
      pChainContext = 0;
      if ( WinHttpQueryOption(hInternet, 0x4Eu, Buffer, dwBufferLength) )
      {
        memset(&hRequest, 0, sizeof(hRequest));
        hRequest.cbSize = 32;
        hRequest.RequestedUsage.dwType = 0;
        if ( CertGetCertificateChain(0, Buffer[0], 0, Buffer[0]->hCertStore, &hRequest, 0x20000001u, 0, &pChainContext) )
        {
          pPolicyPara.cbSize = 16;
          pPolicyPara.dwFlags |= 0x20000u;
          pPolicyPara.pvExtraPolicyPara = 0;
          pPolicyStatus.cbSize = 24;
          if ( CertVerifyCertificateChainPolicy((LPCSTR)7, pChainContext, &pPolicyPara, &pPolicyStatus) )
          {
            v30 = 0;
            if ( !pPolicyStatus.dwError )
              goto LABEL_71;
            std::string::string(v58, "Certificate root failed validation.");
            v31 = web::http::client::details::build_error_msg(v60, 12157, v58);
            web::http::client::details::request_context::report_error(dwContext, 12157, v31);
            std::string::_Tidy_deallocate(v60);
          }
          else
          {
            std::string::string(v58, "Could not verify certificate root");
            v29 = web::http::client::details::build_error_msg(v60, 12157, v58);
            web::http::client::details::request_context::report_error(dwContext, 12157, v29);
            std::string::_Tidy_deallocate(v60);
          }
        }
        else
        {
          std::string::string(v58, "Failed to create certificate chain.");
          v28 = web::http::client::details::build_error_msg(v60, 12157, v58);
          web::http::client::details::request_context::report_error(dwContext, 12157, v28);
          std::string::_Tidy_deallocate(v60);
        }
      }
      else
      {
        std::string::string(v58, "Failed to extract certificate.");
        v27 = web::http::client::details::build_error_msg(v60, 12157, v58);
        web::http::client::details::request_context::report_error(dwContext, 12157, v27);
        std::string::_Tidy_deallocate(v60);
      }
      std::string::_Tidy_deallocate(v58);
      v30 = 1;
LABEL_71:
      if ( pChainContext )
      {
        CertFreeCertificateChain(pChainContext);
        pChainContext = 0;
      }
      if ( Buffer[0] )
      {
        CertFreeCertificateContext(Buffer[0]);
        Buffer[0] = 0;
      }
      if ( v30 )
        goto LABEL_93;
LABEL_76:
      v53 = 0;
      WinHttpQueryHeaders(hInternet, 0x16u, 0, 0, &v53, 0);
      std::vector<std::shared_ptr<pplx::details::_Task_impl<unsigned char>>>::vector<std::shared_ptr<pplx::details::_Task_impl<unsigned char>>>(lpBuffer);
      v32 = (char *)lpBuffer[1];
      if ( (void *)v53 < (void *)((char *)lpBuffer[1] - (char *)lpBuffer[0]) )
      {
        v33 = (char *)lpBuffer[0] + v53;
LABEL_82:
        lpBuffer[1] = v33;
        goto LABEL_83;
      }
      if ( (void *)v53 > (void *)((char *)lpBuffer[1] - (char *)lpBuffer[0]) )
      {
        if ( v53 <= v52 - (unsigned __int64)lpBuffer[0] )
        {
          v34 = v53 - (unsigned __int64)((char *)lpBuffer[1] - (char *)lpBuffer[0]);
          memset_0(lpBuffer[1], 0, v34);
          v33 = &v32[v34];
          goto LABEL_82;
        }
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpBuffer, v53);
      }
LABEL_83:
      if ( WinHttpQueryHeaders(hInternet, 0x16u, 0, lpBuffer[0], &v53, 0) )
      {
        web::http::client::details::parse_winhttp_headers(hInternet);
        if ( *(_WORD *)(*(_QWORD *)(dwContext + 40) + 88LL) != 401
          && *(_WORD *)(*(_QWORD *)(dwContext + 40) + 88LL) != 407
          || !web::http::client::details::winhttp_client::handle_authentication_failure(
                hInternet,
                (struct web::http::client::details::winhttp_request_context *)dwContext,
                0) )
        {
          std::wstring::wstring(v58, L"application/octet-stream");
          pPolicyPara = 0;
          web::http::details::http_msg_base::set_body(*(_QWORD *)(dwContext + 24), &pPolicyPara, v58);
          std::wstring::_Tidy_deallocate(v58);
          std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(
            &pPolicyPara,
            (_QWORD *)(dwContext + 40));
          pplx::task_completion_event<web::http::http_response>::set(dwContext + 72, &pPolicyPara);
          std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*(_QWORD *)(dwContext + 24) + 96LL);
          v37 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(web::http::methods::HEAD);
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                  v39,
                                  *(_QWORD *)(v38 + 112),
                                  v37,
                                  qword_18009BB08) )
          {
            web::http::client::details::memory_holder::allocate_space(
              (web::http::client::details::memory_holder *)(dwContext + 168),
              0);
            web::http::client::details::request_context::complete_request(
              (web::http::client::details::request_context *)dwContext,
              0);
          }
          else
          {
            web::http::client::details::winhttp_client::read_next_response_chunk(
              (struct web::http::client::details::winhttp_request_context *)dwContext,
              0,
              1);
          }
        }
      }
      else
      {
        LastError = GetLastError();
        std::string::string(v58, "WinHttpQueryHeaders");
        v36 = web::http::client::details::build_error_msg(v60, LastError, v58);
        web::http::client::details::request_context::report_error(dwContext, LastError, v36);
        std::string::_Tidy_deallocate(v60);
        std::string::_Tidy_deallocate(v58);
      }
      if ( lpBuffer[0] )
      {
        std::_Deallocate<16>(lpBuffer[0], v52 - (unsigned __int64)lpBuffer[0]);
        v52 = 0;
        *(_OWORD *)lpBuffer = 0;
      }
LABEL_93:
      web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v61);
      return;
    case 0x40000u:
      v21 = *lpvStatusInformation;
      if ( *lpvStatusInformation )
      {
        web::http::client::details::request_context::_get_writebuffer(dwContext, &pPolicyStatus);
        v22 = Concurrency::streams::streambuf<unsigned char>::alloc(&pPolicyStatus, v21);
        v23 = (__int64 *)(dwContext + 168);
        if ( v22 )
          *v23 = v22;
        else
          web::http::client::details::memory_holder::allocate_space(
            (web::http::client::details::memory_holder *)(dwContext + 168),
            v21);
        v24 = (void *)*v23;
        if ( !*v23 )
          v24 = *(void **)(dwContext + 176);
        if ( !WinHttpReadData(hInternet, v24, v21, 0) )
        {
          v25 = GetLastError();
          std::string::string(&hRequest, "WinHttpReadData");
          v26 = web::http::client::details::build_error_msg(v58, v25, &hRequest);
          web::http::client::details::request_context::report_error(dwContext, v25, v26);
          std::string::_Tidy_deallocate(v58);
          std::string::_Tidy_deallocate(&hRequest);
        }
        Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(&pPolicyStatus);
        return;
      }
      std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(
        &pPolicyPara,
        (_QWORD *)(*(_QWORD *)(dwContext + 24) + 664LL));
      if ( *(_QWORD *)&pPolicyPara.cbSize )
      {
        try
        {
          std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(
            *(_QWORD *)&pPolicyPara.cbSize,
            1,
            *(_QWORD *)(dwContext + 64));
        }
        catch ( ... )
        {
          v45 = *(_QWORD *)dwBufferLength;
          v46 = std::current_exception(Buffer);
          guard_dispatch_icall_thunk_10345483385596137414(v45, v46);
          goto LABEL_59;
        }
      }
      goto LABEL_58;
    case 0x80000u:
      std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(
        &pPolicyPara,
        (_QWORD *)(*(_QWORD *)(dwContext + 24) + 664LL));
      *(_QWORD *)(dwContext + 64) += dwStatusInformationLength;
      if ( *(_QWORD *)&pPolicyPara.cbSize )
      {
        try
        {
          std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(
            *(_QWORD *)&pPolicyPara.cbSize,
            1,
            *(_QWORD *)(dwContext + 64));
        }
        catch ( ... )
        {
          v47 = *(_QWORD *)dwBufferLength;
          v48 = std::current_exception(Buffer);
          guard_dispatch_icall_thunk_10345483385596137414(v47, v48);
          goto LABEL_59;
        }
      }
      if ( dwStatusInformationLength )
      {
        web::http::client::details::request_context::_get_writebuffer(dwContext, lpBuffer);
        if ( *(_QWORD *)(dwContext + 168) )
        {
          Concurrency::streams::streambuf<char>::commit(lpBuffer, dwStatusInformationLength);
          web::http::client::details::winhttp_client::read_next_response_chunk(
            (struct web::http::client::details::winhttp_request_context *)dwContext,
            dwStatusInformationLength,
            0);
        }
        else
        {
          v20 = Concurrency::streams::streambuf<unsigned char>::putn_nocopy(
                  lpBuffer,
                  &pChainContext,
                  *(_QWORD *)(dwContext + 176),
                  dwStatusInformationLength);
          *(_QWORD *)&pPolicyStatus.cbSize = hInternet;
          *(_QWORD *)&pPolicyStatus.lChainIndex = dwContext;
          LODWORD(pPolicyStatus.pvExtraPolicyStatus) = dwStatusInformationLength;
          pplx::task<unsigned __int64>::then<_lambda_9136b9a94d0d5493aaa0ceb9af684f74_>(v20, Buffer, &pPolicyStatus);
          pplx::task<long>::~task<long>(Buffer);
          if ( v57 )
            std::_Ref_count_base::_Decref(v57);
        }
        Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(lpBuffer);
        goto LABEL_59;
      }
LABEL_58:
      web::http::client::details::request_context::complete_request(
        (web::http::client::details::request_context *)dwContext,
        *(_QWORD *)(dwContext + 64));
LABEL_59:
      if ( pPolicyPara.pvExtraPolicyPara )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)pPolicyPara.pvExtraPolicyPara);
      return;
    case 0x100000u:
      v14 = *lpvStatusInformation;
      if ( (_DWORD)v14 )
      {
        std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(
          &pPolicyPara,
          (_QWORD *)(*(_QWORD *)(dwContext + 24) + 664LL));
        v15 = *(_QWORD *)&pPolicyPara.cbSize;
        if ( *(_QWORD *)&pPolicyPara.cbSize )
        {
          try
          {
            *(_QWORD *)(dwContext + 56) += v14;
            std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(
              v15,
              0,
              *(_QWORD *)(dwContext + 56));
          }
          catch ( ... )
          {
            v43 = *(_QWORD *)dwBufferLength;
            v44 = std::current_exception(Buffer);
            guard_dispatch_icall_thunk_10345483385596137414(v43, v44);
            goto LABEL_59;
          }
        }
        if ( pPolicyPara.pvExtraPolicyPara )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)pPolicyPara.pvExtraPolicyPara);
      }
      if ( *(_QWORD *)(dwContext + 168) )
      {
        v16 = (*(__int64 (__fastcall **)(DWORD_PTR, _CERT_CHAIN_POLICY_STATUS *))(*(_QWORD *)dwContext + 16LL))(
                dwContext,
                &pPolicyStatus);
        v17 = *(_QWORD *)(dwContext + 168);
        if ( !v17 )
          v17 = *(_QWORD *)(dwContext + 176);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v16 + 248LL))(v16, v17, v14);
        Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(&pPolicyStatus);
      }
      if ( *(_DWORD *)(dwContext + 108) == 2 )
        goto LABEL_36;
      if ( *(_DWORD *)(dwContext + 108) == 1 )
      {
LABEL_38:
        web::http::client::details::winhttp_client::_multiple_segment_write_data((struct web::http::client::details::winhttp_request_context *)dwContext);
        return;
      }
      if ( !WinHttpReceiveResponse(hInternet, 0) )
      {
        v18 = GetLastError();
        std::string::string(&hRequest, "WinHttpReceiveResponse");
        v19 = web::http::client::details::build_error_msg(v58, v18, &hRequest);
        web::http::client::details::request_context::report_error(dwContext, v18, v19);
        std::string::_Tidy_deallocate(v58);
LABEL_22:
        p_hRequest = &hRequest;
LABEL_26:
        std::string::_Tidy_deallocate(p_hRequest);
      }
      break;
    case 0x200000u:
      v12 = lpvStatusInformation[2];
      if ( v12 != 12032
        || !web::http::client::details::winhttp_client::handle_authentication_failure(
              hInternet,
              (struct web::http::client::details::winhttp_request_context *)dwContext,
              0x2F00u) )
      {
        v13 = web::http::client::details::build_error_msg_0(v58, lpvStatusInformation);
        web::http::client::details::request_context::report_error(dwContext, v12, v13);
        p_hRequest = (struct _CERT_CHAIN_PARA *)v58;
        goto LABEL_26;
      }
      break;
    case 0x400000u:
      std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(
        &pPolicyPara,
        (_QWORD *)(*(_QWORD *)(dwContext + 24) + 8LL));
      if ( !*(_QWORD *)&pPolicyPara.cbSize || (v8 = 1, !*(_QWORD *)(*(_QWORD *)&pPolicyPara.cbSize + 8LL)) )
        v8 = 0;
      if ( pPolicyPara.pvExtraPolicyPara )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)pPolicyPara.pvExtraPolicyPara);
      if ( !v8 )
      {
        std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(
          &pPolicyPara,
          (_QWORD *)(*(_QWORD *)(dwContext + 24) + 664LL));
        if ( *(_QWORD *)&pPolicyPara.cbSize )
        {
          try
          {
            std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(
              *(_QWORD *)&pPolicyPara.cbSize,
              0,
              0);
          }
          catch ( ... )
          {
            v40 = *(_QWORD *)dwBufferLength;
            v41 = *(void (__fastcall **)(__int64, __int64))(**(_QWORD **)dwBufferLength + 8LL);
            v42 = std::current_exception(Buffer);
            v41(v40, v42);
            goto LABEL_59;
          }
        }
        if ( pPolicyPara.pvExtraPolicyPara )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)pPolicyPara.pvExtraPolicyPara);
      }
      if ( *(_DWORD *)(dwContext + 108) != 2 )
      {
        if ( *(_DWORD *)(dwContext + 108) != 1 )
        {
          if ( WinHttpReceiveResponse(hInternet, 0) )
            return;
          v9 = GetLastError();
          std::string::string(&hRequest, "WinHttpReceiveResponse");
          v10 = web::http::client::details::build_error_msg(v58, v9, &hRequest);
          web::http::client::details::request_context::report_error(dwContext, v9, v10);
          std::string::_Tidy_deallocate(v58);
          goto LABEL_22;
        }
        goto LABEL_38;
      }
LABEL_36:
      web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data((struct web::http::client::details::winhttp_request_context *)dwContext);
      return;
    default:
      return;
  }
}

```

## disassembly

```asm
0x1800372b0  cmp     r8d, 800h
0x1800372b7  jz      locret_180037D24
0x1800372bd  mov     [rsp+arg_10], rbx
0x1800372c2  push    rsi
0x1800372c3  push    rdi
0x1800372c4  push    r12
0x1800372c6  push    r14
0x1800372c8  push    r15
0x1800372ca  sub     rsp, 320h
0x1800372d1  mov     rax, cs:__security_cookie
0x1800372d8  xor     rax, rsp
0x1800372db  mov     [rsp+348h+var_38], rax
0x1800372e3  mov     rbx, r9
0x1800372e6  mov     rsi, rdx
0x1800372e9  mov     r14, rcx
0x1800372ec  mov     qword ptr [rsp+348h+dwBufferLength], rdx
0x1800372f4  xor     edi, edi
0x1800372f6  test    rdx, rdx
0x1800372f9  jz      loc_180037CFD
0x1800372ff  mov     r15d, 20000h
0x180037305  cmp     r8d, r15d
0x180037308  jz      loc_1800377F1
0x18003730e  cmp     r8d, 40000h
0x180037315  jz      loc_1800376C2
0x18003731b  cmp     r8d, 80000h
0x180037322  jz      loc_1800375CE
0x180037328  cmp     r8d, 100000h
0x18003732f  jz      loc_180037499
0x180037335  cmp     r8d, 200000h
0x18003733c  jz      loc_18003744B
0x180037342  cmp     r8d, 400000h
0x180037349  jnz     loc_180037CFD
0x18003734f  mov     rdx, [rdx+18h]
0x180037353  add     rdx, 8
0x180037357  lea     rcx, [rsp+348h+pPolicyPara]
0x18003735c  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x180037361  mov     rcx, qword ptr [rsp+348h+pPolicyPara.cbSize]
0x180037366  test    rcx, rcx
0x180037369  jz      short loc_180037373
0x18003736b  cmp     [rcx+8], rdi
0x18003736f  mov     bl, 1
0x180037371  jnz     short loc_180037376
0x180037373  mov     bl, dil
0x180037376  mov     rcx, [rsp+348h+pPolicyPara.pvExtraPolicyPara]; this
0x18003737b  test    rcx, rcx
0x18003737e  jz      short loc_180037385
0x180037380  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037385  test    bl, bl
0x180037387  jnz     short loc_1800373C9
0x180037389  mov     rdx, [rsi+18h]
0x18003738d  add     rdx, 298h
0x180037394  lea     rcx, [rsp+348h+pPolicyPara]
0x180037399  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x18003739e  nop
0x18003739f  mov     rcx, qword ptr [rsp+348h+pPolicyPara.cbSize]
0x1800373a4  test    rcx, rcx
0x1800373a7  jz      short loc_1800373BA
0x1800373a9  xor     r8d, r8d
0x1800373ac  xor     edx, edx
0x1800373ae  call    ??R?$_Func_class@XW4direction@message_direction@http@web@@_K@std@@QEBAXW4direction@message_direction@http@web@@_K@Z; std::_Func_class<void,web::http::message_direction::direction,unsigned __int64>::operator()(web::http::message_direction::direction,unsigned __int64)
0x1800373b3  jmp     short loc_1800373BA
0x1800373b5  jmp     loc_1800377D7
0x1800373ba  mov     rcx, [rsp+348h+pPolicyPara.pvExtraPolicyPara]; this
0x1800373bf  test    rcx, rcx
0x1800373c2  jz      short loc_1800373C9
0x1800373c4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800373c9  cmp     dword ptr [rsi+6Ch], 2
0x1800373cd  jz      loc_180037545
0x1800373d3  cmp     dword ptr [rsi+6Ch], 1
0x1800373d7  jz      loc_180037558
0x1800373dd  xor     edx, edx; lpReserved
0x1800373df  mov     rcx, r14; hRequest
0x1800373e2  call    cs:__imp_WinHttpReceiveResponse
0x1800373e8  test    eax, eax
0x1800373ea  jnz     loc_180037CFD
0x1800373f0  call    cs:__imp_GetLastError
0x1800373f6  mov     ebx, eax
0x1800373f8  lea     rdx, aWinhttpreceive; "WinHttpReceiveResponse"
0x1800373ff  lea     rcx, [rsp+348h+hRequest]
0x180037407  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003740c  nop
0x18003740d  lea     r8, [rsp+348h+hRequest]
0x180037415  mov     edx, ebx
0x180037417  lea     rcx, [rsp+348h+var_298]
0x18003741f  call    web__http__client__details__build_error_msg
0x180037424  nop
0x180037425  mov     r8, rax
0x180037428  mov     edx, ebx
0x18003742a  mov     rcx, rsi
0x18003742d  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180037432  nop
0x180037433  lea     rcx, [rsp+348h+var_298]
0x18003743b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180037440  nop
0x180037441  lea     rcx, [rsp+348h+hRequest]; hRequest
0x180037449  jmp     short loc_18003748F
0x18003744b  mov     r15d, [r9+8]
0x18003744f  mov     r8d, 2F00h; unsigned int
0x180037455  cmp     r15d, r8d
0x180037458  jnz     short loc_180037467
0x18003745a  call    ?handle_authentication_failure@winhttp_client@details@client@http@web@@CA_NPEAXPEAVwinhttp_request_context@2345@K@Z; web::http::client::details::winhttp_client::handle_authentication_failure(void *,web::http::client::details::winhttp_request_context *,ulong)
0x18003745f  test    al, al
0x180037461  jnz     loc_180037CFD
0x180037467  mov     rdx, rbx
0x18003746a  lea     rcx, [rsp+348h+var_298]
0x180037472  call    web__http__client__details__build_error_msg_0
0x180037477  nop
0x180037478  mov     r8, rax
0x18003747b  mov     edx, r15d
0x18003747e  mov     rcx, rsi
0x180037481  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180037486  nop
0x180037487  lea     rcx, [rsp+348h+var_298]
0x18003748f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180037494  jmp     loc_180037CFD
0x180037499  mov     ebx, [r9]
0x18003749c  test    ebx, ebx
0x18003749e  jz      short loc_1800374E5
0x1800374a0  mov     rdx, [rdx+18h]
0x1800374a4  add     rdx, 298h
0x1800374ab  lea     rcx, [rsp+348h+pPolicyPara]
0x1800374b0  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x1800374b5  nop
0x1800374b6  mov     rcx, qword ptr [rsp+348h+pPolicyPara.cbSize]
0x1800374bb  test    rcx, rcx
0x1800374be  jz      short loc_1800374D6
0x1800374c0  add     [rsi+38h], rbx
0x1800374c4  mov     r8, [rsi+38h]
0x1800374c8  xor     edx, edx
0x1800374ca  call    ??R?$_Func_class@XW4direction@message_direction@http@web@@_K@std@@QEBAXW4direction@message_direction@http@web@@_K@Z; std::_Func_class<void,web::http::message_direction::direction,unsigned __int64>::operator()(web::http::message_direction::direction,unsigned __int64)
0x1800374cf  jmp     short loc_1800374D6
0x1800374d1  jmp     loc_1800377D7
0x1800374d6  mov     rcx, [rsp+348h+pPolicyPara.pvExtraPolicyPara]; this
0x1800374db  test    rcx, rcx
0x1800374de  jz      short loc_1800374E5
0x1800374e0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800374e5  cmp     [rsi+0A8h], rdi
0x1800374ec  jz      short loc_18003753F
0x1800374ee  mov     rax, [rsi]
0x1800374f1  lea     rdx, [rsp+348h+pPolicyStatus]
0x1800374f9  mov     rcx, rsi
0x1800374fc  mov     rax, [rax+10h]
0x180037500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037505  nop
0x180037506  mov     rcx, [rax]
0x180037509  mov     r9, [rcx+0F8h]
0x180037510  mov     rdx, [rsi+0A8h]
0x180037517  test    rdx, rdx
0x18003751a  jnz     short loc_180037523
0x18003751c  mov     rdx, [rsi+0B0h]
0x180037523  mov     r8, rbx
0x180037526  mov     rcx, rax
0x180037529  mov     rax, r9
0x18003752c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037531  nop
0x180037532  lea     rcx, [rsp+348h+pPolicyStatus]
0x18003753a  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x18003753f  cmp     dword ptr [rsi+6Ch], 2
0x180037543  jnz     short loc_180037552
0x180037545  mov     rcx, rsi; struct web::http::client::details::winhttp_request_context *
0x180037548  call    ?_transfer_encoding_chunked_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@@Z; web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data(web::http::client::details::winhttp_request_context *)
0x18003754d  jmp     loc_180037CFD
0x180037552  cmp     dword ptr [rsi+6Ch], 1
0x180037556  jnz     short loc_180037565
0x180037558  mov     rcx, rsi; struct web::http::client::details::winhttp_request_context *
0x18003755b  call    ?_multiple_segment_write_data@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@@Z; web::http::client::details::winhttp_client::_multiple_segment_write_data(web::http::client::details::winhttp_request_context *)
0x180037560  jmp     loc_180037CFD
0x180037565  xor     edx, edx; lpReserved
0x180037567  mov     rcx, r14; hRequest
0x18003756a  call    cs:__imp_WinHttpReceiveResponse
0x180037570  test    eax, eax
0x180037572  jnz     loc_180037CFD
0x180037578  call    cs:__imp_GetLastError
0x18003757e  mov     ebx, eax
0x180037580  lea     rdx, aWinhttpreceive; "WinHttpReceiveResponse"
0x180037587  lea     rcx, [rsp+348h+hRequest]
0x18003758f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180037594  nop
0x180037595  lea     r8, [rsp+348h+hRequest]
0x18003759d  mov     edx, ebx
0x18003759f  lea     rcx, [rsp+348h+var_298]
0x1800375a7  call    web__http__client__details__build_error_msg
0x1800375ac  nop
0x1800375ad  mov     r8, rax
0x1800375b0  mov     edx, ebx
0x1800375b2  mov     rcx, rsi
0x1800375b5  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x1800375ba  nop
0x1800375bb  lea     rcx, [rsp+348h+var_298]
0x1800375c3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800375c8  nop
0x1800375c9  jmp     loc_180037441
0x1800375ce  mov     rdx, [rdx+18h]
0x1800375d2  add     rdx, 298h
0x1800375d9  lea     rcx, [rsp+348h+pPolicyPara]
0x1800375de  call    ??$?0U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@$0A@@?$shared_ptr@U_Task_impl_base@details@pplx@@@std@@QEAA@AEBV?$shared_ptr@U?$_Task_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@@1@@Z; std::shared_ptr<pplx::details::_Task_impl_base>::shared_ptr<pplx::details::_Task_impl_base>(std::shared_ptr<pplx::details::_Task_impl<BingOnlineServices::OnlineServiceResponse>> const &)
0x1800375e3  nop
0x1800375e4  mov     ebx, [rsp+348h+dwStatusInformationLength]
0x1800375eb  add     [rsi+40h], rbx
0x1800375ef  mov     rcx, qword ptr [rsp+348h+pPolicyPara.cbSize]
0x1800375f4  test    rcx, rcx
0x1800375f7  jz      short loc_18003760B
0x1800375f9  mov     r8, [rsi+40h]
0x1800375fd  mov     edx, 1
0x180037602  call    ??R?$_Func_class@XW4direction@message_direction@http@web@@_K@std@@QEBAXW4direction@message_direction@http@web@@_K@Z; std::_Func_class<void,web::http::message_direction::direction,unsigned __int64>::operator()(web::http::message_direction::direction,unsigned __int64)
0x180037607  jmp     short loc_18003760B
0x180037609  jmp     short loc_18003761C
0x18003760b  mov     rcx, rsi; this
0x18003760e  test    ebx, ebx
0x180037610  jnz     short loc_180037621
0x180037612  mov     rdx, [rsi+40h]; unsigned __int64
0x180037616  call    ?complete_request@request_context@details@client@http@web@@QEAAX_K@Z; web::http::client::details::request_context::complete_request(unsigned __int64)
0x18003761b  nop
0x18003761c  jmp     loc_1800377D7
0x180037621  lea     rdx, [rsp+348h+lpBuffer]
0x180037626  call    ?_get_writebuffer@request_context@details@client@http@web@@QEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::request_context::_get_writebuffer(void)
0x18003762b  nop
0x18003762c  lea     rcx, [rsp+348h+lpBuffer]
0x180037631  cmp     [rsi+0A8h], rdi
0x180037638  jz      short loc_180037651
0x18003763a  mov     rdx, rbx
0x18003763d  call    ?commit@?$streambuf@D@streams@Concurrency@@UEAAX_K@Z; Concurrency::streams::streambuf<char>::commit(unsigned __int64)
0x180037642  xor     r8d, r8d; bool
0x180037645  mov     edx, ebx; unsigned int
0x180037647  mov     rcx, rsi; struct web::http::client::details::winhttp_request_context *
0x18003764a  call    ?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z; web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)
0x18003764f  jmp     short loc_1800376B3
0x180037651  mov     r9, rbx
0x180037654  mov     r8, [rsi+0B0h]
0x18003765b  lea     rdx, [rsp+348h+pChainContext]
0x180037663  call    ?putn_nocopy@?$streambuf@E@streams@Concurrency@@UEAA?AV?$task@_K@pplx@@PEBE_K@Z; Concurrency::streams::streambuf<uchar>::putn_nocopy(uchar const *,unsigned __int64)
0x180037668  nop
0x180037669  mov     qword ptr [rsp+348h+pPolicyStatus.cbSize], r14
0x180037671  mov     qword ptr [rsp+348h+pPolicyStatus.lChainIndex], rsi
0x180037679  mov     dword ptr [rsp+348h+pPolicyStatus.pvExtraPolicyStatus], ebx
0x180037680  lea     r8, [rsp+348h+pPolicyStatus]
0x180037688  lea     rdx, [rsp+348h+Buffer]
0x18003768d  mov     rcx, rax
0x180037690  call    ??$then@V_lambda_9136b9a94d0d5493aaa0ceb9af684f74_@@@?$task@_K@pplx@@QEBA?AV?$task@X@1@AEBV_lambda_9136b9a94d0d5493aaa0ceb9af684f74_@@@Z; pplx::task<unsigned __int64>::then<_lambda_9136b9a94d0d5493aaa0ceb9af684f74_>(_lambda_9136b9a94d0d5493aaa0ceb9af684f74_ const &)
0x180037695  lea     rcx, [rsp+348h+Buffer]; void *
0x18003769a  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18003769f  nop
0x1800376a0  mov     rcx, [rsp+348h+var_2A0]; this
0x1800376a8  test    rcx, rcx
0x1800376ab  jz      short loc_1800376B3
0x1800376ad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800376b2  nop
0x1800376b3  lea     rcx, [rsp+348h+lpBuffer]
0x1800376b8  call    ??1?$streambuf@E@streams@Concurrency@@UEAA@XZ; Concurrency::streams::streambuf<uchar>::~streambuf<uchar>(void)
0x1800376bd  jmp     loc_18003761C
0x1800376c2  mov     r15d, [r9]
0x1800376c5  test    r15d, r15d
0x1800376c8  jz      loc_18003779B
0x1800376ce  lea     rdx, [rsp+348h+pPolicyStatus]
0x1800376d6  mov     rcx, rsi
0x1800376d9  call    ?_get_writebuffer@request_context@details@client@http@web@@QEAA?AV?$streambuf@E@streams@Concurrency@@XZ; web::http::client::details::request_context::_get_writebuffer(void)
0x1800376de  nop
0x1800376df  mov     edx, r15d
0x1800376e2  lea     rcx, [rsp+348h+pPolicyStatus]
0x1800376ea  call    ?alloc@?$streambuf@E@streams@Concurrency@@UEAAPEAE_K@Z; Concurrency::streams::streambuf<uchar>::alloc(unsigned __int64)
0x1800376ef  lea     rbx, [rsi+0A8h]
0x1800376f6  test    rax, rax
0x1800376f9  jnz     short loc_180037708
0x1800376fb  mov     edx, r15d; unsigned __int64
0x1800376fe  mov     rcx, rbx; this
0x180037701  call    ?allocate_space@memory_holder@details@client@http@web@@QEAAX_K@Z; web::http::client::details::memory_holder::allocate_space(unsigned __int64)
0x180037706  jmp     short loc_18003770B
0x180037708  mov     [rbx], rax
0x18003770b  mov     rdx, [rbx]
0x18003770e  test    rdx, rdx
0x180037711  jnz     short loc_180037717
0x180037713  mov     rdx, [rbx+8]; lpBuffer
0x180037717  xor     r9d, r9d; lpdwNumberOfBytesRead
0x18003771a  mov     r8d, r15d; dwNumberOfBytesToRead
0x18003771d  mov     rcx, r14; hRequest
0x180037720  call    cs:__imp_WinHttpReadData
0x180037726  test    eax, eax
0x180037728  jnz     short loc_180037789
0x18003772a  call    cs:__imp_GetLastError
0x180037730  mov     ebx, eax
0x180037732  lea     rdx, aWinhttpreaddat; "WinHttpReadData"
0x180037739  lea     rcx, [rsp+348h+hRequest]
0x180037741  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180037746  nop
0x180037747  lea     r8, [rsp+348h+hRequest]
0x18003774f  mov     edx, ebx
0x180037751  lea     rcx, [rsp+348h+var_298]
0x180037759  call    web__http__client__details__build_error_msg
0x18003775e  nop
0x18003775f  mov     r8, rax
0x180037762  mov     edx, ebx
0x180037764  mov     rcx, rsi
0x180037767  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x18003776c  nop
0x18003776d  lea     rcx, [rsp+348h+var_298]
0x180037775  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003777a  nop
0x18003777b  lea     rcx, [rsp+348h+hRequest]
0x180037783  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180037788  nop
  ... truncated ...
```
