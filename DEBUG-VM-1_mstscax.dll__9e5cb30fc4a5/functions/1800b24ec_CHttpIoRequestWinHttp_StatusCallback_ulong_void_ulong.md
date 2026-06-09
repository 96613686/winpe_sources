# CHttpIoRequestWinHttp::StatusCallback(ulong,void *,ulong)

- ea: `0x1800b24ec`
- end: `0x1800b375f`
- name: `?StatusCallback@CHttpIoRequestWinHttp@@AEAAXKPEAXK@Z`
- size: `4723`
- prototype: `void __fastcall(CHttpIoRequestWinHttp *__hidden this, unsigned int, union CHttpIoRequestWinHttp::STATUS_INFORMATION_BUFFER *, unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1800b3770`

## callees

- `0x1800011f4`
- `0x180001e8c`
- `0x180002660`
- `0x1800031a8`
- `0x1800033b4`
- `0x180003920`
- `0x180005f3c`
- `0x1800829d4`
- `0x180082ad8`
- `0x1800917f4`
- `0x1800b17d4`
- `0x1800b24ec`
- `0x1800cfa74`
- `0x180101d30`
- `0x18012962c`
- `0x18031cc98`
- `0x18031ce64`
- `0x18031e914`
- `0x180321608`
- `0x1803217ec`
- `0x180321850`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1800b2568`
- `KERNEL32!TlsGetValue` at `0x1800b2568`
- `KERNEL32!GetLastError` at `0x1800b2c73`
- `KERNEL32!GetLastError` at `0x1800b2e0c`
- `KERNEL32!GetLastError` at `0x1800b3030`
- `KERNEL32!GetLastError` at `0x1800b330d`
- `KERNEL32!GetLastError` at `0x1800b2c73`
- `KERNEL32!GetLastError` at `0x1800b2e0c`
- `KERNEL32!GetLastError` at `0x1800b3030`
- `KERNEL32!GetLastError` at `0x1800b330d`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800b2772`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800b2772`
- `ADVAPI32!EventActivityIdControl` at `0x1800b254b`
- `ADVAPI32!EventActivityIdControl` at `0x1800b3736`
- `ADVAPI32!EventActivityIdControl` at `0x1800b254b`
- `ADVAPI32!EventActivityIdControl` at `0x1800b3736`
- `WINHTTP!WinHttpWebSocketQueryCloseStatus` at `0x1800b29fd`
- `WINHTTP!WinHttpWebSocketQueryCloseStatus` at `0x1800b29fd`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800b32f7`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800b32f7`
- `WINHTTP!WinHttpReadData` at `0x1800b2c5d`
- `WINHTTP!WinHttpReadData` at `0x1800b2c5d`
- `WINHTTP!WinHttpWriteData` at `0x1800b3016`
- `WINHTTP!WinHttpWriteData` at `0x1800b3016`
- `WINHTTP!WinHttpWebSocketClose` at `0x1800b2b5b`
- `WINHTTP!WinHttpWebSocketClose` at `0x1800b2b5b`
- `WINHTTP!WinHttpCloseHandle` at `0x1800b2af5`
- `WINHTTP!WinHttpCloseHandle` at `0x1800b32a5`
- `WINHTTP!WinHttpCloseHandle` at `0x1800b2af5`
- `WINHTTP!WinHttpCloseHandle` at `0x1800b32a5`

## string_xrefs

- `0x1800b3087`: `WinHttpWriteData failed`
- `0x1800b2cc3`: `WinHttpReadData failed`
- `0x1800b32bb`: `WINHTTP_CALLBACK_STATUS_SENDREQUEST_COMPLETE called`
- `0x1800b30f8`: `Unexpected callback in WINHTTP_CALLBACK_STATUS_WRITE_COMPLETE for out channel`
- `0x1800b2d3c`: `Unexpected callback in WINHTTP_CALLBACK_STATUS_DATA_AVAILABLE for write stream`
- `0x1800b2fb9`: `Partial write`
- `0x1800b3631`: `Unexpected stream type in API_WRITE_DATA`
- `0x1800b3695`: `Unexpected stream type in API_READ_DATA`
- `0x1800b2bc7`: `Unexpected callback in WINHTTP_CALLBACK_STATUS_READ_COMPLETE for write stream`
- `0x1800b322b`: `WINHTTP_CALLBACK_STATUS_CLOSE_COMPLETE called`
- `0x1800b319f`: `WINHTTP_CALLBACK_STATUS_SHUTDOWN_COMPLETE called`
- `0x1800b2791`: `WINHTTP_CALLBACK_STATUS_HANDLE_CREATED called`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHttpIoRequestWinHttp::StatusCallback(
        CHttpIoRequestWinHttp *this,
        unsigned int a2,
        wchar_t *a3,
        unsigned int a4)
{
  signed int LastError; // r14d
  unsigned __int8 *v9; // r13
  int v10; // ecx
  int v11; // r9d
  int v12; // r8d
  const char *v13; // rax
  char *v14; // rdx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // r8d
  int v19; // r9d
  unsigned __int64 v20; // r11
  unsigned __int64 v21; // r15
  unsigned __int16 *v22; // rax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // ecx
  int v27; // r15d
  const char *v28; // rcx
  void *v29; // r15
  int v30; // r8d
  int v31; // r9d
  int v32; // ecx
  int v33; // ecx
  volatile __int32 *v34; // rax
  DWORD v35; // eax
  DWORD v36; // r8d
  signed int v37; // eax
  int v38; // r8d
  int v39; // r9d
  const char *v40; // rax
  char *v41; // rdx
  const char *v42; // rax
  char *v43; // rdx
  int v44; // r8d
  int v45; // r9d
  unsigned int v46; // eax
  unsigned int v47; // ebx
  unsigned int v48; // eax
  unsigned int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  unsigned int v52; // eax
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  char *v56; // rbx
  __int16 *v57; // rdx
  unsigned int v58; // eax
  unsigned int v59; // r8d
  unsigned int v60; // eax
  int v61; // ecx
  int v62; // ecx
  unsigned int v63; // r8d
  unsigned int v64; // eax
  unsigned __int64 v65; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwReasonLengthConsumed[2]; // [rsp+58h] [rbp-A8h] BYREF
  const char *v67; // [rsp+60h] [rbp-A0h] BYREF
  const char *v68; // [rsp+68h] [rbp-98h] BYREF
  const char *v69; // [rsp+70h] [rbp-90h] BYREF
  bool v70; // [rsp+78h] [rbp-88h]
  unsigned int v71; // [rsp+7Ch] [rbp-84h] BYREF
  USHORT pusStatus[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v73; // [rsp+88h] [rbp-78h]
  GUID ActivityId; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pvReason[128]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v76[264]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v77[264]; // [rsp+330h] [rbp+230h] BYREF

  v73 = -2;
  LastError = 0;
  v71 = 0;
  v9 = 0;
  ActivityId = *(GUID *)((char *)this + 120);
  EventActivityIdControl(4u, &ActivityId);
  if ( *((_BYTE *)this + 136) )
    v70 = 0;
  else
    v70 = TlsGetValue(*((_DWORD *)this + 148)) == (LPVOID)4660;
  v12 = -2147467259;
  if ( a2 > 0x4000 )
  {
    v26 = 0x100000;
    if ( a2 <= 0x100000 )
    {
      v27 = 0;
      if ( a2 != 0x100000 )
      {
        switch ( a2 )
        {
          case 0x8000u:
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              LODWORD(v65) = a3 != 0 ? (unsigned int)a3 : 0;
              v67 = "WINHTTP_CALLBACK_STATUS_INTERMEDIATE_RESPONSE";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_1808B5850,
                (unsigned int)byte_18086900B,
                -2147467259,
                v11,
                (__int64)&v67,
                (__int64)&v65);
            }
            goto LABEL_199;
          case 0x10000u:
            v47 = *(_DWORD *)a3;
            v48 = CHttpIoRequestWinHttp::CertErrorToHResult((CHttpIoRequestWinHttp *)0x100000, v47);
            *((_DWORD *)this + 25) = v47;
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_199;
            LODWORD(v65) = *((_DWORD *)this + 25);
            v67 = "StatusCallback";
            pdwReasonLengthConsumed[0] = 2239;
            v28 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v71 = v48;
            v42 = "WINHTTP_CALLBACK_STATUS_SECURE_FAILURE called";
            v43 = &byte_18086921F;
            break;
          case 0x20000u:
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              v67 = "WINHTTP_CALLBACK_STATUS_HEADERS_AVAILABLE called";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                (unsigned int)&dword_1808B5850,
                (unsigned int)&byte_180869487,
                0,
                v11,
                (__int64)&v67);
            }
            pdwReasonLengthConsumed[0] = 0;
            if ( CHttpIoRequestWinHttp::GetResponseStatusCode(this, pdwReasonLengthConsumed)
              && pdwReasonLengthConsumed[0] == 101 )
            {
              if ( CHttpIoRequestWinHttp::WebSocketCompleteUpgrade(this) )
              {
                *((_DWORD *)this + 24) = 3;
              }
              else
              {
                LastError = GetLastError();
                if ( (unsigned int)dword_1808B5850 > 2 )
                {
                  v67 = "StatusCallback";
                  LODWORD(v65) = 1907;
                  v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
                  if ( LastError > 0 )
                    v46 = (unsigned __int16)LastError | 0x80070000;
                  else
                    v46 = LastError;
                  *(_DWORD *)pusStatus = v46;
                  v69 = "WINHTTP_CALLBACK_STATUS_HEADERS_AVAILABLE called";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
                    (unsigned int)byte_180869443,
                    v44,
                    v45,
                    (__int64)&v69,
                    (__int64)pusStatus,
                    (__int64)&v68,
                    (__int64)&v65,
                    (__int64)&v67);
                }
              }
            }
            goto LABEL_37;
          default:
            LODWORD(v28) = 0x40000;
            if ( a2 != 0x40000 )
            {
              if ( a2 != 0x80000 )
                goto LABEL_142;
              if ( *((_DWORD *)this + 24) == 3 )
              {
                if ( a3 && a4 >= 8 && *((_DWORD *)a3 + 1) == 4 )
                {
                  v29 = (void *)_InterlockedCompareExchange64((volatile signed __int64 *)this + 4, 0, 0);
                  pusStatus[0] = 1000;
                  pdwReasonLengthConsumed[0] = 0;
                  memset_0(pvReason, 0, 0x7Cu);
                  if ( v29 )
                  {
                    if ( !WinHttpWebSocketQueryCloseStatus(v29, pusStatus, pvReason, 0x7Bu, pdwReasonLengthConsumed)
                      && pdwReasonLengthConsumed[0] - 1 <= 0x7A )
                    {
                      pvReason[123] = 0;
                      if ( (unsigned int)dword_1808B5850 > 4 )
                      {
                        v68 = pvReason;
                        v69 = "Received websocket close frame reason";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
                          v32,
                          (unsigned int)&byte_1808692C7,
                          v30,
                          v31,
                          (__int64)&v69,
                          (__int64)&v68);
                      }
                    }
                  }
                  v33 = 0;
                  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 19, 0, 0) )
                  {
                    _InterlockedExchange64((volatile __int64 *)this + 4, 0);
                    if ( (unsigned int)dword_1808B5850 > 4 )
                    {
                      LODWORD(v65) = pusStatus[0];
                      v68 = "Received Websocket close frame reply.";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                        (unsigned int)&dword_1808B5850,
                        (unsigned int)word_18086929A,
                        v30,
                        v31,
                        (__int64)&v68,
                        (__int64)&v65);
                    }
                    if ( (unsigned int)dword_1808B5850 > 4 )
                    {
                      v68 = (const char *)v29;
                      v69 = "Closing Websocket Handle";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                        v33,
                        (unsigned int)word_180869272,
                        v30,
                        v31,
                        (__int64)&v69,
                        (__int64)&v68);
                    }
                    if ( v29 )
                      WinHttpCloseHandle(v29);
                    v27 = 0;
                  }
                  else
                  {
                    if ( (unsigned int)dword_1808B5850 > 4 )
                    {
                      LODWORD(v65) = pusStatus[0];
                      v68 = "Received Websocket close frame. Sending reply.";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                        (unsigned int)&dword_1808B5850,
                        (unsigned int)qword_1808693B0,
                        v30,
                        v31,
                        (__int64)&v68,
                        (__int64)&v65);
                    }
                    if ( v29 )
                      WinHttpWebSocketClose(v29, pusStatus[0], 0, 0);
                    a2 = 0x2000000;
                    v27 = 1;
                    a4 = 0;
                  }
                  goto LABEL_87;
                }
                v9 = (unsigned __int8 *)*((_QWORD *)this + 22);
              }
              else
              {
                if ( *((_DWORD *)this + 24) != 1 )
                {
                  if ( (unsigned int)dword_1808B5850 > 2 )
                  {
                    LODWORD(v65) = 0x80000;
                    v68 = "StatusCallback";
                    pdwReasonLengthConsumed[0] = 2111;
                    v69 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
                    *(_DWORD *)pusStatus = -2147467259;
                    v67 = "Unexpected callback in WINHTTP_CALLBACK_STATUS_READ_COMPLETE for write stream";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                      0x40000,
                      (unsigned int)word_180869362,
                      -2147467259,
                      v11,
                      (__int64)&v67,
                      (__int64)pusStatus,
                      (__int64)&v69,
                      (__int64)pdwReasonLengthConsumed,
                      (__int64)&v68,
                      (__int64)&v65);
                  }
                  goto LABEL_87;
                }
                v71 = a4;
                a4 = 0;
                *((_DWORD *)this + 37) -= v71;
                v9 = (unsigned __int8 *)a3;
              }
              v27 = 1;
LABEL_87:
              v34 = (volatile __int32 *)((char *)this + 140);
              goto LABEL_134;
            }
            if ( *((_DWORD *)this + 24) == 1 )
            {
              if ( !a3 )
                goto LABEL_199;
              v35 = *(_DWORD *)a3;
              *((_DWORD *)this + 37) = *(_DWORD *)a3;
              v36 = *((_DWORD *)this + 38);
              if ( v36 >= v35 )
                v36 = v35;
              if ( WinHttpReadData(*((HINTERNET *)this + 3), *((LPVOID *)this + 22), v36, 0) )
                goto LABEL_199;
              a2 = 0x80000;
              a4 = 0;
              v37 = GetLastError();
              LastError = v37;
              _InterlockedExchange((volatile __int32 *)this + 35, 0);
              if ( (unsigned int)dword_1808B5850 > 2 )
              {
                v67 = "StatusCallback";
                LODWORD(v65) = 2006;
                v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
                if ( v37 > 0 )
                  v37 = (unsigned __int16)v37 | 0x80070000;
                pdwReasonLengthConsumed[0] = v37;
                v40 = "WinHttpReadData failed";
                v41 = byte_1808694F5;
LABEL_97:
                v69 = v40;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
                  (_DWORD)v41,
                  v38,
                  v39,
                  (__int64)&v69,
                  (__int64)pdwReasonLengthConsumed,
                  (__int64)&v68,
                  (__int64)&v65,
                  (__int64)&v67);
              }
LABEL_38:
              if ( v70 )
              {
                if ( CHttpIoRequestWinHttp::StoreStatusInfoForProcessing(this, a2, a3, a4, LastError, v71, v9) )
                {
                  (**(void (__fastcall ***)(CHttpIoRequestWinHttp *))this)(this);
                  SubmitThreadpoolWork(*((PTP_WORK *)this + 14));
                }
                else if ( (unsigned int)dword_1808B5850 > 2 )
                {
                  v67 = "StatusCallback";
                  LODWORD(v65) = 2356;
                  v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
                  pdwReasonLengthConsumed[0] = -2147467259;
                  v69 = "StoreStatusInfoForProcessing error";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    v15,
                    (unsigned int)&dword_180868E14,
                    v16,
                    v17,
                    (__int64)&v69,
                    (__int64)pdwReasonLengthConsumed,
                    (__int64)&v68,
                    (__int64)&v65,
                    (__int64)&v67);
                }
              }
              else
              {
                CHttpIoRequestWinHttp::ContinueProcessingCallback(
                  this,
                  a2,
                  (union CHttpIoRequestWinHttp::STATUS_INFORMATION_BUFFER *)a3,
                  a4,
                  LastError,
                  v71,
                  v9);
              }
              goto LABEL_199;
            }
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_199;
            LODWORD(v65) = 0x40000;
            v67 = "StatusCallback";
            pdwReasonLengthConsumed[0] = 2013;
            v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v71 = -2147467259;
            v42 = "Unexpected callback in WINHTTP_CALLBACK_STATUS_DATA_AVAILABLE for write stream";
            v43 = &byte_1808694A7;
            break;
        }
LABEL_100:
        v69 = v42;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v28,
          (_DWORD)v43,
          v12,
          v11,
          (__int64)&v69,
          (__int64)&v71,
          (__int64)&v68,
          (__int64)pdwReasonLengthConsumed,
          (__int64)&v67,
          (__int64)&v65);
        goto LABEL_199;
      }
      if ( *((_DWORD *)this + 24) == 3 )
      {
        v9 = (unsigned __int8 *)*((_QWORD *)this + 23);
      }
      else
      {
        if ( *((_DWORD *)this + 24) != 2 )
        {
          if ( (unsigned int)dword_1808B5850 > 2 )
          {
            LODWORD(v65) = 0x100000;
            v67 = "StatusCallback";
            pdwReasonLengthConsumed[0] = 1976;
            v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            *(_DWORD *)pusStatus = -2147467259;
            v69 = "Unexpected callback in WINHTTP_CALLBACK_STATUS_WRITE_COMPLETE for out channel";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              0x100000,
              (unsigned int)byte_180869539,
              -2147467259,
              v11,
              (__int64)&v69,
              (__int64)pusStatus,
              (__int64)&v68,
              (__int64)pdwReasonLengthConsumed,
              (__int64)&v67,
              (__int64)&v65);
          }
          goto LABEL_133;
        }
        v9 = (unsigned __int8 *)*((_QWORD *)this + 23);
        if ( !a3 || a4 < 4 )
        {
LABEL_133:
          v34 = (volatile __int32 *)((char *)this + 144);
LABEL_134:
          _InterlockedExchange(v34, 0);
          if ( !v27 )
            goto LABEL_199;
          goto LABEL_38;
        }
        v49 = *(_DWORD *)a3;
        *((_DWORD *)this + 51) += *(_DWORD *)a3;
        if ( *((_DWORD *)this + 51) < *((_DWORD *)this + 52) )
        {
          if ( (unsigned int)dword_1808B5850 > 5 )
          {
            LODWORD(v65) = *((_DWORD *)this + 52);
            pdwReasonLengthConsumed[0] = *((_DWORD *)this + 51);
            *(_DWORD *)pusStatus = v49;
            v67 = "Partial write";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v49,
              (unsigned int)byte_1808693DD,
              -2147467259,
              v11,
              (__int64)&v67,
              (__int64)pusStatus,
              (__int64)pdwReasonLengthConsumed,
              (__int64)&v65);
          }
          if ( !WinHttpWriteData(
                  *((HINTERNET *)this + 3),
                  (LPCVOID)(*((_QWORD *)this + 24) + *((unsigned int *)this + 51)),
                  *((_DWORD *)this + 52) - *((_DWORD *)this + 51),
                  0) )
          {
            a2 = 0x100000;
            v27 = 1;
            a4 = 0;
            LastError = GetLastError();
            _InterlockedExchange((volatile __int32 *)this + 36, 0);
            if ( (unsigned int)dword_1808B5850 > 2 )
            {
              v67 = "StatusCallback";
              LODWORD(v65) = 1963;
              v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
              if ( LastError > 0 )
                v52 = (unsigned __int16)LastError | 0x80070000;
              else
                v52 = LastError;
              pdwReasonLengthConsumed[0] = v52;
              v69 = "WinHttpWriteData failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
                (unsigned int)&byte_180869587,
                v50,
                v51,
                (__int64)&v69,
                (__int64)pdwReasonLengthConsumed,
                (__int64)&v68,
                (__int64)&v65,
                (__int64)&v67);
            }
          }
          goto LABEL_133;
        }
      }
      v27 = 1;
      goto LABEL_133;
    }
    if ( a2 != 0x200000 )
    {
      if ( a2 == 0x400000 )
      {
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v67 = "WINHTTP_CALLBACK_STATUS_SENDREQUEST_COMPLETE called";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)&byte_180869697,
            0,
            v11,
            (__int64)&v67);
        }
        if ( *((_DWORD *)this + 24) == 2 )
          goto LABEL_37;
        if ( WinHttpReceiveResponse(*((HINTERNET *)this + 3), 0) )
          goto LABEL_199;
        a2 = 0x20000;
        a4 = 0;
        LastError = GetLastError();
        if ( (unsigned int)dword_1808B5850 <= 2 )
          goto LABEL_38;
        v67 = "StatusCallback";
        LODWORD(v65) = 1884;
        v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        if ( LastError > 0 )
          v58 = (unsigned __int16)LastError | 0x80070000;
        else
          v58 = LastError;
        pdwReasonLengthConsumed[0] = v58;
        v40 = "WinHttpReceiveResponse failed";
        v41 = byte_180869653;
        goto LABEL_97;
      }
      if ( a2 != 0x2000000 )
      {
        if ( a2 != 0x4000000 )
          goto LABEL_142;
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v67 = "WINHTTP_CALLBACK_STATUS_SHUTDOWN_COMPLETE called";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)&byte_180868F5F,
            0,
            v11,
            (__int64)&v67);
        }
        goto LABEL_199;
      }
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v67 = "WINHTTP_CALLBACK_STATUS_CLOSE_COMPLETE called";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&dword_1808B5850,
          (unsigned int)&byte_180868FA7,
          0,
          v11,
          (__int64)&v67);
      }
      v56 = (char *)_InterlockedExchange64((volatile __int64 *)this + 4, 0);
      if ( !v56 )
        goto LABEL_199;
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v57 = (__int16 *)&byte_180868F7F;
LABEL_149:
        v68 = "Closing Websocket Handle";
        v67 = v56;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v26,
          (_DWORD)v57,
          v12,
          v11,
          (__int64)&v68,
          (__int64)&v67);
        goto LABEL_150;
      }
      goto LABEL_150;
    }
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v67 = "WINHTTP_CALLBACK_STATUS_REQUEST_ERROR called";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)word_180869342,
        0,
        v11,
        (__int64)&v67);
    }
    if ( *((_BYTE *)this + 72) )
    {
      memset_0(v77, 0, 0x208u);
      CHttpIoRequestWinHttp::WinHTTPOperationToString(*((_DWORD *)a3 + 4), v77, v59);
      LastError = *((_DWORD *)a3 + 2);
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        v67 = (const char *)v77;
        v68 = "StatusCallback";
        LODWORD(v65) = 2132;
        v69 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        if ( LastError > 0 )
          v60 = (unsigned __int16)LastError | 0x80070000;
        else
          v60 = LastError;
        pdwReasonLengthConsumed[0] = v60;
        *(_QWORD *)pusStatus = "WINHTTP_CALLBACK_STATUS_REQUEST_ERROR WebSocket operation";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
          (unsigned int)&byte_1808692EF,
          v12,
          v11,
          (__int64)pusStatus,
          (__int64)pdwReasonLengthConsumed,
          (__int64)&v69,
          (__int64)&v65,
          (__int64)&v68,
          (__int64)&v67);
      }
      v61 = *((_DWORD *)a3 + 4);
      if ( v61 )
      {
        v62 = v61 - 1;
        if ( v62 )
        {
          v26 = v62 - 1;
          if ( v26 > 1 )
            goto LABEL_199;
          v56 = (char *)_InterlockedExchange64((volatile __int64 *)this + 4, 0);
          if ( !v56 )
            goto LABEL_199;
          if ( (unsigned int)dword_1808B5850 > 4 )
          {
            v57 = word_18086918A;
            goto LABEL_149;
          }
LABEL_150:
          WinHttpCloseHandle(v56);
          goto LABEL_199;
        }
LABEL_192:
        v9 = (unsigned __int8 *)*((_QWORD *)this + 22);
        _InterlockedExchange((volatile __int32 *)this + 35, 0);
        goto LABEL_38;
      }
    }
    else
    {
      memset_0(v76, 0, 0x208u);
      CHttpIoRequestWinHttp::WinHTTPStatusAPIToString(*(_QWORD *)a3, v76, v63);
      LastError = *((_DWORD *)a3 + 2);
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        v67 = (const char *)v76;
        v68 = "StatusCallback";
        LODWORD(v65) = 2176;
        v69 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        if ( LastError > 0 )
          v64 = (unsigned __int16)LastError | 0x80070000;
        else
          v64 = LastError;
        pdwReasonLengthConsumed[0] = v64;
        *(_QWORD *)pusStatus = "WINHTTP_CALLBACK_STATUS_REQUEST_ERROR HTTP API";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
          (unsigned int)byte_180869141,
          v12,
          v11,
          (__int64)pusStatus,
          (__int64)pdwReasonLengthConsumed,
          (__int64)&v69,
          (__int64)&v65,
          (__int64)&v68,
          (__int64)&v67);
      }
      switch ( *(_QWORD *)a3 )
      {
        case 1LL:
          goto LABEL_38;
        case 2LL:
          a2 = 0x80000;
          goto LABEL_192;
        case 3LL:
          if ( *((_DWORD *)this + 24) != 1 )
          {
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_199;
            LODWORD(v65) = *((_DWORD *)this + 24);
            v67 = "StatusCallback";
            pdwReasonLengthConsumed[0] = 2221;
            v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
            v71 = -2147418113;
            v42 = "Unexpected stream type in API_READ_DATA";
            v43 = byte_1808690A1;
            goto LABEL_100;
          }
          goto LABEL_192;
      }
      if ( *(_QWORD *)a3 != 4 )
      {
        if ( *(_QWORD *)a3 != 5 )
          goto LABEL_199;
        a2 = 0x20000;
        goto LABEL_38;
      }
      if ( *((_DWORD *)this + 24) != 2 )
      {
        if ( (unsigned int)dword_1808B5850 <= 2 )
          goto LABEL_199;
        LODWORD(v65) = *((_DWORD *)this + 24);
        v67 = "StatusCallback";
        pdwReasonLengthConsumed[0] = 2199;
        v68 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
        v71 = -2147418113;
        v42 = "Unexpected stream type in API_WRITE_DATA";
        v43 = byte_1808690F1;
        goto LABEL_100;
      }
    }
    v9 = (unsigned __int8 *)*((_QWORD *)this + 23);
    _InterlockedExchange((volatile __int32 *)this + 36, 0);
    goto LABEL_38;
  }
  if ( a2 == 0x4000 )
  {
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v65 = (unsigned __int64)"WINHTTP_CALLBACK_STATUS_REDIRECT called";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)&byte_1808691D7,
        0,
        v11,
        (__int64)&v65);
    }
    if ( a3 )
    {
      v65 = 0;
      v18 = StringCchLengthW(a3, 0x7FFFFFFFu, &v65);
      if ( v18 < 0 )
      {
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          v65 = v20;
          pdwReasonLengthConsumed[0] = 2268;
          v69 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
          *(_DWORD *)pusStatus = v18;
          v68 = "WINHTTP_CALLBACK_STATUS_REDIRECT URL length is incorrect";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (unsigned int)"onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp",
            (unsigned int)&byte_180868FC7,
            v18,
            v19,
            (__int64)&v68,
            (__int64)pusStatus,
            (__int64)&v69,
            (__int64)pdwReasonLengthConsumed,
            (__int64)&v65);
        }
      }
      else
      {
        v21 = v65 + 1;
        v22 = (unsigned __int16 *)operator new(saturated_mul(v65 + 1, 2u));
        *((_QWORD *)this + 73) = v22;
        if ( v22 )
        {
          StringCchCopyW(v22, v21, a3);
          if ( (unsigned int)dword_1808B5850 > 4 )
          {
            v65 = *((_QWORD *)this + 73);
            *(_QWORD *)pdwReasonLengthConsumed = "WINHTTP_CALLBACK_STATUS_REDIRECT";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              v23,
              (unsigned int)word_1808691B2,
              v24,
              v25,
              (__int64)pdwReasonLengthConsumed,
              (__int64)&v65);
          }
        }
      }
    }
    goto LABEL_37;
  }
  if ( a2 <= 0x20 )
  {
    switch ( a2 )
    {
      case 0x20u:
        goto LABEL_199;
      case 1u:
        if ( (unsigned int)dword_1808B5850 <= 4 )
          goto LABEL_199;
        if ( !a3 )
          a3 = (wchar_t *)&sourceString;
        v13 = "WINHTTP_CALLBACK_STATUS_RESOLVING_NAME";
        v14 = (char *)word_180868E82;
        break;
      case 2u:
        if ( (unsigned int)dword_1808B5850 <= 4 )
          goto LABEL_199;
        if ( !a3 )
          a3 = (wchar_t *)&sourceString;
        v13 = "WINHTTP_CALLBACK_STATUS_NAME_RESOLVED";
        v14 = byte_18086907B;
        break;
      case 4u:
        if ( (unsigned int)dword_1808B5850 <= 4 )
          goto LABEL_199;
        if ( !a3 )
          a3 = (wchar_t *)&sourceString;
        v13 = "WINHTTP_CALLBACK_STATUS_CONNECTING_TO_SERVER";
        v14 = byte_180869033;
        break;
      case 8u:
        if ( (unsigned int)dword_1808B5850 <= 4 )
          goto LABEL_199;
        if ( !a3 )
          a3 = (wchar_t *)&sourceString;
        v13 = "WINHTTP_CALLBACK_STATUS_CONNECTED_TO_SERVER";
        v14 = &byte_180869057;
        break;
      case 0x10u:
        goto LABEL_199;
      default:
        goto LABEL_142;
    }
    *(_QWORD *)pdwReasonLengthConsumed = v13;
    v65 = (unsigned __int64)a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      v10,
      (_DWORD)v14,
      -2147467259,
      v11,
      (__int64)pdwReasonLengthConsumed,
      (__int64)&v65);
    goto LABEL_199;
  }
  if ( a2 == 64 || a2 == 128 )
    goto LABEL_199;
  if ( a2 != 1024 )
  {
    if ( a2 == 2048 )
    {
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v65 = (unsigned __int64)a3;
        *(_QWORD *)pdwReasonLengthConsumed = "WINHTTP_CALLBACK_STATUS_HANDLE_CLOSING called";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v10,
          (unsigned int)byte_18086941B,
          -2147467259,
          v11,
          (__int64)pdwReasonLengthConsumed,
          (__int64)&v65);
      }
LABEL_37:
      a4 = 0;
      goto LABEL_38;
    }
LABEL_142:
    CHttpIoRequestWinHttp::CallbackStatusToString(a2, v76, 0x80004005);
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v67 = (const char *)v76;
      v68 = "Winhttp callback called";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v53,
        (unsigned int)qword_180868E58,
        v54,
        v55,
        (__int64)&v68,
        (__int64)&v67);
    }
    goto LABEL_199;
  }
  if ( (unsigned int)dword_1808B5850 > 4 )
  {
    v65 = (unsigned __int64)a3;
    *(_QWORD *)pdwReasonLengthConsumed = "WINHTTP_CALLBACK_STATUS_HANDLE_CREATED called";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v10,
      (unsigned int)&byte_1808691F7,
      -2147467259,
      v11,
      (__int64)pdwReasonLengthConsumed,
      (__int64)&v65);
  }
LABEL_199:
  EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x1800b24ec  push    rbp
0x1800b24ee  push    rbx
0x1800b24ef  push    rsi
0x1800b24f0  push    rdi
0x1800b24f1  push    r12
0x1800b24f3  push    r13
0x1800b24f5  push    r14
0x1800b24f7  push    r15
0x1800b24f9  lea     rbp, [rsp-458h]
0x1800b2501  sub     rsp, 558h
0x1800b2508  mov     [rbp+490h+var_508], 0FFFFFFFFFFFFFFFEh
0x1800b2510  mov     rax, cs:__security_cookie
0x1800b2517  xor     rax, rsp
0x1800b251a  mov     [rbp+490h+var_50], rax
0x1800b2521  mov     r12d, r9d
0x1800b2524  mov     rbx, r8
0x1800b2527  mov     esi, edx
0x1800b2529  mov     rdi, rcx
0x1800b252c  xor     r14d, r14d
0x1800b252f  mov     [rsp+590h+var_514], r14d
0x1800b2534  xor     r13d, r13d
0x1800b2537  movups  xmm0, xmmword ptr [rcx+78h]
0x1800b253b  movdqu  xmmword ptr [rbp+490h+ActivityId.Data1], xmm0
0x1800b2540  lea     rdx, [rbp+490h+ActivityId]; ActivityId
0x1800b2544  lea     r15d, [r14+4]
0x1800b2548  mov     ecx, r15d; ControlCode
0x1800b254b  call    cs:__imp_EventActivityIdControl
0x1800b2551  nop
0x1800b2552  cmp     [rdi+88h], r13b
0x1800b2559  jz      short loc_1800B2562
0x1800b255b  mov     [rsp+590h+var_518], r13b
0x1800b2560  jmp     short loc_1800B2579
0x1800b2562  mov     ecx, [rdi+250h]; dwTlsIndex
0x1800b2568  call    cs:__imp_TlsGetValue
0x1800b256e  cmp     rax, 1234h
0x1800b2574  setz    [rsp+590h+var_518]
0x1800b2579  lea     r11, aStatuscallback; "StatusCallback"
0x1800b2580  lea     rdx, aOnecoreTermsrv_7; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x1800b2587  mov     eax, 4000h
0x1800b258c  mov     r8d, 80004005h; unsigned int
0x1800b2592  cmp     esi, eax
0x1800b2594  ja      loc_1800B2938
0x1800b259a  jz      loc_1800B27C2
0x1800b25a0  cmp     esi, 20h ; ' '
0x1800b25a3  ja      loc_1800B26BB
0x1800b25a9  jz      loc_1800B372D
0x1800b25af  mov     eax, esi
0x1800b25b1  sub     eax, 1
0x1800b25b4  jz      loc_1800B268B
0x1800b25ba  sub     eax, 1
0x1800b25bd  jz      loc_1800B265B
0x1800b25c3  sub     eax, 2
0x1800b25c6  jz      short loc_1800B262E
0x1800b25c8  sub     eax, r15d
0x1800b25cb  jz      short loc_1800B25DB
0x1800b25cd  cmp     eax, 8
0x1800b25d0  jz      loc_1800B372D
0x1800b25d6  jmp     loc_1800B31D6
0x1800b25db  mov     eax, cs:dword_1808B5850
0x1800b25e1  cmp     eax, r15d
0x1800b25e4  jbe     loc_1800B372D
0x1800b25ea  lea     rax, sourceString
0x1800b25f1  test    rbx, rbx
0x1800b25f4  cmovz   rbx, rax
0x1800b25f8  lea     rax, aWinhttpCallbac_8; "WINHTTP_CALLBACK_STATUS_CONNECTED_TO_SE"...
0x1800b25ff  lea     rdx, byte_180869057
0x1800b2606  mov     qword ptr [rsp+590h+var_538], rax
0x1800b260b  lea     rax, [rsp+590h+var_540]
0x1800b2610  mov     qword ptr [rsp+590h+var_568], rax
0x1800b2615  lea     rax, [rsp+590h+var_538]
0x1800b261a  mov     [rsp+590h+var_540], rbx
0x1800b261f  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x1800b2624  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800b2629  jmp     loc_1800B372D
0x1800b262e  mov     eax, cs:dword_1808B5850
0x1800b2634  cmp     eax, r15d
0x1800b2637  jbe     loc_1800B372D
0x1800b263d  lea     rax, sourceString
0x1800b2644  test    rbx, rbx
0x1800b2647  cmovz   rbx, rax
0x1800b264b  lea     rax, aWinhttpCallbac_24; "WINHTTP_CALLBACK_STATUS_CONNECTING_TO_S"...
0x1800b2652  lea     rdx, byte_180869033
0x1800b2659  jmp     short loc_1800B2606
0x1800b265b  mov     eax, cs:dword_1808B5850
0x1800b2661  cmp     eax, r15d
0x1800b2664  jbe     loc_1800B372D
0x1800b266a  lea     rax, sourceString
0x1800b2671  test    rbx, rbx
0x1800b2674  cmovz   rbx, rax
0x1800b2678  lea     rax, aWinhttpCallbac_37; "WINHTTP_CALLBACK_STATUS_NAME_RESOLVED"
0x1800b267f  lea     rdx, byte_18086907B
0x1800b2686  jmp     loc_1800B2606
0x1800b268b  mov     eax, cs:dword_1808B5850
0x1800b2691  cmp     eax, r15d
0x1800b2694  jbe     loc_1800B372D
0x1800b269a  lea     rax, sourceString
0x1800b26a1  test    rbx, rbx
0x1800b26a4  cmovz   rbx, rax
0x1800b26a8  lea     rax, aWinhttpCallbac_13; "WINHTTP_CALLBACK_STATUS_RESOLVING_NAME"
0x1800b26af  lea     rdx, word_180868E82
0x1800b26b6  jmp     loc_1800B2606
0x1800b26bb  mov     eax, esi
0x1800b26bd  sub     eax, 40h ; '@'
0x1800b26c0  jz      loc_1800B372D
0x1800b26c6  sub     eax, 40h ; '@'
0x1800b26c9  jz      loc_1800B372D
0x1800b26cf  sub     eax, 380h
0x1800b26d4  jz      loc_1800B277D
0x1800b26da  cmp     eax, 400h
0x1800b26df  jnz     loc_1800B31D6
0x1800b26e5  mov     eax, cs:dword_1808B5850
0x1800b26eb  cmp     eax, r15d
0x1800b26ee  jbe     short loc_1800B2721
0x1800b26f0  mov     [rsp+590h+var_540], rbx
0x1800b26f5  lea     rax, aWinhttpCallbac_28; "WINHTTP_CALLBACK_STATUS_HANDLE_CLOSING "...
0x1800b26fc  mov     qword ptr [rsp+590h+var_538], rax
0x1800b2701  lea     rax, [rsp+590h+var_540]
0x1800b2706  mov     qword ptr [rsp+590h+var_568], rax
0x1800b270b  lea     rax, [rsp+590h+var_538]
0x1800b2710  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x1800b2715  lea     rdx, byte_18086941B
0x1800b271c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800b2721  xor     r12d, r12d
0x1800b2724  lea     r15, aStatuscallback; "StatusCallback"
0x1800b272b  mov     [rsp+590h+var_560], r13; unsigned __int8 *
0x1800b2730  mov     eax, [rsp+590h+var_514]
0x1800b2734  mov     r9d, r12d; unsigned int
0x1800b2737  mov     r8, rbx; union CHttpIoRequestWinHttp::STATUS_INFORMATION_BUFFER *
0x1800b273a  mov     edx, esi; unsigned int
0x1800b273c  mov     rcx, rdi; this
0x1800b273f  mov     [rsp+590h+var_568], eax; unsigned int
0x1800b2743  mov     dword ptr [rsp+590h+pdwReasonLengthConsumed], r14d; unsigned int
0x1800b2748  cmp     [rsp+590h+var_518], 0
0x1800b274d  jz      loc_1800B3727
0x1800b2753  call    ?StoreStatusInfoForProcessing@CHttpIoRequestWinHttp@@AEAA_NKPEAXKKKPEAE@Z; CHttpIoRequestWinHttp::StoreStatusInfoForProcessing(ulong,void *,ulong,ulong,ulong,uchar *)
0x1800b2758  test    al, al
0x1800b275a  jz      loc_1800B36AF
0x1800b2760  mov     rax, [rdi]
0x1800b2763  mov     rcx, rdi
0x1800b2766  mov     rax, [rax]
0x1800b2769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b276e  mov     rcx, [rdi+70h]; pwk
0x1800b2772  call    cs:__imp_SubmitThreadpoolWork
0x1800b2778  jmp     loc_1800B372D
0x1800b277d  mov     eax, cs:dword_1808B5850
0x1800b2783  cmp     eax, r15d
0x1800b2786  jbe     loc_1800B372D
0x1800b278c  mov     [rsp+590h+var_540], rbx
0x1800b2791  lea     rax, aWinhttpCallbac_32; "WINHTTP_CALLBACK_STATUS_HANDLE_CREATED "...
0x1800b2798  mov     qword ptr [rsp+590h+var_538], rax
0x1800b279d  lea     rax, [rsp+590h+var_540]
0x1800b27a2  mov     qword ptr [rsp+590h+var_568], rax
0x1800b27a7  lea     rax, [rsp+590h+var_538]
0x1800b27ac  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x1800b27b1  lea     rdx, byte_1808691F7
0x1800b27b8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800b27bd  jmp     loc_1800B372D
0x1800b27c2  mov     eax, cs:dword_1808B5850
0x1800b27c8  cmp     eax, r15d
0x1800b27cb  jbe     short loc_1800B2800
0x1800b27cd  lea     rax, aWinhttpCallbac_39; "WINHTTP_CALLBACK_STATUS_REDIRECT called"
0x1800b27d4  mov     [rsp+590h+var_540], rax
0x1800b27d9  lea     rax, [rsp+590h+var_540]
0x1800b27de  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x1800b27e3  xor     r8d, r8d
0x1800b27e6  lea     rdx, byte_1808691D7
0x1800b27ed  lea     rcx, dword_1808B5850
0x1800b27f4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800b27f9  lea     r11, aStatuscallback; "StatusCallback"
0x1800b2800  test    rbx, rbx
0x1800b2803  jz      loc_1800B2721
0x1800b2809  mov     [rsp+590h+var_540], 0
0x1800b2812  lea     r8, [rsp+590h+var_540]; unsigned __int64 *
0x1800b2817  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800b281c  mov     rcx, rbx; unsigned __int16 *
0x1800b281f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800b2824  mov     r8d, eax
0x1800b2827  test    eax, eax
0x1800b2829  js      loc_1800B28BE
0x1800b282f  mov     r15, [rsp+590h+var_540]
0x1800b2834  inc     r15
0x1800b2837  mov     eax, 2
0x1800b283c  mul     r15
0x1800b283f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b2846  cmovb   rax, rcx
0x1800b284a  mov     rcx, rax; Size
0x1800b284d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b2852  mov     [rdi+248h], rax
0x1800b2859  test    rax, rax
0x1800b285c  jz      loc_1800B2721
0x1800b2862  mov     r8, rbx; unsigned __int16 *
0x1800b2865  mov     rdx, r15; unsigned __int64
0x1800b2868  mov     rcx, rax; unsigned __int16 *
0x1800b286b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b2870  mov     r11d, cs:dword_1808B5850
0x1800b2877  cmp     r11d, 4
0x1800b287b  jbe     loc_1800B2721
0x1800b2881  mov     rax, [rdi+248h]
0x1800b2888  mov     [rsp+590h+var_540], rax
0x1800b288d  lea     rax, aWinhttpCallbac_0; "WINHTTP_CALLBACK_STATUS_REDIRECT"
0x1800b2894  mov     qword ptr [rsp+590h+var_538], rax
0x1800b2899  lea     rax, [rsp+590h+var_540]
0x1800b289e  mov     qword ptr [rsp+590h+var_568], rax
0x1800b28a3  lea     rax, [rsp+590h+var_538]
0x1800b28a8  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x1800b28ad  lea     rdx, word_1808691B2
0x1800b28b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800b28b9  jmp     loc_1800B2721
0x1800b28be  mov     eax, cs:dword_1808B5850
0x1800b28c4  cmp     eax, 2
0x1800b28c7  jbe     loc_1800B2721
0x1800b28cd  mov     [rsp+590h+var_540], r11
0x1800b28d2  mov     [rsp+590h+var_538], 8DCh
0x1800b28da  lea     rcx, aOnecoreTermsrv_7; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x1800b28e1  mov     [rsp+590h+var_520], rcx
0x1800b28e6  mov     dword ptr [rbp+490h+pusStatus], r8d
0x1800b28ea  lea     rax, aWinhttpCallbac_10; "WINHTTP_CALLBACK_STATUS_REDIRECT URL le"...
0x1800b28f1  mov     [rsp+590h+var_528], rax
0x1800b28f6  lea     rax, [rsp+590h+var_540]
0x1800b28fb  mov     [rsp+590h+var_550], rax
0x1800b2900  lea     rax, [rsp+590h+var_538]
0x1800b2905  mov     [rsp+590h+var_558], rax
0x1800b290a  lea     rax, [rsp+590h+var_520]
0x1800b290f  mov     [rsp+590h+var_560], rax
0x1800b2914  lea     rax, [rbp+490h+pusStatus]
0x1800b2918  mov     qword ptr [rsp+590h+var_568], rax
0x1800b291d  lea     rax, [rsp+590h+var_528]
0x1800b2922  lea     rdx, byte_180868FC7
0x1800b2929  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x1800b292e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800b2933  jmp     loc_1800B2721
0x1800b2938  mov     ecx, 100000h; this
0x1800b293d  cmp     esi, ecx
0x1800b293f  ja      loc_1800B3164
0x1800b2945  xor     r15d, r15d
0x1800b2948  cmp     esi, ecx
0x1800b294a  jz      loc_1800B2F45
0x1800b2950  cmp     esi, 8000h
0x1800b2956  jz      loc_1800B2EF0
0x1800b295c  cmp     esi, 10000h
0x1800b2962  jz      loc_1800B2E97
0x1800b2968  cmp     esi, 20000h
0x1800b296e  jz      loc_1800B2D95
0x1800b2974  mov     ecx, 40000h
0x1800b2979  cmp     esi, ecx
0x1800b297b  jz      loc_1800B2C26
0x1800b2981  cmp     esi, 80000h
0x1800b2987  jnz     loc_1800B31D0
0x1800b298d  cmp     dword ptr [rdi+60h], 3
0x1800b2991  jnz     loc_1800B2B7D
0x1800b2997  test    rbx, rbx
0x1800b299a  jz      loc_1800B2B74
0x1800b29a0  cmp     r12d, 8
0x1800b29a4  jb      loc_1800B2B74
0x1800b29aa  cmp     dword ptr [rbx+4], 4
0x1800b29ae  jnz     loc_1800B2B74
0x1800b29b4  xor     ecx, ecx
0x1800b29b6  xor     eax, eax
0x1800b29b8  lock cmpxchg [rdi+20h], rcx
0x1800b29be  mov     r15, rax
0x1800b29c1  mov     eax, 3E8h
0x1800b29c6  mov     [rbp+490h+pusStatus], ax
0x1800b29ca  mov     [rsp+590h+var_538], ecx
0x1800b29ce  xor     edx, edx; Val
0x1800b29d0  lea     r8d, [rcx+7Ch]; Size
0x1800b29d4  lea     rcx, [rbp+490h+pvReason]; void *
0x1800b29d8  call    memset_0
0x1800b29dd  test    r15, r15
0x1800b29e0  jz      short loc_1800B2A56
0x1800b29e2  lea     rax, [rsp+590h+var_538]
0x1800b29e7  mov     [rsp+590h+pdwReasonLengthConsumed], rax; pdwReasonLengthConsumed
0x1800b29ec  mov     r9d, 7Bh ; '{'; dwReasonLength
0x1800b29f2  lea     r8, [rbp+490h+pvReason]; pvReason
0x1800b29f6  lea     rdx, [rbp+490h+pusStatus]; pusStatus
0x1800b29fa  mov     rcx, r15; hWebSocket
0x1800b29fd  call    cs:__imp_WinHttpWebSocketQueryCloseStatus
0x1800b2a03  test    eax, eax
0x1800b2a05  jnz     short loc_1800B2A56
0x1800b2a07  mov     eax, [rsp+590h+var_538]
0x1800b2a0b  dec     eax
0x1800b2a0d  cmp     eax, 7Ah ; 'z'
0x1800b2a10  ja      short loc_1800B2A56
0x1800b2a12  mov     [rbp+490h+var_475], 0
0x1800b2a16  mov     eax, cs:dword_1808B5850
0x1800b2a1c  cmp     eax, 4
0x1800b2a1f  jbe     short loc_1800B2A56
0x1800b2a21  lea     rax, [rbp+490h+pvReason]
0x1800b2a25  mov     [rsp+590h+var_528], rax
0x1800b2a2a  lea     rax, aReceivedWebsoc; "Received websocket close frame reason"
0x1800b2a31  mov     [rsp+590h+var_520], rax
0x1800b2a36  lea     rax, [rsp+590h+var_528]
0x1800b2a3b  mov     qword ptr [rsp+590h+var_568], rax
0x1800b2a40  lea     rax, [rsp+590h+var_520]
0x1800b2a45  mov     [rsp+590h+pdwReasonLengthConsumed], rax
0x1800b2a4a  lea     rdx, byte_1808692C7
0x1800b2a51  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800b2a56  xor     ecx, ecx
0x1800b2a58  xor     eax, eax
0x1800b2a5a  lock cmpxchg [rdi+4Ch], ecx
0x1800b2a5f  jz      loc_1800B2B03
  ... truncated ...
```
