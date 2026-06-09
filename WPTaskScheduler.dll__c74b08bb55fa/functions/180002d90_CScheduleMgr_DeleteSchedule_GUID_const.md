# CScheduleMgr::DeleteSchedule(_GUID const *)

- ea: `0x180002d90`
- end: `0x180002ef6`
- name: `?DeleteSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(CScheduleMgr *this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002c80`

## callees

- `0x180001ef0`
- `0x180002010`
- `0x180002d90`
- `0x18000f7cc`
- `0x180017370`
- `0x180019cec`
- `0x180022010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002e9b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002e9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002da4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002da4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002eaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ec8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002eaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ec8`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::DeleteSchedule(CScheduleMgr *this, const struct _GUID *a2)
{
  __int64 v3; // rbx
  void *v4; // rcx
  __int64 v5; // rax
  unsigned int v6; // edi
  _QWORD *v7; // rax
  __int64 v8; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rsi
  __int64 v13; // rcx

  EnterCriticalSection(&CriticalSection);
  v3 = g_ScheduleMgr;
  v4 = &g_ScheduleMgr;
  while ( 1 )
  {
    if ( (_UNKNOWN *)v3 == &g_ScheduleMgr )
    {
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x20) != 0 )
        McTemplateU0j_EventWriteTransfer(&g_ScheduleMgr, ScheduleNotFoundWarning, a2);
      v3 = 0;
      goto LABEL_10;
    }
    v5 = *(_QWORD *)(v3 + 16) - *(_QWORD *)&a2->Data1;
    if ( !v5 )
      v5 = *(_QWORD *)(v3 + 24) - *(_QWORD *)a2->Data4;
    if ( !v5 )
      break;
    v3 = *(_QWORD *)v3;
  }
  if ( !v3 )
  {
LABEL_10:
    if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x20) != 0 )
      McTemplateU0j_EventWriteTransfer(v4, ScheduleNotFoundWarning, a2);
    v6 = -2100362994;
    goto LABEL_15;
  }
  v7 = *(_QWORD **)(v3 + 8);
  v6 = 0;
  v8 = *(_QWORD *)v3;
  *v7 = *(_QWORD *)v3;
  *(_QWORD *)(v8 + 8) = v7;
  if ( (*(_BYTE *)(v3 + 44) & 1) != 0 )
  {
    v6 = TaskStore::Delete((TaskStore *)&g_ScheduleMgr, a2);
    LeaveCriticalSection(&CriticalSection);
    goto LABEL_17;
  }
LABEL_15:
  LeaveCriticalSection(&CriticalSection);
  if ( !v3 )
    return v6;
LABEL_17:
  EnterCriticalSection(&CScheduleMgr::CritLockExpired);
  if ( (byte_180030D09 & 0x10) != 0 )
    McTemplateU0zj_EventWriteTransfer(v11, v10, *(_QWORD *)(v3 + 32), v3 + 16);
  v12 = _InterlockedExchange64((volatile __int64 *)&DeletingSchedule, v3);
  v13 = *(_QWORD *)(v3 + 216);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
  CSchedule::Deinitialize((CSchedule *)v3);
  CSchedule::~CSchedule((CSchedule *)v3);
  operator delete((void *)v3);
  _InterlockedExchange64((volatile __int64 *)&DeletingSchedule, v12);
  LeaveCriticalSection(&CScheduleMgr::CritLockExpired);
  return v6;
}

```

## disassembly

```asm
0x180002d90  mov     [rsp+arg_8], rbx
0x180002d95  push    rsi
0x180002d96  sub     rsp, 20h
0x180002d9a  lea     rcx, CriticalSection; lpCriticalSection
0x180002da1  mov     rsi, rdx
0x180002da4  call    cs:__imp_EnterCriticalSection
0x180002daa  mov     rbx, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180002db1  lea     rcx, ?g_ScheduleMgr@@3VCScheduleMgr@@A; this
0x180002db8  mov     [rsp+28h+arg_0], rdi
0x180002dbd  cmp     rbx, rcx
0x180002dc0  jz      short loc_180002DDD
0x180002dc2  mov     rax, [rbx+10h]
0x180002dc6  sub     rax, [rsi]
0x180002dc9  jnz     short loc_180002DD3
0x180002dcb  mov     rax, [rbx+18h]
0x180002dcf  sub     rax, [rsi+8]
0x180002dd3  test    rax, rax
0x180002dd6  jz      short loc_180002E0D
0x180002dd8  mov     rbx, [rbx]
0x180002ddb  jmp     short loc_180002DBD
0x180002ddd  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 20h
0x180002de4  jnz     loc_180002ED0
0x180002dea  xor     edi, edi
0x180002dec  mov     ebx, edi
0x180002dee  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 20h
0x180002df5  jz      short loc_180002E06
0x180002df7  mov     r8, rsi
0x180002dfa  lea     rdx, ScheduleNotFoundWarning
0x180002e01  call    McTemplateU0j_EventWriteTransfer
0x180002e06  mov     edi, 82CF010Eh
0x180002e0b  jmp     short loc_180002E2C
0x180002e0d  test    rbx, rbx
0x180002e10  jz      short loc_180002DEE
0x180002e12  mov     rax, [rbx+8]
0x180002e16  xor     edi, edi
0x180002e18  mov     rdx, [rbx]
0x180002e1b  mov     [rax], rdx
0x180002e1e  mov     [rdx+8], rax
0x180002e22  test    byte ptr [rbx+2Ch], 1
0x180002e26  jnz     loc_180002EB7
0x180002e2c  lea     rcx, CriticalSection; lpCriticalSection
0x180002e33  call    cs:__imp_LeaveCriticalSection
0x180002e39  test    rbx, rbx
0x180002e3c  jnz     short loc_180002E50
0x180002e3e  mov     rbx, [rsp+28h+arg_8]
0x180002e43  mov     eax, edi
0x180002e45  mov     rdi, [rsp+28h+arg_0]
0x180002e4a  add     rsp, 20h
0x180002e4e  pop     rsi
0x180002e4f  retn
0x180002e50  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002e57  call    cs:__imp_EnterCriticalSection
0x180002e5d  test    cs:byte_180030D09, 10h
0x180002e64  jnz     short loc_180002EE4
0x180002e66  mov     rsi, rbx
0x180002e69  xchg    rsi, cs:?DeletingSchedule@@3PEAVCSchedule@@EA; CSchedule * DeletingSchedule
0x180002e70  mov     rcx, [rbx+0D8h]
0x180002e77  test    rcx, rcx
0x180002e7a  jz      short loc_180002E88
0x180002e7c  mov     rax, [rcx]
0x180002e7f  mov     rax, [rax+18h]
0x180002e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e88  mov     rcx, rbx; this
0x180002e8b  call    ?Deinitialize@CSchedule@@QEAAXXZ; CSchedule::Deinitialize(void)
0x180002e90  mov     rcx, rbx; this
0x180002e93  call    ??1CSchedule@@QEAA@XZ; CSchedule::~CSchedule(void)
0x180002e98  mov     rcx, rbx
0x180002e9b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002ea1  xchg    rsi, cs:?DeletingSchedule@@3PEAVCSchedule@@EA; CSchedule * DeletingSchedule
0x180002ea8  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002eaf  call    cs:__imp_LeaveCriticalSection
0x180002eb5  jmp     short loc_180002E3E
0x180002eb7  mov     rdx, rsi; struct _GUID *
0x180002eba  call    ?Delete@TaskStore@@QEAAJAEBU_GUID@@@Z; TaskStore::Delete(_GUID const &)
0x180002ebf  lea     rcx, CriticalSection; lpCriticalSection
0x180002ec6  mov     edi, eax
0x180002ec8  call    cs:__imp_LeaveCriticalSection
0x180002ece  jmp     short loc_180002E50
0x180002ed0  mov     r8, rsi
0x180002ed3  lea     rdx, ScheduleNotFoundWarning
0x180002eda  call    McTemplateU0j_EventWriteTransfer
0x180002edf  jmp     loc_180002DEA
0x180002ee4  mov     r8, [rbx+20h]
0x180002ee8  lea     r9, [rbx+10h]
0x180002eec  call    McTemplateU0zj_EventWriteTransfer
0x180002ef1  jmp     loc_180002E66
```
