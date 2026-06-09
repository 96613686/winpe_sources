# DeviceCastle::Library::Internal::Authorization::Manager::ScheduleReaper(void)

- ea: `0x180052664`
- end: `0x180052772`
- name: `?ScheduleReaper@Manager@Authorization@Internal@Library@DeviceCastle@@AEAAXXZ`
- size: `270`
- prototype: `void __fastcall(DeviceCastle::Library::Internal::Authorization::Manager *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180052038`
- `0x180052310`
- `0x180052778`

## callees

- `0x18004bf9c`
- `0x180052664`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005273c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005273c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800526e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800526e4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800526fa`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005271b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800526fa`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005271b`

## string_xrefs

- `0x180052745`: `Authorization reaper scheduled; due @ 0x%1!08x!%2!08x!.`

## pseudocode

```c
void __fastcall DeviceCastle::Library::Internal::Authorization::Manager::ScheduleReaper(
        DeviceCastle::Library::Internal::Authorization::Manager *this)
{
  __int64 v2; // rdx
  LONG v3; // eax
  FILETIME v4; // rcx
  struct _TP_TIMER *v5; // rcx
  FILETIME FileTime1; // [rsp+30h] [rbp-10h] BYREF
  FILETIME pftDueTime; // [rsp+60h] [rbp+20h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp+28h] BYREF
  FILETIME FileTime2; // [rsp+70h] [rbp+30h] BYREF
  struct _FILETIME v10; // [rsp+78h] [rbp+38h]

  FileTime1 = 0;
  pftDueTime = 0;
  FileTime2 = 0;
  if ( *((_QWORD *)this + 35) )
  {
    v2 = *(_QWORD *)(**((_QWORD **)this + 34) + 32LL);
    SystemTimeAsFileTime = *(struct _FILETIME *)(v2 + 192);
    v10 = SystemTimeAsFileTime;
    *(_QWORD *)&SystemTimeAsFileTime += *(_QWORD *)(v2 + 200);
    FileTime2 = SystemTimeAsFileTime;
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    FileTime1 = SystemTimeAsFileTime;
    v3 = CompareFileTime(&FileTime1, &FileTime2);
    v4 = 0;
    if ( v3 == -1 )
      v4 = FileTime2;
    pftDueTime = v4;
    if ( CompareFileTime(&pftDueTime, (const FILETIME *)this + 1) == -1 )
    {
      v5 = (struct _TP_TIMER *)*((_QWORD *)this + 3);
      *((FILETIME *)this + 1) = pftDueTime;
      SetThreadpoolTimer(v5, &pftDueTime, 0, 0);
      DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
        DeviceCastle::Library::Internal::g_pCastleInstance,
        5u,
        0,
        L"Authorization reaper scheduled; due @ 0x%1!08x!%2!08x!.",
        pftDueTime.dwHighDateTime,
        pftDueTime.dwLowDateTime);
    }
  }
  else
  {
    *((FILETIME *)this + 1) = FILETIME_MAX;
  }
}

```

## disassembly

```asm
0x180052664  push    rbp
0x180052666  push    rbx
0x180052667  push    rdi
0x180052668  mov     rbp, rsp
0x18005266b  sub     rsp, 40h
0x18005266f  xor     r8d, r8d
0x180052672  mov     rbx, rcx
0x180052675  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r8
0x180052679  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], r8
0x18005267d  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r8
0x180052681  cmp     [rcx+118h], r8
0x180052688  jnz     short loc_18005269A
0x18005268a  mov     rax, qword ptr cs:?FILETIME_MAX@@3U_FILETIME@@B.dwLowDateTime; _FILETIME const FILETIME_MAX ...
0x180052691  mov     [rcx+8], rax
0x180052695  jmp     loc_18005276A
0x18005269a  mov     rax, [rcx+110h]
0x1800526a1  mov     rcx, [rax]
0x1800526a4  mov     rdx, [rcx+20h]
0x1800526a8  mov     rcx, [rdx+0C0h]
0x1800526af  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800526b3  mov     eax, ecx
0x1800526b5  mov     dword ptr [rbp+arg_18], ecx
0x1800526b8  shr     rcx, 20h
0x1800526bc  mov     dword ptr [rbp+arg_18+4], ecx
0x1800526bf  mov     rcx, [rbp+arg_18]
0x1800526c3  add     rcx, [rdx+0C8h]
0x1800526ca  mov     [rbp+SystemTimeAsFileTime.dwLowDateTime], ecx
0x1800526cd  shr     rcx, 20h
0x1800526d1  mov     [rbp+SystemTimeAsFileTime.dwHighDateTime], ecx
0x1800526d4  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800526d8  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800526dc  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x1800526e0  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r8
0x1800526e4  call    cs:__imp_GetSystemTimeAsFileTime
0x1800526ea  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800526ee  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800526f2  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800526f6  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x1800526fa  call    cs:__imp_CompareFileTime
0x180052700  mov     rcx, cs:qword_1800AE490
0x180052707  lea     rdx, [rbx+8]; lpFileTime2
0x18005270b  cmp     eax, 0FFFFFFFFh
0x18005270e  cmovz   rcx, qword ptr [rbp+FileTime2.dwLowDateTime]
0x180052713  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rcx
0x180052717  lea     rcx, [rbp+pftDueTime]; lpFileTime1
0x18005271b  call    cs:__imp_CompareFileTime
0x180052721  cmp     eax, 0FFFFFFFFh
0x180052724  jnz     short loc_18005276A
0x180052726  mov     rax, qword ptr [rbp+pftDueTime.dwLowDateTime]
0x18005272a  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18005272e  mov     rcx, [rbx+18h]; pti
0x180052732  xor     r9d, r9d; msWindowLength
0x180052735  xor     r8d, r8d; msPeriod
0x180052738  mov     [rbx+8], rax
0x18005273c  call    cs:__imp_SetThreadpoolTimer
0x180052742  mov     eax, [rbp+pftDueTime.dwLowDateTime]
0x180052745  lea     r9, aAuthorizationR_0; "Authorization reaper scheduled; due @ 0"...
0x18005274c  mov     rcx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; this
0x180052753  xor     r8d, r8d; struct DeviceCastle::Library::CallerIdentity *
0x180052756  mov     [rsp+40h+var_18], eax
0x18005275a  mov     eax, [rbp+pftDueTime.dwHighDateTime]
0x18005275d  mov     [rsp+40h+var_20], eax
0x180052761  lea     edx, [r8+5]; unsigned int
0x180052765  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x18005276a  add     rsp, 40h
0x18005276e  pop     rdi
0x18005276f  pop     rbx
0x180052770  pop     rbp
0x180052771  retn
```
