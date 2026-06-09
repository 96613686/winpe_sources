# CallerIdentity::GetCoreApplicationForCallingProcess(_GUID const &,void * *)

- ea: `0x180035544`
- end: `0x1800355e6`
- name: `?GetCoreApplicationForCallingProcess@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `162`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800355ec`

## callees

- `0x180003f10`
- `0x180035544`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003557e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003557e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800355ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800355ce`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x1800355ae`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x1800355ae`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x18003558f`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x18003558f`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCoreApplicationForCallingProcess(
        CallerIdentity *this,
        const struct _GUID *a2,
        void **a3)
{
  int CallingProcessHandle; // ebx
  __int64 ProcessId; // rsi
  char *v6; // rcx
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
  v6 = (char *)Process;
  Process = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x180035544  mov     rax, rsp
0x180035547  mov     [rax+10h], rbx
0x18003554b  mov     [rax+18h], rsi
0x18003554f  mov     [rax+8], rcx
0x180035553  push    rdi
0x180035554  sub     rsp, 20h
0x180035558  mov     rdi, rdx
0x18003555b  mov     qword ptr [rdx], 0
0x180035562  lea     rdx, [rax+8]; unsigned int
0x180035566  mov     qword ptr [rax+8], 0
0x18003556e  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x180035573  mov     ebx, eax
0x180035575  test    eax, eax
0x180035577  js      short loc_1800355B6
0x180035579  mov     rcx, [rsp+28h+Process]; Process
0x18003557e  call    cs:__imp_GetProcessId
0x180035584  mov     ecx, eax
0x180035586  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x18003558d  mov     esi, eax
0x18003558f  call    cs:__imp_CoreIsApplicationServiceSupported
0x180035595  mov     ebx, eax
0x180035597  test    eax, eax
0x180035599  js      short loc_1800355B6
0x18003559b  mov     r9, rdi
0x18003559e  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x1800355a5  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x1800355ac  mov     ecx, esi
0x1800355ae  call    cs:__imp_CoreQueryApplicationService
0x1800355b4  mov     ebx, eax
0x1800355b6  mov     rcx, [rsp+28h+Process]; hObject
0x1800355bb  mov     [rsp+28h+Process], 0
0x1800355c4  lea     rax, [rcx-1]
0x1800355c8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800355cc  ja      short loc_1800355D4
0x1800355ce  call    cs:__imp_CloseHandle
0x1800355d4  mov     rsi, [rsp+28h+arg_10]
0x1800355d9  mov     eax, ebx
0x1800355db  mov     rbx, [rsp+28h+arg_8]
0x1800355e0  add     rsp, 20h
0x1800355e4  pop     rdi
0x1800355e5  retn
```
