# UserAwareWindowIdentity::GetCoreApplicationForCallingProcess(_GUID const &,void * *)

- ea: `0x180074da8`
- end: `0x180074e47`
- name: `?GetCoreApplicationForCallingProcess@UserAwareWindowIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `159`
- prototype: `__int64 __fastcall(UserAwareWindowIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180074e50`

## callees

- `0x18000cbc0`
- `0x180027ce8`
- `0x18004eab8`
- `0x180074da8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180074df3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180074df3`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180074e23`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180074e23`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180074e04`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180074e04`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserAwareWindowIdentity::GetCoreApplicationForCallingProcess(
        UserAwareWindowIdentity *this,
        const struct _GUID *a2,
        void **a3)
{
  void **v4; // r8
  int CallingProcessHandle; // ebx
  __int64 ProcessId; // rdi
  HANDLE Process; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)&a2->Data1 = 0;
  Process = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &Process,
    0);
  CallingProcessHandle = UserAwareCallerIdentity::GetCallingProcessHandle(
                           (UserAwareCallerIdentity *)0x1000,
                           (unsigned int)&Process,
                           v4);
  if ( CallingProcessHandle >= 0 )
  {
    ProcessId = GetProcessId(Process);
    CallingProcessHandle = CoreIsApplicationServiceSupported(ProcessId, &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1);
    if ( CallingProcessHandle >= 0 )
      CallingProcessHandle = CoreQueryApplicationService(
                               (unsigned int)ProcessId,
                               &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1,
                               &GUID_17b0e613_942a_422d_904c_f90dc71a7dae,
                               a2);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x180074da8  mov     rax, rsp
0x180074dab  mov     [rax+10h], rbx
0x180074daf  mov     [rax+18h], rsi
0x180074db3  mov     [rax+8], rcx
0x180074db7  push    rdi
0x180074db8  sub     rsp, 20h
0x180074dbc  mov     rsi, rdx
0x180074dbf  mov     qword ptr [rdx], 0
0x180074dc6  mov     qword ptr [rax+8], 0
0x180074dce  xor     edx, edx
0x180074dd0  lea     rcx, [rax+8]
0x180074dd4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180074dd9  lea     rdx, [rsp+28h+Process]; unsigned int
0x180074dde  mov     ecx, 1000h; this
0x180074de3  call    ?GetCallingProcessHandle@UserAwareCallerIdentity@@YAJKPEAPEAX@Z; UserAwareCallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x180074de8  mov     ebx, eax
0x180074dea  test    eax, eax
0x180074dec  js      short loc_180074E2B
0x180074dee  mov     rcx, [rsp+28h+Process]; Process
0x180074df3  call    cs:__imp_GetProcessId
0x180074df9  mov     edi, eax
0x180074dfb  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180074e02  mov     ecx, eax
0x180074e04  call    cs:__imp_CoreIsApplicationServiceSupported
0x180074e0a  mov     ebx, eax
0x180074e0c  test    eax, eax
0x180074e0e  js      short loc_180074E2B
0x180074e10  mov     r9, rsi
0x180074e13  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x180074e1a  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180074e21  mov     ecx, edi
0x180074e23  call    cs:__imp_CoreQueryApplicationService
0x180074e29  mov     ebx, eax
0x180074e2b  lea     rcx, [rsp+28h+Process]
0x180074e30  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180074e35  mov     eax, ebx
0x180074e37  mov     rbx, [rsp+28h+arg_8]
0x180074e3c  mov     rsi, [rsp+28h+arg_10]
0x180074e41  add     rsp, 20h
0x180074e45  pop     rdi
0x180074e46  retn
```
