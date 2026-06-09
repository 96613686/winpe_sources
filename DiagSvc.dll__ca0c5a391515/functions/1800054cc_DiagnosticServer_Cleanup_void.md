# DiagnosticServer::Cleanup(void)

- ea: `0x1800054cc`
- end: `0x1800056cf`
- name: `?Cleanup@DiagnosticServer@@IEAAXXZ`
- size: `515`
- prototype: `void __fastcall(DiagnosticServer *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005a24`
- `0x180005f7c`

## callees

- `0x180001178`
- `0x180001720`
- `0x18000517c`
- `0x1800054cc`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005595`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005595`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800054fb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800054fb`

## string_xrefs

- `0x1800054de`: `onecoreuap\base\diagnosis\pdi\diagsvc\dll\diagnosticserver.cpp`
- `0x180005658`: `Shutdown service instance`

## pseudocode

```c
void __fastcall DiagnosticServer::Cleanup(DiagnosticServer *this)
{
  void *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  void *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  const char *v23; // [rsp+50h] [rbp-10h] BYREF
  const char *v24; // [rsp+58h] [rbp-8h] BYREF
  int v25; // [rsp+98h] [rbp+38h] BYREF
  const char *v26; // [rsp+A0h] [rbp+40h] BYREF
  const char *v27; // [rsp+A8h] [rbp+48h] BYREF

  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    UnregisterWaitEx(v2, 0);
    *((_QWORD *)this + 8) = 0;
    if ( (unsigned int)dword_180039000 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(v4, v3, v5) )
      {
        v23 = "Unregister wait";
        v26 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
        v24 = (char *)this + 120;
        v27 = "DiagnosticServer::Cleanup";
        v25 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v6,
          (__int64)byte_18002EA6B,
          v7,
          v8,
          &v24,
          (__int64)&v25,
          &v23,
          &v27,
          &v26);
      }
    }
  }
  v9 = (void *)*((_QWORD *)this + 7);
  if ( v9 )
  {
    CloseHandle(v9);
    *((_QWORD *)this + 7) = 0;
    if ( (unsigned int)dword_180039000 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(v11, v10, v12) )
      {
        v24 = "Closing shutdown event";
        v26 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
        v23 = (char *)this + 120;
        v27 = "DiagnosticServer::Cleanup";
        v25 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v13,
          (__int64)word_18002EA02,
          v14,
          v15,
          &v23,
          (__int64)&v25,
          &v24,
          &v27,
          &v26);
      }
    }
  }
  v16 = *((_QWORD *)this + 9);
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 48LL))(v16);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease((char *)this + 72);
    if ( (unsigned int)dword_180039000 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(v18, v17, v19) )
      {
        v24 = "Shutdown service instance";
        v26 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
        v23 = (char *)this + 120;
        v27 = "DiagnosticServer::Cleanup";
        v25 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v20,
          (__int64)byte_18002E999,
          v21,
          v22,
          &v23,
          (__int64)&v25,
          &v24,
          &v27,
          &v26);
      }
    }
  }
}

```

## disassembly

```asm
0x1800054cc  push    rbp
0x1800054ce  push    rbx
0x1800054cf  push    rdi
0x1800054d0  push    r14
0x1800054d2  push    r15
0x1800054d4  mov     rbp, rsp
0x1800054d7  sub     rsp, 60h
0x1800054db  mov     rbx, rcx
0x1800054de  lea     r14, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x1800054e5  mov     rcx, [rcx+40h]; WaitHandle
0x1800054e9  lea     r15, aDiagnosticserv_2; "DiagnosticServer::Cleanup"
0x1800054f0  test    rcx, rcx
0x1800054f3  jz      loc_180005588
0x1800054f9  xor     edx, edx; CompletionEvent
0x1800054fb  call    cs:__imp_UnregisterWaitEx
0x180005501  mov     qword ptr [rbx+40h], 0
0x180005509  mov     eax, cs:dword_180039000
0x18000550f  cmp     eax, 5
0x180005512  jbe     short loc_180005588
0x180005514  call    _tlgKeywordOn
0x180005519  test    al, al
0x18000551b  jz      short loc_180005588
0x18000551d  lea     rax, aUnregisterWait; "Unregister wait"
0x180005524  mov     [rbp+arg_0], 0D5h
0x18000552b  mov     [rbp+var_10], rax
0x18000552f  lea     rdx, byte_18002EA6B
0x180005536  lea     rax, [rbx+78h]
0x18000553a  mov     [rbp+arg_10], r14
0x18000553e  mov     [rbp+var_8], rax
0x180005542  lea     rax, [rbp+arg_0]
0x180005546  mov     [rsp+60h+var_18], rax
0x18000554b  lea     rax, [rbp+arg_10]
0x18000554f  mov     [rsp+60h+var_20], rax
0x180005554  lea     rax, [rbp+arg_18]
0x180005558  mov     [rsp+60h+var_28], rax
0x18000555d  lea     rax, [rbp+var_10]
0x180005561  mov     [rsp+60h+var_30], rax
0x180005566  lea     rax, [rbp+arg_8]
0x18000556a  mov     [rsp+60h+var_38], rax
0x18000556f  lea     rax, [rbp+var_8]
0x180005573  mov     [rsp+60h+var_40], rax
0x180005578  mov     [rbp+arg_18], r15
0x18000557c  mov     [rbp+arg_8], 0
0x180005583  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005588  mov     rcx, [rbx+38h]; hObject
0x18000558c  test    rcx, rcx
0x18000558f  jz      loc_180005622
0x180005595  call    cs:__imp_CloseHandle
0x18000559b  mov     qword ptr [rbx+38h], 0
0x1800055a3  mov     eax, cs:dword_180039000
0x1800055a9  cmp     eax, 5
0x1800055ac  jbe     short loc_180005622
0x1800055ae  call    _tlgKeywordOn
0x1800055b3  test    al, al
0x1800055b5  jz      short loc_180005622
0x1800055b7  lea     rax, aClosingShutdow; "Closing shutdown event"
0x1800055be  mov     [rbp+arg_0], 0E0h
0x1800055c5  mov     [rbp+var_8], rax
0x1800055c9  lea     rdx, word_18002EA02
0x1800055d0  lea     rax, [rbx+78h]
0x1800055d4  mov     [rbp+arg_10], r14
0x1800055d8  mov     [rbp+var_10], rax
0x1800055dc  lea     rax, [rbp+arg_0]
0x1800055e0  mov     [rsp+60h+var_18], rax
0x1800055e5  lea     rax, [rbp+arg_10]
0x1800055e9  mov     [rsp+60h+var_20], rax
0x1800055ee  lea     rax, [rbp+arg_18]
0x1800055f2  mov     [rsp+60h+var_28], rax
0x1800055f7  lea     rax, [rbp+var_8]
0x1800055fb  mov     [rsp+60h+var_30], rax
0x180005600  lea     rax, [rbp+arg_8]
0x180005604  mov     [rsp+60h+var_38], rax
0x180005609  lea     rax, [rbp+var_10]
0x18000560d  mov     [rsp+60h+var_40], rax
0x180005612  mov     [rbp+arg_18], r15
0x180005616  mov     [rbp+arg_8], 0
0x18000561d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005622  mov     rcx, [rbx+48h]
0x180005626  test    rcx, rcx
0x180005629  jz      loc_1800056C3
0x18000562f  mov     rax, [rcx]
0x180005632  mov     rax, [rax+30h]
0x180005636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000563b  lea     rcx, [rbx+48h]
0x18000563f  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180005644  mov     eax, cs:dword_180039000
0x18000564a  cmp     eax, 5
0x18000564d  jbe     short loc_1800056C3
0x18000564f  call    _tlgKeywordOn
0x180005654  test    al, al
0x180005656  jz      short loc_1800056C3
0x180005658  lea     rax, aShutdownServic; "Shutdown service instance"
0x18000565f  mov     [rbp+arg_0], 0ECh
0x180005666  mov     [rbp+var_8], rax
0x18000566a  lea     rdx, byte_18002E999
0x180005671  lea     rax, [rbx+78h]
0x180005675  mov     [rbp+arg_10], r14
0x180005679  mov     [rbp+var_10], rax
0x18000567d  lea     rax, [rbp+arg_0]
0x180005681  mov     [rsp+60h+var_18], rax
0x180005686  lea     rax, [rbp+arg_10]
0x18000568a  mov     [rsp+60h+var_20], rax
0x18000568f  lea     rax, [rbp+arg_18]
0x180005693  mov     [rsp+60h+var_28], rax
0x180005698  lea     rax, [rbp+var_8]
0x18000569c  mov     [rsp+60h+var_30], rax
0x1800056a1  lea     rax, [rbp+arg_8]
0x1800056a5  mov     [rsp+60h+var_38], rax
0x1800056aa  lea     rax, [rbp+var_10]
0x1800056ae  mov     [rsp+60h+var_40], rax
0x1800056b3  mov     [rbp+arg_18], r15
0x1800056b7  mov     [rbp+arg_8], 0
0x1800056be  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800056c3  add     rsp, 60h
0x1800056c7  pop     r15
0x1800056c9  pop     r14
0x1800056cb  pop     rdi
0x1800056cc  pop     rbx
0x1800056cd  pop     rbp
0x1800056ce  retn
```
