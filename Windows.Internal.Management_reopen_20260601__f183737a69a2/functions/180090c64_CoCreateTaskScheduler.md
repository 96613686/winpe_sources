# CoCreateTaskScheduler

- ea: `0x180090c64`
- end: `0x180090d58`
- name: `CoCreateTaskScheduler`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180091100`
- `0x180092404`

## callees

- `0x1800151e0`
- `0x180090c64`
- `0x180095efc`
- `0x1800967cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180090cd1`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180090cd1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180090cf5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180090cf5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180090c8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180090d1a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180090c8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180090d1a`

## string_xrefs

- `0x180090ca6`: `CoCreateTaskScheduler`
- `0x180090cc3`: `Global\SC_AutoStartComplete`
- `0x180090d2d`: `CoCreateTaskScheduler Retry`

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
0x180090c64  mov     [rsp+arg_0], rbx
0x180090c69  mov     [rsp+arg_8], rdx
0x180090c6e  push    rdi
0x180090c6f  sub     rsp, 30h
0x180090c73  mov     rdi, r8
0x180090c76  mov     [rsp+38h+ppv], r8; ppv
0x180090c7b  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180090c82  xor     edx, edx; pUnkOuter
0x180090c84  lea     r8d, [rdx+1]; dwClsContext
0x180090c88  lea     rcx, CLSID_TaskScheduler; rclsid
0x180090c8f  call    cs:__imp_CoCreateInstance
0x180090c96  nop     dword ptr [rax+rax+00h]
0x180090c9b  mov     ebx, eax
0x180090c9d  test    eax, eax
0x180090c9f  jns     short loc_180090CB7
0x180090ca1  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180090ca6  lea     r8, aCocreatetasksc_0; "CoCreateTaskScheduler"
0x180090cad  mov     edx, ebx; int
0x180090caf  mov     rcx, rax; this
0x180090cb2  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180090cb7  cmp     ebx, 80040154h
0x180090cbd  jnz     loc_180090D4A
0x180090cc3  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x180090cca  xor     edx, edx; bInheritHandle
0x180090ccc  mov     ecx, 100000h; dwDesiredAccess
0x180090cd1  call    cs:__imp_OpenEventW
0x180090cd8  nop     dword ptr [rax+rax+00h]
0x180090cdd  nop
0x180090cde  mov     [rsp+38h+arg_8], rax
0x180090ce3  lea     rdx, [rax-1]
0x180090ce7  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180090ceb  ja      short loc_180090D01
0x180090ced  mov     edx, 3A98h; dwMilliseconds
0x180090cf2  mov     rcx, rax; hHandle
0x180090cf5  call    cs:__imp_WaitForSingleObject
0x180090cfc  nop     dword ptr [rax+rax+00h]
0x180090d01  mov     [rsp+38h+ppv], rdi; ppv
0x180090d06  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180090d0d  xor     edx, edx; pUnkOuter
0x180090d0f  lea     r8d, [rdx+1]; dwClsContext
0x180090d13  lea     rcx, CLSID_TaskScheduler; rclsid
0x180090d1a  call    cs:__imp_CoCreateInstance
0x180090d21  nop     dword ptr [rax+rax+00h]
0x180090d26  mov     ebx, eax
0x180090d28  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180090d2d  lea     r8, aCocreatetasksc; "CoCreateTaskScheduler Retry"
0x180090d34  mov     edx, ebx; int
0x180090d36  mov     rcx, rax; this
0x180090d39  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x180090d3e  nop
0x180090d3f  lea     rcx, [rsp+38h+arg_8]
0x180090d44  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180090d49  nop
0x180090d4a  mov     eax, ebx
0x180090d4c  mov     rbx, [rsp+38h+arg_0]
0x180090d51  add     rsp, 30h
0x180090d55  pop     rdi
0x180090d56  retn
```
