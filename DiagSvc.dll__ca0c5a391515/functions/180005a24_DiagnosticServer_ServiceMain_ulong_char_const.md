# DiagnosticServer::ServiceMain(ulong,char * * const)

- ea: `0x180005a24`
- end: `0x180005e5c`
- name: `?ServiceMain@DiagnosticServer@@QEAAXKQEAPEAD@Z`
- size: `1080`
- prototype: `void __fastcall(DiagnosticServer *__hidden this, unsigned int, char **const)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x1800051e0`

## callees

- `0x180001178`
- `0x1800012b8`
- `0x180001720`
- `0x1800054cc`
- `0x1800056fc`
- `0x180005768`
- `0x180005a24`
- `0x18000607c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e55`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005b04`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005b04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b21`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005bd0`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005bd0`

## string_xrefs

- `0x180005a74`: `onecoreuap\base\diagnosis\pdi\diagsvc\dll\diagnosticserver.cpp`
- `0x180005a7b`: `DiagnosticServer::ServiceMain`
- `0x180005aa6`: `Creating shutdown event for service`
- `0x180005b59`: `Unable to create shutdown event`
- `0x180005c25`: `Initialized service, Service in start pending state`
- `0x180005cbd`: `Service stop callback registered, Service in running state`
- `0x180005d6b`: `Failed to start the service`
- `0x180005deb`: `Started the service`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DiagnosticServer::ServiceMain(DiagnosticServer *this, int a2, char **const a3)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  signed int LastError; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // edx
  DiagnosticServer *v18; // rcx
  char **const v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  DiagnosticServer *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  char *v34; // [rsp+60h] [rbp-20h] BYREF
  char *v35; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v36[2]; // [rsp+70h] [rbp-10h] BYREF
  const char *v37; // [rsp+C0h] [rbp+40h] BYREF
  int v38; // [rsp+C8h] [rbp+48h]
  char **v39; // [rsp+D0h] [rbp+50h] BYREF
  const char *v40; // [rsp+D8h] [rbp+58h] BYREF

  v39 = a3;
  v38 = a2;
  v37 = (const char *)this;
  EnterCriticalSection(&stru_180039BB0);
  v36[0] = &stru_180039BB0;
  xmmword_180039B78 = 0;
  *(__int128 *)((char *)&xmmword_180039B78 + 12) = 0;
  v6 = 0;
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v4, v3, v5) )
  {
    v38 = 40;
    v37 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
    v40 = "DiagnosticServer::ServiceMain";
    v34 = "Creating shutdown event for service";
    LODWORD(v39) = 0;
    v35 = qword_180039BD8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (__int64)&word_18002EE76,
      v8,
      v9,
      &v35,
      (__int64)&v39,
      &v34,
      &v40,
      &v37);
  }
  qword_180039B98 = (__int64)CreateEventA(0, 0, 0, 0);
  if ( !qword_180039B98 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v12, v11, v13) )
    {
      v38 = 47;
      v37 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
      v40 = "DiagnosticServer::ServiceMain";
      v35 = "Unable to create shutdown event";
      LODWORD(v39) = v6;
      v34 = qword_180039BD8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v14,
        (__int64)byte_18002EE0D,
        v15,
        v16,
        &v34,
        (__int64)&v39,
        &v35,
        &v40,
        &v37);
    }
    if ( v6 < 0 )
      goto LABEL_21;
  }
  LODWORD(xmmword_180039B78) = 32;
  qword_180039B70 = (__int64)RegisterServiceCtrlHandlerExW(
                               L"DiagSvc",
                               DiagnosticServer::StaticServiceHandler,
                               &g_diagServer);
  if ( !qword_180039B70 )
    goto LABEL_21;
  DiagnosticServer::ReportSvcStatus((DiagnosticServer *)&g_diagServer, 2u, 0, 0x1388u);
  v6 = DiagnosticServer::SvcInitialize(v18, v17, v19);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180039000, v20, v21) )
  {
    v38 = 60;
    v37 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
    v40 = "DiagnosticServer::ServiceMain";
    v35 = "Initialized service, Service in start pending state";
    LODWORD(v39) = v6;
    v34 = qword_180039BD8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v22,
      (__int64)&dword_18002EDA4,
      v23,
      v24,
      &v34,
      (__int64)&v39,
      &v35,
      &v40,
      &v37);
  }
  if ( v6 < 0 )
    goto LABEL_21;
  DiagnosticServer::ReportSvcStatus((DiagnosticServer *)&g_diagServer, 4u, 0, 0);
  v6 = DiagnosticServer::RegisterStopCallback(v25);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v27, v26, v28) )
  {
    v38 = 66;
    v37 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
    v40 = "DiagnosticServer::ServiceMain";
    v35 = "Service stop callback registered, Service in running state";
    LODWORD(v39) = v6;
    v34 = qword_180039BD8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)byte_18002ED3B,
      v28,
      v29,
      &v34,
      (__int64)&v39,
      &v35,
      &v40,
      &v37);
  }
  if ( v6 < 0 || !qword_180039B70 )
  {
LABEL_21:
    DiagnosticServer::Cleanup((DiagnosticServer *)&g_diagServer);
    DiagnosticServer::ReportSvcStatus((DiagnosticServer *)&g_diagServer, 1u, v6, 0);
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v27, v26, v28) )
    {
      v38 = qword_180039B70;
      LODWORD(v39) = 79;
      v40 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
      v35 = "DiagnosticServer::ServiceMain";
      v34 = "Failed to start the service";
      LODWORD(v37) = v6;
      v36[0] = qword_180039BD8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v27,
        (__int64)byte_18002ECBD,
        v28,
        v30,
        v36,
        (__int64)&v37,
        &v34,
        &v35,
        &v40);
    }
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v27, v26, v28) )
  {
    v38 = 85;
    v37 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
    v40 = "DiagnosticServer::ServiceMain";
    v36[0] = "Started the service";
    LODWORD(v39) = v6;
    v35 = qword_180039BD8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v31,
      (__int64)&dword_18002EC54,
      v32,
      v33,
      &v35,
      (__int64)&v39,
      v36,
      &v40,
      &v37);
  }
  LeaveCriticalSection(&stru_180039BB0);
}

```

## disassembly

```asm
0x180005a24  mov     [rsp-38h+arg_10], r8
0x180005a29  mov     [rsp-38h+arg_8], edx
0x180005a2d  mov     [rsp-38h+arg_0], rcx
0x180005a32  push    rbp
0x180005a33  push    rbx
0x180005a34  push    rsi
0x180005a35  push    r12
0x180005a37  push    r13
0x180005a39  push    r14
0x180005a3b  push    r15
0x180005a3d  mov     rbp, rsp
0x180005a40  sub     rsp, 80h
0x180005a47  lea     r13, stru_180039BB0
0x180005a4e  mov     rcx, r13; lpCriticalSection
0x180005a51  call    cs:__imp_EnterCriticalSection
0x180005a57  mov     [rbp+var_10], r13
0x180005a5b  xorps   xmm0, xmm0
0x180005a5e  movups  cs:xmmword_180039B78, xmm0
0x180005a65  movups  cs:xmmword_180039B78+0Ch, xmm0
0x180005a6c  xor     ebx, ebx
0x180005a6e  mov     eax, cs:dword_180039000
0x180005a74  lea     r14, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180005a7b  lea     r15, aDiagnosticserv_5; "DiagnosticServer::ServiceMain"
0x180005a82  lea     r12, qword_180039BD8
0x180005a89  cmp     eax, 5
0x180005a8c  jbe     short loc_180005AFA
0x180005a8e  call    _tlgKeywordOn
0x180005a93  test    al, al
0x180005a95  jz      short loc_180005AFA
0x180005a97  mov     [rbp+arg_8], 28h ; '('
0x180005a9e  mov     [rbp+arg_0], r14
0x180005aa2  mov     [rbp+arg_18], r15
0x180005aa6  lea     rax, aCreatingShutdo_0; "Creating shutdown event for service"
0x180005aad  mov     [rbp+var_20], rax
0x180005ab1  mov     dword ptr [rbp+arg_10], ebx
0x180005ab4  mov     [rbp+var_18], r12
0x180005ab8  lea     rax, [rbp+arg_8]
0x180005abc  mov     [rsp+80h+var_38], rax
0x180005ac1  lea     rax, [rbp+arg_0]
0x180005ac5  mov     [rsp+80h+var_40], rax
0x180005aca  lea     rax, [rbp+arg_18]
0x180005ace  mov     [rsp+80h+var_48], rax
0x180005ad3  lea     rax, [rbp+var_20]
0x180005ad7  mov     [rsp+80h+var_50], rax
0x180005adc  lea     rax, [rbp+arg_10]
0x180005ae0  mov     [rsp+80h+var_58], rax
0x180005ae5  lea     rax, [rbp+var_18]
0x180005ae9  mov     [rsp+80h+var_60], rax
0x180005aee  lea     rdx, word_18002EE76
0x180005af5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005afa  xor     r9d, r9d; lpName
0x180005afd  xor     r8d, r8d; bInitialState
0x180005b00  xor     edx, edx; bManualReset
0x180005b02  xor     ecx, ecx; lpEventAttributes
0x180005b04  call    cs:__imp_CreateEventA
0x180005b0a  mov     cs:qword_180039B98, rax
0x180005b11  lea     rsi, ?g_diagServer@@3VDiagnosticServer@@A; DiagnosticServer g_diagServer
0x180005b18  test    rax, rax
0x180005b1b  jnz     loc_180005BB5
0x180005b21  call    cs:__imp_GetLastError
0x180005b27  mov     ebx, eax
0x180005b29  test    eax, eax
0x180005b2b  jle     short loc_180005B36
0x180005b2d  movzx   ebx, ax
0x180005b30  or      ebx, 80070000h
0x180005b36  mov     eax, cs:dword_180039000
0x180005b3c  cmp     eax, 5
0x180005b3f  jbe     short loc_180005BAD
0x180005b41  call    _tlgKeywordOn
0x180005b46  test    al, al
0x180005b48  jz      short loc_180005BAD
0x180005b4a  mov     [rbp+arg_8], 2Fh ; '/'
0x180005b51  mov     [rbp+arg_0], r14
0x180005b55  mov     [rbp+arg_18], r15
0x180005b59  lea     rax, aUnableToCreate; "Unable to create shutdown event"
0x180005b60  mov     [rbp+var_18], rax
0x180005b64  mov     dword ptr [rbp+arg_10], ebx
0x180005b67  mov     [rbp+var_20], r12
0x180005b6b  lea     rax, [rbp+arg_8]
0x180005b6f  mov     [rsp+80h+var_38], rax
0x180005b74  lea     rax, [rbp+arg_0]
0x180005b78  mov     [rsp+80h+var_40], rax
0x180005b7d  lea     rax, [rbp+arg_18]
0x180005b81  mov     [rsp+80h+var_48], rax
0x180005b86  lea     rax, [rbp+var_18]
0x180005b8a  mov     [rsp+80h+var_50], rax
0x180005b8f  lea     rax, [rbp+arg_10]
0x180005b93  mov     [rsp+80h+var_58], rax
0x180005b98  lea     rax, [rbp+var_20]
0x180005b9c  mov     [rsp+80h+var_60], rax
0x180005ba1  lea     rdx, byte_18002EE0D
0x180005ba8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005bad  test    ebx, ebx
0x180005baf  js      loc_180005D25
0x180005bb5  mov     dword ptr cs:xmmword_180039B78, 20h ; ' '
0x180005bbf  mov     r8, rsi; lpContext
0x180005bc2  lea     rdx, ?StaticServiceHandler@DiagnosticServer@@KAKKKPEAX0@Z; lpHandlerProc
0x180005bc9  lea     rcx, ServiceName; "DiagSvc"
0x180005bd0  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180005bd6  mov     cs:qword_180039B70, rax
0x180005bdd  test    rax, rax
0x180005be0  jz      loc_180005D25
0x180005be6  mov     r9d, 1388h; unsigned int
0x180005bec  xor     r8d, r8d; unsigned int
0x180005bef  lea     edx, [r8+2]; unsigned int
0x180005bf3  mov     rcx, rsi; this
0x180005bf6  call    ?ReportSvcStatus@DiagnosticServer@@IEAAXKKK@Z; DiagnosticServer::ReportSvcStatus(ulong,ulong,ulong)
0x180005bfb  call    ?SvcInitialize@DiagnosticServer@@IEAAJKQEAPEAD@Z; DiagnosticServer::SvcInitialize(ulong,char * * const)
0x180005c00  mov     ebx, eax
0x180005c02  mov     ecx, cs:dword_180039000
0x180005c08  cmp     ecx, 5
0x180005c0b  jbe     short loc_180005C79
0x180005c0d  call    _tlgKeywordOn
0x180005c12  test    al, al
0x180005c14  jz      short loc_180005C79
0x180005c16  mov     [rbp+arg_8], 3Ch ; '<'
0x180005c1d  mov     [rbp+arg_0], r14
0x180005c21  mov     [rbp+arg_18], r15
0x180005c25  lea     rax, aInitializedSer; "Initialized service, Service in start p"...
0x180005c2c  mov     [rbp+var_18], rax
0x180005c30  mov     dword ptr [rbp+arg_10], ebx
0x180005c33  mov     [rbp+var_20], r12
0x180005c37  lea     rax, [rbp+arg_8]
0x180005c3b  mov     [rsp+80h+var_38], rax
0x180005c40  lea     rax, [rbp+arg_0]
0x180005c44  mov     [rsp+80h+var_40], rax
0x180005c49  lea     rax, [rbp+arg_18]
0x180005c4d  mov     [rsp+80h+var_48], rax
0x180005c52  lea     rax, [rbp+var_18]
0x180005c56  mov     [rsp+80h+var_50], rax
0x180005c5b  lea     rax, [rbp+arg_10]
0x180005c5f  mov     [rsp+80h+var_58], rax
0x180005c64  lea     rax, [rbp+var_20]
0x180005c68  mov     [rsp+80h+var_60], rax
0x180005c6d  lea     rdx, dword_18002EDA4
0x180005c74  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005c79  test    ebx, ebx
0x180005c7b  js      loc_180005D25
0x180005c81  xor     r9d, r9d; unsigned int
0x180005c84  xor     r8d, r8d; unsigned int
0x180005c87  lea     edx, [r9+4]; unsigned int
0x180005c8b  mov     rcx, rsi; this
0x180005c8e  call    ?ReportSvcStatus@DiagnosticServer@@IEAAXKKK@Z; DiagnosticServer::ReportSvcStatus(ulong,ulong,ulong)
0x180005c93  call    ?RegisterStopCallback@DiagnosticServer@@IEAAJXZ; DiagnosticServer::RegisterStopCallback(void)
0x180005c98  mov     ebx, eax
0x180005c9a  mov     eax, cs:dword_180039000
0x180005ca0  cmp     eax, 5
0x180005ca3  jbe     short loc_180005D11
0x180005ca5  call    _tlgKeywordOn
0x180005caa  test    al, al
0x180005cac  jz      short loc_180005D11
0x180005cae  mov     [rbp+arg_8], 42h ; 'B'
0x180005cb5  mov     [rbp+arg_0], r14
0x180005cb9  mov     [rbp+arg_18], r15
0x180005cbd  lea     rax, aServiceStopCal; "Service stop callback registered, Servi"...
0x180005cc4  mov     [rbp+var_18], rax
0x180005cc8  mov     dword ptr [rbp+arg_10], ebx
0x180005ccb  mov     [rbp+var_20], r12
0x180005ccf  lea     rax, [rbp+arg_8]
0x180005cd3  mov     [rsp+80h+var_38], rax
0x180005cd8  lea     rax, [rbp+arg_0]
0x180005cdc  mov     [rsp+80h+var_40], rax
0x180005ce1  lea     rax, [rbp+arg_18]
0x180005ce5  mov     [rsp+80h+var_48], rax
0x180005cea  lea     rax, [rbp+var_18]
0x180005cee  mov     [rsp+80h+var_50], rax
0x180005cf3  lea     rax, [rbp+arg_10]
0x180005cf7  mov     [rsp+80h+var_58], rax
0x180005cfc  lea     rax, [rbp+var_20]
0x180005d00  mov     [rsp+80h+var_60], rax
0x180005d05  lea     rdx, byte_18002ED3B
0x180005d0c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005d11  test    ebx, ebx
0x180005d13  js      short loc_180005D25
0x180005d15  mov     rax, cs:qword_180039B70
0x180005d1c  test    rax, rax
0x180005d1f  jnz     loc_180005DC8
0x180005d25  mov     rcx, rsi; this
0x180005d28  call    ?Cleanup@DiagnosticServer@@IEAAXXZ; DiagnosticServer::Cleanup(void)
0x180005d2d  xor     r9d, r9d; unsigned int
0x180005d30  mov     r8d, ebx; unsigned int
0x180005d33  lea     edx, [r9+1]; unsigned int
0x180005d37  mov     rcx, rsi; this
0x180005d3a  call    ?ReportSvcStatus@DiagnosticServer@@IEAAXKKK@Z; DiagnosticServer::ReportSvcStatus(ulong,ulong,ulong)
0x180005d3f  mov     eax, cs:dword_180039000
0x180005d45  cmp     eax, 5
0x180005d48  jbe     short loc_180005DC8
0x180005d4a  call    _tlgKeywordOn
0x180005d4f  test    al, al
0x180005d51  jz      short loc_180005DC8
0x180005d53  mov     eax, dword ptr cs:qword_180039B70
0x180005d59  mov     [rbp+arg_8], eax
0x180005d5c  mov     dword ptr [rbp+arg_10], 4Fh ; 'O'
0x180005d63  mov     [rbp+arg_18], r14
0x180005d67  mov     [rbp+var_18], r15
0x180005d6b  lea     rax, aFailedToStartT; "Failed to start the service"
0x180005d72  mov     [rbp+var_20], rax
0x180005d76  mov     dword ptr [rbp+arg_0], ebx
0x180005d79  mov     [rbp+var_10], r12
0x180005d7d  lea     rax, [rbp+arg_8]
0x180005d81  mov     [rsp+80h+var_30], rax
0x180005d86  lea     rax, [rbp+arg_10]
0x180005d8a  mov     [rsp+80h+var_38], rax
0x180005d8f  lea     rax, [rbp+arg_18]
0x180005d93  mov     [rsp+80h+var_40], rax
0x180005d98  lea     rax, [rbp+var_18]
0x180005d9c  mov     [rsp+80h+var_48], rax
0x180005da1  lea     rax, [rbp+var_20]
0x180005da5  mov     [rsp+80h+var_50], rax
0x180005daa  lea     rax, [rbp+arg_0]
0x180005dae  mov     [rsp+80h+var_58], rax
0x180005db3  lea     rax, [rbp+var_10]
0x180005db7  mov     [rsp+80h+var_60], rax
0x180005dbc  lea     rdx, byte_18002ECBD
0x180005dc3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180005dc8  mov     eax, cs:dword_180039000
0x180005dce  cmp     eax, 5
0x180005dd1  jbe     short loc_180005E40
0x180005dd3  call    _tlgKeywordOn
0x180005dd8  test    al, al
0x180005dda  jz      short loc_180005E40
0x180005ddc  mov     [rbp+arg_8], 55h ; 'U'
0x180005de3  mov     [rbp+arg_0], r14
0x180005de7  mov     [rbp+arg_18], r15
0x180005deb  lea     rax, aStartedTheServ; "Started the service"
0x180005df2  mov     [rbp+var_10], rax
0x180005df6  mov     dword ptr [rbp+arg_10], ebx
0x180005df9  mov     [rbp+var_18], r12
0x180005dfd  lea     rax, [rbp+arg_8]
0x180005e01  mov     [rsp+80h+var_38], rax
0x180005e06  lea     rax, [rbp+arg_0]
0x180005e0a  mov     [rsp+80h+var_40], rax
0x180005e0f  lea     rax, [rbp+arg_18]
0x180005e13  mov     [rsp+80h+var_48], rax
0x180005e18  lea     rax, [rbp+var_10]
0x180005e1c  mov     [rsp+80h+var_50], rax
0x180005e21  lea     rax, [rbp+arg_10]
0x180005e25  mov     [rsp+80h+var_58], rax
0x180005e2a  lea     rax, [rbp+var_18]
0x180005e2e  mov     [rsp+80h+var_60], rax
0x180005e33  lea     rdx, dword_18002EC54
0x180005e3a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005e3f  nop
0x180005e40  mov     rcx, r13
0x180005e43  add     rsp, 80h
0x180005e4a  pop     r15
0x180005e4c  pop     r14
0x180005e4e  pop     r13
0x180005e50  pop     r12
0x180005e52  pop     rsi
0x180005e53  pop     rbx
0x180005e54  pop     rbp
0x180005e55  jmp     cs:__imp_LeaveCriticalSection
```
