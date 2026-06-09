# CCbsLockMonitor::RemoveLock(_RTL_CRITICAL_SECTION *)

- ea: `0x140016af8`
- end: `0x140016b87`
- name: `?RemoveLock@CCbsLockMonitor@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z`
- size: `143`
- prototype: `void __fastcall(CCbsLockMonitor *__hidden this, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140016324`

## callees

- `0x140009118`
- `0x1400091b4`
- `0x14000d81c`
- `0x14001610c`
- `0x140016374`
- `0x140016a78`
- `0x140016af8`

## pseudocode

```c
void __fastcall CCbsLockMonitor::RemoveLock(CCbsLockMonitor *this, struct _RTL_CRITICAL_SECTION *a2)
{
  __int64 v3; // rcx
  unsigned __int64 i; // rbx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  _BYTE v12[40]; // [rsp+20h] [rbp-28h] BYREF
  CCbsLockMonitor *v13; // [rsp+50h] [rbp+8h] BYREF

  v13 = this;
  CritSecLocker::CritSecLocker((CritSecLocker *)v12, (struct AutoCritSec *)&stru_140053560, 1);
  for ( i = 0; i < qword_140053538; ++i )
  {
    if ( *(struct _RTL_CRITICAL_SECTION **)(CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](v3, i) + 72) == a2 )
    {
      v13 = (CCbsLockMonitor *)qword_140053538;
      CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](v3, v5);
      v8 = CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](v7, v6);
      LogAdapter::TraceInfo<wchar_t [32],unsigned int,unsigned __int64>(v9, v8, v10, &v13);
      CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::RemoveAt(v11, i);
      goto LABEL_7;
    }
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_7:
  CritSecLocker::~CritSecLocker((CritSecLocker *)v12);
}

```

## disassembly

```asm
0x140016af8  mov     [rsp+arg_8], rbx
0x140016afd  mov     [rsp+arg_0], rcx
0x140016b02  push    rdi
0x140016b03  sub     rsp, 40h
0x140016b07  mov     rdi, rdx
0x140016b0a  lea     rcx, [rsp+48h+var_28]; this
0x140016b0f  lea     rdx, stru_140053560; struct AutoCritSec *
0x140016b16  mov     r8b, 1; bool
0x140016b19  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x140016b1e  xor     ebx, ebx
0x140016b20  cmp     rbx, cs:qword_140053538
0x140016b27  jnb     short loc_140016B6D
0x140016b29  mov     rdx, rbx
0x140016b2c  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x140016b31  cmp     [rax+48h], rdi
0x140016b35  jz      short loc_140016B3C
0x140016b37  inc     rbx
0x140016b3a  jmp     short loc_140016B20
0x140016b3c  mov     rax, cs:qword_140053538
0x140016b43  mov     [rsp+48h+arg_0], rax
0x140016b48  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x140016b4d  lea     r8, [rax+40h]
0x140016b51  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x140016b56  mov     rdx, rax
0x140016b59  lea     r9, [rsp+48h+arg_0]
0x140016b5e  call    ??$TraceInfo@$$BY0CA@_WI_K@LogAdapter@@YAXQEBDAEAY0CA@$$CB_WAEBIAEB_K@Z; LogAdapter::TraceInfo<wchar_t [32],uint,unsigned __int64>(char const * const,wchar_t const (&)[32],uint const &,unsigned __int64 const &)
0x140016b63  mov     rdx, rbx
0x140016b66  call    ?RemoveAt@?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAJ_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::RemoveAt(unsigned __int64)
0x140016b6b  jmp     short loc_140016B72
0x140016b6d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140016b72  lea     rcx, [rsp+48h+var_28]; this
0x140016b77  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x140016b7c  mov     rbx, [rsp+48h+arg_8]
0x140016b81  add     rsp, 40h
0x140016b85  pop     rdi
0x140016b86  retn
```
