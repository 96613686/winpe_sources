# CScheduleMgr::GetSchedule(_GUID const *,_TASK_SCHEDULE * *,_TASK_STATISTICS * *,_TASK_RUNTIME_DATA * *)

- ea: `0x1800192ec`
- end: `0x180019395`
- name: `?GetSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@PEAPEAU_TASK_RUNTIME_DATA@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(CScheduleMgr *__hidden this, const struct _GUID *, struct _TASK_SCHEDULE **, struct _TASK_STATISTICS **, struct _TASK_RUNTIME_DATA **)`
- caller_count: `7`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180001bd0`
- `0x180018dac`
- `0x18001910c`
- `0x18001f3ec`
- `0x18001f65c`
- `0x18001f7e0`
- `0x18001f87c`

## callees

- `0x180005c30`
- `0x18000d7f0`
- `0x180017e48`
- `0x1800192ec`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001932d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001932d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001936b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001936b`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::GetSchedule(
        CScheduleMgr *this,
        const struct _GUID *a2,
        struct _TASK_SCHEDULE **a3,
        struct _TASK_STATISTICS **a4,
        struct _TASK_RUNTIME_DATA **a5)
{
  unsigned int v9; // esi
  CSchedule *Schedule; // rax
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+30h] [rbp-158h] BYREF

  v9 = -2100362994;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  TimeInfo::TimeInfo(&TimeZoneInformation);
  Schedule = CScheduleMgr::FindSchedule(this, a2);
  if ( Schedule )
    v9 = CSchedule::GetSchedule(Schedule, (const struct TimeInfo *)&TimeZoneInformation, a3, a4, a5);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v9;
}

```

## disassembly

```asm
0x1800192ec  push    rbx
0x1800192ee  push    rbp
0x1800192ef  push    rsi
0x1800192f0  push    rdi
0x1800192f1  push    r12
0x1800192f3  push    r14
0x1800192f5  push    r15
0x1800192f7  sub     rsp, 150h
0x1800192fe  mov     rax, cs:__security_cookie
0x180019305  xor     rax, rsp
0x180019308  mov     [rsp+188h+var_48], rax
0x180019310  mov     r12, [rsp+188h+arg_20]
0x180019318  mov     rbx, rcx
0x18001931b  add     rcx, 10h; lpCriticalSection
0x18001931f  mov     r15, r9
0x180019322  mov     r14, r8
0x180019325  mov     rdi, rdx
0x180019328  mov     esi, 82CF010Eh
0x18001932d  call    cs:__imp_EnterCriticalSection
0x180019333  lea     rcx, [rsp+188h+TimeZoneInformation]; lpTimeZoneInformation
0x180019338  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x18001933d  mov     rdx, rdi; struct _GUID *
0x180019340  mov     rcx, rbx; this
0x180019343  call    ?FindSchedule@CScheduleMgr@@QEAAPEAVCSchedule@@PEBU_GUID@@@Z; CScheduleMgr::FindSchedule(_GUID const *)
0x180019348  test    rax, rax
0x18001934b  jz      short loc_180019367
0x18001934d  mov     r9, r15; struct _TASK_STATISTICS **
0x180019350  mov     [rsp+188h+var_168], r12; struct _TASK_RUNTIME_DATA **
0x180019355  mov     r8, r14; struct _TASK_SCHEDULE **
0x180019358  lea     rdx, [rsp+188h+TimeZoneInformation]; struct TimeInfo *
0x18001935d  mov     rcx, rax; this
0x180019360  call    ?GetSchedule@CSchedule@@QEAAJAEBVTimeInfo@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@PEAPEAU_TASK_RUNTIME_DATA@@@Z; CSchedule::GetSchedule(TimeInfo const &,_TASK_SCHEDULE * *,_TASK_STATISTICS * *,_TASK_RUNTIME_DATA * *)
0x180019365  mov     esi, eax
0x180019367  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001936b  call    cs:__imp_LeaveCriticalSection
0x180019371  mov     eax, esi
0x180019373  mov     rcx, [rsp+188h+var_48]
0x18001937b  xor     rcx, rsp; StackCookie
0x18001937e  call    __security_check_cookie
0x180019383  add     rsp, 150h
0x18001938a  pop     r15
0x18001938c  pop     r14
0x18001938e  pop     r12
0x180019390  pop     rdi
0x180019391  pop     rsi
0x180019392  pop     rbp
0x180019393  pop     rbx
0x180019394  retn
```
