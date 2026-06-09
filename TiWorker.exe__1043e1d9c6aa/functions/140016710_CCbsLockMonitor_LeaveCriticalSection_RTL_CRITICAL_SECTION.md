# CCbsLockMonitor::LeaveCriticalSection(_RTL_CRITICAL_SECTION *)

- ea: `0x140016710`
- end: `0x14001679e`
- name: `?LeaveCriticalSection@CCbsLockMonitor@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z`
- size: `142`
- prototype: `void __fastcall(CCbsLockMonitor *__hidden this, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140008be0`
- `0x14000cd48`
- `0x140016bd0`

## callees

- `0x140009118`
- `0x1400091b4`
- `0x14000d81c`
- `0x14001613c`
- `0x1400166bc`
- `0x140016710`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016750`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001675a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140016750`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001675a`

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
  CritSecLocker::CritSecLocker((CritSecLocker *)v10, (struct AutoCritSec *)&stru_140053560, 1);
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
0x140016710  mov     rax, rsp
0x140016713  mov     [rax+10h], rbx
0x140016717  mov     [rax+18h], rsi
0x14001671b  mov     [rax+8], rcx
0x14001671f  push    rdi
0x140016720  sub     rsp, 40h
0x140016724  mov     rbx, rdx
0x140016727  lea     rcx, [rax-28h]; this
0x14001672b  lea     rdx, stru_140053560; struct AutoCritSec *
0x140016732  mov     r8b, 1; bool
0x140016735  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x14001673a  mov     rdx, rbx
0x14001673d  call    FindLockInfo
0x140016742  mov     rdi, rax
0x140016745  test    rax, rax
0x140016748  jz      short loc_140016784
0x14001674a  lea     rsi, [rax+50h]
0x14001674e  mov     ebx, [rsi]
0x140016750  call    cs:__imp_GetCurrentThreadId
0x140016756  cmp     ebx, eax
0x140016758  jz      short loc_140016778
0x14001675a  call    cs:__imp_GetCurrentThreadId
0x140016760  lea     r8, [rsp+48h+arg_0]
0x140016765  mov     rdx, rsi
0x140016768  mov     dword ptr [rsp+48h+arg_0], eax
0x14001676c  call    ??$TraceInfo@KK@LogAdapter@@YAXQEBDAEBK1@Z; LogAdapter::TraceInfo<ulong,ulong>(char const * const,ulong const &,ulong const &)
0x140016771  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140016776  jmp     short loc_140016784
0x140016778  add     dword ptr [rdi+54h], 0FFFFFFFFh
0x14001677c  jnz     short loc_140016784
0x14001677e  mov     dword ptr [rsi], 0
0x140016784  lea     rcx, [rsp+48h+var_28]; this
0x140016789  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x14001678e  mov     rbx, [rsp+48h+arg_8]
0x140016793  mov     rsi, [rsp+48h+arg_10]
0x140016798  add     rsp, 40h
0x14001679c  pop     rdi
0x14001679d  retn
```
