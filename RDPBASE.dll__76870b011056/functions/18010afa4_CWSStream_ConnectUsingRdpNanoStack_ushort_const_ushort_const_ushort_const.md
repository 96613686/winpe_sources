# CWSStream::ConnectUsingRdpNanoStack(ushort const *,ushort const *,ushort const *)

- ea: `0x18010afa4`
- end: `0x18010ba88`
- name: `?ConnectUsingRdpNanoStack@CWSStream@@AEAAJPEBG00@Z`
- size: `2788`
- prototype: `__int64 __fastcall(CWSStream *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180109cb0`

## callees

- `0x1800012d8`
- `0x180001aa0`
- `0x1800025dc`
- `0x180002f0c`
- `0x180004f70`
- `0x180005090`
- `0x180038984`
- `0x18006ce24`
- `0x1800787d4`
- `0x180078c20`
- `0x18007969c`
- `0x18010afa4`
- `0x180162010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010b0e0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010b0e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010b306`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010b306`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010b39a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010b39a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18010b0c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18010b0c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18010b006`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18010b006`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18010b6a9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18010b6a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b2a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b6b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b9bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b2a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b6b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b9bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010b7d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010b7d4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18010b27b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18010b27b`

## string_xrefs

- `0x18010b11f`: `StringCchCat of file path failed`
- `0x18010b0e6`: `rdpnanoTransport.dll`
- `0x18010b252`: `Loading dll`
- `0x18010b1ba`: `StringCchCopy of file path failed`
- `0x18010b2be`: `LoadLibrary failed for RdpNano.dll used for websocket.`
- `0x18010b2fc`: `CreateRdpWebSocketStreamWrapper`
- `0x18010b341`: `CreateRdpWebSocketStreamWrapper failed`
- `0x18010b6dc`: `CreateThread for STATIC_Decouple_ReadCompletion failed.`

## pseudocode

```c
__int64 __fastcall CWSStream::ConnectUsingRdpNanoStack(
        CWSStream *this,
        const char *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  signed int v7; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  signed int v11; // ebx
  __int16 *v12; // rdx
  const char **v13; // rax
  DWORD ModuleFileNameW; // eax
  wchar_t *v15; // rax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  HMODULE LibraryW; // rax
  signed int v20; // eax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  _QWORD **v24; // r15
  FARPROC ProcAddress; // rax
  int v26; // eax
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rcx
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  _QWORD *i; // r14
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  HANDLE Thread; // rax
  signed int v47; // eax
  int v48; // ecx
  int v49; // r8d
  int v50; // r9d
  int v51; // ecx
  int v52; // r8d
  _QWORD *v53; // r9
  __int128 v54; // xmm0
  __int128 v55; // xmm0
  __int64 v56; // rcx
  const char *v57; // rsi
  __int64 (__fastcall **v58)(__int64, const char *, _QWORD); // rax
  int v59; // ecx
  int v60; // r8d
  int v61; // r9d
  signed int LastError; // eax
  DWORD *v64; // [rsp+38h] [rbp-C8h]
  const char **v65; // [rsp+40h] [rbp-C0h]
  DWORD *v66; // [rsp+48h] [rbp-B8h]
  int v67; // [rsp+50h] [rbp-B0h] BYREF
  const char *v68; // [rsp+58h] [rbp-A8h] BYREF
  const char *v69; // [rsp+60h] [rbp-A0h] BYREF
  const char *v70; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v71[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v72; // [rsp+80h] [rbp-80h] BYREF
  DWORD ThreadId[2]; // [rsp+90h] [rbp-70h] BYREF
  HMODULE phModule; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Filename[264]; // [rsp+A0h] [rbp-60h] BYREF

  v71[0] = a3;
  phModule = 0;
  memset_0(Filename, 0, 0x20Au);
  if ( GetModuleHandleExW(6u, (LPCWSTR)CWSStream::STATIC_ReadCompletionWorker, &phModule) )
  {
    ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
    if ( !ModuleFileNameW || ModuleFileNameW == 261 )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        ThreadId[0] = 537;
        *(_QWORD *)&v72 = "Failed to get the module file name";
        v69 = "ConnectUsingRdpNanoStack";
        v68 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
        v12 = (__int16 *)&byte_1801C9D9F;
        v70 = "Error condition failed";
        v66 = (DWORD *)&v72;
        v65 = &v69;
        v64 = ThreadId;
        v13 = &v70;
        goto LABEL_69;
      }
    }
    else
    {
      v15 = wcsrchr(Filename, 0x5Cu);
      if ( v15 )
      {
        v15[1] = 0;
        v11 = StringCchCatW(Filename, 0x105u, L"rdpnanoTransport.dll");
        if ( v11 < 0 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            v67 = 545;
            v69 = "StringCchCat of file path failed";
            v68 = "ConnectUsingRdpNanoStack";
            v70 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
            LODWORD(v71[0]) = v11;
            *(_QWORD *)ThreadId = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              (_DWORD)CallbackContext,
              (unsigned int)&dword_1801C9CAC,
              v17,
              v18,
              (__int64)ThreadId,
              (__int64)v71,
              (__int64)&v70,
              (__int64)&v67,
              (__int64)&v68,
              (__int64)&v69);
          }
          return (unsigned int)v11;
        }
      }
      else
      {
        v11 = StringCchCopyW(Filename, 0x105u, L"rdpnanoTransport.dll");
        if ( v11 < 0 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            v67 = 550;
            v69 = "StringCchCopy of file path failed";
            v68 = "ConnectUsingRdpNanoStack";
            v70 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
            LODWORD(v71[0]) = v11;
            *(_QWORD *)ThreadId = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v16,
              (unsigned int)byte_1801C9CFD,
              v17,
              v18,
              (__int64)ThreadId,
              (__int64)v71,
              (__int64)&v70,
              (__int64)&v67,
              (__int64)&v68,
              (__int64)&v69);
          }
          return (unsigned int)v11;
        }
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v69 = (const char *)Filename;
        v68 = "Loading dll";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v16,
          (unsigned int)byte_1801C9C43,
          v17,
          v18,
          (__int64)&v68,
          (__int64)&v69);
      }
      LibraryW = LoadLibraryW(Filename);
      *((_QWORD *)this + 164) = LibraryW;
      if ( LibraryW )
      {
        v24 = (_QWORD **)((char *)this + 1296);
        *((_QWORD *)this + 162) = 0;
        ProcAddress = GetProcAddress(LibraryW, "CreateRdpWebSocketStreamWrapper");
        if ( ProcAddress )
        {
          v26 = ((__int64 (__fastcall *)(__int64, char *))ProcAddress)(1, (char *)this + 1296);
          if ( v26 < 0 && (unsigned int)CallbackContext > 3 )
          {
            v67 = v26;
            v69 = "ConnectUsingRdpNanoStack";
            v68 = "CreateRdpWebSocketStreamWrapper failed";
            v70 = "HResult failed but continue";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              (_DWORD)CallbackContext,
              (unsigned int)&byte_1801C9BBF,
              v27,
              v28,
              (__int64)&v70,
              (__int64)&v68,
              (__int64)&v67,
              (__int64)&v69);
          }
        }
        v29 = (__int64)*v24;
        if ( *v24 )
        {
          ThreadId[0] = 0;
          v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const char *))(*(_QWORD *)v29 + 24LL))(
                  v29,
                  L"RDG-Connection-Id",
                  a2);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *))(**v24 + 24LL))(
                    *v24,
                    L"RDG-Auth-Scheme",
                    L"CONNID");
            if ( v11 >= 0 )
            {
              if ( a4
                && *a4
                && (v11 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const unsigned __int16 *))(**v24 + 24LL))(
                            *v24,
                            L"RDG-Correlation-Id",
                            a4),
                    v11 < 0) )
              {
                if ( (unsigned int)CallbackContext > 2 )
                {
                  v69 = "ConnectUsingRdpNanoStack";
                  *(_QWORD *)&v72 = "AddCustomHttpHeader (rdg-correlation-id) failed";
                  v67 = 619;
                  v68 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
                  v70 = "Error HResult failed";
                  LODWORD(v71[0]) = v11;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v39,
                    (unsigned int)byte_1801C9B1D,
                    v40,
                    v41,
                    (__int64)&v70,
                    (__int64)v71,
                    (__int64)&v68,
                    (__int64)&v67,
                    (__int64)&v69,
                    (__int64)&v72);
                }
              }
              else
              {
                for ( i = (_QWORD *)*((_QWORD *)this + 229); ; i = (_QWORD *)*i )
                {
                  if ( !i )
                  {
                    Thread = CreateThread(0, 0, CWSStream::STATIC_ReadCompletionWorker, this, 0, ThreadId);
                    if ( Thread )
                    {
                      CloseHandle(Thread);
                      v53 = operator new(0x20u);
                      if ( v53 )
                      {
                        v54 = *(_OWORD *)((char *)this + 1148);
                        v53[1] = this;
                        *v53 = &RdpWebSocketStreamWrapperCallbackImpl::`vftable';
                        *((_OWORD *)v53 + 1) = v54;
                      }
                      else
                      {
                        v53 = 0;
                      }
                      *((_QWORD *)this + 163) = v53;
                      if ( v53 )
                      {
                        v55 = *(_OWORD *)((char *)this + 1148);
                        v56 = (__int64)*v24;
                        v57 = (const char *)v71[0];
                        v58 = (__int64 (__fastcall **)(__int64, const char *, _QWORD))**v24;
                        v72 = v55;
                        v11 = (*v58)(v56, a2, v71[0]);
                        if ( v11 >= 0 )
                        {
                          if ( (unsigned int)CallbackContext > 5 )
                          {
                            *(_QWORD *)&v72 = a4;
                            v70 = "RdpNano: Connecting";
                            v69 = a2;
                            v68 = v57;
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                              v59,
                              (unsigned int)&dword_1801C995C,
                              v60,
                              v61,
                              (__int64)&v70,
                              (__int64)&v68,
                              (__int64)&v69,
                              (__int64)&v72);
                          }
                        }
                        else if ( (unsigned int)CallbackContext > 2 )
                        {
                          v69 = "ConnectUsingRdpNanoStack";
                          *(_QWORD *)&v72 = "RdpWebSocketNanoWrapper Initialize failed";
                          v67 = 656;
                          v68 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
                          v70 = "Error HResult failed";
                          LODWORD(v71[0]) = v11;
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                            v59,
                            (unsigned int)byte_1801C990B,
                            v60,
                            v61,
                            (__int64)&v70,
                            (__int64)v71,
                            (__int64)&v68,
                            (__int64)&v67,
                            (__int64)&v69,
                            (__int64)&v72);
                        }
                      }
                      else
                      {
                        v11 = -2147024882;
                        if ( (unsigned int)CallbackContext > 2 )
                        {
                          v69 = "ConnectUsingRdpNanoStack";
                          *(_QWORD *)&v72 = "WebSocketStreamWrapperCallback allocation";
                          v67 = 653;
                          v68 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
                          v70 = "Error condition failed";
                          LODWORD(v71[0]) = -2147024882;
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                            v51,
                            (unsigned int)qword_1801C99F8,
                            v52,
                            0,
                            (__int64)&v70,
                            (__int64)v71,
                            (__int64)&v68,
                            (__int64)&v67,
                            (__int64)&v69,
                            (__int64)&v72);
                        }
                      }
                    }
                    else
                    {
                      v47 = GetLastError();
                      v11 = v47;
                      if ( v47 > 0 )
                        v11 = (unsigned __int16)v47 | 0x80070000;
                      if ( (unsigned int)CallbackContext > 2 )
                      {
                        v69 = "ConnectUsingRdpNanoStack";
                        *(_QWORD *)&v72 = "CreateThread for STATIC_Decouple_ReadCompletion failed.";
                        v67 = 644;
                        v68 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
                        v70 = "Error condition failed";
                        LODWORD(v71[0]) = v11;
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                          v48,
                          (unsigned int)&byte_1801C99A7,
                          v49,
                          v50,
                          (__int64)&v70,
                          (__int64)v71,
                          (__int64)&v68,
                          (__int64)&v67,
                          (__int64)&v69,
                          (__int64)&v72);
                      }
                    }
                    return (unsigned int)v11;
                  }
                  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**v24 + 24LL))(*v24, i[1], i[2]);
                  if ( v11 < 0 )
                    break;
                  if ( (unsigned int)CallbackContext > 5 )
                  {
                    *(_QWORD *)&v72 = i[2];
                    v69 = (const char *)i[1];
                    v68 = "RdpNano: Header";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                      v43,
                      (unsigned int)word_1801C9A9A,
                      v44,
                      v45,
                      (__int64)&v68,
                      (__int64)&v69,
                      (__int64)&v72);
                  }
                }
                if ( (unsigned int)CallbackContext > 2 )
                {
                  v69 = "ConnectUsingRdpNanoStack";
                  *(_QWORD *)&v72 = "AddCustomHttpHeader custom failed";
                  v67 = 629;
                  v68 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
                  v70 = "Error HResult failed";
                  LODWORD(v71[0]) = v11;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v43,
                    (unsigned int)byte_1801C9A49,
                    v44,
                    v45,
                    (__int64)&v70,
                    (__int64)v71,
                    (__int64)&v68,
                    (__int64)&v67,
                    (__int64)&v69,
                    (__int64)&v72);
                }
              }
            }
            else if ( (unsigned int)CallbackContext > 2 )
            {
              v69 = "ConnectUsingRdpNanoStack";
              *(_QWORD *)&v72 = "AddCustomHttpHeader (RDG-AuthScheme) failed";
              v67 = 608;
              v68 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
              v70 = "Error HResult failed";
              LODWORD(v71[0]) = v11;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v36,
                (unsigned int)&dword_1801C9ACC,
                v37,
                v38,
                (__int64)&v70,
                (__int64)v71,
                (__int64)&v68,
                (__int64)&v67,
                (__int64)&v69,
                (__int64)&v72);
            }
          }
          else if ( (unsigned int)CallbackContext > 2 )
          {
            v68 = "ConnectUsingRdpNanoStack";
            v69 = "AddCustomHttpHeader (rdg-connection-id) failed";
            v67 = 601;
            v70 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
            *(_QWORD *)&v72 = "Error HResult failed";
            LODWORD(v71[0]) = v11;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v33,
              (unsigned int)&word_1801C9B6E,
              v34,
              v35,
              (__int64)&v72,
              (__int64)v71,
              (__int64)&v70,
              (__int64)&v67,
              (__int64)&v68,
              (__int64)&v69);
          }
        }
        else
        {
          FreeLibrary(*((HMODULE *)this + 164));
          *((_QWORD *)this + 164) = 0;
          if ( (unsigned int)CallbackContext > 3 )
          {
            v69 = a2;
            v68 = "Failed to get Nano wrapper with the right interface version.";
            v67 = 1;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              v30,
              (unsigned int)&word_1801C9BFE,
              v31,
              v32,
              (__int64)&v68,
              (__int64)&v67,
              (__int64)&v69);
          }
          return 0;
        }
      }
      else if ( (unsigned int)CallbackContext > 3 )
      {
        v69 = a2;
        v20 = GetLastError();
        if ( v20 > 0 )
          v20 = (unsigned __int16)v20 | 0x80070000;
        v67 = v20;
        v68 = "LoadLibrary failed for RdpNano.dll used for websocket.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v21,
          (unsigned int)byte_1801C9C71,
          v22,
          v23,
          (__int64)&v68,
          (__int64)&v67,
          (__int64)&v69);
      }
    }
  }
  else
  {
    v7 = GetLastError();
    v11 = v7;
    if ( v7 > 0 )
      v11 = (unsigned __int16)v7 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v71[0]) = 533;
      *(_QWORD *)ThreadId = "Failed to get module handle to itself.";
      v70 = "ConnectUsingRdpNanoStack";
      v68 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v12 = &word_1801C9D4E;
      v69 = "Error condition failed";
      v66 = ThreadId;
      v65 = &v70;
      v64 = (DWORD *)v71;
      v13 = &v69;
LABEL_69:
      v67 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v8,
        (_DWORD)v12,
        v9,
        v10,
        (__int64)v13,
        (__int64)&v67,
        (__int64)&v68,
        (__int64)v64,
        (__int64)v65,
        (__int64)v66);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18010afa4  push    rbp
0x18010afa6  push    rbx
0x18010afa7  push    rsi
0x18010afa8  push    rdi
0x18010afa9  push    r12
0x18010afab  push    r13
0x18010afad  push    r14
0x18010afaf  push    r15
0x18010afb1  lea     rbp, [rsp-1C8h]
0x18010afb9  sub     rsp, 2C8h
0x18010afc0  mov     rax, cs:__security_cookie
0x18010afc7  xor     rax, rsp
0x18010afca  mov     [rbp+200h+var_50], rax
0x18010afd1  mov     [rsp+300h+var_290], r8
0x18010afd6  mov     r12, rdx
0x18010afd9  mov     rsi, rcx
0x18010afdc  xor     r14d, r14d
0x18010afdf  xor     edx, edx; Val
0x18010afe1  mov     [rbp+200h+phModule], r14
0x18010afe5  mov     r8d, 20Ah; Size
0x18010afeb  lea     rcx, [rbp+200h+Filename]; void *
0x18010afef  mov     r13, r9
0x18010aff2  call    memset_0
0x18010aff7  lea     r8, [rbp+200h+phModule]; phModule
0x18010affb  lea     rdx, ?STATIC_ReadCompletionWorker@CWSStream@@CAKPEAX@Z; lpModuleName
0x18010b002  lea     ecx, [r14+6]; dwFlags
0x18010b006  call    cs:__imp_GetModuleHandleExW
0x18010b00c  test    eax, eax
0x18010b00e  jnz     loc_18010B0B1
0x18010b014  call    cs:__imp_GetLastError
0x18010b01a  mov     ebx, eax
0x18010b01c  test    eax, eax
0x18010b01e  jle     short loc_18010B029
0x18010b020  movzx   ebx, ax
0x18010b023  or      ebx, 80070000h
0x18010b029  mov     eax, cs:CallbackContext
0x18010b02f  cmp     eax, 2
0x18010b032  jbe     loc_18010BA63
0x18010b038  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself."
0x18010b03f  mov     dword ptr [rsp+300h+var_290], 215h
0x18010b047  mov     qword ptr [rbp+200h+ThreadId], rax
0x18010b04b  lea     rdi, aConnectusingrd; "ConnectUsingRdpNanoStack"
0x18010b052  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010b059  mov     [rsp+300h+var_298], rdi
0x18010b05e  mov     [rsp+300h+var_2A8], rax
0x18010b063  lea     rdx, word_1801C9D4E
0x18010b06a  lea     rax, aErrorCondition; "Error condition failed"
0x18010b071  mov     [rsp+300h+var_2A0], rax
0x18010b076  lea     rax, [rbp+200h+ThreadId]
0x18010b07a  mov     [rsp+300h+var_2B8], rax
0x18010b07f  lea     rax, [rsp+300h+var_298]
0x18010b084  mov     [rsp+300h+var_2C0], rax
0x18010b089  lea     rax, [rsp+300h+var_290]
0x18010b08e  mov     [rsp+300h+var_2C8], rax
0x18010b093  lea     rax, [rsp+300h+var_2A8]
0x18010b098  mov     [rsp+300h+var_2D0], rax
0x18010b09d  lea     rax, [rsp+300h+var_2B0]
0x18010b0a2  mov     [rsp+300h+lpThreadId], rax
0x18010b0a7  lea     rax, [rsp+300h+var_2A0]
0x18010b0ac  jmp     loc_18010BA55
0x18010b0b1  mov     rcx, [rbp+200h+phModule]; hModule
0x18010b0b5  lea     rdx, [rbp+200h+Filename]; lpFilename
0x18010b0b9  mov     ebx, 105h
0x18010b0be  mov     r8d, ebx; nSize
0x18010b0c1  call    cs:__imp_GetModuleFileNameW
0x18010b0c7  test    eax, eax
0x18010b0c9  jz      loc_18010B9BF
0x18010b0cf  cmp     eax, ebx
0x18010b0d1  jz      loc_18010B9BF
0x18010b0d7  mov     edx, 5Ch ; '\'; Ch
0x18010b0dc  lea     rcx, [rbp+200h+Filename]; Str
0x18010b0e0  call    cs:__imp_wcsrchr
0x18010b0e6  lea     r8, aRdpnanotranspo; "rdpnanoTransport.dll"
0x18010b0ed  mov     edx, ebx; unsigned __int64
0x18010b0ef  lea     rcx, [rbp+200h+Filename]; unsigned __int16 *
0x18010b0f3  test    rax, rax
0x18010b0f6  jz      loc_18010B19C
0x18010b0fc  mov     [rax+2], r14w
0x18010b101  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18010b106  mov     ebx, eax
0x18010b108  test    eax, eax
0x18010b10a  jns     loc_18010B237
0x18010b110  mov     ecx, cs:CallbackContext
0x18010b116  cmp     ecx, 2
0x18010b119  jbe     loc_18010BA63
0x18010b11f  lea     rax, aStringcchcatOf; "StringCchCat of file path failed"
0x18010b126  mov     [rsp+300h+var_2B0], 221h
0x18010b12e  mov     [rsp+300h+var_2A0], rax
0x18010b133  lea     rdi, aConnectusingrd; "ConnectUsingRdpNanoStack"
0x18010b13a  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010b141  mov     [rsp+300h+var_2A8], rdi
0x18010b146  mov     [rsp+300h+var_298], rax
0x18010b14b  lea     rdx, dword_1801C9CAC
0x18010b152  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18010b159  mov     dword ptr [rsp+300h+var_290], ebx
0x18010b15d  mov     qword ptr [rbp+200h+ThreadId], rax
0x18010b161  lea     rax, [rsp+300h+var_2A0]
0x18010b166  mov     [rsp+300h+var_2B8], rax
0x18010b16b  lea     rax, [rsp+300h+var_2A8]
0x18010b170  mov     [rsp+300h+var_2C0], rax
0x18010b175  lea     rax, [rsp+300h+var_2B0]
0x18010b17a  mov     [rsp+300h+var_2C8], rax
0x18010b17f  lea     rax, [rsp+300h+var_298]
0x18010b184  mov     [rsp+300h+var_2D0], rax
0x18010b189  lea     rax, [rsp+300h+var_290]
0x18010b18e  mov     [rsp+300h+lpThreadId], rax
0x18010b193  lea     rax, [rbp+200h+ThreadId]
0x18010b197  jmp     loc_18010BA59
0x18010b19c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18010b1a1  mov     ebx, eax
0x18010b1a3  test    eax, eax
0x18010b1a5  jns     loc_18010B237
0x18010b1ab  mov     eax, cs:CallbackContext
0x18010b1b1  cmp     eax, 2
0x18010b1b4  jbe     loc_18010BA63
0x18010b1ba  lea     rax, aStringcchcopyO_2; "StringCchCopy of file path failed"
0x18010b1c1  mov     [rsp+300h+var_2B0], 226h
0x18010b1c9  mov     [rsp+300h+var_2A0], rax
0x18010b1ce  lea     rdi, aConnectusingrd; "ConnectUsingRdpNanoStack"
0x18010b1d5  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010b1dc  mov     [rsp+300h+var_2A8], rdi
0x18010b1e1  mov     [rsp+300h+var_298], rax
0x18010b1e6  lea     rdx, byte_1801C9CFD
0x18010b1ed  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18010b1f4  mov     dword ptr [rsp+300h+var_290], ebx
0x18010b1f8  mov     qword ptr [rbp+200h+ThreadId], rax
0x18010b1fc  lea     rax, [rsp+300h+var_2A0]
0x18010b201  mov     [rsp+300h+var_2B8], rax
0x18010b206  lea     rax, [rsp+300h+var_2A8]
0x18010b20b  mov     [rsp+300h+var_2C0], rax
0x18010b210  lea     rax, [rsp+300h+var_2B0]
0x18010b215  mov     [rsp+300h+var_2C8], rax
0x18010b21a  lea     rax, [rsp+300h+var_298]
0x18010b21f  mov     [rsp+300h+var_2D0], rax
0x18010b224  lea     rax, [rsp+300h+var_290]
0x18010b229  mov     [rsp+300h+lpThreadId], rax
0x18010b22e  lea     rax, [rbp+200h+ThreadId]
0x18010b232  jmp     loc_18010BA59
0x18010b237  mov     eax, cs:CallbackContext
0x18010b23d  cmp     eax, 4
0x18010b240  jbe     short loc_18010B277
0x18010b242  lea     rax, [rbp+200h+Filename]
0x18010b246  mov     [rsp+300h+var_2A0], rax
0x18010b24b  lea     rdx, byte_1801C9C43
0x18010b252  lea     rax, aLoadingDll; "Loading dll"
0x18010b259  mov     [rsp+300h+var_2A8], rax
0x18010b25e  lea     rax, [rsp+300h+var_2A0]
0x18010b263  mov     [rsp+300h+lpThreadId], rax
0x18010b268  lea     rax, [rsp+300h+var_2A8]
0x18010b26d  mov     qword ptr [rsp+300h+dwCreationFlags], rax
0x18010b272  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18010b277  lea     rcx, [rbp+200h+Filename]; lpLibFileName
0x18010b27b  call    cs:__imp_LoadLibraryW
0x18010b281  mov     [rsi+520h], rax
0x18010b288  test    rax, rax
0x18010b28b  jnz     short loc_18010B2F2
0x18010b28d  mov     eax, cs:CallbackContext
0x18010b293  cmp     eax, 3
0x18010b296  jbe     loc_18010BA63
0x18010b29c  mov     [rsp+300h+var_2A0], r12
0x18010b2a1  call    cs:__imp_GetLastError
0x18010b2a7  test    eax, eax
0x18010b2a9  jle     short loc_18010B2B3
0x18010b2ab  movzx   eax, ax
0x18010b2ae  or      eax, 80070000h
0x18010b2b3  mov     [rsp+300h+var_2B0], eax
0x18010b2b7  lea     rdx, byte_1801C9C71
0x18010b2be  lea     rax, aLoadlibraryFai; "LoadLibrary failed for RdpNano.dll used"...
0x18010b2c5  mov     [rsp+300h+var_2A8], rax
0x18010b2ca  lea     rax, [rsp+300h+var_2A0]
0x18010b2cf  mov     [rsp+300h+var_2D0], rax
0x18010b2d4  lea     rax, [rsp+300h+var_2B0]
0x18010b2d9  mov     [rsp+300h+lpThreadId], rax
0x18010b2de  lea     rax, [rsp+300h+var_2A8]
0x18010b2e3  mov     qword ptr [rsp+300h+dwCreationFlags], rax
0x18010b2e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18010b2ed  jmp     loc_18010BA63
0x18010b2f2  lea     r15, [rsi+510h]
0x18010b2f9  mov     rcx, rax; hModule
0x18010b2fc  lea     rdx, aCreaterdpwebso_0; "CreateRdpWebSocketStreamWrapper"
0x18010b303  mov     [r15], r14
0x18010b306  call    cs:__imp_GetProcAddress
0x18010b30c  lea     rdi, aConnectusingrd; "ConnectUsingRdpNanoStack"
0x18010b313  mov     ebx, 1
0x18010b318  test    rax, rax
0x18010b31b  jz      short loc_18010B38B
0x18010b31d  mov     rdx, r15
0x18010b320  mov     ecx, ebx
0x18010b322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b327  test    eax, eax
0x18010b329  jns     short loc_18010B38B
0x18010b32b  mov     ecx, cs:CallbackContext
0x18010b331  cmp     ecx, 3
0x18010b334  jbe     short loc_18010B38B
0x18010b336  mov     [rsp+300h+var_2B0], eax
0x18010b33a  lea     rdx, byte_1801C9BBF
0x18010b341  lea     rax, aCreaterdpwebso; "CreateRdpWebSocketStreamWrapper failed"
0x18010b348  mov     [rsp+300h+var_2A0], rdi
0x18010b34d  mov     [rsp+300h+var_2A8], rax
0x18010b352  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18010b359  mov     [rsp+300h+var_298], rax
0x18010b35e  lea     rax, [rsp+300h+var_2A0]
0x18010b363  mov     [rsp+300h+var_2C8], rax
0x18010b368  lea     rax, [rsp+300h+var_2B0]
0x18010b36d  mov     [rsp+300h+var_2D0], rax
0x18010b372  lea     rax, [rsp+300h+var_2A8]
0x18010b377  mov     [rsp+300h+lpThreadId], rax
0x18010b37c  lea     rax, [rsp+300h+var_298]
0x18010b381  mov     qword ptr [rsp+300h+dwCreationFlags], rax
0x18010b386  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010b38b  mov     rcx, [r15]
0x18010b38e  test    rcx, rcx
0x18010b391  jnz     short loc_18010B3F9
0x18010b393  mov     rcx, [rsi+520h]; hLibModule
0x18010b39a  call    cs:__imp_FreeLibrary
0x18010b3a0  mov     [rsi+520h], r14
0x18010b3a7  mov     eax, cs:CallbackContext
0x18010b3ad  cmp     eax, 3
0x18010b3b0  jbe     short loc_18010B3F1
0x18010b3b2  lea     rax, aFailedToGetNan; "Failed to get Nano wrapper with the rig"...
0x18010b3b9  mov     [rsp+300h+var_2A0], r12
0x18010b3be  mov     [rsp+300h+var_2A8], rax
0x18010b3c3  lea     rdx, word_1801C9BFE
0x18010b3ca  lea     rax, [rsp+300h+var_2A0]
0x18010b3cf  mov     [rsp+300h+var_2B0], ebx
0x18010b3d3  mov     [rsp+300h+var_2D0], rax
0x18010b3d8  lea     rax, [rsp+300h+var_2B0]
0x18010b3dd  mov     [rsp+300h+lpThreadId], rax
0x18010b3e2  lea     rax, [rsp+300h+var_2A8]
0x18010b3e7  mov     qword ptr [rsp+300h+dwCreationFlags], rax
0x18010b3ec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18010b3f1  mov     ebx, r14d
0x18010b3f4  jmp     loc_18010BA63
0x18010b3f9  mov     [rbp+200h+ThreadId], r14d
0x18010b3fd  lea     rdx, aRdgConnectionI; "RDG-Connection-Id"
0x18010b404  mov     rax, [rcx]
0x18010b407  mov     r8, r12
0x18010b40a  mov     rax, [rax+18h]
0x18010b40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b413  mov     ebx, eax
0x18010b415  test    eax, eax
0x18010b417  jns     loc_18010B4A2
0x18010b41d  mov     eax, cs:CallbackContext
0x18010b423  cmp     eax, 2
0x18010b426  jbe     loc_18010BA63
0x18010b42c  lea     rax, aAddcustomhttph_1; "AddCustomHttpHeader (rdg-connection-id)"...
0x18010b433  mov     [rsp+300h+var_2A8], rdi
0x18010b438  mov     [rsp+300h+var_2A0], rax
0x18010b43d  lea     rdx, word_1801C9B6E
0x18010b444  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010b44b  mov     [rsp+300h+var_2B0], 259h
0x18010b453  mov     [rsp+300h+var_298], rax
0x18010b458  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18010b45f  mov     qword ptr [rbp+200h+var_280], rax
0x18010b463  lea     rax, [rsp+300h+var_2A0]
0x18010b468  mov     [rsp+300h+var_2B8], rax
0x18010b46d  lea     rax, [rsp+300h+var_2A8]
0x18010b472  mov     [rsp+300h+var_2C0], rax
0x18010b477  lea     rax, [rsp+300h+var_2B0]
0x18010b47c  mov     [rsp+300h+var_2C8], rax
0x18010b481  lea     rax, [rsp+300h+var_298]
0x18010b486  mov     [rsp+300h+var_2D0], rax
0x18010b48b  lea     rax, [rsp+300h+var_290]
0x18010b490  mov     [rsp+300h+lpThreadId], rax
0x18010b495  lea     rax, [rbp+200h+var_280]
0x18010b499  mov     dword ptr [rsp+300h+var_290], ebx
0x18010b49d  jmp     loc_18010BA59
0x18010b4a2  mov     rcx, [r15]
0x18010b4a5  lea     r8, aConnid; "CONNID"
0x18010b4ac  lea     rdx, aRdgAuthScheme; "RDG-Auth-Scheme"
0x18010b4b3  mov     rax, [rcx]
0x18010b4b6  mov     rax, [rax+18h]
0x18010b4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b4bf  mov     ebx, eax
0x18010b4c1  test    eax, eax
0x18010b4c3  jns     loc_18010B54E
0x18010b4c9  mov     eax, cs:CallbackContext
0x18010b4cf  cmp     eax, 2
0x18010b4d2  jbe     loc_18010BA63
0x18010b4d8  lea     rax, aAddcustomhttph_0; "AddCustomHttpHeader (RDG-AuthScheme) fa"...
0x18010b4df  mov     [rsp+300h+var_2A0], rdi
0x18010b4e4  mov     qword ptr [rbp+200h+var_280], rax
0x18010b4e8  lea     rdx, dword_1801C9ACC
0x18010b4ef  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010b4f6  mov     [rsp+300h+var_2B0], 260h
0x18010b4fe  mov     [rsp+300h+var_2A8], rax
0x18010b503  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18010b50a  mov     [rsp+300h+var_298], rax
0x18010b50f  lea     rax, [rbp+200h+var_280]
0x18010b513  mov     [rsp+300h+var_2B8], rax
0x18010b518  lea     rax, [rsp+300h+var_2A0]
0x18010b51d  mov     [rsp+300h+var_2C0], rax
0x18010b522  lea     rax, [rsp+300h+var_2B0]
0x18010b527  mov     [rsp+300h+var_2C8], rax
0x18010b52c  lea     rax, [rsp+300h+var_2A8]
0x18010b531  mov     [rsp+300h+var_2D0], rax
0x18010b536  lea     rax, [rsp+300h+var_290]
0x18010b53b  mov     [rsp+300h+lpThreadId], rax
0x18010b540  lea     rax, [rsp+300h+var_298]
0x18010b545  mov     dword ptr [rsp+300h+var_290], ebx
  ... truncated ...
```
