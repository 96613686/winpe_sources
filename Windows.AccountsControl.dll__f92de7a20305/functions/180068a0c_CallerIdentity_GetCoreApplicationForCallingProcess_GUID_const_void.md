# CallerIdentity::GetCoreApplicationForCallingProcess(_GUID const &,void * *)

- ea: `0x180068a0c`
- end: `0x180068a9b`
- name: `?GetCoreApplicationForCallingProcess@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `143`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180068aa4`

## callees

- `0x180024118`
- `0x180067df0`
- `0x180068a0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180068a46`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180068a46`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180068a76`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180068a76`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180068a57`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180068a57`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::GetCoreApplicationForCallingProcess(
        CallerIdentity *this,
        const struct _GUID *a2,
        void **a3)
{
  int CallingProcessHandle; // ebx
  __int64 ProcessId; // rsi
  HANDLE Process; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)&a2->Data1 = 0;
  Process = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(this, (unsigned int)&Process, a3);
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
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::~CTSmartObj<void *,CAutoHandle_Policy<void *>>(&Process);
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x180068a0c  mov     rax, rsp
0x180068a0f  mov     [rax+10h], rbx
0x180068a13  mov     [rax+18h], rsi
0x180068a17  mov     [rax+8], rcx
0x180068a1b  push    rdi
0x180068a1c  sub     rsp, 20h
0x180068a20  mov     rdi, rdx
0x180068a23  mov     qword ptr [rdx], 0
0x180068a2a  mov     qword ptr [rax+8], 0
0x180068a32  lea     rdx, [rax+8]; unsigned int
0x180068a36  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x180068a3b  mov     ebx, eax
0x180068a3d  test    eax, eax
0x180068a3f  js      short loc_180068A7E
0x180068a41  mov     rcx, [rsp+28h+Process]; Process
0x180068a46  call    cs:__imp_GetProcessId
0x180068a4c  mov     esi, eax
0x180068a4e  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180068a55  mov     ecx, eax
0x180068a57  call    cs:__imp_CoreIsApplicationServiceSupported
0x180068a5d  mov     ebx, eax
0x180068a5f  test    eax, eax
0x180068a61  js      short loc_180068A7E
0x180068a63  mov     r9, rdi
0x180068a66  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x180068a6d  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180068a74  mov     ecx, esi
0x180068a76  call    cs:__imp_CoreQueryApplicationService
0x180068a7c  mov     ebx, eax
0x180068a7e  lea     rcx, [rsp+28h+Process]
0x180068a83  call    ??1?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAA@XZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::~CTSmartObj<void *,CAutoHandle_Policy<void *>>(void)
0x180068a88  nop
0x180068a89  mov     eax, ebx
0x180068a8b  mov     rbx, [rsp+28h+arg_8]
0x180068a90  mov     rsi, [rsp+28h+arg_10]
0x180068a95  add     rsp, 20h
0x180068a99  pop     rdi
0x180068a9a  retn
```
