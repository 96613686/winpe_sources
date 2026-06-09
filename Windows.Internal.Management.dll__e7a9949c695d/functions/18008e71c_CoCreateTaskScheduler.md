# CoCreateTaskScheduler

- ea: `0x18008e71c`
- end: `0x18008e7f3`
- name: `CoCreateTaskScheduler`
- size: `215`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18008eb90`
- `0x18008fdf8`

## callees

- `0x180014af0`
- `0x18008e71c`
- `0x180093684`
- `0x180093f34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e79d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e79d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18008e77f`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18008e77f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008e747`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008e7bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008e747`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008e7bc`

## string_xrefs

- `0x18008e758`: `CoCreateTaskScheduler`
- `0x18008e771`: `Global\SC_AutoStartComplete`
- `0x18008e7c9`: `CoCreateTaskScheduler Retry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CoCreateTaskScheduler(__int64 a1, char *a2, LPVOID *ppv)
{
  HRESULT Instance; // ebx
  CEnrollmentLogger *Logger; // rax
  char *v6; // rax
  CEnrollmentLogger *v7; // rax
  char *v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = a2;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
  if ( Instance < 0 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(Logger, Instance, "CoCreateTaskScheduler");
  }
  if ( Instance == -2147221164 )
  {
    v6 = (char *)OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
    v9 = v6;
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      WaitForSingleObject(v6, 0x3A98u);
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
    v7 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(v7, Instance, "CoCreateTaskScheduler Retry");
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18008e71c  mov     [rsp+arg_0], rbx
0x18008e721  mov     [rsp+arg_8], rdx
0x18008e726  push    rdi
0x18008e727  sub     rsp, 30h
0x18008e72b  mov     rdi, r8
0x18008e72e  mov     [rsp+38h+ppv], r8; ppv
0x18008e733  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18008e73a  xor     edx, edx; pUnkOuter
0x18008e73c  lea     r8d, [rdx+1]; dwClsContext
0x18008e740  lea     rcx, CLSID_TaskScheduler; rclsid
0x18008e747  call    cs:__imp_CoCreateInstance
0x18008e74d  mov     ebx, eax
0x18008e74f  test    eax, eax
0x18008e751  jns     short loc_18008E769
0x18008e753  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18008e758  lea     r8, aCocreatetasksc_0; "CoCreateTaskScheduler"
0x18008e75f  mov     edx, ebx; int
0x18008e761  mov     rcx, rax; this
0x18008e764  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18008e769  cmp     ebx, 80040154h
0x18008e76f  jnz     short loc_18008E7E6
0x18008e771  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x18008e778  xor     edx, edx; bInheritHandle
0x18008e77a  mov     ecx, 100000h; dwDesiredAccess
0x18008e77f  call    cs:__imp_OpenEventW
0x18008e785  nop
0x18008e786  mov     [rsp+38h+arg_8], rax
0x18008e78b  lea     rdx, [rax-1]
0x18008e78f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18008e793  ja      short loc_18008E7A3
0x18008e795  mov     edx, 3A98h; dwMilliseconds
0x18008e79a  mov     rcx, rax; hHandle
0x18008e79d  call    cs:__imp_WaitForSingleObject
0x18008e7a3  mov     [rsp+38h+ppv], rdi; ppv
0x18008e7a8  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18008e7af  xor     edx, edx; pUnkOuter
0x18008e7b1  lea     r8d, [rdx+1]; dwClsContext
0x18008e7b5  lea     rcx, CLSID_TaskScheduler; rclsid
0x18008e7bc  call    cs:__imp_CoCreateInstance
0x18008e7c2  mov     ebx, eax
0x18008e7c4  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18008e7c9  lea     r8, aCocreatetasksc; "CoCreateTaskScheduler Retry"
0x18008e7d0  mov     edx, ebx; int
0x18008e7d2  mov     rcx, rax; this
0x18008e7d5  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18008e7da  nop
0x18008e7db  lea     rcx, [rsp+38h+arg_8]
0x18008e7e0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008e7e5  nop
0x18008e7e6  mov     eax, ebx
0x18008e7e8  mov     rbx, [rsp+38h+arg_0]
0x18008e7ed  add     rsp, 30h
0x18008e7f1  pop     rdi
0x18008e7f2  retn
```
