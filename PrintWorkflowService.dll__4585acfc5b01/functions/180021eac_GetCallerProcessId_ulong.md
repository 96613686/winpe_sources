# GetCallerProcessId(ulong *)

- ea: `0x180021eac`
- end: `0x180021f22`
- name: `?GetCallerProcessId@@YAJPEAK@Z`
- size: `118`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180019290`
- `0x180020330`
- `0x180021570`
- `0x180023f70`
- `0x18002c49c`
- `0x18003f4b8`
- `0x180044ec4`
- `0x1800457c0`
- `0x1800487dc`

## callees

- `0x1800166a8`
- `0x18001a7c0`
- `0x180021df4`
- `0x180021eac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180021efc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180021efc`

## pseudocode

```c
__int64 __fastcall GetCallerProcessId(unsigned int *a1)
{
  int CallerOrSelfProcessHandle; // edi
  HANDLE Process; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  Process = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &Process,
    0);
  CallerOrSelfProcessHandle = GetCallerOrSelfProcessHandle(0x1000u, &Process);
  if ( CallerOrSelfProcessHandle >= 0 )
  {
    *a1 = GetProcessId(Process);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
    return 0;
  }
  else
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
    return (unsigned int)CallerOrSelfProcessHandle;
  }
}

```

## disassembly

```asm
0x180021eac  mov     [rsp+arg_8], rbx
0x180021eb1  push    rdi
0x180021eb2  sub     rsp, 20h
0x180021eb6  mov     rbx, rcx
0x180021eb9  mov     dword ptr [rcx], 0
0x180021ebf  mov     [rsp+28h+Process], 0
0x180021ec8  xor     edx, edx
0x180021eca  lea     rcx, [rsp+28h+Process]
0x180021ecf  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180021ed4  lea     rdx, [rsp+28h+Process]; void **
0x180021ed9  mov     ecx, 1000h; unsigned int
0x180021ede  call    ?GetCallerOrSelfProcessHandle@@YAJKPEAPEAX@Z; GetCallerOrSelfProcessHandle(ulong,void * *)
0x180021ee3  mov     edi, eax
0x180021ee5  test    eax, eax
0x180021ee7  jns     short loc_180021EF7
0x180021ee9  lea     rcx, [rsp+28h+Process]
0x180021eee  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180021ef3  mov     eax, edi
0x180021ef5  jmp     short loc_180021F16
0x180021ef7  mov     rcx, [rsp+28h+Process]; Process
0x180021efc  call    cs:__imp_GetProcessId
0x180021f02  mov     [rbx], eax
0x180021f04  lea     rcx, [rsp+28h+Process]
0x180021f09  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180021f0e  xor     eax, eax
0x180021f10  jmp     short loc_180021F16
0x180021f12  mov     eax, dword ptr [rsp+28h+Process]
0x180021f16  mov     rbx, [rsp+28h+arg_8]
0x180021f1b  add     rsp, 20h
0x180021f1f  pop     rdi
0x180021f20  retn
```
