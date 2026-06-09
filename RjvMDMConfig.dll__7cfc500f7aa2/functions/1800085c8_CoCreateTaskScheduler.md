# CoCreateTaskScheduler

- ea: `0x1800085c8`
- end: `0x1800086bc`
- name: `CoCreateTaskScheduler`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180008bd4`
- `0x18000de68`

## callees

- `0x1800038c0`
- `0x1800085c8`
- `0x18001b9d8`
- `0x18001bde0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008659`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008659`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180008635`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180008635`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800085f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000867e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800085f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000867e`

## string_xrefs

- `0x180008627`: `Global\SC_AutoStartComplete`
- `0x18000860a`: `CoCreateTaskScheduler`
- `0x180008691`: `CoCreateTaskScheduler Retry`

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
0x1800085c8  mov     [rsp+arg_0], rbx
0x1800085cd  mov     [rsp+arg_8], rdx
0x1800085d2  push    rdi
0x1800085d3  sub     rsp, 30h
0x1800085d7  mov     rdi, r8
0x1800085da  mov     [rsp+38h+ppv], r8; ppv
0x1800085df  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800085e6  xor     edx, edx; pUnkOuter
0x1800085e8  lea     r8d, [rdx+1]; dwClsContext
0x1800085ec  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800085f3  call    cs:__imp_CoCreateInstance
0x1800085fa  nop     dword ptr [rax+rax+00h]
0x1800085ff  mov     ebx, eax
0x180008601  test    eax, eax
0x180008603  jns     short loc_18000861B
0x180008605  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18000860a  lea     r8, aCocreatetasksc_0; "CoCreateTaskScheduler"
0x180008611  mov     edx, ebx; int
0x180008613  mov     rcx, rax; this
0x180008616  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x18000861b  cmp     ebx, 80040154h
0x180008621  jnz     loc_1800086AE
0x180008627  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x18000862e  xor     edx, edx; bInheritHandle
0x180008630  mov     ecx, 100000h; dwDesiredAccess
0x180008635  call    cs:__imp_OpenEventW
0x18000863c  nop     dword ptr [rax+rax+00h]
0x180008641  nop
0x180008642  mov     [rsp+38h+arg_8], rax
0x180008647  lea     rdx, [rax-1]
0x18000864b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000864f  ja      short loc_180008665
0x180008651  mov     edx, 3A98h; dwMilliseconds
0x180008656  mov     rcx, rax; hHandle
0x180008659  call    cs:__imp_WaitForSingleObject
0x180008660  nop     dword ptr [rax+rax+00h]
0x180008665  mov     [rsp+38h+ppv], rdi; ppv
0x18000866a  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180008671  xor     edx, edx; pUnkOuter
0x180008673  lea     r8d, [rdx+1]; dwClsContext
0x180008677  lea     rcx, CLSID_TaskScheduler; rclsid
0x18000867e  call    cs:__imp_CoCreateInstance
0x180008685  nop     dword ptr [rax+rax+00h]
0x18000868a  mov     ebx, eax
0x18000868c  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180008691  lea     r8, aCocreatetasksc; "CoCreateTaskScheduler Retry"
0x180008698  mov     edx, ebx; int
0x18000869a  mov     rcx, rax; this
0x18000869d  call    ?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z; CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)
0x1800086a2  nop
0x1800086a3  lea     rcx, [rsp+38h+arg_8]
0x1800086a8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800086ad  nop
0x1800086ae  mov     eax, ebx
0x1800086b0  mov     rbx, [rsp+38h+arg_0]
0x1800086b5  add     rsp, 30h
0x1800086b9  pop     rdi
0x1800086ba  retn
```
