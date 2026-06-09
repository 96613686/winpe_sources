# web::http::client::details::winhttp_client::completion_callback(void *,unsigned __int64,ulong,void *,ulong)

- ea: `0x1800492f0`
- end: `0x18004aa45`
- name: `?completion_callback@winhttp_client@details@client@http@web@@CAXPEAX_KK0K@Z`
- size: `5973`
- prototype: `void __stdcall(HINTERNET hInternet, DWORD_PTR dwContext, DWORD dwInternetStatus, LPVOID lpvStatusInformation, DWORD dwStatusInformationLength)`
- caller_count: `0`
- callee_count: `40`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180007270`
- `0x180007640`
- `0x180007b62`
- `0x180027760`
- `0x180029c30`
- `0x18002a210`
- `0x18002a220`
- `0x18002a360`
- `0x18002ac30`
- `0x18002b430`
- `0x18003db90`
- `0x1800420a0`
- `0x180043160`
- `0x180043270`
- `0x180046030`
- `0x180047400`
- `0x180047760`
- `0x180048460`
- `0x180048d50`
- `0x180048db0`
- `0x180048fb0`
- `0x180049250`
- `0x1800492f0`
- `0x18004ae20`
- `0x18004b2c0`
- `0x18004c980`
- `0x18004dd80`
- `0x18004e370`
- `0x18004e6d0`
- `0x180051d48`
- `0x1800522a2`
- `0x1800726d8`
- `0x18007c24c`
- `0x18007c810`
- `0x18007cbb0`
- `0x1800839f8`
- `0x1800848e4`
- `0x1800849dc`
- `0x180094184`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800498b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049af6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a274`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800498b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049af6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a274`
- `WINHTTP!WinHttpReceiveResponse` at `0x18004a00f`
- `WINHTTP!WinHttpReceiveResponse` at `0x18004a266`
- `WINHTTP!WinHttpReceiveResponse` at `0x18004a00f`
- `WINHTTP!WinHttpReceiveResponse` at `0x18004a266`
- `WINHTTP!WinHttpQueryHeaders` at `0x18004944e`
- `WINHTTP!WinHttpQueryHeaders` at `0x180049492`
- `WINHTTP!WinHttpQueryHeaders` at `0x180049864`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800498a8`
- `WINHTTP!WinHttpQueryHeaders` at `0x18004944e`
- `WINHTTP!WinHttpQueryHeaders` at `0x180049492`
- `WINHTTP!WinHttpQueryHeaders` at `0x180049864`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800498a8`
- `WINHTTP!WinHttpReadData` at `0x180049ae8`
- `WINHTTP!WinHttpReadData` at `0x180049ae8`

## string_xrefs

- `0x180049b1e`: `WinHttpReadData`
- `0x180049d8e`: `Received incomplete compressed stream`
- `0x18004a4f5`: `Received incomplete compressed stream`

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
0x1800492f0  test    rdx, rdx
0x1800492f3  jz      locret_18004A9C9
0x1800492f9  push    rbx
0x1800492fa  push    rsi
0x1800492fb  push    rdi
0x1800492fc  push    r12
0x1800492fe  push    r13
0x180049300  push    r14
0x180049302  push    r15
0x180049304  sub     rsp, 1A0h
0x18004930b  movaps  [rsp+1D8h+var_48], xmm6
0x180049313  mov     rax, cs:__security_cookie
0x18004931a  xor     rax, rsp
0x18004931d  mov     [rsp+1D8h+var_58], rax
0x180049325  mov     rbx, r9
0x180049328  mov     rdi, rdx
0x18004932b  mov     r15, rcx
0x18004932e  xor     r13d, r13d
0x180049331  mov     rdx, [rdx+8]
0x180049335  cmp     r8d, 800h
0x18004933c  jnz     short loc_180049373
0x18004933e  test    rdx, rdx
0x180049341  jz      short loc_180049361
0x180049343  mov     esi, 0FFFFFFFFh
0x180049348  lock xadd [rdx+0Ch], esi
0x18004934d  cmp     esi, 1
0x180049350  jnz     short loc_180049361
0x180049352  mov     rax, [rdx]
0x180049355  mov     rcx, rdx
0x180049358  mov     rax, [rax+8]
0x18004935c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049361  mov     edx, 10h; struct std::nothrow_t *
0x180049366  mov     rcx, rdi; void *
0x180049369  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004936e  jmp     loc_18004A99F
0x180049373  xorps   xmm6, xmm6
0x180049376  movdqa  xmmword ptr [rsp+1D8h+var_168], xmm6
0x18004937c  test    rdx, rdx
0x18004937f  jz      short loc_1800493BD
0x180049381  mov     eax, [rdx+8]
0x180049384  test    eax, eax
0x180049386  jz      short loc_1800493BD
0x180049388  nop     dword ptr [rax+rax+00000000h]
0x180049390  lea     ecx, [rax+1]
0x180049393  lock cmpxchg [rdx+8], ecx
0x180049398  jz      short loc_1800493A4
0x18004939a  test    eax, eax
0x18004939c  jnz     short loc_180049390
0x18004939e  movdqa  xmm0, xmm6
0x1800493a2  jmp     short loc_1800493C0
0x1800493a4  mov     r14, [rdi]
0x1800493a7  mov     [rsp+1D8h+var_168], r14
0x1800493ac  mov     rdi, [rdi+8]
0x1800493b0  mov     [rsp+1D8h+var_168+8], rdi
0x1800493b5  movdqa  xmm6, xmmword ptr [rsp+1D8h+var_168]
0x1800493bb  jmp     short loc_1800493CF
0x1800493bd  xorps   xmm0, xmm0
0x1800493c0  psrldq  xmm0, 8
0x1800493c5  movq    r14, xmm6
0x1800493ca  movq    rdi, xmm0
0x1800493cf  test    r14, r14
0x1800493d2  jnz     short loc_1800493E7
0x1800493d4  test    rdi, rdi
0x1800493d7  jz      loc_18004A99F
0x1800493dd  mov     esi, 0FFFFFFFFh
0x1800493e2  jmp     loc_18004A96C
0x1800493e7  cmp     r8d, 40000h
0x1800493ee  ja      loc_180049EB0
0x1800493f4  jz      loc_180049A17
0x1800493fa  cmp     r8d, 10h
0x1800493fe  jz      loc_1800499FB
0x180049404  cmp     r8d, 4000h
0x18004940b  jz      loc_180049819
0x180049411  mov     eax, 10000h
0x180049416  cmp     r8d, eax
0x180049419  jz      loc_1800496D4
0x18004941f  cmp     r8d, 20000h
0x180049426  jnz     loc_180049EE0
0x18004942c  mov     [rsp+1D8h+dwBufferLength], r13d
0x180049431  mov     [rsp+1D8h+lpdwIndex], r13; lpdwIndex
0x180049436  lea     rax, [rsp+1D8h+dwBufferLength]
0x18004943b  mov     [rsp+1D8h+lpdwBufferLength], rax; lpdwBufferLength
0x180049440  xor     r9d, r9d; lpBuffer
0x180049443  xor     r8d, r8d; pwszName
0x180049446  mov     edx, 16h; dwInfoLevel
0x18004944b  mov     rcx, r15; hRequest
0x18004944e  call    cs:__imp_WinHttpQueryHeaders
0x180049454  xorps   xmm0, xmm0
0x180049457  movdqu  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x18004945d  mov     qword ptr [rsp+1D8h+var_178], r13
0x180049462  mov     edx, [rsp+1D8h+dwBufferLength]
0x180049466  lea     rcx, [rsp+1D8h+lpBuffer]
0x18004946b  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180049470  mov     rsi, [rsp+1D8h+lpBuffer]
0x180049475  mov     [rsp+1D8h+lpdwIndex], r13; lpdwIndex
0x18004947a  lea     rax, [rsp+1D8h+dwBufferLength]
0x18004947f  mov     [rsp+1D8h+lpdwBufferLength], rax; lpdwBufferLength
0x180049484  mov     r9, rsi; lpBuffer
0x180049487  xor     r8d, r8d; pwszName
0x18004948a  mov     edx, 16h; dwInfoLevel
0x18004948f  mov     rcx, r15; hRequest
0x180049492  call    cs:__imp_WinHttpQueryHeaders
0x180049498  test    eax, eax
0x18004949a  jnz     loc_180049560
0x1800494a0  call    cs:__imp_GetLastError
0x1800494a6  mov     ebx, eax
0x1800494a8  xorps   xmm0, xmm0
0x1800494ab  movups  xmmword ptr [rsp+1D8h+var_F0], xmm0
0x1800494b3  mov     qword ptr [rsp+1D8h+var_E0], r13
0x1800494bb  mov     qword ptr [rsp+1D8h+var_E0+8], r13
0x1800494c3  mov     r8d, 13h
0x1800494c9  lea     rdx, aWinhttpqueryhe_0; "WinHttpQueryHeaders"
0x1800494d0  lea     rcx, [rsp+1D8h+var_F0]
0x1800494d8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800494dd  nop
0x1800494de  lea     r8, [rsp+1D8h+var_F0]
0x1800494e6  mov     edx, ebx
0x1800494e8  lea     rcx, [rsp+1D8h+Src]; Src
0x1800494f0  call    web__http__client__details__build_error_msg
0x1800494f5  nop
0x1800494f6  mov     r8, rax
0x1800494f9  mov     edx, ebx
0x1800494fb  mov     rcx, r14
0x1800494fe  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::string const &)
0x180049503  nop
0x180049504  lea     rcx, [rsp+1D8h+Src]
0x18004950c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180049511  nop
0x180049512  mov     rdx, qword ptr [rsp+1D8h+var_E0+8]
0x18004951a  cmp     rdx, 0Fh
0x18004951e  jbe     short loc_18004955B
0x180049520  mov     rax, [rsp+1D8h+var_F0]
0x180049528  inc     rdx; struct std::nothrow_t *
0x18004952b  cmp     rdx, 1000h
0x180049532  jb      short loc_180049552
0x180049534  mov     rcx, [rax-8]
0x180049538  sub     rax, rcx
0x18004953b  sub     rax, 8
0x18004953f  cmp     rax, 1Fh
0x180049543  ja      short loc_18004954B
0x180049545  add     rdx, 27h ; '''
0x180049549  jmp     short loc_180049555
0x18004954b  mov     ecx, 5
0x180049550  int     29h; Win8: RtlFailFast(ecx)
0x180049552  mov     rcx, rax; void *
0x180049555  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004955a  nop
0x18004955b  jmp     loc_18004995E
0x180049560  lea     r8, [r14+28h]
0x180049564  mov     rdx, rsi; this
0x180049567  mov     rcx, r15; hRequest
0x18004956a  call    web__http__client__details__parse_winhttp_headers
0x18004956f  mov     rax, [r14+28h]
0x180049573  movzx   ecx, word ptr [rax+88h]
0x18004957a  mov     eax, 191h
0x18004957f  cmp     cx, ax
0x180049582  jz      short loc_18004958E
0x180049584  mov     eax, 197h
0x180049589  cmp     cx, ax
0x18004958c  jnz     short loc_180049601
0x18004958e  xor     r8d, r8d
0x180049591  lea     rdx, [rsp+1D8h+var_168]
0x180049596  mov     rcx, r15
0x180049599  call    ?handle_authentication_failure@winhttp_client@details@client@http@web@@CA_NPEAXAEBV?$shared_ptr@Vwinhttp_request_context@details@client@http@web@@@std@@K@Z; web::http::client::details::winhttp_client::handle_authentication_failure(void *,std::shared_ptr<web::http::client::details::winhttp_request_context> const &,ulong)
0x18004959e  test    al, al
0x1800495a0  jz      short loc_1800495F7
0x1800495a2  mov     rax, [rsp+1D8h+lpBuffer]
0x1800495a7  test    rax, rax
0x1800495aa  jz      loc_180049FBA
0x1800495b0  mov     rdx, qword ptr [rsp+1D8h+var_178]
0x1800495b5  sub     rdx, rax; struct std::nothrow_t *
0x1800495b8  cmp     rdx, 1000h
0x1800495bf  jb      short loc_1800495DC
0x1800495c1  mov     rcx, [rax-8]
0x1800495c5  sub     rax, rcx
0x1800495c8  sub     rax, 8
0x1800495cc  cmp     rax, 1Fh
0x1800495d0  ja      loc_18004A357
0x1800495d6  add     rdx, 27h ; '''
0x1800495da  jmp     short loc_1800495DF
0x1800495dc  mov     rcx, rax; void *
0x1800495df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800495e4  xorps   xmm0, xmm0
0x1800495e7  movdqu  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x1800495ed  mov     qword ptr [rsp+1D8h+var_178], r13
0x1800495f2  jmp     loc_180049FBA
0x1800495f7  mov     rdi, [rsp+1D8h+var_168+8]
0x1800495fc  mov     r14, [rsp+1D8h+var_168]
0x180049601  mov     rcx, r14; this
0x180049604  call    ?handle_compression@request_context@details@client@http@web@@QEAA_NXZ; web::http::client::details::request_context::handle_compression(void)
0x180049609  test    al, al
0x18004960b  jnz     short loc_180049612
0x18004960d  jmp     loc_18004995E
0x180049612  cmp     qword ptr [r14+60h], 0
0x180049617  jz      short loc_180049684
0x180049619  mov     rcx, [r14+8]; this
0x18004961d  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x180049622  cmp     byte ptr [rax+1A8h], 0
0x180049629  jnz     short loc_180049684
0x18004962b  mov     ecx, 10h; Size
0x180049630  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049635  mov     [rsp+1D8h+var_198], rax
0x18004963a  test    rax, rax
0x18004963d  jz      short loc_18004964F
0x18004963f  mov     [rax], r13
0x180049642  mov     dword ptr [rax+8], 1
0x180049649  mov     byte ptr [rax+0Ch], 0
0x18004964d  jmp     short loc_180049652
0x18004964f  mov     rax, r13
0x180049652  mov     [rsp+1D8h+var_198], rax
0x180049657  lea     rcx, [r14+140h]
0x18004965e  lea     rdx, [rsp+1D8h+var_198]
0x180049663  call    ??$?4U?$default_delete@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@@std@@$0A@@?$unique_ptr@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@U?$default_delete@V_chunk_helper@compression_state@winhttp_request_context@details@client@http@web@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>::operator=<std::default_delete<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper>,0>(std::unique_ptr<web::http::client::details::winhttp_request_context::compression_state::_chunk_helper> &&)
0x180049668  mov     rcx, [rsp+1D8h+var_198]; void *
0x18004966d  test    rcx, rcx
0x180049670  jz      short loc_18004967C
0x180049672  mov     edx, 10h; struct std::nothrow_t *
0x180049677  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004967c  mov     byte ptr [r14+133h], 1
0x180049684  mov     rcx, r14; this
0x180049687  call    ?complete_headers@request_context@details@client@http@web@@QEAAXXZ; web::http::client::details::request_context::complete_headers(void)
0x18004968c  mov     rcx, [r14+18h]
0x180049690  add     rcx, 90h
0x180049697  lea     rdx, ?HEAD@methods@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::methods::HEAD
0x18004969e  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator==<ushort>(std::wstring const &,std::wstring const &)
0x1800496a3  mov     rcx, r14; this
0x1800496a6  test    al, al
0x1800496a8  jz      short loc_1800496C4
0x1800496aa  xor     r8d, r8d; unsigned __int64
0x1800496ad  xor     edx, edx; unsigned __int8 *
0x1800496af  call    ?allocate_request_space@winhttp_request_context@details@client@http@web@@QEAAXPEAE_K@Z; web::http::client::details::winhttp_request_context::allocate_request_space(uchar *,unsigned __int64)
0x1800496b4  xor     edx, edx; unsigned __int64
0x1800496b6  mov     rcx, r14; this
0x1800496b9  call    ?complete_request@request_context@details@client@http@web@@QEAAX_K@Z; web::http::client::details::request_context::complete_request(unsigned __int64)
0x1800496be  nop
0x1800496bf  jmp     loc_18004995E
0x1800496c4  mov     r8b, 1; bool
0x1800496c7  xor     edx, edx; unsigned int
0x1800496c9  call    ?read_next_response_chunk@winhttp_client@details@client@http@web@@CAXPEAVwinhttp_request_context@2345@K_N@Z; web::http::client::details::winhttp_client::read_next_response_chunk(web::http::client::details::winhttp_request_context *,ulong,bool)
0x1800496ce  nop
0x1800496cf  jmp     loc_18004995E
0x1800496d4  mov     edx, [r9]
0x1800496d7  lea     rcx, [rsp+1D8h+Src]; Src
0x1800496df  call    _anonymous_namespace___generate_security_failure_message
0x1800496e4  mov     rdx, rax
0x1800496e7  xorps   xmm0, xmm0
0x1800496ea  movups  [rsp+1D8h+var_A0], xmm0
0x1800496f2  lea     rcx, ??_7http_exception@http@web@@6B@; const web::http::http_exception::`vftable'
0x1800496f9  mov     [rsp+1D8h+var_A8], rcx
0x180049701  mov     [rsp+1D8h+var_90], r13d
0x180049709  lea     rcx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180049710  mov     [rsp+1D8h+var_88], rcx
0x180049718  movups  xmmword ptr [rsp+1D8h+var_80], xmm0
0x180049720  mov     qword ptr [rsp+1D8h+var_70], r13
0x180049728  mov     qword ptr [rsp+1D8h+var_70+8], r13
0x180049730  mov     rcx, [rax]
0x180049733  mov     [rsp+1D8h+var_80], rcx
0x18004973b  mov     rcx, [rax+8]
0x18004973f  mov     [rsp+1D8h+var_80+8], rcx
0x180049747  mov     rax, [rax+10h]
0x18004974b  mov     qword ptr [rsp+1D8h+var_70], rax
0x180049753  mov     rax, [rdx+18h]
0x180049757  mov     qword ptr [rsp+1D8h+var_70+8], rax
0x18004975f  mov     qword ptr [rdx+18h], 0Fh
0x180049767  mov     byte ptr [rdx], 0
0x18004976a  mov     [rdx+10h], r13
0x18004976e  mov     qword ptr [rdx+18h], 0Fh
0x180049776  mov     byte ptr [rdx], 0
0x180049779  lea     rdx, [rsp+1D8h+var_A8]
0x180049781  mov     rcx, r14
0x180049784  call    ??$report_exception@Vhttp_exception@http@web@@@request_context@details@client@http@web@@QEAAXAEBVhttp_exception@34@@Z; web::http::client::details::request_context::report_exception<web::http::http_exception>(web::http::http_exception const &)
0x180049789  nop
0x18004978a  mov     rdx, qword ptr [rsp+1D8h+var_70+8]
0x180049792  cmp     rdx, 0Fh
0x180049796  jbe     short loc_1800497CD
0x180049798  inc     rdx
0x18004979b  mov     rcx, [rsp+1D8h+var_80]
0x1800497a3  cmp     rdx, 1000h
0x1800497aa  jb      short loc_1800497C8
0x1800497ac  mov     rax, [rcx-8]
0x1800497b0  sub     rcx, rax
0x1800497b3  sub     rcx, 8
0x1800497b7  cmp     rcx, 1Fh
0x1800497bb  ja      loc_18004A357
0x1800497c1  add     rdx, 27h ; '''; struct std::nothrow_t *
0x1800497c5  mov     rcx, rax; void *
0x1800497c8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800497cd  mov     qword ptr [rsp+1D8h+var_70], r13
0x1800497d5  mov     qword ptr [rsp+1D8h+var_70+8], 0Fh
0x1800497e1  mov     byte ptr [rsp+1D8h+var_80], 0
0x1800497e9  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800497f0  mov     [rsp+1D8h+var_A8], rax
0x1800497f8  lea     rcx, [rsp+1D8h+var_A0]
0x180049800  call    _o___std_exception_destroy_0
0x180049805  nop
0x180049806  test    rdi, rdi
0x180049809  jz      loc_18004A99F
0x18004980f  mov     esi, 0FFFFFFFFh
0x180049814  jmp     loc_18004A96C
0x180049819  mov     rax, [r14+80h]
  ... truncated ...
```
