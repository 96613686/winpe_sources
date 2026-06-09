# WebSocketServer::HandleReceiveRequestCompletion(WebSocketServer::RECEIVE_REQUEST_OVERLAPPED *,ulong,unsigned __int64)

- ea: `0x1801344cc`
- end: `0x1801349d4`
- name: `?HandleReceiveRequestCompletion@WebSocketServer@@AEAAXPEAURECEIVE_REQUEST_OVERLAPPED@1@K_K@Z`
- size: `1288`
- prototype: `void __fastcall(WebSocketServer *__hidden this, struct WebSocketServer::RECEIVE_REQUEST_OVERLAPPED *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180135290`

## callees

- `0x18000116c`
- `0x18000202c`
- `0x180002170`
- `0x18003b118`
- `0x18007e9e0`
- `0x18007f390`
- `0x18007f42c`
- `0x180133364`
- `0x1801344cc`
- `0x1801356bc`
- `0x18013590c`
- `0x180135984`
- `0x180136aec`
- `0x180137a64`
- `0x18019b280`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013482c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180134928`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013482c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180134928`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180134916`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180134916`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1801348c8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1801348c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134668`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134668`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18013463a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18013463a`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180134648`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180134648`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1801348f4`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x1801348f4`

## string_xrefs

- `0x18013453e`: `HandleReceiveRequestCompletion`
- `0x1801345e1`: `HandleReceiveRequestCompletion`
- `0x1801346ed`: `HandleReceiveRequestCompletion`
- `0x180134851`: `HandleReceiveRequestCompletion`
- `0x1801348ab`: `HandleReceiveRequestCompletion`

## pseudocode

```c
void __fastcall WebSocketServer::HandleReceiveRequestCompletion(
        WebSocketServer *this,
        struct WebSocketServer::RECEIVE_REQUEST_OVERLAPPED *a2,
        int a3)
{
  unsigned int v6; // r8d
  struct _HTTP_RESPONSE_V2 **v7; // r9
  WebSocketServer *v8; // rcx
  char *v9; // rdi
  unsigned __int64 v10; // rdx
  WebSocketServer *v11; // rcx
  int v12; // ebx
  _WORD *v13; // r8
  rsize_t v14; // r9
  const char *v15; // rax
  char *v16; // rdx
  __int64 v17; // rdx
  int v18; // ebx
  int v19; // r8d
  int v20; // r9d
  ULONG v21; // eax
  signed int v22; // ebx
  int v23; // r8d
  int v24; // r9d
  unsigned int RequestBufferLength; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  struct _HTTP_RESPONSE_V2 *v27; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v28; // [rsp+60h] [rbp-A0h] BYREF
  const char *v29; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v30[2]; // [rsp+70h] [rbp-90h] BYREF
  GUID ActivityId; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v32; // [rsp+90h] [rbp-70h] BYREF
  const char *v33; // [rsp+98h] [rbp-68h] BYREF
  LPOLESTR lpsz; // [rsp+A0h] [rbp-60h] BYREF
  struct _WEB_SOCKET_HTTP_HEADER *v35; // [rsp+A8h] [rbp-58h] BYREF
  GUID pguid; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v37[40]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 v38[24576]; // [rsp+110h] [rbp+10h] BYREF

  memset_0(v37, 0, sizeof(v37));
  v27 = 0;
  v28 = 7;
  v8 = (WebSocketServer *)"HandleReceiveRequestCompletion";
  v35 = 0;
  v32 = 0;
  if ( a3 )
  {
    v9 = 0;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v30[0] = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      *(_QWORD *)&ActivityId.Data1 = "HttpReceiveRequest failed";
      LODWORD(v33) = a3;
      v29 = "HandleReceiveRequestCompletion";
      v26 = 1987;
      LODWORD(v27) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)"HandleReceiveRequestCompletion",
        (unsigned int)byte_180293401,
        v6,
        (_DWORD)v7,
        (__int64)&ActivityId,
        (__int64)&v27,
        (__int64)v30,
        (__int64)&v26,
        (__int64)&v29,
        (__int64)&v33);
    }
    goto LABEL_4;
  }
  lpsz = 0;
  pguid = 0;
  v9 = (char *)a2 + 56;
  CoCreateGuid(&pguid);
  if ( StringFromIID(&pguid, &lpsz) >= 0 )
  {
    StringCchCopyW(v37, 0x28u, lpsz);
    CoTaskMemFree(lpsz);
  }
  v12 = WebSocketServer::ValidateRequest(
          v11,
          (struct _HTTP_REQUEST_V2 *)((char *)a2 + 56),
          (enum WebSocketServer::OVERLAP_ID *)&v28);
  if ( v12 < 0 )
  {
    v8 = (WebSocketServer *)(unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 52);
    if ( (_DWORD)v8 == 1 )
    {
      v13 = (_WORD *)*((_QWORD *)a2 + 20);
      v14 = 16;
      if ( *v13 == 23 )
        v14 = 28;
      memcpy_s((char *)this + 224, 0x80u, v13, v14);
    }
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_4;
    v15 = "ValidateRequest failed";
    LODWORD(v27) = 2019;
    v16 = byte_180293361;
    goto LABEL_17;
  }
  ActivityId = 0;
  v12 = WebSocketServer::ProcessWebSocketRequest(
          this,
          v37,
          &ActivityId,
          (struct _HTTP_REQUEST_V2 *)((char *)a2 + 56),
          (enum WebSocketServer::OVERLAP_ID *)&v28,
          &v35,
          &v32);
  if ( v12 < 0 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_4;
    v15 = "ProcessWebSocketRequest failed";
    LODWORD(v27) = 2028;
    v16 = byte_1802933B1;
LABEL_17:
    *(_QWORD *)&ActivityId.Data1 = v15;
    v26 = v12;
    v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
    v33 = "Error HResult failed";
    v30[0] = "HandleReceiveRequestCompletion";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)v8,
      (_DWORD)v16,
      v6,
      (_DWORD)v7,
      (__int64)&v33,
      (__int64)&v26,
      (__int64)&v29,
      (__int64)&v27,
      (__int64)v30,
      (__int64)&ActivityId);
LABEL_4:
    if ( v28 == 2 )
      WebSocketServer::Prepare400Response(v8, v38, v6, v7);
    if ( v9 )
    {
      v10 = *((_QWORD *)v9 + 2);
      ActivityId = 0;
      WebSocketServer::CancelHttpRequest(this, v10, &ActivityId);
    }
    goto LABEL_26;
  }
  if ( v28 == 3 )
  {
    WebSocketServer::Prepare101Response(v8, v35, v32, v38, RequestBufferLength, &v27);
    if ( v27 )
    {
      v17 = *((_QWORD *)a2 + 9);
      ActivityId = 0;
      v18 = WebSocketServer::SendResponse(this, v17, v37, &ActivityId, v28, v27);
      if ( v18 < 0 )
      {
        ActivityId = 0;
        EventActivityIdControl(2u, &ActivityId);
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v27) = 2079;
          v29 = "SendResponse failed";
          *(_QWORD *)&ActivityId.Data1 = "HandleReceiveRequestCompletion";
          v30[0] = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
          v26 = v18;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)CallbackContext,
            (unsigned int)byte_1802932D1,
            v19,
            v20,
            (__int64)&v29,
            (__int64)&v26,
            (__int64)v30,
            (__int64)&v27,
            (__int64)&ActivityId);
        }
      }
    }
  }
LABEL_26:
  *((_DWORD *)a2 + 8) = 0;
  StartThreadpoolIo(*((PTP_IO *)this + 20));
  v21 = HttpReceiveHttpRequest(
          *((HANDLE *)this + 19),
          0,
          0,
          (PHTTP_REQUEST)((char *)a2 + 56),
          0x6000u,
          0,
          (LPOVERLAPPED)a2);
  v22 = v21;
  if ( v21 )
  {
    if ( v21 != 997 )
    {
      CancelThreadpoolIo(*((PTP_IO *)this + 20));
      ActivityId = 0;
      EventActivityIdControl(2u, &ActivityId);
      if ( (unsigned int)CallbackContext > 2 )
      {
        *(_QWORD *)&ActivityId.Data1 = "HandleReceiveRequestCompletion";
        LODWORD(v27) = 2108;
        v30[0] = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
        if ( v22 > 0 )
          v22 = (unsigned __int16)v22 | 0x80070000;
        v26 = v22;
        v29 = "HttpReceiveHttpRequest failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_180293319,
          v23,
          v24,
          (__int64)&v29,
          (__int64)&v26,
          (__int64)v30,
          (__int64)&v27,
          (__int64)&ActivityId);
      }
    }
  }
}

```

## disassembly

```asm
0x1801344cc  mov     [rsp-8+arg_10], rbx
0x1801344d1  mov     [rsp-8+arg_18], rsi
0x1801344d6  push    rbp
0x1801344d7  push    rdi
0x1801344d8  push    r13
0x1801344da  push    r14
0x1801344dc  push    r15
0x1801344de  lea     rbp, [rsp-6030h]
0x1801344e6  mov     eax, 6130h
0x1801344eb  call    _alloca_probe
0x1801344f0  sub     rsp, rax
0x1801344f3  movaps  [rsp+6150h+var_30], xmm6
0x1801344fb  mov     rax, cs:__security_cookie
0x180134502  xor     rax, rsp
0x180134505  mov     [rbp+6050h+var_40], rax
0x18013450c  mov     r15, rdx
0x18013450f  mov     r14d, r8d
0x180134512  xor     edx, edx; Val
0x180134514  mov     rsi, rcx
0x180134517  lea     rcx, [rbp+6050h+var_6090]; void *
0x18013451b  xorps   xmm6, xmm6
0x18013451e  lea     r8d, [rdx+50h]; Size
0x180134522  call    memset_0
0x180134527  mov     [rsp+6150h+var_60F8], 0
0x180134530  mov     r13d, 2
0x180134536  mov     [rsp+6150h+var_60F0], 7
0x18013453e  lea     rcx, aHandlereceiver; "HandleReceiveRequestCompletion"
0x180134545  mov     [rbp+6050h+var_60A8], 0
0x18013454d  lea     rdx, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180134554  mov     [rbp+6050h+var_60C0], 0
0x18013455b  test    r14d, r14d
0x18013455e  jz      loc_180134623
0x180134564  mov     eax, cs:CallbackContext
0x18013456a  xor     edi, edi
0x18013456c  mov     ebx, 80004005h
0x180134571  cmp     eax, r13d
0x180134574  jbe     short loc_1801345E1
0x180134576  lea     rax, aHttpreceivereq_0; "HttpReceiveRequest failed"
0x18013457d  mov     [rsp+6150h+var_60E0], rdx
0x180134582  mov     qword ptr [rbp+6050h+ActivityId.Data1], rax
0x180134586  lea     rdx, byte_180293401
0x18013458d  lea     rax, [rbp+6050h+var_60B8]
0x180134591  mov     dword ptr [rbp+6050h+var_60B8], r14d
0x180134595  mov     [rsp+6150h+var_6108], rax
0x18013459a  lea     rax, [rsp+6150h+var_60E8]
0x18013459f  mov     [rsp+6150h+var_6110], rax
0x1801345a4  lea     rax, [rsp+6150h+var_6100]
0x1801345a9  mov     [rsp+6150h+var_6118], rax
0x1801345ae  lea     rax, [rsp+6150h+var_60E0]
0x1801345b3  mov     [rsp+6150h+Overlapped], rax
0x1801345b8  lea     rax, [rsp+6150h+var_60F8]
0x1801345bd  mov     [rsp+6150h+BytesReturned], rax
0x1801345c2  lea     rax, [rbp+6050h+ActivityId]
0x1801345c6  mov     qword ptr [rsp+6150h+RequestBufferLength], rax
0x1801345cb  mov     [rsp+6150h+var_60E8], rcx
0x1801345d0  mov     [rsp+6150h+var_6100], 7C3h
0x1801345d8  mov     dword ptr [rsp+6150h+var_60F8], ebx
0x1801345dc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801345e1  lea     r14, aHandlereceiver; "HandleReceiveRequestCompletion"
0x1801345e8  cmp     [rsp+6150h+var_60F0], r13d
0x1801345ed  jnz     short loc_1801345F8
0x1801345ef  lea     rdx, [rbp+6050h+var_6040]; unsigned __int8 *
0x1801345f3  call    ?Prepare400Response@WebSocketServer@@AEAAXPEAEKPEAPEAU_HTTP_RESPONSE_V2@@@Z; WebSocketServer::Prepare400Response(uchar *,ulong,_HTTP_RESPONSE_V2 * *)
0x1801345f8  test    ebx, ebx
0x1801345fa  jns     loc_1801348B2
0x180134600  test    rdi, rdi
0x180134603  jz      loc_1801348B2
0x180134609  mov     rdx, [rdi+10h]; unsigned __int64
0x18013460d  lea     r8, [rbp+6050h+ActivityId]; struct _GUID
0x180134611  mov     rcx, rsi; this
0x180134614  movdqa  xmmword ptr [rbp+6050h+ActivityId.Data1], xmm6
0x180134619  call    ?CancelHttpRequest@WebSocketServer@@AEAAX_KU_GUID@@@Z; WebSocketServer::CancelHttpRequest(unsigned __int64,_GUID)
0x18013461e  jmp     loc_1801348B2
0x180134623  xorps   xmm0, xmm0
0x180134626  mov     [rbp+6050h+lpsz], 0
0x18013462e  lea     rcx, [rbp+6050h+pguid]; pguid
0x180134632  movups  xmmword ptr [rbp+6050h+pguid.Data1], xmm0
0x180134636  lea     rdi, [r15+38h]
0x18013463a  call    cs:__imp_CoCreateGuid
0x180134640  lea     rdx, [rbp+6050h+lpsz]; lplpsz
0x180134644  lea     rcx, [rbp+6050h+pguid]; rclsid
0x180134648  call    cs:__imp_StringFromIID
0x18013464e  test    eax, eax
0x180134650  js      short loc_18013466E
0x180134652  mov     r8, [rbp+6050h+lpsz]; unsigned __int16 *
0x180134656  lea     rcx, [rbp+6050h+var_6090]; unsigned __int16 *
0x18013465a  mov     edx, 28h ; '('; unsigned __int64
0x18013465f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180134664  mov     rcx, [rbp+6050h+lpsz]; pv
0x180134668  call    cs:__imp_CoTaskMemFree
0x18013466e  lea     r8, [rsp+6150h+var_60F0]; enum WebSocketServer::OVERLAP_ID *
0x180134673  mov     rdx, rdi; struct _HTTP_REQUEST_V2 *
0x180134676  call    ?ValidateRequest@WebSocketServer@@AEAAJPEAU_HTTP_REQUEST_V2@@AEAW4OVERLAP_ID@1@@Z; WebSocketServer::ValidateRequest(_HTTP_REQUEST_V2 *,WebSocketServer::OVERLAP_ID &)
0x18013467b  mov     ebx, eax
0x18013467d  test    eax, eax
0x18013467f  jns     loc_180134758
0x180134685  mov     ecx, 1
0x18013468a  lock xadd [rsi+0D0h], ecx
0x180134692  inc     ecx
0x180134694  cmp     ecx, 1
0x180134697  jnz     short loc_1801346C4
0x180134699  mov     r8, [rdi+68h]; Source
0x18013469d  lea     r9d, [rcx+0Fh]
0x1801346a1  cmp     [r8], r13w
0x1801346a5  jz      short loc_1801346B3
0x1801346a7  cmp     word ptr [r8], 17h
0x1801346ac  lea     eax, [rcx+1Bh]
0x1801346af  cmovz   r9d, eax; SourceSize
0x1801346b3  lea     rcx, [rsi+0E0h]; Destination
0x1801346ba  mov     edx, 80h; DestinationSize
0x1801346bf  call    memcpy_s
0x1801346c4  mov     eax, cs:CallbackContext
0x1801346ca  cmp     eax, r13d
0x1801346cd  jbe     loc_1801345E1
0x1801346d3  lea     rax, aValidatereques; "ValidateRequest failed"
0x1801346da  mov     dword ptr [rsp+6150h+var_60F8], 7E3h
0x1801346e2  lea     rdx, byte_180293361
0x1801346e9  mov     qword ptr [rbp+6050h+ActivityId.Data1], rax
0x1801346ed  lea     r14, aHandlereceiver; "HandleReceiveRequestCompletion"
0x1801346f4  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801346fb  mov     [rsp+6150h+var_6100], ebx
0x1801346ff  mov     [rsp+6150h+var_60E8], rax
0x180134704  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18013470b  mov     [rbp+6050h+var_60B8], rax
0x18013470f  lea     rax, [rbp+6050h+ActivityId]
0x180134713  mov     [rsp+6150h+var_6108], rax
0x180134718  lea     rax, [rsp+6150h+var_60E0]
0x18013471d  mov     [rsp+6150h+var_6110], rax
0x180134722  lea     rax, [rsp+6150h+var_60F8]
0x180134727  mov     [rsp+6150h+var_6118], rax
0x18013472c  lea     rax, [rsp+6150h+var_60E8]
0x180134731  mov     [rsp+6150h+Overlapped], rax
0x180134736  lea     rax, [rsp+6150h+var_6100]
0x18013473b  mov     [rsp+6150h+BytesReturned], rax
0x180134740  lea     rax, [rbp+6050h+var_60B8]
0x180134744  mov     qword ptr [rsp+6150h+RequestBufferLength], rax
0x180134749  mov     [rsp+6150h+var_60E0], r14
0x18013474e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180134753  jmp     loc_1801345E8
0x180134758  lea     rax, [rbp+6050h+var_60C0]
0x18013475c  movdqa  xmmword ptr [rbp+6050h+ActivityId.Data1], xmm6
0x180134761  mov     [rsp+6150h+Overlapped], rax; unsigned int *
0x180134766  lea     r8, [rbp+6050h+ActivityId]; struct _GUID
0x18013476a  lea     rax, [rbp+6050h+var_60A8]
0x18013476e  mov     r9, rdi; struct _HTTP_REQUEST_V2 *
0x180134771  mov     [rsp+6150h+BytesReturned], rax; struct _WEB_SOCKET_HTTP_HEADER **
0x180134776  lea     rdx, [rbp+6050h+var_6090]; unsigned __int16 *
0x18013477a  lea     rax, [rsp+6150h+var_60F0]
0x18013477f  mov     rcx, rsi; this
0x180134782  mov     qword ptr [rsp+6150h+RequestBufferLength], rax; unsigned int
0x180134787  call    ?ProcessWebSocketRequest@WebSocketServer@@AEAAJPEAGU_GUID@@PEAU_HTTP_REQUEST_V2@@PEAW4OVERLAP_ID@1@PEAPEAU_WEB_SOCKET_HTTP_HEADER@@PEAK@Z; WebSocketServer::ProcessWebSocketRequest(ushort *,_GUID,_HTTP_REQUEST_V2 *,WebSocketServer::OVERLAP_ID *,_WEB_SOCKET_HTTP_HEADER * *,ulong *)
0x18013478c  mov     ebx, eax
0x18013478e  test    eax, eax
0x180134790  jns     short loc_1801347BC
0x180134792  mov     eax, cs:CallbackContext
0x180134798  cmp     eax, r13d
0x18013479b  jbe     loc_1801345E1
0x1801347a1  lea     rax, aProcesswebsock; "ProcessWebSocketRequest failed"
0x1801347a8  mov     dword ptr [rsp+6150h+var_60F8], 7ECh
0x1801347b0  lea     rdx, byte_1802933B1
0x1801347b7  jmp     loc_1801346E9
0x1801347bc  cmp     [rsp+6150h+var_60F0], 3
0x1801347c1  jnz     loc_1801348AB
0x1801347c7  mov     r8d, [rbp+6050h+var_60C0]; unsigned int
0x1801347cb  lea     rax, [rsp+6150h+var_60F8]
0x1801347d0  mov     rdx, [rbp+6050h+var_60A8]; struct _WEB_SOCKET_HTTP_HEADER *
0x1801347d4  lea     r9, [rbp+6050h+var_6040]; unsigned __int8 *
0x1801347d8  mov     [rsp+6150h+BytesReturned], rax; struct _HTTP_RESPONSE_V2 **
0x1801347dd  call    ?Prepare101Response@WebSocketServer@@AEAAXPEAU_WEB_SOCKET_HTTP_HEADER@@KPEAEKPEAPEAU_HTTP_RESPONSE_V2@@@Z; WebSocketServer::Prepare101Response(_WEB_SOCKET_HTTP_HEADER *,ulong,uchar *,ulong,_HTTP_RESPONSE_V2 * *)
0x1801347e2  mov     rax, [rsp+6150h+var_60F8]
0x1801347e7  test    rax, rax
0x1801347ea  jz      loc_1801348AB
0x1801347f0  mov     rdx, [rdi+10h]
0x1801347f4  lea     r9, [rbp+6050h+ActivityId]
0x1801347f8  mov     [rsp+6150h+BytesReturned], rax
0x1801347fd  lea     r8, [rbp+6050h+var_6090]
0x180134801  mov     eax, [rsp+6150h+var_60F0]
0x180134805  mov     rcx, rsi
0x180134808  mov     [rsp+6150h+RequestBufferLength], eax
0x18013480c  movdqa  xmmword ptr [rbp+6050h+ActivityId.Data1], xmm6
0x180134811  call    ?SendResponse@WebSocketServer@@AEAAJ_KPEAGU_GUID@@W4OVERLAP_ID@1@PEAU_HTTP_RESPONSE_V2@@@Z; WebSocketServer::SendResponse(unsigned __int64,ushort *,_GUID,WebSocketServer::OVERLAP_ID,_HTTP_RESPONSE_V2 *)
0x180134816  mov     ebx, eax
0x180134818  test    eax, eax
0x18013481a  jns     loc_1801348AB
0x180134820  lea     rdx, [rbp+6050h+ActivityId]; ActivityId
0x180134824  movdqa  xmmword ptr [rbp+6050h+ActivityId.Data1], xmm6
0x180134829  mov     ecx, r13d; ControlCode
0x18013482c  call    cs:__imp_EventActivityIdControl
0x180134832  mov     ecx, cs:CallbackContext
0x180134838  cmp     ecx, r13d
0x18013483b  jbe     short loc_1801348AB
0x18013483d  lea     rax, aSendresponseFa; "SendResponse failed"
0x180134844  mov     dword ptr [rsp+6150h+var_60F8], 81Fh
0x18013484c  mov     [rsp+6150h+var_60E8], rax
0x180134851  lea     r14, aHandlereceiver; "HandleReceiveRequestCompletion"
0x180134858  lea     rax, [rbp+6050h+ActivityId]
0x18013485c  mov     qword ptr [rbp+6050h+ActivityId.Data1], r14
0x180134860  mov     [rsp+6150h+var_6110], rax
0x180134865  lea     rdi, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18013486c  lea     rax, [rsp+6150h+var_60F8]
0x180134871  mov     [rsp+6150h+var_60E0], rdi
0x180134876  mov     [rsp+6150h+var_6118], rax
0x18013487b  lea     rdx, byte_1802932D1
0x180134882  lea     rax, [rsp+6150h+var_60E0]
0x180134887  mov     [rsp+6150h+var_6100], ebx
0x18013488b  mov     [rsp+6150h+Overlapped], rax
0x180134890  lea     rax, [rsp+6150h+var_6100]
0x180134895  mov     [rsp+6150h+BytesReturned], rax
0x18013489a  lea     rax, [rsp+6150h+var_60E8]
0x18013489f  mov     qword ptr [rsp+6150h+RequestBufferLength], rax
0x1801348a4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801348a9  jmp     short loc_1801348B9
0x1801348ab  lea     r14, aHandlereceiver; "HandleReceiveRequestCompletion"
0x1801348b2  lea     rdi, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801348b9  mov     dword ptr [r15+20h], 0
0x1801348c1  mov     rcx, [rsi+0A0h]; pio
0x1801348c8  call    cs:__imp_StartThreadpoolIo
0x1801348ce  mov     rcx, [rsi+98h]; RequestQueueHandle
0x1801348d5  lea     r9, [r15+38h]; RequestBuffer
0x1801348d9  mov     [rsp+6150h+Overlapped], r15; Overlapped
0x1801348de  xor     r8d, r8d; Flags
0x1801348e1  mov     [rsp+6150h+BytesReturned], 0; BytesReturned
0x1801348ea  xor     edx, edx; RequestId
0x1801348ec  mov     [rsp+6150h+RequestBufferLength], 6000h; RequestBufferLength
0x1801348f4  call    cs:__imp_HttpReceiveHttpRequest
0x1801348fa  mov     ebx, eax
0x1801348fc  test    eax, eax
0x1801348fe  jz      loc_1801349A4
0x180134904  cmp     eax, 3E5h
0x180134909  jz      loc_1801349A4
0x18013490f  mov     rcx, [rsi+0A0h]; pio
0x180134916  call    cs:__imp_CancelThreadpoolIo
0x18013491c  lea     rdx, [rbp+6050h+ActivityId]; ActivityId
0x180134920  movdqa  xmmword ptr [rbp+6050h+ActivityId.Data1], xmm6
0x180134925  mov     ecx, r13d; ControlCode
0x180134928  call    cs:__imp_EventActivityIdControl
0x18013492e  mov     ecx, cs:CallbackContext
0x180134934  cmp     ecx, r13d
0x180134937  jbe     short loc_1801349A4
0x180134939  mov     qword ptr [rbp+6050h+ActivityId.Data1], r14
0x18013493d  mov     dword ptr [rsp+6150h+var_60F8], 83Ch
0x180134945  mov     [rsp+6150h+var_60E0], rdi
0x18013494a  test    ebx, ebx
0x18013494c  jle     short loc_180134957
0x18013494e  movzx   ebx, bx
0x180134951  or      ebx, 80070000h
0x180134957  lea     rax, aHttpreceivehtt_0; "HttpReceiveHttpRequest failed"
0x18013495e  mov     [rsp+6150h+var_6100], ebx
0x180134962  mov     [rsp+6150h+var_60E8], rax
0x180134967  lea     rdx, byte_180293319
0x18013496e  lea     rax, [rbp+6050h+ActivityId]
0x180134972  mov     [rsp+6150h+var_6110], rax
0x180134977  lea     rax, [rsp+6150h+var_60F8]
0x18013497c  mov     [rsp+6150h+var_6118], rax
0x180134981  lea     rax, [rsp+6150h+var_60E0]
0x180134986  mov     [rsp+6150h+Overlapped], rax
0x18013498b  lea     rax, [rsp+6150h+var_6100]
0x180134990  mov     [rsp+6150h+BytesReturned], rax
0x180134995  lea     rax, [rsp+6150h+var_60E8]
0x18013499a  mov     qword ptr [rsp+6150h+RequestBufferLength], rax
0x18013499f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801349a4  mov     rcx, [rbp+6050h+var_40]
0x1801349ab  xor     rcx, rsp; StackCookie
0x1801349ae  call    __security_check_cookie
0x1801349b3  lea     r11, [rsp+6150h+var_20]
0x1801349bb  mov     rbx, [r11+40h]
0x1801349bf  mov     rsi, [r11+48h]
0x1801349c3  movaps  xmm6, xmmword ptr [r11-10h]
0x1801349c8  mov     rsp, r11
0x1801349cb  pop     r15
0x1801349cd  pop     r14
0x1801349cf  pop     r13
0x1801349d1  pop     rdi
0x1801349d2  pop     rbp
0x1801349d3  retn
```
