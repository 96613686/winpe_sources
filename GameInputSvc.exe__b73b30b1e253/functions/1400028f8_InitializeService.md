# InitializeService

- ea: `0x1400028f8`
- end: `0x140002aba`
- name: `InitializeService`
- size: `450`
- prototype: `signed int __fastcall(_QWORD *lpContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1400037d0`

## callees

- `0x140001008`
- `0x1400028f8`
- `0x140002ac0`
- `0x140003c5c`
- `0x140004950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140002939`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140002939`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140002922`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140002922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a1c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x140002a09`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x140002a09`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x140002974`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x140002974`

## string_xrefs

- `0x1400029b5`: `onecore\xbox\gameinput\published\svc\service.cpp`
- `0x140002a52`: `onecore\xbox\gameinput\published\svc\service.cpp`

## pseudocode

```c
signed int __fastcall InitializeService(_QWORD *lpContext)
{
  HANDLE EventW; // rax
  signed int result; // eax
  DWORD active; // eax
  signed int LastError; // ebx
  int v6; // r9d
  SERVICE_STATUS_HANDLE v7; // rax
  int v8; // r8d
  int v9; // r9d
  signed int v10; // [rsp+60h] [rbp+20h] BYREF
  int v11; // [rsp+68h] [rbp+28h] BYREF
  const char *v12; // [rsp+70h] [rbp+30h] BYREF

  qword_14000E6F8 = (__int64)&qword_14000E6F0;
  qword_14000E6F0 = (__int64)&qword_14000E6F0;
  InitializeCriticalSection(&CriticalSection);
  StopAllSessions();
  EventW = CreateEventW(0, 1, 0, 0);
  *lpContext = EventW;
  if ( EventW )
  {
    if ( (int)ModifyGameInputFiles(1) < 0 )
      ModifyGameInputFiles(0);
    active = WTSGetActiveConsoleSessionId();
    LastError = EnsureSessionStarted(active);
    if ( LastError >= 0 )
    {
      v7 = RegisterServiceCtrlHandlerExW(L"GameInputSvc", SvcControlHandler, lpContext);
      lpContext[1] = v7;
      if ( v7 )
        return 0;
      LastError = GetLastError();
      if ( (unsigned int)dword_14000E000 > 2
        && (qword_14000E010 & 0x800) != 0
        && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v10 = LastError;
        v12 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
        v11 = 574;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14000E018,
          (unsigned int)word_14000A992,
          v8,
          v9,
          (__int64)&v12,
          (__int64)&v11,
          (__int64)&v10);
      }
      if ( LastError )
      {
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        return -2147418113;
      }
    }
    else if ( (unsigned int)dword_14000E000 > 2
           && (qword_14000E010 & 0x800) != 0
           && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v10 = LastError;
      v12 = "onecore\\xbox\\gameinput\\published\\svc\\service.cpp";
      v11 = 571;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E010,
        (unsigned int)word_14000A9D2,
        qword_14000E018,
        v6,
        (__int64)&v12,
        (__int64)&v11,
        (__int64)&v10);
    }
    return LastError;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400028f8  push    rbp
0x1400028fa  push    rbx
0x1400028fb  push    rdi
0x1400028fc  mov     rbp, rsp
0x1400028ff  sub     rsp, 40h
0x140002903  lea     rax, qword_14000E6F0
0x14000290a  mov     rdi, rcx
0x14000290d  lea     rcx, CriticalSection; lpCriticalSection
0x140002914  mov     cs:qword_14000E6F8, rax
0x14000291b  mov     cs:qword_14000E6F0, rax
0x140002922  call    cs:__imp_InitializeCriticalSection
0x140002928  call    ?StopAllSessions@@YAXXZ; StopAllSessions(void)
0x14000292d  xor     r9d, r9d; lpName
0x140002930  xor     r8d, r8d; bInitialState
0x140002933  xor     ecx, ecx; lpEventAttributes
0x140002935  lea     edx, [r9+1]; bManualReset
0x140002939  call    cs:__imp_CreateEventW
0x14000293f  mov     [rdi], rax
0x140002942  test    rax, rax
0x140002945  jnz     short loc_140002962
0x140002947  call    cs:__imp_GetLastError
0x14000294d  test    eax, eax
0x14000294f  jle     loc_140002AB2
0x140002955  movzx   eax, ax
0x140002958  or      eax, 80070000h
0x14000295d  jmp     loc_140002AB2
0x140002962  mov     cl, 1
0x140002964  call    ModifyGameInputFiles
0x140002969  test    eax, eax
0x14000296b  jns     short loc_140002974
0x14000296d  xor     ecx, ecx
0x14000296f  call    ModifyGameInputFiles
0x140002974  call    cs:__imp_WTSGetActiveConsoleSessionId
0x14000297a  mov     ecx, eax; unsigned int
0x14000297c  call    ?EnsureSessionStarted@@YAJK@Z; EnsureSessionStarted(ulong)
0x140002981  mov     ebx, eax
0x140002983  test    eax, eax
0x140002985  jns     short loc_1400029F8
0x140002987  mov     ecx, cs:dword_14000E000
0x14000298d  cmp     ecx, 2
0x140002990  jbe     short loc_1400029F1
0x140002992  mov     r8, cs:qword_14000E018
0x140002999  mov     edx, 800h
0x14000299e  mov     rcx, cs:qword_14000E010
0x1400029a5  test    rdx, rcx
0x1400029a8  jz      short loc_1400029F1
0x1400029aa  mov     rax, r8
0x1400029ad  and     rax, rdx
0x1400029b0  cmp     rax, r8
0x1400029b3  jnz     short loc_1400029F1
0x1400029b5  lea     rax, aOnecoreXboxGam_6; "onecore\\xbox\\gameinput\\published\\sv"...
0x1400029bc  mov     [rbp+arg_0], ebx
0x1400029bf  mov     [rbp+arg_10], rax
0x1400029c3  lea     rdx, word_14000A9D2
0x1400029ca  lea     rax, [rbp+arg_0]
0x1400029ce  mov     [rbp+arg_8], 23Bh
0x1400029d5  mov     [rsp+40h+var_10], rax
0x1400029da  lea     rax, [rbp+arg_8]
0x1400029de  mov     [rsp+40h+var_18], rax
0x1400029e3  lea     rax, [rbp+arg_10]
0x1400029e7  mov     [rsp+40h+var_20], rax
0x1400029ec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400029f1  mov     eax, ebx
0x1400029f3  jmp     loc_140002AB2
0x1400029f8  mov     r8, rdi; lpContext
0x1400029fb  lea     rdx, SvcControlHandler; lpHandlerProc
0x140002a02  lea     rcx, ServiceName; "GameInputSvc"
0x140002a09  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x140002a0f  mov     [rdi+8], rax
0x140002a13  test    rax, rax
0x140002a16  jnz     loc_140002AB0
0x140002a1c  call    cs:__imp_GetLastError
0x140002a22  mov     ebx, eax
0x140002a24  mov     eax, cs:dword_14000E000
0x140002a2a  cmp     eax, 2
0x140002a2d  jbe     short loc_140002A8E
0x140002a2f  mov     rcx, cs:qword_14000E018
0x140002a36  mov     edx, 800h
0x140002a3b  mov     rax, cs:qword_14000E010
0x140002a42  test    rdx, rax
0x140002a45  jz      short loc_140002A8E
0x140002a47  mov     rax, rcx
0x140002a4a  and     rax, rdx
0x140002a4d  cmp     rax, rcx
0x140002a50  jnz     short loc_140002A8E
0x140002a52  lea     rax, aOnecoreXboxGam_6; "onecore\\xbox\\gameinput\\published\\sv"...
0x140002a59  mov     [rbp+arg_0], ebx
0x140002a5c  mov     [rbp+arg_10], rax
0x140002a60  lea     rdx, word_14000A992
0x140002a67  lea     rax, [rbp+arg_0]
0x140002a6b  mov     [rbp+arg_8], 23Eh
0x140002a72  mov     [rsp+40h+var_10], rax
0x140002a77  lea     rax, [rbp+arg_8]
0x140002a7b  mov     [rsp+40h+var_18], rax
0x140002a80  lea     rax, [rbp+arg_10]
0x140002a84  mov     [rsp+40h+var_20], rax
0x140002a89  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140002a8e  test    ebx, ebx
0x140002a90  jnz     short loc_140002A9C
0x140002a92  mov     ebx, 8000FFFFh
0x140002a97  jmp     loc_1400029F1
0x140002a9c  jle     loc_1400029F1
0x140002aa2  movzx   ebx, bx
0x140002aa5  or      ebx, 80070000h
0x140002aab  jmp     loc_1400029F1
0x140002ab0  xor     eax, eax
0x140002ab2  add     rsp, 40h
0x140002ab6  pop     rdi
0x140002ab7  pop     rbx
0x140002ab8  pop     rbp
0x140002ab9  retn
```
