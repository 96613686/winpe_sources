# CProfMgr::OnServiceStart(void)

- ea: `0x180032390`
- end: `0x1800325eb`
- name: `?OnServiceStart@CProfMgr@@QEAAJXZ`
- size: `603`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180030da0`

## callees

- `0x180003f30`
- `0x18001200c`
- `0x180030e64`
- `0x180031e28`
- `0x180032390`
- `0x1800326a4`
- `0x1800336d4`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x1800323e9`
- `ntdll!EtwEventRegister` at `0x1800323e9`
- `ntdll!EtwEventUnregister` at `0x1800323b6`
- `ntdll!EtwEventUnregister` at `0x1800323b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800324cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003250c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003253f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003258f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800324cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003250c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003253f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003258f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800324b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800324fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800324b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800324fa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003257d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003257d`
- `USERENV!RegisterGPNotification` at `0x180032535`
- `USERENV!RegisterGPNotification` at `0x180032535`

## string_xrefs

- `0x1800324e4`: `CreateEvent failed: 0x%x in %s`
- `0x1800325a4`: `CreateThread failed: 0x%x in %s`
- `0x1800325ab`: `CProfMgr::OnServiceStart`

## pseudocode

```c
__int64 __fastcall CProfMgr::OnServiceStart(PVOID Parameter)
{
  signed int v2; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v5; // rax
  signed int v6; // eax
  signed int v7; // eax
  HANDLE v8; // rax
  signed int v9; // eax
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF

  ThreadId = 0;
  if ( qword_180087820 )
  {
    EtwEventUnregister();
    qword_180087820 = 0;
  }
  CrimsonHelper::s_instance = S_TermService;
  if ( !(unsigned int)EtwEventRegister(&CrimsonHelper::s_instance, 0, 0, &qword_180087820) )
    byte_180087828 = 1;
  byte_180087829 = 1;
  qword_1800877E0 = (__int64)TRACE_INF;
  qword_1800877E8 = (__int64)TRACE_WRN;
  qword_1800877F0 = (__int64)TRACE_ERR;
  qword_1800877F8 = (__int64)TRACE_FATAL;
  qword_180087800 = (__int64)TRACE_ALV;
  qword_180087808 = (__int64)TRACE_ENT;
  qword_180087810 = (__int64)TRACE_EXIT;
  qword_180087818 = (__int64)TRACE_DUMP;
  if ( (unsigned int)IsTSInAppServerMode() )
  {
    CUVHDProfileTelemetryLogging::Register();
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)Parameter + 199) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 < 0 )
        goto LABEL_11;
    }
    v5 = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)Parameter + 200) = v5;
    if ( v5 )
      goto LABEL_16;
    v6 = GetLastError();
    v2 = v6;
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_16:
      CProfMgr::OnPolicyChange(Parameter);
      if ( RegisterGPNotification(*((HANDLE *)Parameter + 200), 1) )
        goto LABEL_21;
      v7 = GetLastError();
      v2 = v7;
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      if ( v2 >= 0 )
      {
LABEL_21:
        v8 = CreateThread(0, 0, CProfMgr::staticMonitorPolicyChanges, Parameter, 0, &ThreadId);
        *((_QWORD *)Parameter + 201) = v8;
        if ( v8 )
          return 0;
        v9 = GetLastError();
        v2 = v9;
        if ( v9 > 0 )
          v2 = (unsigned __int16)v9 | 0x80070000;
        if ( v2 >= 0 )
          return 0;
        _DbgPrintMessage(8, "CreateThread failed: 0x%x in %s", (unsigned int)v2, "CProfMgr::OnServiceStart");
      }
      else
      {
        _DbgPrintMessage(8, "RegisterGPNotification failed: 0x%x in %s", (unsigned int)v2, "CProfMgr::OnServiceStart");
      }
    }
    else
    {
LABEL_11:
      _DbgPrintMessage(8, "CreateEvent failed: 0x%x in %s", (unsigned int)v2, "CProfMgr::OnServiceStart");
    }
    CrimsonHelper::RaiseEvent<long>(
      (CrimsonHelper *)&CrimsonHelper::s_instance,
      (const struct _EVENT_DESCRIPTOR *)EVENT_TS_RUP_START_FAILED,
      v2);
  }
  else
  {
    v2 = 0;
    _DbgPrintMessage(1, "Not in TS App Server Mode; exiting Profile Monitor");
    CrimsonHelper::RaiseEventInternal((CrimsonHelper *)&CrimsonHelper::s_instance, &EVENT_TS_NO_APPSERVER, 0, 0);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180032390  mov     [rsp+arg_0], rbx
0x180032395  mov     [rsp+arg_10], rbp
0x18003239a  push    rdi
0x18003239b  sub     rsp, 30h
0x18003239f  mov     rdi, rcx
0x1800323a2  mov     [rsp+38h+ThreadId], 0
0x1800323aa  mov     rcx, cs:qword_180087820
0x1800323b1  test    rcx, rcx
0x1800323b4  jz      short loc_1800323C7
0x1800323b6  call    cs:__imp_EtwEventUnregister
0x1800323bc  mov     cs:qword_180087820, 0
0x1800323c7  movups  xmm0, cs:S_TermService
0x1800323ce  lea     r9, qword_180087820
0x1800323d5  xor     r8d, r8d
0x1800323d8  xor     edx, edx
0x1800323da  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x1800323e1  movdqu  cs:?s_instance@CrimsonHelper@@0V1@A, xmm0; CrimsonHelper CrimsonHelper::s_instance
0x1800323e9  call    cs:__imp_EtwEventRegister
0x1800323ef  test    eax, eax
0x1800323f1  jnz     short loc_1800323FA
0x1800323f3  mov     cs:byte_180087828, 1
0x1800323fa  lea     rax, TRACE_INF
0x180032401  mov     cs:byte_180087829, 1
0x180032408  mov     cs:qword_1800877E0, rax
0x18003240f  lea     rax, TRACE_WRN
0x180032416  mov     cs:qword_1800877E8, rax
0x18003241d  lea     rax, TRACE_ERR
0x180032424  mov     cs:qword_1800877F0, rax
0x18003242b  lea     rax, TRACE_FATAL
0x180032432  mov     cs:qword_1800877F8, rax
0x180032439  lea     rax, TRACE_ALV
0x180032440  mov     cs:qword_180087800, rax
0x180032447  lea     rax, TRACE_ENT
0x18003244e  mov     cs:qword_180087808, rax
0x180032455  lea     rax, TRACE_EXIT
0x18003245c  mov     cs:qword_180087810, rax
0x180032463  lea     rax, TRACE_DUMP
0x18003246a  mov     cs:qword_180087818, rax
0x180032471  call    ?IsTSInAppServerMode@@YAHXZ; IsTSInAppServerMode(void)
0x180032476  test    eax, eax
0x180032478  jnz     short loc_1800324A9
0x18003247a  lea     rdx, aNotInTsAppServ; "Not in TS App Server Mode; exiting Prof"...
0x180032481  xor     ebx, ebx
0x180032483  lea     ecx, [rax+1]; int
0x180032486  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003248b  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x18003248e  lea     rdx, EVENT_TS_NO_APPSERVER; struct _EVENT_DESCRIPTOR *
0x180032495  xor     r8d, r8d; unsigned int
0x180032498  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x18003249f  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x1800324a4  jmp     loc_1800325D9
0x1800324a9  call    ?Register@CUVHDProfileTelemetryLogging@@SAJXZ; CUVHDProfileTelemetryLogging::Register(void)
0x1800324ae  xor     r9d, r9d; lpName
0x1800324b1  xor     r8d, r8d; bInitialState
0x1800324b4  xor     edx, edx; bManualReset
0x1800324b6  xor     ecx, ecx; lpEventAttributes
0x1800324b8  call    cs:__imp_CreateEventW
0x1800324be  mov     [rdi+638h], rax
0x1800324c5  mov     ebp, 80070000h
0x1800324ca  test    rax, rax
0x1800324cd  jnz     short loc_1800324F0
0x1800324cf  call    cs:__imp_GetLastError
0x1800324d5  mov     ebx, eax
0x1800324d7  test    eax, eax
0x1800324d9  jle     short loc_1800324E0
0x1800324db  movzx   ebx, ax
0x1800324de  or      ebx, ebp
0x1800324e0  test    ebx, ebx
0x1800324e2  jns     short loc_1800324F0
0x1800324e4  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x1800324eb  jmp     loc_1800325AB
0x1800324f0  xor     r9d, r9d; lpName
0x1800324f3  xor     r8d, r8d; bInitialState
0x1800324f6  xor     edx, edx; bManualReset
0x1800324f8  xor     ecx, ecx; lpEventAttributes
0x1800324fa  call    cs:__imp_CreateEventW
0x180032500  mov     [rdi+640h], rax
0x180032507  test    rax, rax
0x18003250a  jnz     short loc_180032521
0x18003250c  call    cs:__imp_GetLastError
0x180032512  mov     ebx, eax
0x180032514  test    eax, eax
0x180032516  jle     short loc_18003251D
0x180032518  movzx   ebx, ax
0x18003251b  or      ebx, ebp
0x18003251d  test    ebx, ebx
0x18003251f  js      short loc_1800324E4
0x180032521  mov     rcx, rdi; Parameter
0x180032524  call    ?OnPolicyChange@CProfMgr@@QEAAJXZ; CProfMgr::OnPolicyChange(void)
0x180032529  mov     rcx, [rdi+640h]; hEvent
0x180032530  mov     edx, 1; bMachine
0x180032535  call    cs:__imp_RegisterGPNotification
0x18003253b  test    eax, eax
0x18003253d  jnz     short loc_18003255D
0x18003253f  call    cs:__imp_GetLastError
0x180032545  mov     ebx, eax
0x180032547  test    eax, eax
0x180032549  jle     short loc_180032550
0x18003254b  movzx   ebx, ax
0x18003254e  or      ebx, ebp
0x180032550  test    ebx, ebx
0x180032552  jns     short loc_18003255D
0x180032554  lea     rdx, aRegistergpnoti_1; "RegisterGPNotification failed: 0x%x in "...
0x18003255b  jmp     short loc_1800325AB
0x18003255d  lea     rax, [rsp+38h+ThreadId]
0x180032562  mov     r9, rdi; lpParameter
0x180032565  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18003256a  lea     r8, ?staticMonitorPolicyChanges@CProfMgr@@CAKPEAX@Z; lpStartAddress
0x180032571  xor     edx, edx; dwStackSize
0x180032573  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18003257b  xor     ecx, ecx; lpThreadAttributes
0x18003257d  call    cs:__imp_CreateThread
0x180032583  mov     [rdi+648h], rax
0x18003258a  test    rax, rax
0x18003258d  jnz     short loc_1800325D7
0x18003258f  call    cs:__imp_GetLastError
0x180032595  mov     ebx, eax
0x180032597  test    eax, eax
0x180032599  jle     short loc_1800325A0
0x18003259b  movzx   ebx, ax
0x18003259e  or      ebx, ebp
0x1800325a0  test    ebx, ebx
0x1800325a2  jns     short loc_1800325D7
0x1800325a4  lea     rdx, aCreatethreadFa_0; "CreateThread failed: 0x%x in %s"
0x1800325ab  lea     r9, aCprofmgrOnserv; "CProfMgr::OnServiceStart"
0x1800325b2  mov     r8d, ebx
0x1800325b5  mov     ecx, 8; int
0x1800325ba  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800325bf  mov     r8d, ebx
0x1800325c2  lea     rdx, EVENT_TS_RUP_START_FAILED
0x1800325c9  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x1800325d0  call    ??$RaiseEvent@J@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@J@Z; CrimsonHelper::RaiseEvent<long>(_EVENT_DESCRIPTOR const &,long)
0x1800325d5  jmp     short loc_1800325D9
0x1800325d7  xor     ebx, ebx
0x1800325d9  mov     rbp, [rsp+38h+arg_10]
0x1800325de  mov     eax, ebx
0x1800325e0  mov     rbx, [rsp+38h+arg_0]
0x1800325e5  add     rsp, 30h
0x1800325e9  pop     rdi
0x1800325ea  retn
```
