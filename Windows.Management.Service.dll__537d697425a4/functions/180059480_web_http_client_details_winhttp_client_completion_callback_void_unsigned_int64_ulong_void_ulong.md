# web::http::client::details::winhttp_client::completion_callback(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x180059480`
- end: `0x18005abd5`
- name: `?completion_callback@winhttp_client@details@client@http@web@@CAXPEAX_KK0K@Z`
- size: `5973`
- prototype: `void __stdcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, LPVOID lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `40`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x18000bd9c`
- `0x18000bddc`
- `0x18000c3be`
- `0x18000c510`
- `0x18003b580`
- `0x18003da10`
- `0x18003dff0`
- `0x18003e000`
- `0x18003e140`
- `0x18003ea10`
- `0x18003f210`
- `0x18004dd20`
- `0x180052230`
- `0x1800532f0`
- `0x180053400`
- `0x1800561c0`
- `0x180057590`
- `0x1800578f0`
- `0x1800585f0`
- `0x180058ee0`
- `0x180058f40`
- `0x180059140`
- `0x1800593e0`
- `0x180059480`
- `0x18005afb0`
- `0x18005b450`
- `0x18005cb10`
- `0x18005df10`
- `0x18005e500`
- `0x180065aec`
- `0x180077c04`
- `0x1800816a8`
- `0x1800834b4`
- `0x180084cac`
- `0x180094678`
- `0x180139510`
- `0x1801543d4`
- `0x18016609c`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a1ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a1ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a404`
- `WINHTTP!WinHttpReadData` at `0x180059c78`
- `WINHTTP!WinHttpReadData` at `0x180059c78`
- `WINHTTP!WinHttpReceiveResponse` at `0x18005a19f`
- `WINHTTP!WinHttpReceiveResponse` at `0x18005a3f6`
- `WINHTTP!WinHttpReceiveResponse` at `0x18005a19f`
- `WINHTTP!WinHttpReceiveResponse` at `0x18005a3f6`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800595de`
- `WINHTTP!WinHttpQueryHeaders` at `0x180059622`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800599f4`
- `WINHTTP!WinHttpQueryHeaders` at `0x180059a38`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800595de`
- `WINHTTP!WinHttpQueryHeaders` at `0x180059622`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800599f4`
- `WINHTTP!WinHttpQueryHeaders` at `0x180059a38`

## string_xrefs

- `0x180059cae`: `WinHttpReadData`
- `0x180059f1e`: `Received incomplete compressed stream`
- `0x18005a685`: `Received incomplete compressed stream`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall web::http::client::details::winhttp_client::completion_callback(
        HINTERNET hInternet,
        std::_Ref_count_base **dwContext,
        DWORD dwInternetStatus,
        _DWORD *lpvStatusInformation,
        DWORD dwStatusInformationLength)
{
  volatile signed __int32 *v7; // rdx
  __m128i si128; // xmm6
  signed __int32 v9; // eax
  signed __int32 v10; // ett
  __m128i v11; // xmm0
  std::_Ref_count_base *v12; // r14
  volatile signed __int32 *v13; // rdi
  web::http::details *v14; // rsi
  DWORD v15; // ebx
  __int64 v16; // rax
  const struct std::nothrow_t *v17; // rdx
  void *v18; // rcx
  __int16 v19; // cx
  const struct std::nothrow_t *v20; // rdx
  void *v21; // rcx
  _QWORD *v22; // rax
  __int64 security_failure_message; // rax
  const struct std::nothrow_t *v24; // rdx
  void *v25; // rcx
  void *v26; // rax
  __int64 v27; // rax
  web::http::details *v28; // rbx
  DWORD LastError; // ebx
  __int64 v30; // rax
  const struct std::nothrow_t *v31; // rdx
  void *v32; // rcx
  unsigned __int64 v33; // rsi
  void *v34; // rbx
  __int64 v35; // rax
  DWORD v36; // ebx
  __int64 v37; // r8
  const struct std::nothrow_t *v38; // rdx
  void *v39; // rcx
  void *v40; // rcx
  char *v41; // rax
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rcx
  volatile signed __int32 *v45; // rbx
  __int64 v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rax
  volatile signed __int32 *v49; // rbx
  bool v50; // r12
  __int64 v51; // rbx
  __int64 v52; // rax
  __int64 v53; // rcx
  std::_Ref_count_base *v54; // rbx
  int v55; // eax
  DWORD v56; // ebx
  __int64 v57; // rax
  unsigned int v58; // esi
  __int64 v59; // rax
  const struct std::nothrow_t *v60; // rdx
  void *v61; // rcx
  __int64 v62; // r12
  __int64 v63; // rbx
  __int64 v64; // rax
  __int64 v65; // rcx
  volatile signed __int32 *v66; // rbx
  __int64 readbuffer; // rax
  __int64 v68; // rdx
  int v69; // eax
  DWORD v70; // ebx
  __int64 v71; // rax
  void *v72; // rcx
  __int64 v73; // rbx
  __int64 v74; // rax
  __int64 v75; // rcx
  const struct std::nothrow_t *v76; // rdx
  void *v77; // rcx
  unsigned __int64 v78; // rcx
  unsigned __int64 v79; // rax
  __int64 v80; // rax
  volatile signed __int32 *v81; // r14
  volatile signed __int32 *v82; // r14
  volatile signed __int32 *v83; // r14
  __int64 v84; // r8
  volatile signed __int32 *v85; // r14
  volatile signed __int32 *v86; // r14
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rax
  DWORD dwBufferLength[4]; // [rsp+30h] [rbp-1A8h] BYREF
  void *v92[2]; // [rsp+40h] [rbp-198h] BYREF
  LPVOID lpBuffer[2]; // [rsp+50h] [rbp-188h] BYREF
  __int128 v94; // [rsp+60h] [rbp-178h]
  std::_Ref_count_base *v95[2]; // [rsp+70h] [rbp-168h] BYREF
  __int64 v96; // [rsp+80h] [rbp-158h]
  std::_Ref_count_base *v97; // [rsp+88h] [rbp-150h]
  _BYTE v98[8]; // [rsp+90h] [rbp-148h] BYREF
  volatile signed __int32 *v99; // [rsp+98h] [rbp-140h]
  _BYTE pExceptionObject[24]; // [rsp+A0h] [rbp-138h] BYREF
  _BYTE v101[24]; // [rsp+B8h] [rbp-120h] BYREF
  _BYTE v102[24]; // [rsp+D0h] [rbp-108h] BYREF
  void *v103[2]; // [rsp+E8h] [rbp-F0h] BYREF
  __int128 v104; // [rsp+F8h] [rbp-E0h]
  void *Src[2]; // [rsp+108h] [rbp-D0h] BYREF
  volatile signed __int32 *v106; // [rsp+118h] [rbp-C0h]
  unsigned __int64 v107; // [rsp+120h] [rbp-B8h]
  void **v108; // [rsp+130h] [rbp-A8h] BYREF
  __int128 v109; // [rsp+138h] [rbp-A0h] BYREF
  int v110; // [rsp+148h] [rbp-90h]
  void ***v111; // [rsp+150h] [rbp-88h]
  void *v112[2]; // [rsp+158h] [rbp-80h] BYREF
  __int128 v113; // [rsp+168h] [rbp-70h]

  if ( !dwContext )
    return;
  v7 = (volatile signed __int32 *)dwContext[1];
  if ( dwInternetStatus == 2048 )
  {
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
    operator delete(dwContext, (const struct std::nothrow_t *)0x10);
    return;
  }
  si128 = 0;
  *(_OWORD *)v95 = 0;
  if ( v7 && (v9 = *((_DWORD *)v7 + 2)) != 0 )
  {
    while ( 1 )
    {
      v10 = v9;
      v9 = _InterlockedCompareExchange(v7 + 2, v9 + 1, v9);
      if ( v10 == v9 )
        break;
      if ( !v9 )
      {
        v11 = 0;
        goto LABEL_14;
      }
    }
    v12 = *dwContext;
    v95[0] = *dwContext;
    v13 = (volatile signed __int32 *)dwContext[1];
    v95[1] = (std::_Ref_count_base *)v13;
    si128 = _mm_load_si128((const __m128i *)v95);
  }
  else
  {
    v11 = 0;
LABEL_14:
    v12 = 0;
    v13 = (volatile signed __int32 *)_mm_srli_si128(v11, 8).m128i_u64[0];
  }
  if ( !v12 )
  {
    if ( !v13 )
      return;
LABEL_251:
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
    return;
  }
  if ( dwInternetStatus <= 0x40000 )
  {
    if ( dwInternetStatus != 0x40000 )
    {
      if ( dwInternetStatus == 16 )
      {
        web::http::client::details::winhttp_request_context::on_send_request_validate_cn(v12);
        if ( !v13 )
          return;
        goto LABEL_251;
      }
      if ( dwInternetStatus == 0x4000 )
      {
        v27 = *((_QWORD *)v12 + 16);
        if ( v27 )
        {
          *((_QWORD *)v12 + 16) = v27 - 1;
          if ( !v13 )
            return;
          goto LABEL_251;
        }
        dwBufferLength[0] = 0;
        WinHttpQueryHeaders(hInternet, 0x16u, 0, 0, dwBufferLength, 0);
        *(_OWORD *)lpBuffer = 0;
        *(_QWORD *)&v94 = 0;
        std::vector<unsigned char>::resize(lpBuffer, dwBufferLength[0]);
        v28 = (web::http::details *)lpBuffer[0];
        if ( WinHttpQueryHeaders(hInternet, 0x16u, 0, lpBuffer[0], dwBufferLength, 0) )
        {
          web::http::client::details::parse_winhttp_headers(hInternet, v28);
          web::http::client::details::request_context::complete_headers(v12);
          web::http::client::details::winhttp_request_context::allocate_request_space(v12, 0, 0);
          web::http::client::details::request_context::complete_request(v12, 0);
          web::http::client::details::winhttp_request_context::cleanup(v12);
        }
        else
        {
          LastError = GetLastError();
          *(_OWORD *)v103 = 0;
          v92[0] = (void *)31;
          v103[0] = (void *)std::string::_Allocate_for_capacity<0>(v103, v92);
          *(_QWORD *)&v104 = 19;
          *((void **)&v104 + 1) = v92[0];
          strcpy((char *)v103[0], "WinHttpQueryHeaders");
          v30 = web::http::client::details::build_error_msg(Src);
          web::http::client::details::request_context::report_error(v12, LastError, v30);
          std::string::~string(Src);
          std::string::~string(v103);
        }
        goto LABEL_67;
      }
      if ( dwInternetStatus != 0x10000 )
      {
        if ( dwInternetStatus == 0x20000 )
        {
          dwBufferLength[0] = 0;
          WinHttpQueryHeaders(hInternet, 0x16u, 0, 0, dwBufferLength, 0);
          *(_OWORD *)lpBuffer = 0;
          *(_QWORD *)&v94 = 0;
          std::vector<unsigned char>::resize(lpBuffer, dwBufferLength[0]);
          v14 = (web::http::details *)lpBuffer[0];
          if ( !WinHttpQueryHeaders(hInternet, 0x16u, 0, lpBuffer[0], dwBufferLength, 0) )
          {
            v15 = GetLastError();
            *(_OWORD *)v103 = 0;
            v104 = 0u;
            std::string::_Construct<1,char const *>(v103, "WinHttpQueryHeaders", 19);
            v16 = web::http::client::details::build_error_msg(Src);
            web::http::client::details::request_context::report_error(v12, v15, v16);
            std::string::~string(Src);
            if ( *((_QWORD *)&v104 + 1) > 0xFu )
            {
              v17 = (const struct std::nothrow_t *)(*((_QWORD *)&v104 + 1) + 1LL);
              if ( (unsigned __int64)(*((_QWORD *)&v104 + 1) + 1LL) < 0x1000 )
              {
                v18 = v103[0];
              }
              else
              {
                v18 = (void *)*((_QWORD *)v103[0] - 1);
                if ( (unsigned __int64)((char *)v103[0] - (char *)v18 - 8) > 0x1F )
                  __fastfail(5u);
                v17 = (const struct std::nothrow_t *)(*((_QWORD *)&v104 + 1) + 40LL);
              }
              operator delete(v18, v17);
            }
LABEL_67:
            if ( !lpBuffer[0] )
              goto LABEL_73;
            v31 = (const struct std::nothrow_t *)(v94 - (unsigned __int64)lpBuffer[0]);
            if ( (unsigned __int64)v94 - (unsigned __int64)lpBuffer[0] < 0x1000 )
            {
              v32 = lpBuffer[0];
              goto LABEL_72;
            }
            v32 = (void *)*((_QWORD *)lpBuffer[0] - 1);
            if ( (unsigned __int64)((char *)lpBuffer[0] - (char *)v32 - 8) <= 0x1F )
            {
              v31 = (const struct std::nothrow_t *)((char *)v31 + 39);
LABEL_72:
              operator delete(v32, v31);
              *(_OWORD *)lpBuffer = 0;
              *(_QWORD *)&v94 = 0;
LABEL_73:
              if ( v13 )
                std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
              return;
            }
LABEL_183:
            __fastfail(5u);
          }
          web::http::client::details::parse_winhttp_headers(hInternet, v14);
          v19 = *(_WORD *)(*((_QWORD *)v12 + 5) + 136LL);
          if ( v19 == 401 || v19 == 407 )
          {
            if ( (unsigned __int8)web::http::client::details::winhttp_client::handle_authentication_failure(
                                    hInternet,
                                    v95,
                                    0) )
            {
              if ( lpBuffer[0] )
              {
                v20 = (const struct std::nothrow_t *)(v94 - (unsigned __int64)lpBuffer[0]);
                if ( (unsigned __int64)v94 - (unsigned __int64)lpBuffer[0] < 0x1000 )
                {
                  v21 = lpBuffer[0];
                }
                else
                {
                  v21 = (void *)*((_QWORD *)lpBuffer[0] - 1);
                  if ( (unsigned __int64)((char *)lpBuffer[0] - (char *)v21 - 8) > 0x1F )
                    goto LABEL_183;
                  v20 = (const struct std::nothrow_t *)((char *)v20 + 39);
                }
                operator delete(v21, v20);
                *(_OWORD *)lpBuffer = 0;
                *(_QWORD *)&v94 = 0;
              }
              goto LABEL_143;
            }
            v13 = (volatile signed __int32 *)v95[1];
            v12 = v95[0];
          }
          if ( web::http::client::details::request_context::handle_compression(v12) )
          {
            if ( *((_QWORD *)v12 + 12)
              && !*((_BYTE *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)v12
                                                                                                  + 1))
                  + 424) )
            {
              v22 = operator new(0x10u);
              v92[0] = v22;
              if ( v22 )
              {
                *v22 = 0;
                *((_DWORD *)v22 + 2) = 1;
                *((_BYTE *)v22 + 12) = 0;
              }
              else
              {
                v22 = 0;
              }
              v92[0] = v22;
              std::unique_ptr<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>::operator=<std::default_delete<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>,0>(
                (char *)v12 + 320,
                v92);
              if ( v92[0] )
                operator delete(v92[0], (const struct std::nothrow_t *)0x10);
              *((_BYTE *)v12 + 307) = 1;
            }
            web::http::client::details::request_context::complete_headers(v12);
            if ( (unsigned __int8)std::operator==<unsigned short>(
                                    *((_QWORD *)v12 + 3) + 144LL,
                                    &web::http::methods::HEAD) )
            {
              web::http::client::details::winhttp_request_context::allocate_request_space(v12, 0, 0);
              web::http::client::details::request_context::complete_request(v12, 0);
            }
            else
            {
              web::http::client::details::winhttp_client::read_next_response_chunk(v12, 0, 1);
            }
          }
          goto LABEL_67;
        }
LABEL_124:
        if ( !v13 )
          return;
        goto LABEL_251;
      }
      security_failure_message = anonymous_namespace_::generate_security_failure_message(Src);
      v109 = 0;
      v108 = &web::http::http_exception::`vftable';
      v110 = 0;
      v111 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
      *(_OWORD *)v112 = 0;
      v113 = 0u;
      v112[0] = *(void **)security_failure_message;
      v112[1] = *(void **)(security_failure_message + 8);
      v113 = *(_OWORD *)(security_failure_message + 16);
      *(_QWORD *)(security_failure_message + 24) = 15;
      *(_BYTE *)security_failure_message = 0;
      *(_QWORD *)(security_failure_message + 16) = 0;
      *(_QWORD *)(security_failure_message + 24) = 15;
      *(_BYTE *)security_failure_message = 0;
      web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v108);
      if ( *((_QWORD *)&v113 + 1) > 0xFu )
      {
        v24 = (const struct std::nothrow_t *)(*((_QWORD *)&v113 + 1) + 1LL);
        v25 = v112[0];
        if ( (unsigned __int64)(*((_QWORD *)&v113 + 1) + 1LL) < 0x1000 )
        {
LABEL_59:
          operator delete(v25, v24);
          goto LABEL_60;
        }
        v26 = (void *)*((_QWORD *)v112[0] - 1);
        if ( (unsigned __int64)((char *)v112[0] - (char *)v26 - 8) > 0x1F )
          goto LABEL_183;
        v24 = (const struct std::nothrow_t *)(*((_QWORD *)&v113 + 1) + 40LL);
LABEL_58:
        v25 = v26;
        goto LABEL_59;
      }
      goto LABEL_60;
    }
    v33 = (unsigned int)*lpvStatusInformation;
    if ( (_DWORD)v33 )
    {
      if ( *((_QWORD *)v12 + 12) )
      {
        if ( *((_QWORD *)v12 + 34) - *((_QWORD *)v12 + 32) < v33 )
          std::vector<unsigned char>::reserve((char *)v12 + 256, (unsigned int)v33);
        v34 = (void *)*((_QWORD *)v12 + 32);
      }
      else
      {
        web::http::client::details::request_context::_get_writebuffer(v12, v103);
        if ( !v103[1] )
        {
          std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "Invalid streambuf object");
          throw (std::invalid_argument *)pExceptionObject;
        }
        v35 = (*(__int64 (__fastcall **)(void *, unsigned __int64))(*(_QWORD *)v103[1] + 224LL))(v103[1], v33);
        if ( v35 )
        {
          *((_QWORD *)v12 + 31) = v33;
        }
        else
        {
          if ( v33 > *((_QWORD *)v12 + 29) - *((_QWORD *)v12 + 28) )
            std::vector<unsigned char>::resize((char *)v12 + 224, v33);
          v35 = 0;
        }
        *((_QWORD *)v12 + 27) = v35;
        v34 = (void *)v35;
        if ( !v35 )
          v34 = (void *)*((_QWORD *)v12 + 28);
        Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v103);
      }
      if ( !WinHttpReadData(hInternet, v34, v33, 0) )
      {
        v36 = GetLastError();
        *(_QWORD *)&v104 = 15;
        *((_QWORD *)&v104 + 1) = 15;
        qmemcpy(v103, "WinHttpReadDat", 14);
        HIWORD(v103[1]) = (unsigned __int8)aWinhttpreaddat_0[14];
        v37 = web::http::client::details::build_error_msg(Src);
        web::http::client::details::request_context::report_error(v12, v36, v37);
        if ( v107 > 0xF )
        {
          v38 = (const struct std::nothrow_t *)(v107 + 1);
          if ( v107 + 1 < 0x1000 )
          {
            v39 = Src[0];
          }
          else
          {
            v39 = (void *)*((_QWORD *)Src[0] - 1);
            if ( (unsigned __int64)((char *)Src[0] - (char *)v39 - 8) > 0x1F )
              __fastfail(5u);
            v38 = (const struct std::nothrow_t *)(v107 + 40);
          }
          operator delete(v39, v38);
        }
        v106 = 0;
        v107 = 15;
        LOBYTE(Src[0]) = 0;
        if ( *((_QWORD *)&v104 + 1) > 0xFu )
        {
          if ( (unsigned __int64)(*((_QWORD *)&v104 + 1) + 1LL) < 0x1000 )
          {
            operator delete(v103[0], (const struct std::nothrow_t *)(*((_QWORD *)&v104 + 1) + 1LL));
          }
          else
          {
            v40 = (void *)*((_QWORD *)v103[0] - 1);
            if ( (unsigned __int64)((char *)v103[0] - (char *)v40 - 8) > 0x1F )
              goto LABEL_183;
            operator delete(v40, (const struct std::nothrow_t *)(*((_QWORD *)&v104 + 1) + 40LL));
          }
        }
      }
      goto LABEL_250;
    }
    if ( *((_QWORD *)v12 + 12) )
    {
      if ( *((_BYTE *)v12 + 307) )
      {
        v41 = (char *)operator new(0x30u);
        strcpy(v41, "Chunked response stream ended unexpectedly");
        v109 = 0;
        v108 = &web::http::http_exception::`vftable';
        v110 = 0;
        v111 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        v112[0] = v41;
        v112[1] = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        *(_QWORD *)&v113 = 42;
        *((_QWORD *)&v113 + 1) = 47;
        web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v108);
        if ( *((_QWORD *)&v113 + 1) > 0xFu )
        {
          v26 = v112[0];
          v24 = (const struct std::nothrow_t *)(*((_QWORD *)&v113 + 1) + 1LL);
          if ( (unsigned __int64)(*((_QWORD *)&v113 + 1) + 1LL) >= 0x1000 )
          {
            v25 = (void *)*((_QWORD *)v112[0] - 1);
            if ( (unsigned __int64)((char *)v112[0] - (char *)v25 - 8) > 0x1F )
              goto LABEL_183;
            v24 = (const struct std::nothrow_t *)(*((_QWORD *)&v113 + 1) + 40LL);
            goto LABEL_59;
          }
          goto LABEL_58;
        }
LABEL_60:
        *(_QWORD *)&v113 = 0;
        *((_QWORD *)&v113 + 1) = 15;
        LOBYTE(v112[0]) = 0;
        v108 = &std::exception::`vftable';
        o___std_exception_destroy_0(&v109);
        if ( !v13 )
          return;
        goto LABEL_251;
      }
      if ( *((_BYTE *)v12 + 305) && !*((_BYTE *)v12 + 306) )
      {
        *(_OWORD *)v103 = 0;
        v104 = 0u;
        std::string::_Construct<1,char const *>(v103, "Received incomplete compressed stream", 37);
        v109 = 0;
        v108 = &web::http::http_exception::`vftable';
        v110 = 0;
        v111 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        *(_OWORD *)v112 = *(_OWORD *)v103;
        v113 = v104;
        web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v108);
        std::string::~string(v112);
        v108 = &std::exception::`vftable';
        o___std_exception_destroy_0(&v109);
        if ( v13 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
        return;
      }
    }
    v42 = *((_QWORD *)v12 + 3);
    v43 = *(_QWORD *)(v42 + 720);
    if ( v43 )
      _InterlockedIncrement((volatile signed __int32 *)(v43 + 8));
    v44 = *(_QWORD *)(v42 + 712);
    v96 = v44;
    v45 = *(volatile signed __int32 **)(v42 + 720);
    v97 = (std::_Ref_count_base *)v45;
    if ( v44 )
    {
      try
      {
        std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v44, 1);
      }
      catch ( ... )
      {
        v89 = std::current_exception(v92);
        web::http::client::details::request_context::report_exception(v95[0], v89);
        goto LABEL_141;
      }
    }
    web::http::client::details::request_context::complete_request(v12, *((_QWORD *)v12 + 8));
    if ( !v45 )
      goto LABEL_250;
LABEL_247:
    if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
      if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
    }
    goto LABEL_250;
  }
  if ( dwInternetStatus != 0x80000 )
  {
    if ( dwInternetStatus == 0x100000 )
    {
      v62 = (unsigned int)*lpvStatusInformation;
      if ( (_DWORD)v62 )
      {
        v63 = *((_QWORD *)v12 + 3);
        v64 = *(_QWORD *)(v63 + 720);
        if ( v64 )
          _InterlockedIncrement((volatile signed __int32 *)(v64 + 8));
        v65 = *(_QWORD *)(v63 + 712);
        v96 = v65;
        v66 = *(volatile signed __int32 **)(v63 + 720);
        v97 = (std::_Ref_count_base *)v66;
        if ( v65 )
        {
          try
          {
            *((_QWORD *)v12 + 7) += v62;
            std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v65, 0);
          }
          catch ( ... )
          {
            v88 = std::current_exception(v92);
            web::http::client::details::request_context::report_exception(v95[0], v88);
            goto LABEL_141;
          }
        }
        if ( v66 )
        {
          if ( _InterlockedExchangeAdd(v66 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
            if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
          }
        }
      }
      if ( *((_QWORD *)v12 + 27) )
      {
        readbuffer = web::http::client::details::winhttp_request_context::_get_readbuffer(v12, v103);
        v68 = *((_QWORD *)v12 + 27);
        if ( !v68 )
          v68 = *((_QWORD *)v12 + 28);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)readbuffer + 248LL))(readbuffer, v68, v62);
        Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v103);
      }
      v69 = *((_DWORD *)v12 + 34);
      if ( v69 == 2 )
      {
LABEL_148:
        web::http::client::details::winhttp_client::_transfer_encoding_chunked_write_data(v12);
        goto LABEL_250;
      }
      if ( v69 != 1 )
      {
        if ( !WinHttpReceiveResponse(hInternet, 0) )
        {
          v70 = GetLastError();
          *(_OWORD *)v103 = 0;
          v92[0] = (void *)31;
          v103[0] = (void *)std::string::_Allocate_for_capacity<0>(v103, v92);
          *(_QWORD *)&v104 = 22;
          *((void **)&v104 + 1) = v92[0];
          strcpy((char *)v103[0], "WinHttpReceiveResponse");
          v71 = web::http::client::details::build_error_msg(Src);
          web::http::client::details::request_context::report_error(v12, v70, v71);
          std::string::~string(Src);
          if ( *((_QWORD *)&v104 + 1) > 0xFu )
          {
            if ( (unsigned __int64)(*((_QWORD *)&v104 + 1) + 1LL) < 0x1000 )
            {
              operator delete(v103[0], (const struct std::nothrow_t *)(*((_QWORD *)&v104 + 1) + 1LL));
            }
            else
            {
              v72 = (void *)*((_QWORD *)v103[0] - 1);
              if ( (unsigned __int64)((char *)v103[0] - (char *)v72 - 8) > 0x1F )
                goto LABEL_183;
              operator delete(v72, (const struct std::nothrow_t *)(*((_QWORD *)&v104 + 1) + 40LL));
            }
          }
        }
LABEL_250:
        if ( !v13 )
          return;
        goto LABEL_251;
      }
LABEL_150:
      web::http::client::details::winhttp_client::_multiple_segment_write_data(v12);
      goto LABEL_250;
    }
    if ( dwInternetStatus != 0x200000 )
    {
      if ( dwInternetStatus != 0x400000 )
        goto LABEL_124;
      v46 = *((_QWORD *)v12 + 3);
      v47 = *(_QWORD *)(v46 + 56);
      if ( v47 )
        _InterlockedIncrement((volatile signed __int32 *)(v47 + 8));
      v48 = *(_QWORD *)(v46 + 48);
      v49 = *(volatile signed __int32 **)(v46 + 56);
      v50 = !v48 || !*(_QWORD *)(v48 + 8);
      if ( v49 )
      {
        if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
          if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
        }
      }
      if ( v50 )
      {
        v51 = *((_QWORD *)v12 + 3);
        v52 = *(_QWORD *)(v51 + 720);
        if ( v52 )
          _InterlockedIncrement((volatile signed __int32 *)(v52 + 8));
        v53 = *(_QWORD *)(v51 + 712);
        v96 = v53;
        v54 = *(std::_Ref_count_base **)(v51 + 720);
        v97 = v54;
        if ( v53 )
        {
          try
          {
            std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v53, 0);
          }
          catch ( ... )
          {
            v87 = std::current_exception(v92);
            web::http::client::details::request_context::report_exception(v95[0], v87);
            goto LABEL_141;
          }
        }
        if ( v54 )
          std::_Ref_count_base::_Decref(v54);
      }
      v55 = *((_DWORD *)v12 + 34);
      if ( v55 == 2 )
        goto LABEL_148;
      if ( v55 != 1 )
      {
        if ( !WinHttpReceiveResponse(hInternet, 0) )
        {
          v56 = GetLastError();
          *(_OWORD *)Src = 0;
          v106 = 0;
          v107 = 0;
          std::string::_Construct<1,char const *>(Src, "WinHttpReceiveResponse", 22);
          v57 = web::http::client::details::build_error_msg(v103);
          web::http::client::details::request_context::report_error(v12, v56, v57);
          std::string::~string(v103);
          std::string::~string(Src);
        }
        goto LABEL_250;
      }
      goto LABEL_150;
    }
    v58 = lpvStatusInformation[2];
    if ( v58 != 12032 )
    {
LABEL_156:
      v59 = web::http::client::details::build_error_msg_0(Src);
      web::http::client::details::request_context::report_error(v12, v58, v59);
      if ( v107 > 0xF )
      {
        v60 = (const struct std::nothrow_t *)(v107 + 1);
        if ( v107 + 1 < 0x1000 )
        {
          v61 = Src[0];
        }
        else
        {
          v61 = (void *)*((_QWORD *)Src[0] - 1);
          if ( (unsigned __int64)((char *)Src[0] - (char *)v61 - 8) > 0x1F )
            goto LABEL_183;
          v60 = (const struct std::nothrow_t *)(v107 + 40);
        }
        operator delete(v61, v60);
      }
      if ( !v13 )
        return;
      goto LABEL_251;
    }
    if ( !(unsigned __int8)web::http::client::details::winhttp_client::handle_authentication_failure(
                             hInternet,
                             v95,
                             12032) )
    {
      v13 = (volatile signed __int32 *)v95[1];
      v12 = v95[0];
      goto LABEL_156;
    }
LABEL_143:
    if ( v95[1] )
      std::_Ref_count_base::_Decref(v95[1]);
    return;
  }
  v73 = *((_QWORD *)v12 + 3);
  v74 = *(_QWORD *)(v73 + 720);
  if ( v74 )
    _InterlockedIncrement((volatile signed __int32 *)(v74 + 8));
  v96 = *(_QWORD *)(v73 + 712);
  v75 = v96;
  v45 = *(volatile signed __int32 **)(v73 + 720);
  v97 = (std::_Ref_count_base *)v45;
  *((_QWORD *)v12 + 8) += dwStatusInformationLength;
  if ( v75 )
  {
    try
    {
      std::_Func_class<void,enum web::http::message_direction::direction,unsigned __int64>::operator()(v75, 1);
    }
    catch ( ... )
    {
      v90 = std::current_exception(v92);
      web::http::client::details::request_context::report_exception(v95[0], v90);
LABEL_141:
      if ( v97 )
        std::_Ref_count_base::_Decref(v97);
      goto LABEL_143;
    }
  }
  if ( dwStatusInformationLength )
  {
    web::http::client::details::request_context::_get_writebuffer(v12, v103);
    if ( *((_QWORD *)v12 + 12) )
    {
      v78 = *((_QWORD *)web::http::client::details::_http_client_communicator::client_config(*((web::http::client::details::_http_client_communicator **)v12
                                                                                             + 1))
            + 52);
      if ( !v78 )
        v78 = 0x10000;
      v79 = dwStatusInformationLength;
      if ( dwStatusInformationLength < v78 )
        v79 = v78;
      *((_QWORD *)v12 + 36) = dwStatusInformationLength;
      *((_QWORD *)v12 + 39) = 0;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      *(__m128i *)v92 = si128;
      *(_OWORD *)Src = 0;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      Src[0] = v12;
      Src[1] = (void *)v13;
      v106 = (volatile signed __int32 *)v79;
      v107 = v79;
      v80 = ____do_while_V_lambda_2___JB___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z__N_details_pplx__YA_AV__task__N_1_V_lambda_2___JB___completion_callback_winhttp_client_0client_http_web__CAXPEAX_KK0K_Z__Z(
              lpBuffer,
              Src);
      ___then_V_lambda_3___JB___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z____task__N_pplx__QEBA_AV__task_X_1___QEAV_lambda_3___JB___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z__Z(
        v80,
        v98,
        v92);
      v81 = v99;
      if ( v99 )
      {
        if ( _InterlockedExchangeAdd(v99 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v81)(v81);
          if ( _InterlockedExchangeAdd(v81 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v81 + 8LL))(v81);
        }
      }
      v82 = (volatile signed __int32 *)lpBuffer[1];
      if ( lpBuffer[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpBuffer[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
          if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
        }
      }
      v83 = (volatile signed __int32 *)v92[1];
    }
    else
    {
      if ( *((_QWORD *)v12 + 27) )
      {
        if ( !v103[1] )
        {
          std::invalid_argument::invalid_argument((std::invalid_argument *)v101, "Invalid streambuf object");
          throw (std::invalid_argument *)v101;
        }
        (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v103[1] + 232LL))(v103[1], dwStatusInformationLength);
        web::http::client::details::winhttp_client::read_next_response_chunk(v12, dwStatusInformationLength, 0);
        goto LABEL_245;
      }
      Src[0] = hInternet;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      Src[1] = v12;
      v106 = v13;
      LODWORD(v107) = dwStatusInformationLength;
      v84 = *((_QWORD *)v12 + 27);
      if ( !v84 )
        v84 = *((_QWORD *)v12 + 28);
      if ( !v103[1] )
      {
        std::invalid_argument::invalid_argument((std::invalid_argument *)v102, "Invalid streambuf object");
        throw (std::invalid_argument *)v102;
      }
      (*(void (__fastcall **)(void *, void **, __int64, _QWORD))(*(_QWORD *)v103[1] + 112LL))(
        v103[1],
        v92,
        v84,
        dwStatusInformationLength);
      ___then_V_lambda_4___JI___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z____task__K_pplx__QEBA_AV__task_X_1___QEAV_lambda_4___JI___completion_callback_winhttp_client_details_client_http_web__CAXPEAX_KK0K_Z__Z(
        v92,
        lpBuffer,
        Src);
      v85 = (volatile signed __int32 *)lpBuffer[1];
      if ( lpBuffer[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpBuffer[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v85)(v85);
          if ( _InterlockedExchangeAdd(v85 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v85 + 8LL))(v85);
        }
      }
      v86 = (volatile signed __int32 *)v92[1];
      if ( v92[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v92[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v86)(v86);
          if ( _InterlockedExchangeAdd(v86 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
        }
      }
      v83 = v106;
    }
    if ( v83 )
    {
      if ( _InterlockedExchangeAdd(v83 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v83)(v83);
        if ( _InterlockedExchangeAdd(v83 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 8LL))(v83);
      }
    }
LABEL_245:
    Concurrency::streams::streambuf<unsigned char>::~streambuf<unsigned char>(v103);
LABEL_246:
    if ( !v45 )
      goto LABEL_250;
    goto LABEL_247;
  }
  if ( !*((_QWORD *)v12 + 12) )
    goto LABEL_205;
  if ( *((_BYTE *)v12 + 307) )
  {
    lpBuffer[1] = 0;
    lpBuffer[0] = operator new(0x30u);
    *(_QWORD *)&v94 = 42;
    *((_QWORD *)&v94 + 1) = 47;
    strcpy((char *)lpBuffer[0], "Chunked response stream ended unexpectedly");
    v109 = 0;
    v108 = &web::http::http_exception::`vftable';
    v110 = 0;
    v111 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    *(_OWORD *)v112 = *(_OWORD *)lpBuffer;
    v113 = v94;
    web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v108);
    std::string::~string(v112);
    v108 = &std::exception::`vftable';
    o___std_exception_destroy_0(&v109);
    goto LABEL_246;
  }
  if ( !*((_BYTE *)v12 + 305) || *((_BYTE *)v12 + 306) )
  {
LABEL_205:
    web::http::client::details::request_context::complete_request(v12, *((_QWORD *)v12 + 8));
    goto LABEL_246;
  }
  *(_OWORD *)lpBuffer = 0;
  v94 = 0u;
  std::string::_Construct<1,char const *>(lpBuffer, "Received incomplete compressed stream", 37);
  v109 = 0;
  v108 = &web::http::http_exception::`vftable';
  v110 = 0;
  v111 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v112[0] = lpBuffer[0];
  v112[1] = lpBuffer[1];
  v113 = v94;
  web::http::client::details::request_context::report_exception<web::http::http_exception>(v12, &v108);
  if ( *((_QWORD *)&v113 + 1) > 0xFu )
  {
    v76 = (const struct std::nothrow_t *)(*((_QWORD *)&v113 + 1) + 1LL);
    if ( (unsigned __int64)(*((_QWORD *)&v113 + 1) + 1LL) < 0x1000 )
    {
      v77 = v112[0];
    }
    else
    {
      v77 = (void *)*((_QWORD *)v112[0] - 1);
      if ( (unsigned __int64)((char *)v112[0] - (char *)v77 - 8) > 0x1F )
        __fastfail(5u);
      v76 = (const struct std::nothrow_t *)(*((_QWORD *)&v113 + 1) + 40LL);
    }
    operator delete(v77, v76);
  }
  *(_QWORD *)&v113 = 0;
  *((_QWORD *)&v113 + 1) = 15;
  LOBYTE(v112[0]) = 0;
  v108 = &std::exception::`vftable';
  o___std_exception_destroy_0(&v109);
  if ( v45 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v45);
  if ( v13 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v13);
}

```

## disassembly

```asm
0x180059480  test    rdx, rdx
0x180059483  jz      locret_18005AB59
0x180059489  push    rbx
0x18005948a  push    rsi
0x18005948b  push    rdi
0x18005948c  push    r12
0x18005948e  push    r13
0x180059490  push    r14
0x180059492  push    r15
0x180059494  sub     rsp, 1A0h
0x18005949b  movaps  [rsp+1D8h+var_48], xmm6
0x1800594a3  mov     rax, cs:__security_cookie
0x1800594aa  xor     rax, rsp
0x1800594ad  mov     [rsp+1D8h+var_58], rax
0x1800594b5  mov     rbx, r9
0x1800594b8  mov     rdi, rdx
0x1800594bb  mov     r15, rcx
0x1800594be  xor     r13d, r13d
0x1800594c1  mov     rdx, [rdx+8]
0x1800594c5  cmp     r8d, 800h
0x1800594cc  jnz     short loc_180059503
0x1800594ce  test    rdx, rdx
0x1800594d1  jz      short loc_1800594F1
0x1800594d3  mov     esi, 0FFFFFFFFh
0x1800594d8  lock xadd [rdx+0Ch], esi
0x1800594dd  cmp     esi, 1
0x1800594e0  jnz     short loc_1800594F1
0x1800594e2  mov     rax, [rdx]
0x1800594e5  mov     rcx, rdx
0x1800594e8  mov     rax, [rax+8]
0x1800594ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594f1  mov     edx, 10h; struct std::nothrow_t *
0x1800594f6  mov     rcx, rdi; void *
0x1800594f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800594fe  jmp     loc_18005AB2F
0x180059503  xorps   xmm6, xmm6
0x180059506  movdqa  xmmword ptr [rsp+1D8h+var_168], xmm6
0x18005950c  test    rdx, rdx
0x18005950f  jz      short loc_18005954D
0x180059511  mov     eax, [rdx+8]
0x180059514  test    eax, eax
0x180059516  jz      short loc_18005954D
0x180059518  nop     dword ptr [rax+rax+00000000h]
0x180059520  lea     ecx, [rax+1]
0x180059523  lock cmpxchg [rdx+8], ecx
0x180059528  jz      short loc_180059534
0x18005952a  test    eax, eax
0x18005952c  jnz     short loc_180059520
0x18005952e  movdqa  xmm0, xmm6
0x180059532  jmp     short loc_180059550
0x180059534  mov     r14, [rdi]
0x180059537  mov     [rsp+1D8h+var_168], r14
0x18005953c  mov     rdi, [rdi+8]
0x180059540  mov     [rsp+1D8h+var_168+8], rdi
0x180059545  movdqa  xmm6, xmmword ptr [rsp+1D8h+var_168]
0x18005954b  jmp     short loc_18005955F
0x18005954d  xorps   xmm0, xmm0
0x180059550  psrldq  xmm0, 8
0x180059555  movq    r14, xmm6
0x18005955a  movq    rdi, xmm0
0x18005955f  test    r14, r14
0x180059562  jnz     short loc_180059577
0x180059564  test    rdi, rdi
0x180059567  jz      loc_18005AB2F
0x18005956d  mov     esi, 0FFFFFFFFh
0x180059572  jmp     loc_18005AAFC
0x180059577  cmp     r8d, 40000h
0x18005957e  ja      loc_18005A040
0x180059584  jz      loc_180059BA7
0x18005958a  cmp     r8d, 10h
0x18005958e  jz      loc_180059B8B
0x180059594  cmp     r8d, 4000h
0x18005959b  jz      loc_1800599A9
0x1800595a1  mov     eax, 10000h
0x1800595a6  cmp     r8d, eax
0x1800595a9  jz      loc_180059864
0x1800595af  cmp     r8d, 20000h
0x1800595b6  jnz     loc_18005A070
0x1800595bc  mov     [rsp+1D8h+dwBufferLength], r13d
0x1800595c1  mov     [rsp+1D8h+lpdwIndex], r13; lpdwIndex
0x1800595c6  lea     rax, [rsp+1D8h+dwBufferLength]
0x1800595cb  mov     [rsp+1D8h+lpdwBufferLength], rax; lpdwBufferLength
0x1800595d0  xor     r9d, r9d; lpBuffer
0x1800595d3  xor     r8d, r8d; pwszName
0x1800595d6  mov     edx, 16h; dwInfoLevel
0x1800595db  mov     rcx, r15; hRequest
0x1800595de  call    cs:__imp_WinHttpQueryHeaders
0x1800595e4  xorps   xmm0, xmm0
0x1800595e7  movdqu  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x1800595ed  mov     qword ptr [rsp+1D8h+var_178], r13
0x1800595f2  mov     edx, [rsp+1D8h+dwBufferLength]
0x1800595f6  lea     rcx, [rsp+1D8h+lpBuffer]
0x1800595fb  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180059600  mov     rsi, [rsp+1D8h+lpBuffer]
0x180059605  mov     [rsp+1D8h+lpdwIndex], r13; lpdwIndex
0x18005960a  lea     rax, [rsp+1D8h+dwBufferLength]
0x18005960f  mov     [rsp+1D8h+lpdwBufferLength], rax; lpdwBufferLength
0x180059614  mov     r9, rsi; lpBuffer
0x180059617  xor     r8d, r8d; pwszName
0x18005961a  mov     edx, 16h; dwInfoLevel
0x18005961f  mov     rcx, r15; hRequest
0x180059622  call    cs:__imp_WinHttpQueryHeaders
0x180059628  test    eax, eax
0x18005962a  jnz     loc_1800596F0
0x180059630  call    cs:__imp_GetLastError
0x180059636  mov     ebx, eax
0x180059638  xorps   xmm0, xmm0
0x18005963b  movups  xmmword ptr [rsp+1D8h+var_F0], xmm0
0x180059643  mov     qword ptr [rsp+1D8h+var_E0], r13
0x18005964b  mov     qword ptr [rsp+1D8h+var_E0+8], r13
0x180059653  mov     r8d, 13h
0x180059659  lea     rdx, aWinhttpqueryhe_0; "WinHttpQueryHeaders"
0x180059660  lea     rcx, [rsp+1D8h+var_F0]
0x180059668  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005966d  nop
0x18005966e  lea     r8, [rsp+1D8h+var_F0]
0x180059676  mov     edx, ebx
0x180059678  lea     rcx, [rsp+1D8h+Src]; Src
0x180059680  call    web__http__client__details__build_error_msg
0x180059685  nop
0x180059686  mov     r8, rax
0x180059689  mov     edx, ebx
0x18005968b  mov     rcx, r14
0x18005968e  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180059693  nop
0x180059694  lea     rcx, [rsp+1D8h+Src]
0x18005969c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800596a1  nop
0x1800596a2  mov     rdx, qword ptr [rsp+1D8h+var_E0+8]
0x1800596aa  cmp     rdx, 0Fh
0x1800596ae  jbe     short loc_1800596EB
0x1800596b0  mov     rax, [rsp+1D8h+var_F0]
0x1800596b8  inc     rdx; struct std::nothrow_t *
0x1800596bb  cmp     rdx, 1000h
0x1800596c2  jb      short loc_1800596E2
0x1800596c4  mov     rcx, [rax-8]
0x1800596c8  sub     rax, rcx
0x1800596cb  sub     rax, 8
0x1800596cf  cmp     rax, 1Fh
0x1800596d3  ja      short loc_1800596DB
0x1800596d5  add     rdx, 27h ; '''
0x1800596d9  jmp     short loc_1800596E5
0x1800596db  mov     ecx, 5
0x1800596e0  int     29h; Win8: RtlFailFast(ecx)
0x1800596e2  mov     rcx, rax; void *
0x1800596e5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800596ea  nop
0x1800596eb  jmp     loc_180059AEE
0x1800596f0  lea     r8, [r14+28h]
0x1800596f4  mov     rdx, rsi; this
0x1800596f7  mov     rcx, r15; hRequest
0x1800596fa  call    web__http__client__details__parse_winhttp_headers
0x1800596ff  mov     rax, [r14+28h]
0x180059703  movzx   ecx, word ptr [rax+88h]
0x18005970a  mov     eax, 191h
0x18005970f  cmp     cx, ax
0x180059712  jz      short loc_18005971E
0x180059714  mov     eax, 197h
0x180059719  cmp     cx, ax
0x18005971c  jnz     short loc_180059791
0x18005971e  xor     r8d, r8d
0x180059721  lea     rdx, [rsp+1D8h+var_168]
0x180059726  mov     rcx, r15
0x180059729  call    ?handle_authentication_failure@winhttp_client@details@client@http@web@@CA_NPEAXAEBV?$shared_ptr@Vwinhttp_request_context@details@client@http@web@@@std@@K@Z; web::http::client::details::winhttp_client::handle_authentication_failure(void *,std::shared_ptr<web::http::client::details::winhttp_request_context> const &,ulong)
0x18005972e  test    al, al
0x180059730  jz      short loc_180059787
0x180059732  mov     rax, [rsp+1D8h+lpBuffer]
0x180059737  test    rax, rax
0x18005973a  jz      loc_18005A14A
0x180059740  mov     rdx, qword ptr [rsp+1D8h+var_178]
0x180059745  sub     rdx, rax; struct std::nothrow_t *
0x180059748  cmp     rdx, 1000h
0x18005974f  jb      short loc_18005976C
0x180059751  mov     rcx, [rax-8]
0x180059755  sub     rax, rcx
0x180059758  sub     rax, 8
0x18005975c  cmp     rax, 1Fh
0x180059760  ja      loc_18005A4E7
0x180059766  add     rdx, 27h ; '''
0x18005976a  jmp     short loc_18005976F
0x18005976c  mov     rcx, rax; void *
0x18005976f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180059774  xorps   xmm0, xmm0
0x180059777  movdqu  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x18005977d  mov     qword ptr [rsp+1D8h+var_178], r13
0x180059782  jmp     loc_18005A14A
0x180059787  mov     rdi, [rsp+1D8h+var_168+8]
0x18005978c  mov     r14, [rsp+1D8h+var_168]
0x180059791  mov     rcx, r14; this
0x180059794  call    ?handle_compression@request_context@details@client@http@web@@QEAA_NXZ; web::http::client::details::request_context::handle_compression(void)
0x180059799  test    al, al
0x18005979b  jnz     short loc_1800597A2
0x18005979d  jmp     loc_180059AEE
0x1800597a2  cmp     qword ptr [r14+60h], 0
0x1800597a7  jz      short loc_180059814
0x1800597a9  mov     rcx, [r14+8]; this
0x1800597ad  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800597b2  cmp     byte ptr [rax+1A8h], 0
0x1800597b9  jnz     short loc_180059814
0x1800597bb  mov     ecx, 10h; Size
0x1800597c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800597c5  mov     [rsp+1D8h+var_198], rax
0x1800597ca  test    rax, rax
0x1800597cd  jz      short loc_1800597DF
0x1800597cf  mov     [rax], r13
0x1800597d2  mov     dword ptr [rax+8], 1
0x1800597d9  mov     byte ptr [rax+0Ch], 0
0x1800597dd  jmp     short loc_1800597E2
0x1800597df  mov     rax, r13
0x1800597e2  mov     [rsp+1D8h+var_198], rax
0x1800597e7  lea     rcx, [r14+140h]
0x1800597ee  lea     rdx, [rsp+1D8h+var_198]
0x1800597f3  call    ??$?4U?$default_delete@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@@std@@$0A@@?$unique_ptr@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@U?$default_delete@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>::operator=<std::default_delete<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>,0>(std::unique_ptr<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper> &&)
0x1800597f8  mov     rcx, [rsp+1D8h+var_198]; void *
0x1800597fd  test    rcx, rcx
0x180059800  jz      short loc_18005980C
0x180059802  mov     edx, 10h; struct std::nothrow_t *
0x180059807  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005980c  mov     byte ptr [r14+133h], 1
0x180059814  mov     rcx, r14; this
0x180059817  call    ?complete_headers@request_context@details@client@http@web@@QEAAXXZ; web::http::client::details::request_context::complete_headers(void)
0x18005981c  mov     rcx, [r14+18h]
0x180059820  add     rcx, 90h
0x180059827  lea     rdx, ?HEAD@methods@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::methods::HEAD
0x18005982e  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator==<ushort>(std::wstring const &,std::wstring const &)
0x180059833  mov     rcx, r14; this
0x180059836  test    al, al
0x180059838  jz      short loc_180059854
0x18005983a  xor     r8d, r8d; unsigned __int64
0x18005983d  xor     edx, edx; unsigned __int8 *
0x18005983f  call    ?allocate_request_space@winhttp_request_context@details@client@http@web@@QEAAXPEAE_K@Z; web::http::client::details::winhttp_request_context::allocate_request_space(uchar *,unsigned __int64)
0x180059844  xor     edx, edx; unsigned __int64
0x180059846  mov     rcx, r14; this
0x180059849  call    ?complete_request@request_context@details@client@http@web@@QEAAX_K@Z; web::http::client::details::request_context::complete_request(unsigned __int64)
0x18005984e  nop
0x18005984f  jmp     loc_180059AEE
0x180059854  mov     r8b, 1; bool
0x180059857  xor     edx, edx; unsigned int
0x180059859  call    ?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z; web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)
0x18005985e  nop
0x18005985f  jmp     loc_180059AEE
0x180059864  mov     edx, [r9]
0x180059867  lea     rcx, [rsp+1D8h+Src]; Src
0x18005986f  call    _anonymous_namespace___generate_security_failure_message
0x180059874  mov     rdx, rax
0x180059877  xorps   xmm0, xmm0
0x18005987a  movups  [rsp+1D8h+var_A0], xmm0
0x180059882  lea     rcx, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x180059889  mov     [rsp+1D8h+var_A8], rcx
0x180059891  mov     [rsp+1D8h+var_90], r13d
0x180059899  lea     rcx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1800598a0  mov     [rsp+1D8h+var_88], rcx
0x1800598a8  movups  xmmword ptr [rsp+1D8h+var_80], xmm0
0x1800598b0  mov     qword ptr [rsp+1D8h+var_70], r13
0x1800598b8  mov     qword ptr [rsp+1D8h+var_70+8], r13
0x1800598c0  mov     rcx, [rax]
0x1800598c3  mov     [rsp+1D8h+var_80], rcx
0x1800598cb  mov     rcx, [rax+8]
0x1800598cf  mov     [rsp+1D8h+var_80+8], rcx
0x1800598d7  mov     rax, [rax+10h]
0x1800598db  mov     qword ptr [rsp+1D8h+var_70], rax
0x1800598e3  mov     rax, [rdx+18h]
0x1800598e7  mov     qword ptr [rsp+1D8h+var_70+8], rax
0x1800598ef  mov     qword ptr [rdx+18h], 0Fh
0x1800598f7  mov     byte ptr [rdx], 0
0x1800598fa  mov     [rdx+10h], r13
0x1800598fe  mov     qword ptr [rdx+18h], 0Fh
0x180059906  mov     byte ptr [rdx], 0
0x180059909  lea     rdx, [rsp+1D8h+var_A8]
0x180059911  mov     rcx, r14
0x180059914  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x180059919  nop
0x18005991a  mov     rdx, qword ptr [rsp+1D8h+var_70+8]
0x180059922  cmp     rdx, 0Fh
0x180059926  jbe     short loc_18005995D
0x180059928  inc     rdx
0x18005992b  mov     rcx, [rsp+1D8h+var_80]
0x180059933  cmp     rdx, 1000h
0x18005993a  jb      short loc_180059958
0x18005993c  mov     rax, [rcx-8]
0x180059940  sub     rcx, rax
0x180059943  sub     rcx, 8
0x180059947  cmp     rcx, 1Fh
0x18005994b  ja      loc_18005A4E7
0x180059951  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180059955  mov     rcx, rax; void *
0x180059958  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005995d  mov     qword ptr [rsp+1D8h+var_70], r13
0x180059965  mov     qword ptr [rsp+1D8h+var_70+8], 0Fh
0x180059971  mov     byte ptr [rsp+1D8h+var_80], 0
0x180059979  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180059980  mov     [rsp+1D8h+var_A8], rax
0x180059988  lea     rcx, [rsp+1D8h+var_A0]
0x180059990  call    _o___std_exception_destroy_0
0x180059995  nop
0x180059996  test    rdi, rdi
0x180059999  jz      loc_18005AB2F
0x18005999f  mov     esi, 0FFFFFFFFh
0x1800599a4  jmp     loc_18005AAFC
0x1800599a9  mov     rax, [r14+80h]
  ... truncated ...
```
