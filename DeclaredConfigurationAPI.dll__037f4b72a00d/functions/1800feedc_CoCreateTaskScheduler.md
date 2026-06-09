# CoCreateTaskScheduler

- ea: `0x1800feedc`
- end: `0x1800fef7f`
- name: `CoCreateTaskScheduler`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800ff304`

## callees

- `0x180058630`
- `0x1800feedc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800fef24`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800fef24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800fef41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800fef41`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fef07`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fef60`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fef07`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fef60`

## string_xrefs

- `0x1800fef16`: `Global\SC_AutoStartComplete`

## pseudocode

```c
__int64 __fastcall CoCreateTaskScheduler(__int64 a1, char *a2, LPVOID *ppv)
{
  unsigned int Instance; // ebx
  char *v5; // rax
  char *v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = a2;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
  if ( Instance == -2147221164 )
  {
    v5 = (char *)OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
    v7 = v5;
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      WaitForSingleObject(v5, 0x3A98u);
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v7);
  }
  return Instance;
}

```

## disassembly

```asm
0x1800feedc  mov     [rsp+arg_0], rbx
0x1800feee1  mov     [rsp+arg_8], rdx
0x1800feee6  push    rdi
0x1800feee7  sub     rsp, 30h
0x1800feeeb  xor     edx, edx; pUnkOuter
0x1800feeed  mov     [rsp+38h+ppv], r8; ppv
0x1800feef2  mov     rdi, r8
0x1800feef5  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800feefc  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800fef03  lea     r8d, [rdx+1]; dwClsContext
0x1800fef07  call    cs:__imp_CoCreateInstance
0x1800fef0d  mov     ebx, eax
0x1800fef0f  cmp     eax, 80040154h
0x1800fef14  jnz     short loc_1800FEF72
0x1800fef16  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x1800fef1d  xor     edx, edx; bInheritHandle
0x1800fef1f  mov     ecx, 100000h; dwDesiredAccess
0x1800fef24  call    cs:__imp_OpenEventW
0x1800fef2a  mov     [rsp+38h+arg_8], rax
0x1800fef2f  lea     rdx, [rax-1]
0x1800fef33  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800fef37  ja      short loc_1800FEF47
0x1800fef39  mov     edx, 3A98h; dwMilliseconds
0x1800fef3e  mov     rcx, rax; hHandle
0x1800fef41  call    cs:__imp_WaitForSingleObject
0x1800fef47  xor     edx, edx; pUnkOuter
0x1800fef49  mov     [rsp+38h+ppv], rdi; ppv
0x1800fef4e  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800fef55  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800fef5c  lea     r8d, [rdx+1]; dwClsContext
0x1800fef60  call    cs:__imp_CoCreateInstance
0x1800fef66  lea     rcx, [rsp+38h+arg_8]
0x1800fef6b  mov     ebx, eax
0x1800fef6d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fef72  mov     eax, ebx
0x1800fef74  mov     rbx, [rsp+38h+arg_0]
0x1800fef79  add     rsp, 30h
0x1800fef7d  pop     rdi
0x1800fef7e  retn
```
