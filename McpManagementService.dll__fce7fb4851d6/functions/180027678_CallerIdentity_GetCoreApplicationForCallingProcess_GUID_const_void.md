# CallerIdentity::GetCoreApplicationForCallingProcess(_GUID const &,void * *)

- ea: `0x180027678`
- end: `0x18002771a`
- name: `?GetCoreApplicationForCallingProcess@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `162`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800274b8`
- `0x180027720`

## callees

- `0x1800273b4`
- `0x180027678`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800276b2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800276b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027702`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027702`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x1800276e2`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x1800276e2`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x1800276c3`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x1800276c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180027678  mov     rax, rsp
0x18002767b  mov     [rax+10h], rbx
0x18002767f  mov     [rax+18h], rsi
0x180027683  mov     [rax+8], rcx
0x180027687  push    rdi
0x180027688  sub     rsp, 20h
0x18002768c  mov     rdi, rdx
0x18002768f  mov     qword ptr [rdx], 0
0x180027696  lea     rdx, [rax+8]; unsigned int
0x18002769a  mov     qword ptr [rax+8], 0
0x1800276a2  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x1800276a7  mov     ebx, eax
0x1800276a9  test    eax, eax
0x1800276ab  js      short loc_1800276EA
0x1800276ad  mov     rcx, [rsp+28h+Process]; Process
0x1800276b2  call    cs:__imp_GetProcessId
0x1800276b8  mov     ecx, eax
0x1800276ba  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x1800276c1  mov     esi, eax
0x1800276c3  call    cs:__imp_CoreIsApplicationServiceSupported
0x1800276c9  mov     ebx, eax
0x1800276cb  test    eax, eax
0x1800276cd  js      short loc_1800276EA
0x1800276cf  mov     r9, rdi
0x1800276d2  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x1800276d9  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x1800276e0  mov     ecx, esi
0x1800276e2  call    cs:__imp_CoreQueryApplicationService
0x1800276e8  mov     ebx, eax
0x1800276ea  mov     rcx, [rsp+28h+Process]; hObject
0x1800276ef  mov     [rsp+28h+Process], 0
0x1800276f8  lea     rax, [rcx-1]
0x1800276fc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180027700  ja      short loc_180027708
0x180027702  call    cs:__imp_CloseHandle
0x180027708  mov     rsi, [rsp+28h+arg_10]
0x18002770d  mov     eax, ebx
0x18002770f  mov     rbx, [rsp+28h+arg_8]
0x180027714  add     rsp, 20h
0x180027718  pop     rdi
0x180027719  retn
```
