# InitializeSstpServer

- ea: `0x18000b2e0`
- end: `0x18000b9f3`
- name: `InitializeSstpServer`
- size: `1811`
- prototype: `__int64 __fastcall(char)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005920`
- `0x18000a0d4`
- `0x180014840`

## callees

- `0x18000827c`
- `0x180008360`
- `0x180008434`
- `0x18000b2e0`
- `0x18000bc78`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b824`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18000b80b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18000b80b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18000b7e5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18000b913`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18000b7e5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18000b913`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18000b7d1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18000b7d1`
- `rtutils!RouterLogEventStringW` at `0x18000b60e`
- `rtutils!RouterLogEventStringW` at `0x18000b6e9`
- `rtutils!RouterLogEventStringW` at `0x18000b7ae`
- `rtutils!RouterLogEventStringW` at `0x18000b60e`
- `rtutils!RouterLogEventStringW` at `0x18000b6e9`
- `rtutils!RouterLogEventStringW` at `0x18000b7ae`
- `HTTPAPI!HttpCreateRequestQueue` at `0x18000b673`
- `HTTPAPI!HttpCreateRequestQueue` at `0x18000b673`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x18000b738`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x18000b738`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18000b939`
- `HTTPAPI!HttpCloseRequestQueue` at `0x18000b939`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18000b955`
- `HTTPAPI!HttpCloseUrlGroup` at `0x18000b955`
- `HTTPAPI!HttpCreateUrlGroup` at `0x18000b552`
- `HTTPAPI!HttpCreateUrlGroup` at `0x18000b552`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x18000b5db`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x18000b5db`
- `HTTPAPI!HttpInitialize` at `0x18000b404`
- `HTTPAPI!HttpInitialize` at `0x18000b404`
- `HTTPAPI!HttpCreateServerSession` at `0x18000b507`
- `HTTPAPI!HttpCreateServerSession` at `0x18000b507`
- `HTTPAPI!HttpTerminate` at `0x18000b987`
- `HTTPAPI!HttpTerminate` at `0x18000b987`
- `HTTPAPI!HttpCloseServerSession` at `0x18000b971`
- `HTTPAPI!HttpCloseServerSession` at `0x18000b971`
- `sstpcfg!GetUrlForConfig` at `0x18000b5bd`
- `sstpcfg!GetUrlForConfig` at `0x18000b5bd`
- `sstpcfg!GetCryptoBindingInfo` at `0x18000b49b`
- `sstpcfg!GetCryptoBindingInfo` at `0x18000b49b`
- `sstpcfg!GetCryptoBindingSupportedAlgoInfo` at `0x18000b463`
- `sstpcfg!GetCryptoBindingSupportedAlgoInfo` at `0x18000b463`
- `sstpcfg!GetSstpServerConfig` at `0x18000b3e0`
- `sstpcfg!GetSstpServerConfig` at `0x18000b3e0`

## string_xrefs

- `0x18000b52d`: `HttpCreateServerSession fails with error %d (%d)`
- `0x18000b578`: `HttpCreateUrlGroup fails with error %d (%d)`
- `0x18000b846`: `Unable to create ThreadpoolI/O...0x%x (%d)`

## pseudocode

```c
__int64 __fastcall InitializeSstpServer(char a1)
{
  DWORD dwErrorCode; // edi
  HTTPAPI_VERSION v3; // ebx
  HTTPAPI_VERSION v4; // ecx
  ULONG v5; // eax
  LPVOID v6; // rdx
  __int64 v7; // r9
  DWORD CryptoBindingInfo; // eax
  ULONG ServerSession; // eax
  ULONG UrlGroup; // eax
  void *v11; // rcx
  ULONG RequestQueue; // eax
  void *v13; // rcx
  ULONG v14; // eax
  void *v15; // rcx
  char *v16; // rcx
  PTP_IO ThreadpoolIo; // rax
  LPVOID v18; // rcx
  DWORD LastError; // eax
  DWORD v20; // r15d
  char v21; // bl
  unsigned int v22; // r12d
  DWORD v23; // eax
  ULONG v24; // eax
  __int16 v26; // [rsp+40h] [rbp-C0h] BYREF
  char v27; // [rsp+42h] [rbp-BEh]
  HTTPAPI_VERSION Version; // [rsp+44h] [rbp-BCh]
  __int128 PropertyInformation; // [rsp+48h] [rbp-B8h] BYREF
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  char v31[2044]; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR pFullyQualifiedUrl[264]; // [rsp+860h] [rbp+760h] BYREF

  Version = (HTTPAPI_VERSION)2;
  memset_0(pFullyQualifiedUrl, 0, 0x208u);
  v30 = 0;
  v27 = 0;
  v26 = 0;
  PropertyInformation = 0;
  memset_0(v31, 0, sizeof(v31));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v30) = 0;
    FormatRRASErrorString((wchar_t *)&v30, L"Entering %ws", L"InitializeSstpServer");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v30);
  }
  dwErrorCode = 0;
  if ( (a1 & 1) != 0 )
    SetSstpConfigFlag(2, 1);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)SstpSvcGlobals + 191, 1, 1) )
    return dwErrorCode;
  GetSstpServerConfig(&v26);
  v3 = Version;
  v4 = Version;
  *((_DWORD *)SstpSvcGlobals + 160) = 10;
  v5 = HttpInitialize(v4, 3u, 0);
  dwErrorCode = v5;
  if ( !v5 )
  {
    GetCryptoBindingSupportedAlgoInfo(0, (char *)SstpSvcGlobals + 644);
    v6 = SstpSvcGlobals;
    LOBYTE(v7) = 1;
    LOBYTE(v6) = *((_BYTE *)SstpSvcGlobals + 644);
    CryptoBindingInfo = GetCryptoBindingInfo(
                          0,
                          v6,
                          0,
                          v7,
                          0,
                          (char *)SstpSvcGlobals + 645,
                          (char *)SstpSvcGlobals + 665);
    dwErrorCode = CryptoBindingInfo;
    if ( CryptoBindingInfo )
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_63;
      LOWORD(v30) = 0;
      FormatRRASErrorString((wchar_t *)&v30, L"GetCryptoBindingInfo failed with error %d", CryptoBindingInfo);
    }
    else
    {
      ServerSession = HttpCreateServerSession(v3, (PHTTP_SERVER_SESSION_ID)SstpSvcGlobals + 6, 0);
      dwErrorCode = ServerSession;
      if ( !ServerSession )
      {
        UrlGroup = HttpCreateUrlGroup(*((_QWORD *)SstpSvcGlobals + 6), (PHTTP_URL_GROUP_ID)SstpSvcGlobals + 7, 0);
        dwErrorCode = UrlGroup;
        if ( UrlGroup )
        {
          if ( (byte_18002D803 & 8) != 0 )
          {
            LOWORD(v30) = 0;
            FormatRRASErrorString((wchar_t *)&v30, L"HttpCreateUrlGroup fails with error %d (%d)", UrlGroup, UrlGroup);
            if ( (byte_18002D803 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v30);
          }
        }
        else
        {
          GetUrlForConfig(&v26, &qword_180023068, pFullyQualifiedUrl);
          dwErrorCode = HttpAddUrlToUrlGroup(*((_QWORD *)SstpSvcGlobals + 7), pFullyQualifiedUrl, 0, 0);
          if ( dwErrorCode )
          {
            v11 = (void *)*((_QWORD *)SstpSvcGlobals + 9);
            if ( v11 )
              RouterLogEventStringW(v11, 1u, 0x16u, 0, 0, dwErrorCode, 0);
            if ( (byte_18002D803 & 8) != 0 )
            {
              LOWORD(v30) = 0;
              FormatRRASErrorString(
                (wchar_t *)&v30,
                L"Error adding the URL to URL group (%d - %d)",
                dwErrorCode,
                dwErrorCode);
              if ( (byte_18002D803 & 8) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v30);
            }
          }
          else
          {
            RequestQueue = HttpCreateRequestQueue(v3, 0, 0, 0, (PHANDLE)SstpSvcGlobals + 8);
            dwErrorCode = RequestQueue;
            if ( RequestQueue )
            {
              if ( (byte_18002D803 & 8) != 0 )
              {
                LOWORD(v30) = 0;
                FormatRRASErrorString(
                  (wchar_t *)&v30,
                  L"Error setting up the request queue (%d - %d)",
                  RequestQueue,
                  RequestQueue);
                if ( (byte_18002D803 & 8) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v30);
              }
              v13 = (void *)*((_QWORD *)SstpSvcGlobals + 9);
              if ( v13 )
                RouterLogEventStringW(v13, 1u, 0x16u, 0, 0, dwErrorCode, 0);
            }
            else
            {
              if ( (byte_18002D803 & 0x10) != 0 )
                McTemplateU0z_EventWriteTransfer(
                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  RasSSTPSvcTraceInfo,
                  L"Successfully setup the request queue");
              LODWORD(PropertyInformation) = PropertyInformation | 1;
              *((_QWORD *)&PropertyInformation + 1) = *((_QWORD *)SstpSvcGlobals + 8);
              v14 = HttpSetUrlGroupProperty(
                      *((_QWORD *)SstpSvcGlobals + 7),
                      HttpServerBindingProperty,
                      &PropertyInformation,
                      0x10u);
              dwErrorCode = v14;
              if ( v14 )
              {
                if ( (byte_18002D803 & 8) != 0 )
                {
                  LOWORD(v30) = 0;
                  FormatRRASErrorString(
                    (wchar_t *)&v30,
                    L"Unable to setup the binding between the UrlGroup and the request queue (%d - %d)",
                    v14,
                    v14);
                  if ( (byte_18002D803 & 8) != 0 )
                    McTemplateU0z_EventWriteTransfer(
                      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      RasSSTPSvcTraceError,
                      &v30);
                }
                v15 = (void *)*((_QWORD *)SstpSvcGlobals + 9);
                if ( v15 )
                  RouterLogEventStringW(v15, 1u, 0x16u, 0, 0, dwErrorCode, 0);
              }
              else
              {
                v16 = (char *)SstpSvcGlobals;
                if ( *((_QWORD *)SstpSvcGlobals + 21) )
                {
                  WaitForThreadpoolIoCallbacks(*((PTP_IO *)SstpSvcGlobals + 21), 0);
                  CloseThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
                  v16 = (char *)SstpSvcGlobals;
                  *((_QWORD *)SstpSvcGlobals + 21) = 0;
                }
                ThreadpoolIo = CreateThreadpoolIo(
                                 *((HANDLE *)v16 + 8),
                                 (PTP_WIN32_IO_CALLBACK)HttpThreadPoolRequestQueueCallback,
                                 0,
                                 (PTP_CALLBACK_ENVIRON)(v16 + 80));
                v18 = SstpSvcGlobals;
                *((_QWORD *)SstpSvcGlobals + 21) = ThreadpoolIo;
                if ( ThreadpoolIo )
                {
                  v20 = 0;
                  v21 = 0;
                  v22 = 0;
                  if ( *((_DWORD *)v18 + 160) )
                  {
                    do
                    {
                      v23 = PostNewHttpRequest();
                      v18 = SstpSvcGlobals;
                      v20 = v23;
                      if ( !v23 )
                        v21 = 1;
                      ++v22;
                    }
                    while ( v22 < *((_DWORD *)SstpSvcGlobals + 160) );
                    if ( v21 )
                    {
                      *((_DWORD *)SstpSvcGlobals + 191) = 1;
                      _InterlockedExchange((volatile __int32 *)v18 + 191, 1);
                      return dwErrorCode;
                    }
                  }
                  if ( (byte_18002D803 & 8) != 0 )
                  {
                    LOWORD(v30) = 0;
                    FormatRRASErrorString((wchar_t *)&v30, L"Unable to setup listener successfully - %d", v20);
                    if ( (byte_18002D803 & 8) != 0 )
                      McTemplateU0z_EventWriteTransfer(
                        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        RasSSTPSvcTraceError,
                        &v30);
                    v18 = SstpSvcGlobals;
                  }
                  dwErrorCode = v20;
                  CloseThreadpoolIo(*((PTP_IO *)v18 + 21));
                  *((_QWORD *)SstpSvcGlobals + 21) = 0;
                }
                else
                {
                  LastError = GetLastError();
                  dwErrorCode = LastError;
                  if ( (byte_18002D803 & 8) != 0 )
                  {
                    LOWORD(v30) = 0;
                    FormatRRASErrorString(
                      (wchar_t *)&v30,
                      L"Unable to create ThreadpoolI/O...0x%x (%d)",
                      LastError,
                      LastError);
                    if ( (byte_18002D803 & 8) != 0 )
                      McTemplateU0z_EventWriteTransfer(
                        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        RasSSTPSvcTraceError,
                        &v30);
                  }
                }
              }
              HttpCloseRequestQueue(*((HANDLE *)SstpSvcGlobals + 8));
              *((_QWORD *)SstpSvcGlobals + 8) = 0;
            }
          }
          HttpCloseUrlGroup(*((_QWORD *)SstpSvcGlobals + 7));
          *((_QWORD *)SstpSvcGlobals + 7) = 0;
        }
        HttpCloseServerSession(*((_QWORD *)SstpSvcGlobals + 6));
        *((_QWORD *)SstpSvcGlobals + 6) = 0;
        goto LABEL_63;
      }
      if ( (byte_18002D803 & 8) == 0 )
      {
LABEL_63:
        v24 = HttpTerminate(3u, 0);
        if ( v24 )
        {
          if ( (byte_18002D803 & 8) != 0 )
          {
            LOWORD(v30) = 0;
            FormatRRASErrorString((wchar_t *)&v30, L"HttpTerminate fails with error %d (%d)", v24, v24);
            if ( (byte_18002D803 & 8) != 0 )
              goto LABEL_66;
          }
        }
        return dwErrorCode;
      }
      LOWORD(v30) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v30,
        L"HttpCreateServerSession fails with error %d (%d)",
        ServerSession,
        ServerSession);
    }
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v30);
    goto LABEL_63;
  }
  if ( (byte_18002D803 & 8) != 0 )
  {
    LOWORD(v30) = 0;
    FormatRRASErrorString((wchar_t *)&v30, L"HttpInitialize fails with error %d (%d)", v5, v5);
    if ( (byte_18002D803 & 8) != 0 )
LABEL_66:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v30);
  }
  return dwErrorCode;
}

```

## disassembly

```asm
0x18000b2e0  push    rbp
0x18000b2e2  push    rbx
0x18000b2e3  push    rsi
0x18000b2e4  push    rdi
0x18000b2e5  push    r12
0x18000b2e7  push    r13
0x18000b2e9  push    r14
0x18000b2eb  push    r15
0x18000b2ed  lea     rbp, [rsp-988h]
0x18000b2f5  sub     rsp, 0A88h
0x18000b2fc  mov     rax, cs:__security_cookie
0x18000b303  xor     rax, rsp
0x18000b306  mov     [rbp+9C0h+var_50], rax
0x18000b30d  mov     ebx, ecx
0x18000b30f  mov     r14d, 2
0x18000b315  lea     rcx, [rbp+9C0h+pFullyQualifiedUrl]; void *
0x18000b31c  mov     dword ptr [rsp+0AC0h+Version.HttpApiMajorVersion], r14d
0x18000b321  xor     edx, edx; Val
0x18000b323  mov     r8d, 208h; Size
0x18000b329  xor     r13d, r13d
0x18000b32c  call    memset_0
0x18000b331  xor     eax, eax
0x18000b333  mov     [rsp+0AC0h+var_A60], r13d
0x18000b338  xorps   xmm0, xmm0
0x18000b33b  mov     [rsp+0AC0h+var_A7F], ax
0x18000b340  xor     edx, edx; Val
0x18000b342  mov     [rsp+40h], ax
0x18000b347  mov     r8d, 7FCh; Size
0x18000b34d  lea     rcx, [rsp+0AC0h+var_A5C]; void *
0x18000b352  movups  [rsp+0AC0h+PropertyInformation], xmm0
0x18000b357  call    memset_0
0x18000b35c  lea     r12d, [r14+0Eh]
0x18000b360  test    cs:byte_18002D803, r12b
0x18000b367  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b36e  jz      short loc_18000B3AB
0x18000b370  lea     r8, aInitializesstp; "InitializeSstpServer"
0x18000b377  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000b37d  lea     rdx, aEnteringWs; "Entering %ws"
0x18000b384  lea     rcx, [rsp+0AC0h+var_A60]
0x18000b389  call    FormatRRASErrorString
0x18000b38e  test    cs:byte_18002D803, r12b
0x18000b395  jz      short loc_18000B3AB
0x18000b397  lea     r8, [rsp+0AC0h+var_A60]
0x18000b39c  mov     rcx, r15
0x18000b39f  lea     rdx, RasSSTPSvcTraceInfo
0x18000b3a6  call    McTemplateU0z_EventWriteTransfer
0x18000b3ab  mov     esi, 1
0x18000b3b0  mov     edi, r13d
0x18000b3b3  test    sil, bl
0x18000b3b6  jz      short loc_18000B3C2
0x18000b3b8  mov     edx, esi
0x18000b3ba  mov     ecx, r14d
0x18000b3bd  call    SetSstpConfigFlag
0x18000b3c2  mov     rcx, cs:SstpSvcGlobals
0x18000b3c9  mov     eax, esi
0x18000b3cb  lock cmpxchg [rcx+2FCh], esi
0x18000b3d3  test    eax, eax
0x18000b3d5  jnz     loc_18000B9CE
0x18000b3db  lea     rcx, [rsp+0AC0h+var_A80]
0x18000b3e0  call    cs:__imp_GetSstpServerConfig
0x18000b3e6  mov     rax, cs:SstpSvcGlobals
0x18000b3ed  xor     r8d, r8d; pReserved
0x18000b3f0  mov     ebx, dword ptr [rsp+0AC0h+Version.HttpApiMajorVersion]
0x18000b3f4  mov     ecx, ebx; Version
0x18000b3f6  lea     edx, [r8+3]; Flags
0x18000b3fa  mov     dword ptr [rax+280h], 0Ah
0x18000b404  call    cs:__imp_HttpInitialize
0x18000b40a  mov     edi, eax
0x18000b40c  test    eax, eax
0x18000b40e  jz      short loc_18000B453
0x18000b410  mov     bl, 8
0x18000b412  test    cs:byte_18002D803, bl
0x18000b418  jz      loc_18000B9CE
0x18000b41e  mov     r9d, eax
0x18000b421  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000b427  mov     r8d, eax
0x18000b42a  lea     rdx, aHttpinitialize; "HttpInitialize fails with error %d (%d)"
0x18000b431  lea     rcx, [rsp+0AC0h+var_A60]
0x18000b436  call    FormatRRASErrorString
0x18000b43b  test    cs:byte_18002D803, bl
0x18000b441  jz      loc_18000B9CE
0x18000b447  lea     rdx, RasSSTPSvcTraceError
0x18000b44e  jmp     loc_18000B9C1
0x18000b453  mov     rdx, cs:SstpSvcGlobals
0x18000b45a  xor     ecx, ecx
0x18000b45c  add     rdx, 284h
0x18000b463  call    cs:__imp_GetCryptoBindingSupportedAlgoInfo
0x18000b469  mov     rdx, cs:SstpSvcGlobals
0x18000b470  mov     r9b, sil
0x18000b473  xor     r8d, r8d
0x18000b476  lea     rcx, [rdx+285h]
0x18000b47d  lea     rax, [rdx+299h]
0x18000b484  mov     dl, [rdx+284h]
0x18000b48a  mov     qword ptr [rsp+0AC0h+dwErrorIndex], rax
0x18000b48f  mov     qword ptr [rsp+0AC0h+dwErrorCode], rcx
0x18000b494  xor     ecx, ecx
0x18000b496  mov     [rsp+0AC0h+plpszSubStringArray], r13
0x18000b49b  call    cs:__imp_GetCryptoBindingInfo
0x18000b4a1  lea     r14, RasSSTPSvcTraceError
0x18000b4a8  mov     edi, eax
0x18000b4aa  test    eax, eax
0x18000b4ac  jz      short loc_18000B4F7
0x18000b4ae  mov     bl, 8
0x18000b4b0  test    cs:byte_18002D803, bl
0x18000b4b6  jz      loc_18000B982
0x18000b4bc  mov     r8d, eax
0x18000b4bf  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000b4c5  lea     rdx, aGetcryptobindi; "GetCryptoBindingInfo failed with error "...
0x18000b4cc  lea     rcx, [rsp+0AC0h+var_A60]
0x18000b4d1  call    FormatRRASErrorString
0x18000b4d6  test    cs:byte_18002D803, bl
0x18000b4dc  jz      loc_18000B982
0x18000b4e2  lea     r8, [rsp+0AC0h+var_A60]
0x18000b4e7  mov     rdx, r14
0x18000b4ea  mov     rcx, r15
0x18000b4ed  call    McTemplateU0z_EventWriteTransfer
0x18000b4f2  jmp     loc_18000B982
0x18000b4f7  mov     rdx, cs:SstpSvcGlobals
0x18000b4fe  xor     r8d, r8d; Reserved
0x18000b501  add     rdx, 30h ; '0'; ServerSessionId
0x18000b505  mov     ecx, ebx; Version
0x18000b507  call    cs:__imp_HttpCreateServerSession
0x18000b50d  mov     edi, eax
0x18000b50f  test    eax, eax
0x18000b511  jz      short loc_18000B540
0x18000b513  mov     bl, 8
0x18000b515  test    cs:byte_18002D803, bl
0x18000b51b  jz      loc_18000B982
0x18000b521  mov     r9d, eax
0x18000b524  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000b52a  mov     r8d, eax
0x18000b52d  lea     rdx, aHttpcreateserv; "HttpCreateServerSession fails with erro"...
0x18000b534  lea     rcx, [rsp+0AC0h+var_A60]
0x18000b539  call    FormatRRASErrorString
0x18000b53e  jmp     short loc_18000B4D6
0x18000b540  mov     rcx, cs:SstpSvcGlobals
0x18000b547  xor     r8d, r8d; Reserved
0x18000b54a  lea     rdx, [rcx+38h]; pUrlGroupId
0x18000b54e  mov     rcx, [rcx+30h]; ServerSessionId
0x18000b552  call    cs:__imp_HttpCreateUrlGroup
0x18000b558  mov     edi, eax
0x18000b55a  test    eax, eax
0x18000b55c  jz      short loc_18000B5AA
0x18000b55e  mov     bl, 8
0x18000b560  test    cs:byte_18002D803, bl
0x18000b566  jz      loc_18000B966
0x18000b56c  mov     r9d, eax
0x18000b56f  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000b575  mov     r8d, eax
0x18000b578  lea     rdx, aHttpcreateurlg; "HttpCreateUrlGroup fails with error %d "...
0x18000b57f  lea     rcx, [rsp+0AC0h+var_A60]
0x18000b584  call    FormatRRASErrorString
0x18000b589  test    cs:byte_18002D803, bl
0x18000b58f  jz      loc_18000B966
0x18000b595  lea     r8, [rsp+0AC0h+var_A60]
0x18000b59a  mov     rdx, r14
0x18000b59d  mov     rcx, r15
0x18000b5a0  call    McTemplateU0z_EventWriteTransfer
0x18000b5a5  jmp     loc_18000B966
0x18000b5aa  lea     r8, [rbp+9C0h+pFullyQualifiedUrl]
0x18000b5b1  lea     rdx, qword_180023068
0x18000b5b8  lea     rcx, [rsp+0AC0h+var_A80]
0x18000b5bd  call    cs:__imp_GetUrlForConfig
0x18000b5c3  mov     rcx, cs:SstpSvcGlobals
0x18000b5ca  lea     rdx, [rbp+9C0h+pFullyQualifiedUrl]; pFullyQualifiedUrl
0x18000b5d1  xor     r9d, r9d; Reserved
0x18000b5d4  xor     r8d, r8d; UrlContext
0x18000b5d7  mov     rcx, [rcx+38h]; UrlGroupId
0x18000b5db  call    cs:__imp_HttpAddUrlToUrlGroup
0x18000b5e1  mov     edi, eax
0x18000b5e3  test    eax, eax
0x18000b5e5  mov     rax, cs:SstpSvcGlobals
0x18000b5ec  jz      short loc_18000B660
0x18000b5ee  mov     rcx, [rax+48h]; hLogHandle
0x18000b5f2  test    rcx, rcx
0x18000b5f5  jz      short loc_18000B614
0x18000b5f7  xor     r9d, r9d; dwSubStringCount
0x18000b5fa  mov     [rsp+0AC0h+dwErrorIndex], r13d; dwErrorIndex
0x18000b5ff  mov     [rsp+0AC0h+dwErrorCode], edi; dwErrorCode
0x18000b603  mov     edx, esi; dwEventType
0x18000b605  mov     [rsp+0AC0h+plpszSubStringArray], r13; plpszSubStringArray
0x18000b60a  lea     r8d, [r9+16h]; dwMessageId
0x18000b60e  call    cs:__imp_RouterLogEventStringW
0x18000b614  mov     bl, 8
0x18000b616  test    cs:byte_18002D803, bl
0x18000b61c  jz      loc_18000B94A
0x18000b622  mov     r9d, edi
0x18000b625  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000b62b  mov     r8d, edi
0x18000b62e  lea     rdx, aErrorAddingThe; "Error adding the URL to URL group (%d -"...
0x18000b635  lea     rcx, [rsp+0AC0h+var_A60]
0x18000b63a  call    FormatRRASErrorString
0x18000b63f  test    cs:byte_18002D803, bl
0x18000b645  jz      loc_18000B94A
0x18000b64b  lea     r8, [rsp+0AC0h+var_A60]
0x18000b650  mov     rdx, r14
0x18000b653  mov     rcx, r15
0x18000b656  call    McTemplateU0z_EventWriteTransfer
0x18000b65b  jmp     loc_18000B94A
0x18000b660  add     rax, 40h ; '@'
0x18000b664  xor     r9d, r9d; Flags
0x18000b667  xor     r8d, r8d; SecurityAttributes
0x18000b66a  mov     [rsp+0AC0h+plpszSubStringArray], rax; RequestQueueHandle
0x18000b66f  xor     edx, edx; Name
0x18000b671  mov     ecx, ebx; Version
0x18000b673  call    cs:__imp_HttpCreateRequestQueue
0x18000b679  mov     edi, eax
0x18000b67b  test    eax, eax
0x18000b67d  jz      short loc_18000B6F4
0x18000b67f  mov     bl, 8
0x18000b681  test    cs:byte_18002D803, bl
0x18000b687  jz      short loc_18000B6BE
0x18000b689  mov     r9d, eax
0x18000b68c  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000b692  mov     r8d, eax
0x18000b695  lea     rdx, aErrorSettingUp; "Error setting up the request queue (%d "...
0x18000b69c  lea     rcx, [rsp+0AC0h+var_A60]
0x18000b6a1  call    FormatRRASErrorString
0x18000b6a6  test    cs:byte_18002D803, bl
0x18000b6ac  jz      short loc_18000B6BE
0x18000b6ae  lea     r8, [rsp+0AC0h+var_A60]
0x18000b6b3  mov     rdx, r14
0x18000b6b6  mov     rcx, r15
0x18000b6b9  call    McTemplateU0z_EventWriteTransfer
0x18000b6be  mov     rax, cs:SstpSvcGlobals
0x18000b6c5  mov     rcx, [rax+48h]; hLogHandle
0x18000b6c9  test    rcx, rcx
0x18000b6cc  jz      loc_18000B94A
0x18000b6d2  xor     r9d, r9d; dwSubStringCount
0x18000b6d5  mov     [rsp+0AC0h+dwErrorIndex], r13d; dwErrorIndex
0x18000b6da  mov     [rsp+0AC0h+dwErrorCode], edi; dwErrorCode
0x18000b6de  mov     edx, esi; dwEventType
0x18000b6e0  mov     [rsp+0AC0h+plpszSubStringArray], r13; plpszSubStringArray
0x18000b6e5  lea     r8d, [r9+16h]; dwMessageId
0x18000b6e9  call    cs:__imp_RouterLogEventStringW
0x18000b6ef  jmp     loc_18000B94A
0x18000b6f4  test    cs:byte_18002D803, r12b
0x18000b6fb  jz      short loc_18000B713
0x18000b6fd  lea     r8, aSuccessfullySe; "Successfully setup the request queue"
0x18000b704  mov     rcx, r15
0x18000b707  lea     rdx, RasSSTPSvcTraceInfo
0x18000b70e  call    McTemplateU0z_EventWriteTransfer
0x18000b713  mov     rcx, cs:SstpSvcGlobals
0x18000b71a  lea     r8, [rsp+0AC0h+PropertyInformation]; PropertyInformation
0x18000b71f  or      dword ptr [rsp+0AC0h+PropertyInformation], esi
0x18000b723  mov     r9d, r12d; PropertyInformationLength
0x18000b726  mov     edx, 7; Property
0x18000b72b  mov     rax, [rcx+40h]
0x18000b72f  mov     qword ptr [rsp+0AC0h+PropertyInformation+8], rax
0x18000b734  mov     rcx, [rcx+38h]; UrlGroupId
0x18000b738  call    cs:__imp_HttpSetUrlGroupProperty
0x18000b73e  mov     edi, eax
0x18000b740  test    eax, eax
0x18000b742  jz      short loc_18000B7B9
0x18000b744  mov     bl, 8
0x18000b746  test    cs:byte_18002D803, bl
0x18000b74c  jz      short loc_18000B783
0x18000b74e  mov     r9d, eax
0x18000b751  mov     word ptr [rsp+0AC0h+var_A60], r13w
0x18000b757  mov     r8d, eax
0x18000b75a  lea     rdx, aUnableToSetupT; "Unable to setup the binding between the"...
0x18000b761  lea     rcx, [rsp+0AC0h+var_A60]
0x18000b766  call    FormatRRASErrorString
0x18000b76b  test    cs:byte_18002D803, bl
0x18000b771  jz      short loc_18000B783
0x18000b773  lea     r8, [rsp+0AC0h+var_A60]
0x18000b778  mov     rdx, r14
0x18000b77b  mov     rcx, r15
0x18000b77e  call    McTemplateU0z_EventWriteTransfer
0x18000b783  mov     rax, cs:SstpSvcGlobals
0x18000b78a  mov     rcx, [rax+48h]; hLogHandle
0x18000b78e  test    rcx, rcx
0x18000b791  jz      loc_18000B92E
0x18000b797  xor     r9d, r9d; dwSubStringCount
0x18000b79a  mov     [rsp+0AC0h+dwErrorIndex], r13d; dwErrorIndex
0x18000b79f  mov     [rsp+0AC0h+dwErrorCode], edi; dwErrorCode
0x18000b7a3  mov     edx, esi; dwEventType
0x18000b7a5  mov     [rsp+0AC0h+plpszSubStringArray], r13; plpszSubStringArray
0x18000b7aa  lea     r8d, [r9+16h]; dwMessageId
0x18000b7ae  call    cs:__imp_RouterLogEventStringW
0x18000b7b4  jmp     loc_18000B92E
0x18000b7b9  mov     rcx, cs:SstpSvcGlobals
0x18000b7c0  mov     rax, [rcx+0A8h]
0x18000b7c7  test    rax, rax
0x18000b7ca  jz      short loc_18000B7F9
0x18000b7cc  xor     edx, edx; fCancelPendingCallbacks
0x18000b7ce  mov     rcx, rax; pio
0x18000b7d1  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18000b7d7  mov     rcx, cs:SstpSvcGlobals
0x18000b7de  mov     rcx, [rcx+0A8h]; pio
0x18000b7e5  call    cs:__imp_CloseThreadpoolIo
0x18000b7eb  mov     rcx, cs:SstpSvcGlobals
0x18000b7f2  mov     [rcx+0A8h], r13
0x18000b7f9  lea     r9, [rcx+50h]; pcbe
0x18000b7fd  xor     r8d, r8d; pv
0x18000b800  mov     rcx, [rcx+40h]; fl
0x18000b804  lea     rdx, HttpThreadPoolRequestQueueCallback; pfnio
0x18000b80b  call    cs:__imp_CreateThreadpoolIo
0x18000b811  mov     rcx, cs:SstpSvcGlobals
0x18000b818  mov     [rcx+0A8h], rax
  ... truncated ...
```
