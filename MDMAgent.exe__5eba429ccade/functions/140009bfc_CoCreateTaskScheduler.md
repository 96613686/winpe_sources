# CoCreateTaskScheduler

- ea: `0x140009bfc`
- end: `0x140009cd0`
- name: `CoCreateTaskScheduler`
- size: `212`
- prototype: `__int64 __fastcall(__int64, char *, LPVOID *ppv)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000a0b8`
- `0x14000e530`

## callees

- `0x140008fdc`
- `0x140009bfc`
- `0x1400177b0`
- `0x140017ba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140009c5f`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140009c5f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140009c7c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140009c7c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009c27`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009c9b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009c27`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009c9b`

## string_xrefs

- `0x140009c51`: `Global\SC_AutoStartComplete`
- `0x140009c38`: `CoCreateTaskScheduler`
- `0x140009ca8`: `CoCreateTaskScheduler Retry`

## pseudocode

```c
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
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140009bfc  mov     [rsp+arg_0], rbx
0x140009c01  mov     [rsp+arg_8], rdx
0x140009c06  push    rdi
0x140009c07  sub     rsp, 30h
0x140009c0b  xor     edx, edx; pUnkOuter
0x140009c0d  mov     [rsp+38h+ppv], r8; ppv
0x140009c12  mov     rdi, r8
0x140009c15  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140009c1c  lea     rcx, CLSID_TaskScheduler; rclsid
0x140009c23  lea     r8d, [rdx+1]; dwClsContext
0x140009c27  call    cs:__imp_CoCreateInstance
0x140009c2d  mov     ebx, eax
0x140009c2f  test    eax, eax
0x140009c31  jns     short loc_140009C49
0x140009c33  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140009c38  lea     r8, aCocreatetasksc_0; "CoCreateTaskScheduler"
0x140009c3f  mov     edx, ebx; int
0x140009c41  mov     rcx, rax; this
0x140009c44  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x140009c49  cmp     ebx, 80040154h
0x140009c4f  jnz     short loc_140009CC3
0x140009c51  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x140009c58  xor     edx, edx; bInheritHandle
0x140009c5a  mov     ecx, 100000h; dwDesiredAccess
0x140009c5f  call    cs:__imp_OpenEventW
0x140009c65  mov     [rsp+38h+arg_8], rax
0x140009c6a  lea     rdx, [rax-1]
0x140009c6e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140009c72  ja      short loc_140009C82
0x140009c74  mov     edx, 3A98h; dwMilliseconds
0x140009c79  mov     rcx, rax; hHandle
0x140009c7c  call    cs:__imp_WaitForSingleObject
0x140009c82  xor     edx, edx; pUnkOuter
0x140009c84  mov     [rsp+38h+ppv], rdi; ppv
0x140009c89  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140009c90  lea     rcx, CLSID_TaskScheduler; rclsid
0x140009c97  lea     r8d, [rdx+1]; dwClsContext
0x140009c9b  call    cs:__imp_CoCreateInstance
0x140009ca1  mov     ebx, eax
0x140009ca3  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140009ca8  lea     r8, aCocreatetasksc; "CoCreateTaskScheduler Retry"
0x140009caf  mov     edx, ebx; int
0x140009cb1  mov     rcx, rax; this
0x140009cb4  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x140009cb9  lea     rcx, [rsp+38h+arg_8]
0x140009cbe  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140009cc3  mov     eax, ebx
0x140009cc5  mov     rbx, [rsp+38h+arg_0]
0x140009cca  add     rsp, 30h
0x140009cce  pop     rdi
0x140009ccf  retn
```
