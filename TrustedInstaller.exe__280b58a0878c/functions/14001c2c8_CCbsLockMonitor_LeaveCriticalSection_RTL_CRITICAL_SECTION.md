# CCbsLockMonitor::LeaveCriticalSection(_RTL_CRITICAL_SECTION *)

- ea: `0x14001c2c8`
- end: `0x14001c356`
- name: `?LeaveCriticalSection@CCbsLockMonitor@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z`
- size: `142`
- prototype: `void __fastcall(CCbsLockMonitor *__hidden this, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001c6c0`

## callees

- `0x140006778`
- `0x14000e2ac`
- `0x140016948`
- `0x14001bd3c`
- `0x14001c274`
- `0x14001c2c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c308`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c312`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c308`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c312`

## pseudocode

```c
void __fastcall CCbsLockMonitor::LeaveCriticalSection(CCbsLockMonitor *this, struct _RTL_CRITICAL_SECTION *a2)
{
  __int64 v3; // rcx
  __int64 LockInfo; // rax
  __int64 v5; // rdi
  _DWORD *v6; // rsi
  int v7; // ebx
  __int64 v8; // rcx
  _BYTE v10[40]; // [rsp+20h] [rbp-28h] BYREF
  CCbsLockMonitor *v11; // [rsp+50h] [rbp+8h] BYREF

  v11 = this;
  CritSecLocker::CritSecLocker((CritSecLocker *)v10, (struct AutoCritSec *)&stru_1400406D0, 1);
  LockInfo = FindLockInfo(v3, a2);
  v5 = LockInfo;
  if ( LockInfo )
  {
    v6 = (_DWORD *)(LockInfo + 80);
    v7 = *(_DWORD *)(LockInfo + 80);
    if ( v7 == GetCurrentThreadId() )
    {
      if ( (*(_DWORD *)(v5 + 84))-- == 1 )
        *v6 = 0;
    }
    else
    {
      LODWORD(v11) = GetCurrentThreadId();
      LogAdapter::TraceInfo<unsigned long,unsigned long>(v8, v6, &v11);
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  CritSecLocker::~CritSecLocker((CritSecLocker *)v10);
}

```

## disassembly

```asm
0x14001c2c8  mov     rax, rsp
0x14001c2cb  mov     [rax+10h], rbx
0x14001c2cf  mov     [rax+18h], rsi
0x14001c2d3  mov     [rax+8], rcx
0x14001c2d7  push    rdi
0x14001c2d8  sub     rsp, 40h
0x14001c2dc  mov     rbx, rdx
0x14001c2df  lea     rcx, [rax-28h]; this
0x14001c2e3  lea     rdx, stru_1400406D0; struct AutoCritSec *
0x14001c2ea  mov     r8b, 1; bool
0x14001c2ed  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x14001c2f2  mov     rdx, rbx
0x14001c2f5  call    FindLockInfo
0x14001c2fa  mov     rdi, rax
0x14001c2fd  test    rax, rax
0x14001c300  jz      short loc_14001C33C
0x14001c302  lea     rsi, [rax+50h]
0x14001c306  mov     ebx, [rsi]
0x14001c308  call    cs:__imp_GetCurrentThreadId
0x14001c30e  cmp     ebx, eax
0x14001c310  jz      short loc_14001C330
0x14001c312  call    cs:__imp_GetCurrentThreadId
0x14001c318  lea     r8, [rsp+48h+arg_0]
0x14001c31d  mov     rdx, rsi
0x14001c320  mov     dword ptr [rsp+48h+arg_0], eax
0x14001c324  call    ??$TraceInfo@KK@LogAdapter@@YAXQEBDAEBK1@Z; LogAdapter::TraceInfo<ulong,ulong>(char const * const,ulong const &,ulong const &)
0x14001c329  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001c32e  jmp     short loc_14001C33C
0x14001c330  add     dword ptr [rdi+54h], 0FFFFFFFFh
0x14001c334  jnz     short loc_14001C33C
0x14001c336  mov     dword ptr [rsi], 0
0x14001c33c  lea     rcx, [rsp+48h+var_28]; this
0x14001c341  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x14001c346  mov     rbx, [rsp+48h+arg_8]
0x14001c34b  mov     rsi, [rsp+48h+arg_10]
0x14001c350  add     rsp, 40h
0x14001c354  pop     rdi
0x14001c355  retn
```
