# CScheduleMgr::SetStatistics(_GUID const *,_TASK_STATISTICS *)

- ea: `0x180019610`
- end: `0x1800196d7`
- name: `?SetStatistics@CScheduleMgr@@QEAAJPEBU_GUID@@PEAU_TASK_STATISTICS@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(CScheduleMgr *__hidden this, const struct _GUID *, struct _TASK_STATISTICS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001efc8`

## callees

- `0x180005c30`
- `0x18000d7f0`
- `0x18000ea40`
- `0x180018158`
- `0x180019610`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019647`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019647`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019682`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019682`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::SetStatistics(CScheduleMgr *this, const struct _GUID *a2, struct _TASK_STATISTICS *a3)
{
  unsigned int v6; // ebx
  CSchedule *Schedule; // rax
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+30h] [rbp-158h] BYREF
  _BYTE v10[16]; // [rsp+140h] [rbp-48h] BYREF

  if ( a3 && a2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    TimeInfo::TimeInfo(&TimeZoneInformation);
    v6 = -2100362994;
    Schedule = CScheduleMgr::FindSchedule((struct CSchedule **)this, a2);
    if ( Schedule )
      v6 = CSchedule::SetStatistics(Schedule, (const struct TimeInfo *)&TimeZoneInformation, a3);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    return v6;
  }
  else
  {
    if ( (byte_180030D04 & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(this, ErrorNullPointer, a3, 1, v10);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180019610  push    rbx
0x180019612  push    rbp
0x180019613  push    rsi
0x180019614  push    rdi
0x180019615  push    r14
0x180019617  sub     rsp, 160h
0x18001961e  mov     rax, cs:__security_cookie
0x180019625  xor     rax, rsp
0x180019628  mov     [rsp+188h+var_38], rax
0x180019630  mov     rbp, r8
0x180019633  mov     rdi, rdx
0x180019636  mov     r14, rcx
0x180019639  test    r8, r8
0x18001963c  jz      short loc_18001968C
0x18001963e  test    rdx, rdx
0x180019641  jz      short loc_18001968C
0x180019643  add     rcx, 10h; lpCriticalSection
0x180019647  call    cs:__imp_EnterCriticalSection
0x18001964d  lea     rcx, [rsp+188h+TimeZoneInformation]; lpTimeZoneInformation
0x180019652  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x180019657  mov     rdx, rdi; struct _GUID *
0x18001965a  mov     rcx, r14; this
0x18001965d  mov     ebx, 82CF010Eh
0x180019662  call    ?FindSchedule@CScheduleMgr@@QEAAPEAVCSchedule@@PEBU_GUID@@@Z; CScheduleMgr::FindSchedule(_GUID const *)
0x180019667  test    rax, rax
0x18001966a  jz      short loc_18001967E
0x18001966c  mov     r8, rbp; struct _TASK_STATISTICS *
0x18001966f  lea     rdx, [rsp+188h+TimeZoneInformation]; struct TimeInfo *
0x180019674  mov     rcx, rax; this
0x180019677  call    ?SetStatistics@CSchedule@@QEAAJAEBVTimeInfo@@PEAU_TASK_STATISTICS@@@Z; CSchedule::SetStatistics(TimeInfo const &,_TASK_STATISTICS *)
0x18001967c  mov     ebx, eax
0x18001967e  lea     rcx, [r14+10h]; lpCriticalSection
0x180019682  call    cs:__imp_LeaveCriticalSection
0x180019688  mov     eax, ebx
0x18001968a  jmp     short loc_1800196B9
0x18001968c  mov     r9d, 1
0x180019692  test    cs:byte_180030D04, r9b
0x180019699  jz      short loc_1800196B4
0x18001969b  lea     rax, [rsp+188h+var_48]
0x1800196a3  lea     rdx, ErrorNullPointer
0x1800196aa  mov     [rsp+188h+var_168], rax
0x1800196af  call    McGenEventWrite_EventWriteTransfer
0x1800196b4  mov     eax, 80004003h
0x1800196b9  mov     rcx, [rsp+188h+var_38]
0x1800196c1  xor     rcx, rsp; StackCookie
0x1800196c4  call    __security_check_cookie
0x1800196c9  add     rsp, 160h
0x1800196d0  pop     r14
0x1800196d2  pop     rdi
0x1800196d3  pop     rsi
0x1800196d4  pop     rbp
0x1800196d5  pop     rbx
0x1800196d6  retn
```
