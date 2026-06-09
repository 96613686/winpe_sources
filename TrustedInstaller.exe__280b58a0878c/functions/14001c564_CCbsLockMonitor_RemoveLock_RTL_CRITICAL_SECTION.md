# CCbsLockMonitor::RemoveLock(_RTL_CRITICAL_SECTION *)

- ea: `0x14001c564`
- end: `0x14001c5f3`
- name: `?RemoveLock@CCbsLockMonitor@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z`
- size: `143`
- prototype: `void __fastcall(CCbsLockMonitor *__hidden this, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14001bee0`
- `0x14001c0f4`

## callees

- `0x140006778`
- `0x14000e2ac`
- `0x140016948`
- `0x14001bd0c`
- `0x14001bf30`
- `0x14001c4e4`
- `0x14001c564`

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
  CritSecLocker::CritSecLocker((CritSecLocker *)v12, (struct AutoCritSec *)&stru_1400406D0, 1);
  for ( i = 0; i < qword_1400406A8; ++i )
  {
    if ( *(struct _RTL_CRITICAL_SECTION **)(CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](v3, i) + 72) == a2 )
    {
      v13 = (CCbsLockMonitor *)qword_1400406A8;
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
0x14001c564  mov     [rsp+arg_8], rbx
0x14001c569  mov     [rsp+arg_0], rcx
0x14001c56e  push    rdi
0x14001c56f  sub     rsp, 40h
0x14001c573  mov     rdi, rdx
0x14001c576  lea     rcx, [rsp+48h+var_28]; this
0x14001c57b  lea     rdx, stru_1400406D0; struct AutoCritSec *
0x14001c582  mov     r8b, 1; bool
0x14001c585  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x14001c58a  xor     ebx, ebx
0x14001c58c  cmp     rbx, cs:qword_1400406A8
0x14001c593  jnb     short loc_14001C5D9
0x14001c595  mov     rdx, rbx
0x14001c598  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001c59d  cmp     [rax+48h], rdi
0x14001c5a1  jz      short loc_14001C5A8
0x14001c5a3  inc     rbx
0x14001c5a6  jmp     short loc_14001C58C
0x14001c5a8  mov     rax, cs:qword_1400406A8
0x14001c5af  mov     [rsp+48h+arg_0], rax
0x14001c5b4  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001c5b9  lea     r8, [rax+40h]
0x14001c5bd  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001c5c2  mov     rdx, rax
0x14001c5c5  lea     r9, [rsp+48h+arg_0]
0x14001c5ca  call    ??$TraceInfo@$$BY0CA@_WI_K@LogAdapter@@YAXQEBDAEAY0CA@$$CB_WAEBIAEB_K@Z; LogAdapter::TraceInfo<wchar_t [32],uint,unsigned __int64>(char const * const,wchar_t const (&)[32],uint const &,unsigned __int64 const &)
0x14001c5cf  mov     rdx, rbx
0x14001c5d2  call    ?RemoveAt@?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAJ_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::RemoveAt(unsigned __int64)
0x14001c5d7  jmp     short loc_14001C5DE
0x14001c5d9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001c5de  lea     rcx, [rsp+48h+var_28]; this
0x14001c5e3  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x14001c5e8  mov     rbx, [rsp+48h+arg_8]
0x14001c5ed  add     rsp, 40h
0x14001c5f1  pop     rdi
0x14001c5f2  retn
```
