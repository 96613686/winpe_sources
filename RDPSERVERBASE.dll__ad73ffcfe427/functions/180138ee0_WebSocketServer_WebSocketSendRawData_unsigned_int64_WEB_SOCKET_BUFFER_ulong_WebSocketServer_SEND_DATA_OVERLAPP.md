# WebSocketServer::WebSocketSendRawData(unsigned __int64,_WEB_SOCKET_BUFFER *,ulong,WebSocketServer::SEND_DATA_OVERLAPPED *)

- ea: `0x180138ee0`
- end: `0x1801391c7`
- name: `?WebSocketSendRawData@WebSocketServer@@AEAAJ_KPEAT_WEB_SOCKET_BUFFER@@KPEAUSEND_DATA_OVERLAPPED@1@@Z`
- size: `743`
- prototype: `int(WebSocketServer *__hidden this, unsigned __int64, union _WEB_SOCKET_BUFFER *, unsigned int, struct WebSocketServer::SEND_DATA_OVERLAPPED *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180137c30`
- `0x18013893c`

## callees

- `0x18000116c`
- `0x180002170`
- `0x18003b118`
- `0x18007e9e0`
- `0x18007f348`
- `0x18007f42c`
- `0x180133f50`
- `0x180138ee0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138f32`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138f32`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180139165`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180139165`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180139198`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180139198`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180139131`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180139131`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1801390a2`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1801390a2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180139045`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180139045`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x180139080`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x180139080`

## pseudocode

```c
__int64 __fastcall WebSocketServer::WebSocketSendRawData(
        WebSocketServer *this,
        HTTP_REQUEST_ID a2,
        union _WEB_SOCKET_BUFFER *a3,
        unsigned int a4,
        struct WebSocketServer::SEND_DATA_OVERLAPPED *Overlapped)
{
  int v9; // r8d
  int v10; // r9d
  unsigned int v11; // edi
  unsigned int v12; // r8d
  __int64 v13; // r10
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  ULONG v16; // eax
  signed int v17; // edi
  int v18; // r8d
  int v19; // r9d
  __int64 i; // rdx
  __int64 NextOf; // rax
  __int64 v22; // rdi
  ULONGLONG TickCount64; // rax
  __int64 v24; // r8
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v28; // [rsp+58h] [rbp-A8h] BYREF
  const char *v29; // [rsp+60h] [rbp-A0h] BYREF
  const char *v30; // [rsp+68h] [rbp-98h] BYREF
  GUID ActivityId; // [rsp+70h] [rbp-90h] BYREF
  struct _HTTP_DATA_CHUNK EntityChunks[4]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t String2[40]; // [rsp+100h] [rbp+0h] BYREF

  ActivityId = *(GUID *)((char *)Overlapped + 36);
  EventActivityIdControl(2u, &ActivityId);
  memset_0(EntityChunks, 0, sizeof(EntityChunks));
  v11 = 4;
  if ( a4 <= 4 )
  {
    v11 = a4;
    v12 = 0;
    if ( !a4 )
      goto LABEL_8;
  }
  else
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v28 = a4;
      *(_QWORD *)&ActivityId.Data1 = "WebSocketSendRawData - bufferCount is bigger than 4 bufferCount: %d";
      v29 = "WebSocketSendRawData";
      v26 = 714;
      v30 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      v27 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp",
        (unsigned int)byte_1802939DD,
        v9,
        v10,
        (__int64)&ActivityId,
        (__int64)&v27,
        (__int64)&v30,
        (__int64)&v26,
        (__int64)&v29,
        (__int64)&v28);
    }
    v12 = 0;
  }
  v13 = 0;
  do
  {
    v14 = 32 * v13;
    v15 = 2 * v13;
    ++v12;
    ++v13;
    *(PVOID *)((char *)&EntityChunks[0].FromMemory.pBuffer + v14) = (PVOID)*((_QWORD *)a3 + v15);
    *(DWORD *)((char *)&EntityChunks[0].FromFragmentCacheEx.ByteRange.Length.LowPart + v14) = *((_DWORD *)a3
                                                                                              + 2 * v15
                                                                                              + 2);
    EntityChunks[v14 / 0x20].DataChunkType = HttpDataChunkFromMemory;
  }
  while ( v12 < v11 );
LABEL_8:
  StringCchCopyW(String2, 0x28u, (const unsigned __int16 *)Overlapped + 28);
  *((_DWORD *)Overlapped + 8) = 5;
  StartThreadpoolIo(*((PTP_IO *)this + 20));
  v16 = HttpSendResponseEntityBody(
          *((HANDLE *)this + 19),
          a2,
          6u,
          v11,
          EntityChunks,
          0,
          0,
          0,
          (LPOVERLAPPED)Overlapped,
          0);
  v17 = v16;
  if ( !v16 || v16 == 997 )
  {
    AcquireSRWLockShared((PSRWLOCK)this + 8);
    for ( i = 0; ; i = v22 )
    {
      NextOf = CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx((char *)this + 176, i);
      v22 = NextOf;
      if ( !NextOf )
        break;
      if ( !wcsicmp((const wchar_t *)(NextOf + 48), String2) )
      {
        TickCount64 = GetTickCount64();
        v24 = *(_QWORD *)(v22 + 256);
        if ( v24 && TickCount64 - v24 > *(_QWORD *)(v22 + 264) )
          *(_QWORD *)(v22 + 264) = TickCount64 - v24;
        *(_QWORD *)(v22 + 256) = TickCount64;
        break;
      }
    }
    ReleaseSRWLockShared((PSRWLOCK)this + 8);
  }
  else
  {
    CancelThreadpoolIo(*((PTP_IO *)this + 20));
    if ( (unsigned int)CallbackContext > 2 )
    {
      *(_QWORD *)&ActivityId.Data1 = "WebSocketSendRawData";
      v30 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      v27 = 753;
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      v26 = v17;
      v29 = "HttpSendResponseEntityBody (WS) failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_180293995,
        v18,
        v19,
        (__int64)&v29,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)&v27,
        (__int64)&ActivityId);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180138ee0  mov     [rsp-8+arg_10], rbx
0x180138ee5  push    rbp
0x180138ee6  push    rsi
0x180138ee7  push    rdi
0x180138ee8  push    r12
0x180138eea  push    r13
0x180138eec  push    r14
0x180138eee  push    r15
0x180138ef0  lea     rbp, [rsp-60h]
0x180138ef5  sub     rsp, 160h
0x180138efc  mov     rax, cs:__security_cookie
0x180138f03  xor     rax, rsp
0x180138f06  mov     [rbp+90h+var_40], rax
0x180138f0a  mov     r14, [rbp+90h+arg_20]
0x180138f11  mov     r12, rdx
0x180138f14  mov     rsi, rcx
0x180138f17  lea     rdx, [rsp+190h+ActivityId]; ActivityId
0x180138f1c  mov     ecx, 2; ControlCode
0x180138f21  mov     ebx, r9d
0x180138f24  mov     r15, r8
0x180138f27  movups  xmm0, xmmword ptr [r14+24h]
0x180138f2c  movdqu  xmmword ptr [rsp+190h+ActivityId.Data1], xmm0
0x180138f32  call    cs:__imp_EventActivityIdControl
0x180138f38  xor     edx, edx; Val
0x180138f3a  lea     rcx, [rbp+90h+var_110]; void *
0x180138f3e  mov     r8d, 80h; Size
0x180138f44  call    memset_0
0x180138f49  mov     edi, 4
0x180138f4e  lea     r13, aWebsocketsendr; "WebSocketSendRawData"
0x180138f55  lea     rcx, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180138f5c  cmp     ebx, edi
0x180138f5e  jbe     loc_180138FE8
0x180138f64  mov     eax, cs:CallbackContext
0x180138f6a  cmp     eax, 2
0x180138f6d  jbe     short loc_180138FE1
0x180138f6f  lea     rax, aWebsocketsendr_1; "WebSocketSendRawData - bufferCount is b"...
0x180138f76  mov     [rsp+190h+var_138], ebx
0x180138f7a  mov     qword ptr [rsp+190h+ActivityId.Data1], rax
0x180138f7f  lea     rdx, byte_1802939DD
0x180138f86  lea     rax, [rsp+190h+var_138]
0x180138f8b  mov     [rsp+190h+var_130], r13
0x180138f90  mov     [rsp+190h+LogData], rax
0x180138f95  lea     rax, [rsp+190h+var_130]
0x180138f9a  mov     [rsp+190h+Overlapped], rax
0x180138f9f  lea     rax, [rsp+190h+var_140]
0x180138fa4  mov     qword ptr [rsp+190h+Reserved2], rax
0x180138fa9  lea     rax, [rsp+190h+var_128]
0x180138fae  mov     [rsp+190h+Reserved1], rax
0x180138fb3  lea     rax, [rsp+190h+var_13C]
0x180138fb8  mov     [rsp+190h+BytesSent], rax
0x180138fbd  lea     rax, [rsp+190h+ActivityId]
0x180138fc2  mov     [rsp+190h+EntityChunks], rax
0x180138fc7  mov     [rsp+190h+var_140], 2CAh
0x180138fcf  mov     [rsp+190h+var_128], rcx
0x180138fd4  mov     [rsp+190h+var_13C], 80004005h
0x180138fdc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180138fe1  xor     ebx, ebx
0x180138fe3  mov     r8d, ebx
0x180138fe6  jmp     short loc_180138FF3
0x180138fe8  mov     edi, ebx
0x180138fea  xor     ebx, ebx
0x180138fec  mov     r8d, ebx
0x180138fef  test    edi, edi
0x180138ff1  jz      short loc_180139024
0x180138ff3  mov     r10, rbx
0x180138ff6  mov     rcx, r10
0x180138ff9  mov     rdx, r10
0x180138ffc  shl     rdx, 5
0x180139000  add     rcx, rcx
0x180139003  inc     r8d
0x180139006  inc     r10
0x180139009  mov     rax, [r15+rcx*8]
0x18013900d  mov     qword ptr [rbp+rdx+90h+var_110.8], rax
0x180139012  mov     eax, [r15+rcx*8+8]
0x180139017  mov     dword ptr [rbp+rdx+90h+var_110.8+8], eax
0x18013901b  mov     [rbp+rdx+90h+var_110.DataChunkType], ebx
0x18013901f  cmp     r8d, edi
0x180139022  jb      short loc_180138FF6
0x180139024  lea     r8, [r14+38h]; unsigned __int16 *
0x180139028  mov     edx, 28h ; '('; unsigned __int64
0x18013902d  lea     rcx, [rbp+90h+String2]; unsigned __int16 *
0x180139031  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180139036  mov     dword ptr [r14+20h], 5
0x18013903e  mov     rcx, [rsi+0A0h]; pio
0x180139045  call    cs:__imp_StartThreadpoolIo
0x18013904b  mov     rcx, [rsi+98h]; RequestQueueHandle
0x180139052  lea     rax, [rbp+90h+var_110]
0x180139056  mov     [rsp+190h+LogData], rbx; LogData
0x18013905b  movzx   r9d, di; EntityChunkCount
0x18013905f  mov     [rsp+190h+Overlapped], r14; Overlapped
0x180139064  mov     r8d, 6; Flags
0x18013906a  mov     [rsp+190h+Reserved2], ebx; Reserved2
0x18013906e  mov     rdx, r12; RequestId
0x180139071  mov     [rsp+190h+Reserved1], rbx; Reserved1
0x180139076  mov     [rsp+190h+BytesSent], rbx; BytesSent
0x18013907b  mov     [rsp+190h+EntityChunks], rax; EntityChunks
0x180139080  call    cs:__imp_HttpSendResponseEntityBody
0x180139086  mov     edi, eax
0x180139088  test    eax, eax
0x18013908a  jz      loc_18013912D
0x180139090  cmp     eax, 3E5h
0x180139095  jz      loc_18013912D
0x18013909b  mov     rcx, [rsi+0A0h]; pio
0x1801390a2  call    cs:__imp_CancelThreadpoolIo
0x1801390a8  mov     ecx, cs:CallbackContext
0x1801390ae  cmp     ecx, 2
0x1801390b1  jbe     loc_18013919E
0x1801390b7  mov     qword ptr [rsp+190h+ActivityId.Data1], r13
0x1801390bc  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801390c3  mov     [rsp+190h+var_128], rax
0x1801390c8  mov     [rsp+190h+var_13C], 2F1h
0x1801390d0  test    edi, edi
0x1801390d2  jle     short loc_1801390DD
0x1801390d4  movzx   edi, di
0x1801390d7  or      edi, 80070000h
0x1801390dd  lea     rax, aHttpsendrespon_1; "HttpSendResponseEntityBody (WS) failed"
0x1801390e4  mov     [rsp+190h+var_140], edi
0x1801390e8  mov     [rsp+190h+var_130], rax
0x1801390ed  lea     rdx, byte_180293995
0x1801390f4  lea     rax, [rsp+190h+ActivityId]
0x1801390f9  mov     [rsp+190h+Overlapped], rax
0x1801390fe  lea     rax, [rsp+190h+var_13C]
0x180139103  mov     qword ptr [rsp+190h+Reserved2], rax
0x180139108  lea     rax, [rsp+190h+var_128]
0x18013910d  mov     [rsp+190h+Reserved1], rax
0x180139112  lea     rax, [rsp+190h+var_140]
0x180139117  mov     [rsp+190h+BytesSent], rax
0x18013911c  lea     rax, [rsp+190h+var_130]
0x180139121  mov     [rsp+190h+EntityChunks], rax
0x180139126  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18013912b  jmp     short loc_18013919E
0x18013912d  lea     rcx, [rsi+40h]; SRWLock
0x180139131  call    cs:__imp_AcquireSRWLockShared
0x180139137  xor     edx, edx
0x180139139  jmp     short loc_18013914F
0x18013913b  lea     rcx, [rdi+30h]; String1
0x18013913f  lea     rdx, [rbp+90h+String2]; String2
0x180139143  call    _wcsicmp
0x180139148  test    eax, eax
0x18013914a  jz      short loc_180139165
0x18013914c  mov     rdx, rdi
0x18013914f  lea     rcx, [rsi+0B0h]
0x180139156  call    ?GetNextOfEx@?$CTEntryList@UHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@$0OI@@@QEAAPEAUHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@PEAU23@@Z; CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx(WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO *)
0x18013915b  mov     rdi, rax
0x18013915e  test    rax, rax
0x180139161  jnz     short loc_18013913B
0x180139163  jmp     short loc_180139194
0x180139165  call    cs:__imp_GetTickCount64
0x18013916b  mov     r8, [rdi+100h]
0x180139172  test    r8, r8
0x180139175  jz      short loc_18013918D
0x180139177  mov     rdx, rax
0x18013917a  sub     rdx, r8
0x18013917d  cmp     rdx, [rdi+108h]
0x180139184  jbe     short loc_18013918D
0x180139186  mov     [rdi+108h], rdx
0x18013918d  mov     [rdi+100h], rax
0x180139194  lea     rcx, [rsi+40h]; SRWLock
0x180139198  call    cs:__imp_ReleaseSRWLockShared
0x18013919e  xor     eax, eax
0x1801391a0  mov     rcx, [rbp+90h+var_40]
0x1801391a4  xor     rcx, rsp; StackCookie
0x1801391a7  call    __security_check_cookie
0x1801391ac  mov     rbx, [rsp+190h+arg_10]
0x1801391b4  add     rsp, 160h
0x1801391bb  pop     r15
0x1801391bd  pop     r14
0x1801391bf  pop     r13
0x1801391c1  pop     r12
0x1801391c3  pop     rdi
0x1801391c4  pop     rsi
0x1801391c5  pop     rbp
0x1801391c6  retn
```
