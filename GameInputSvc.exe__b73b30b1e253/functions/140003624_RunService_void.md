# RunService(void)

- ea: `0x140003624`
- end: `0x1400037c4`
- name: `?RunService@@YAJXZ`
- size: `416`
- prototype: `__int64 __fastcall(__int64, __int64, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x140005cb8`

## callees

- `0x140001008`
- `0x14000116c`
- `0x14000125c`
- `0x140003624`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400036d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400036d0`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x1400036c6`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x1400036c6`

## string_xrefs

- `0x140003636`: `onecore\xbox\gameinput\published\svc\service.cpp`
- `0x140003665`: `GameInputService service starting`
- `0x14000370e`: `GameInputService service stopped`

## pseudocode

```c
__int64 __fastcall RunService(__int64 a1, __int64 a2, int a3, int a4)
{
  signed int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  signed int LastError; // eax
  SERVICE_TABLE_ENTRYW ServiceStartTable; // [rsp+40h] [rbp-28h] BYREF
  __int64 v10; // [rsp+50h] [rbp-18h]
  __int64 v11; // [rsp+58h] [rbp-10h]
  int v12; // [rsp+90h] [rbp+28h] BYREF
  const char *v13; // [rsp+98h] [rbp+30h] BYREF
  const char *v14; // [rsp+A0h] [rbp+38h] BYREF
  const char *v15; // [rsp+A8h] [rbp+40h] BYREF

  if ( (unsigned int)dword_14000E000 > 4
    && (qword_14000E010 & 0x800) != 0
    && (qword_14000E018 & 0x800) == qword_14000E018 )
  {
    v12 = 631;
    v13 = "GameInputService service starting";
    v14 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      qword_14000E018,
      (unsigned int)&byte_14000A957,
      a3,
      a4,
      (__int64)&v14,
      (__int64)&v12,
      (__int64)&v13);
  }
  v4 = 0;
  ServiceStartTable.lpServiceName = (LPWSTR)L"GameInputSvc";
  v10 = 0;
  ServiceStartTable.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)ServiceMain;
  v11 = 0;
  if ( !StartServiceCtrlDispatcherW(&ServiceStartTable) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( (unsigned int)dword_14000E000 > 4
    && (qword_14000E010 & 0x800) != 0
    && (qword_14000E018 & 0x800) == qword_14000E018 )
  {
    v12 = v4;
    v14 = "GameInputService service stopped";
    LODWORD(v13) = 656;
    v15 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_14000E018,
      (unsigned int)byte_14000A913,
      v5,
      v6,
      (__int64)&v15,
      (__int64)&v13,
      (__int64)&v14,
      (__int64)&v12);
  }
  if ( v4 < 0
    && (unsigned int)dword_14000E000 > 2
    && (qword_14000E010 & 0x800) != 0
    && (qword_14000E018 & 0x800) == qword_14000E018 )
  {
    v12 = v4;
    LODWORD(v13) = 658;
    v14 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_14000E018,
      (unsigned int)&word_14000A8D6,
      v5,
      v6,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140003624  push    rbp
0x140003626  push    rbx
0x140003627  push    rsi
0x140003628  push    rdi
0x140003629  mov     rbp, rsp
0x14000362c  sub     rsp, 68h
0x140003630  mov     eax, cs:dword_14000E000
0x140003636  lea     rsi, aOnecoreXboxGam_6; "onecore\\xbox\\gameinput\\published\\sv"...
0x14000363d  mov     edi, 800h
0x140003642  cmp     eax, 4
0x140003645  jbe     short loc_1400036A2
0x140003647  mov     rcx, cs:qword_14000E018
0x14000364e  mov     rax, cs:qword_14000E010
0x140003655  test    rdi, rax
0x140003658  jz      short loc_1400036A2
0x14000365a  mov     rax, rcx
0x14000365d  and     rax, rdi
0x140003660  cmp     rax, rcx
0x140003663  jnz     short loc_1400036A2
0x140003665  lea     rax, aGameinputservi_0; "GameInputService service starting"
0x14000366c  mov     [rbp+arg_0], 277h
0x140003673  mov     [rbp+arg_8], rax
0x140003677  lea     rdx, byte_14000A957
0x14000367e  lea     rax, [rbp+arg_8]
0x140003682  mov     [rbp+arg_10], rsi
0x140003686  mov     [rsp+68h+var_38], rax
0x14000368b  lea     rax, [rbp+arg_0]
0x14000368f  mov     [rsp+68h+var_40], rax
0x140003694  lea     rax, [rbp+arg_10]
0x140003698  mov     [rsp+68h+var_48], rax
0x14000369d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400036a2  lea     rax, ServiceName; "GameInputSvc"
0x1400036a9  xor     ebx, ebx
0x1400036ab  mov     [rbp+ServiceStartTable.lpServiceName], rax
0x1400036af  lea     rcx, [rbp+ServiceStartTable]; lpServiceStartTable
0x1400036b3  lea     rax, ServiceMain
0x1400036ba  mov     [rbp+var_18], rbx
0x1400036be  mov     [rbp+ServiceStartTable.lpServiceProc], rax
0x1400036c2  mov     [rbp+var_10], rbx
0x1400036c6  call    cs:__imp_StartServiceCtrlDispatcherW
0x1400036cc  test    eax, eax
0x1400036ce  jnz     short loc_1400036E5
0x1400036d0  call    cs:__imp_GetLastError
0x1400036d6  mov     ebx, eax
0x1400036d8  test    eax, eax
0x1400036da  jle     short loc_1400036E5
0x1400036dc  movzx   ebx, ax
0x1400036df  or      ebx, 80070000h
0x1400036e5  mov     eax, cs:dword_14000E000
0x1400036eb  cmp     eax, 4
0x1400036ee  jbe     short loc_140003757
0x1400036f0  mov     rcx, cs:qword_14000E018
0x1400036f7  mov     rax, cs:qword_14000E010
0x1400036fe  test    rdi, rax
0x140003701  jz      short loc_140003757
0x140003703  mov     rax, rcx
0x140003706  and     rax, rdi
0x140003709  cmp     rax, rcx
0x14000370c  jnz     short loc_140003757
0x14000370e  lea     rax, aGameinputservi_2; "GameInputService service stopped"
0x140003715  mov     [rbp+arg_0], ebx
0x140003718  mov     [rbp+arg_10], rax
0x14000371c  lea     rdx, byte_14000A913
0x140003723  lea     rax, [rbp+arg_0]
0x140003727  mov     dword ptr [rbp+arg_8], 290h
0x14000372e  mov     [rsp+68h+var_30], rax
0x140003733  lea     rax, [rbp+arg_10]
0x140003737  mov     [rsp+68h+var_38], rax
0x14000373c  lea     rax, [rbp+arg_8]
0x140003740  mov     [rsp+68h+var_40], rax
0x140003745  lea     rax, [rbp+arg_18]
0x140003749  mov     [rsp+68h+var_48], rax
0x14000374e  mov     [rbp+arg_18], rsi
0x140003752  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003757  test    ebx, ebx
0x140003759  jns     short loc_1400037B9
0x14000375b  mov     eax, cs:dword_14000E000
0x140003761  cmp     eax, 2
0x140003764  jbe     short loc_1400037B9
0x140003766  mov     rcx, cs:qword_14000E018
0x14000376d  mov     rax, cs:qword_14000E010
0x140003774  test    rdi, rax
0x140003777  jz      short loc_1400037B9
0x140003779  mov     rax, rcx
0x14000377c  and     rax, rdi
0x14000377f  cmp     rax, rcx
0x140003782  jnz     short loc_1400037B9
0x140003784  lea     rax, [rbp+arg_0]
0x140003788  mov     [rbp+arg_0], ebx
0x14000378b  mov     [rsp+68h+var_38], rax
0x140003790  lea     rdx, word_14000A8D6
0x140003797  lea     rax, [rbp+arg_8]
0x14000379b  mov     dword ptr [rbp+arg_8], 292h
0x1400037a2  mov     [rsp+68h+var_40], rax
0x1400037a7  lea     rax, [rbp+arg_10]
0x1400037ab  mov     [rsp+68h+var_48], rax
0x1400037b0  mov     [rbp+arg_10], rsi
0x1400037b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400037b9  mov     eax, ebx
0x1400037bb  add     rsp, 68h
0x1400037bf  pop     rdi
0x1400037c0  pop     rsi
0x1400037c1  pop     rbx
0x1400037c2  pop     rbp
0x1400037c3  retn
```
