# CoCreateTaskScheduler

- ea: `0x14000a03c`
- end: `0x14000a12d`
- name: `CoCreateTaskScheduler`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000a51c`
- `0x14000ec7c`

## callees

- `0x1400093a0`
- `0x14000a03c`
- `0x14001848c`
- `0x140018890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000a0a9`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14000a0a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000a0cc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000a0cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000a067`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000a0f1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000a067`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000a0f1`

## string_xrefs

- `0x14000a09b`: `Global\SC_AutoStartComplete`
- `0x14000a07e`: `CoCreateTaskScheduler`
- `0x14000a104`: `CoCreateTaskScheduler Retry`

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
0x14000a03c  mov     [rsp+arg_0], rbx
0x14000a041  mov     [rsp+arg_8], rdx
0x14000a046  push    rdi
0x14000a047  sub     rsp, 30h
0x14000a04b  xor     edx, edx; pUnkOuter
0x14000a04d  mov     [rsp+38h+ppv], r8; ppv
0x14000a052  mov     rdi, r8
0x14000a055  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14000a05c  lea     rcx, CLSID_TaskScheduler; rclsid
0x14000a063  lea     r8d, [rdx+1]; dwClsContext
0x14000a067  call    cs:__imp_CoCreateInstance
0x14000a06e  nop     dword ptr [rax+rax+00h]
0x14000a073  mov     ebx, eax
0x14000a075  test    eax, eax
0x14000a077  jns     short loc_14000A08F
0x14000a079  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000a07e  lea     r8, aCocreatetasksc_0; "CoCreateTaskScheduler"
0x14000a085  mov     edx, ebx; int
0x14000a087  mov     rcx, rax; this
0x14000a08a  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000a08f  cmp     ebx, 80040154h
0x14000a095  jnz     loc_14000A11F
0x14000a09b  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x14000a0a2  xor     edx, edx; bInheritHandle
0x14000a0a4  mov     ecx, 100000h; dwDesiredAccess
0x14000a0a9  call    cs:__imp_OpenEventW
0x14000a0b0  nop     dword ptr [rax+rax+00h]
0x14000a0b5  mov     [rsp+38h+arg_8], rax
0x14000a0ba  lea     rdx, [rax-1]
0x14000a0be  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000a0c2  ja      short loc_14000A0D8
0x14000a0c4  mov     edx, 3A98h; dwMilliseconds
0x14000a0c9  mov     rcx, rax; hHandle
0x14000a0cc  call    cs:__imp_WaitForSingleObject
0x14000a0d3  nop     dword ptr [rax+rax+00h]
0x14000a0d8  xor     edx, edx; pUnkOuter
0x14000a0da  mov     [rsp+38h+ppv], rdi; ppv
0x14000a0df  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14000a0e6  lea     rcx, CLSID_TaskScheduler; rclsid
0x14000a0ed  lea     r8d, [rdx+1]; dwClsContext
0x14000a0f1  call    cs:__imp_CoCreateInstance
0x14000a0f8  nop     dword ptr [rax+rax+00h]
0x14000a0fd  mov     ebx, eax
0x14000a0ff  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x14000a104  lea     r8, aCocreatetasksc; "CoCreateTaskScheduler Retry"
0x14000a10b  mov     edx, ebx; int
0x14000a10d  mov     rcx, rax; this
0x14000a110  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x14000a115  lea     rcx, [rsp+38h+arg_8]
0x14000a11a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14000a11f  mov     eax, ebx
0x14000a121  mov     rbx, [rsp+38h+arg_0]
0x14000a126  add     rsp, 30h
0x14000a12a  pop     rdi
0x14000a12b  retn
```
