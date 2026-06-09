# CoCreateTaskScheduler

- ea: `0x14002cb58`
- end: `0x14002cc39`
- name: `CoCreateTaskScheduler`
- size: `225`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002cfbc`
- `0x14002f150`

## callees

- `0x14002cb58`
- `0x1400347e8`
- `0x140034b28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002cbd5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002cbd5`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14002cbbb`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14002cbbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cc20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cc20`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002cb83`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002cbf4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002cb83`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002cbf4`

## string_xrefs

- `0x14002cbad`: `Global\SC_AutoStartComplete`
- `0x14002cb94`: `CoCreateTaskScheduler`
- `0x14002cc01`: `CoCreateTaskScheduler Retry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CoCreateTaskScheduler(__int64 a1, __int64 a2, LPVOID *ppv)
{
  HRESULT Instance; // edi
  CEnrollmentLogger *Logger; // rax
  char *v6; // rbx
  CEnrollmentLogger *v7; // rax

  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
  if ( Instance < 0 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Instance, "CoCreateTaskScheduler");
  }
  if ( Instance == -2147221164 )
  {
    v6 = (char *)OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      WaitForSingleObject(v6, 0x3A98u);
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
    v7 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(v7, Instance, "CoCreateTaskScheduler Retry");
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v6);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x14002cb58  mov     [rsp+arg_0], rbx
0x14002cb5d  mov     [rsp+arg_8], rsi
0x14002cb62  push    rdi
0x14002cb63  sub     rsp, 30h
0x14002cb67  mov     rsi, r8
0x14002cb6a  mov     [rsp+38h+ppv], r8; ppv
0x14002cb6f  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14002cb76  xor     edx, edx; pUnkOuter
0x14002cb78  lea     r8d, [rdx+1]; dwClsContext
0x14002cb7c  lea     rcx, CLSID_TaskScheduler; rclsid
0x14002cb83  call    cs:__imp_CoCreateInstance
0x14002cb89  mov     edi, eax
0x14002cb8b  test    eax, eax
0x14002cb8d  jns     short loc_14002CBA5
0x14002cb8f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14002cb94  lea     r8, aCocreatetasksc_0; "CoCreateTaskScheduler"
0x14002cb9b  mov     edx, edi; int
0x14002cb9d  mov     rcx, rax; this
0x14002cba0  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14002cba5  cmp     edi, 80040154h
0x14002cbab  jnz     short loc_14002CC27
0x14002cbad  lea     r8, aGlobalScAutost; "Global\\SC_AutoStartComplete"
0x14002cbb4  xor     edx, edx; bInheritHandle
0x14002cbb6  mov     ecx, 100000h; dwDesiredAccess
0x14002cbbb  call    cs:__imp_OpenEventW
0x14002cbc1  mov     rbx, rax
0x14002cbc4  dec     rax
0x14002cbc7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002cbcb  ja      short loc_14002CBDB
0x14002cbcd  mov     edx, 3A98h; dwMilliseconds
0x14002cbd2  mov     rcx, rbx; hHandle
0x14002cbd5  call    cs:__imp_WaitForSingleObject
0x14002cbdb  mov     [rsp+38h+ppv], rsi; ppv
0x14002cbe0  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14002cbe7  xor     edx, edx; pUnkOuter
0x14002cbe9  lea     r8d, [rdx+1]; dwClsContext
0x14002cbed  lea     rcx, CLSID_TaskScheduler; rclsid
0x14002cbf4  call    cs:__imp_CoCreateInstance
0x14002cbfa  mov     edi, eax
0x14002cbfc  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14002cc01  lea     r8, aCocreatetasksc; "CoCreateTaskScheduler Retry"
0x14002cc08  mov     edx, edi; int
0x14002cc0a  mov     rcx, rax; this
0x14002cc0d  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14002cc12  nop
0x14002cc13  lea     rax, [rbx-1]
0x14002cc17  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002cc1b  ja      short loc_14002CC27
0x14002cc1d  mov     rcx, rbx; hObject
0x14002cc20  call    cs:__imp_CloseHandle
0x14002cc26  nop
0x14002cc27  mov     eax, edi
0x14002cc29  mov     rbx, [rsp+38h+arg_0]
0x14002cc2e  mov     rsi, [rsp+38h+arg_8]
0x14002cc33  add     rsp, 30h
0x14002cc37  pop     rdi
0x14002cc38  retn
```
