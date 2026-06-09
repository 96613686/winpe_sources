# CCbsLockMonitor::EnterCriticalSection(_RTL_CRITICAL_SECTION *,int)

- ea: `0x1400165a8`
- end: `0x1400166b3`
- name: `?EnterCriticalSection@CCbsLockMonitor@@QEAAXPEAU_RTL_CRITICAL_SECTION@@H@Z`
- size: `267`
- prototype: `void __fastcall(CCbsLockMonitor *__hidden this, struct _RTL_CRITICAL_SECTION *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140008860`
- `0x1400167b0`
- `0x140016b90`

## callees

- `0x140009118`
- `0x1400091b4`
- `0x14000d81c`
- `0x1400160a8`
- `0x1400160d4`
- `0x140016374`
- `0x1400165a8`
- `0x1400166bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400165e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001661d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400165e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001661d`

## pseudocode

```c
void __fastcall CCbsLockMonitor::EnterCriticalSection(CCbsLockMonitor *this, struct _RTL_CRITICAL_SECTION *a2, int a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 LockInfo; // rsi
  DWORD CurrentThreadId; // eax
  unsigned __int64 i; // rdi
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rdx
  _DWORD *v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // r9
  __int64 v21; // rax
  __int64 v22; // rcx
  _BYTE v23[40]; // [rsp+30h] [rbp-28h] BYREF

  CritSecLocker::CritSecLocker((CritSecLocker *)v23, (struct AutoCritSec *)&stru_140053560, 1);
  LockInfo = FindLockInfo(v5, a2);
  if ( LockInfo )
  {
    if ( a3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      ++*(_DWORD *)(LockInfo + 84);
      *(_DWORD *)(LockInfo + 80) = CurrentThreadId;
    }
    if ( *(_DWORD *)(LockInfo + 84) == 1 || !a3 )
    {
      for ( i = 0; i < qword_140053538; ++i )
      {
        v10 = *(_DWORD *)(CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](v6, i) + 80);
        if ( v10 == GetCurrentThreadId() && LockInfo != CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](v6, i) )
        {
          v12 = CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](v6, v11);
          if ( *v14 < *(_DWORD *)(v12 + 64) )
          {
            CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](v6, v13);
            v17 = CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](v16, v15);
            LogAdapter::TraceInfo<wchar_t [32],unsigned int,wchar_t [32],unsigned int>(v18, v17, v19, LockInfo, v20);
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          if ( dword_140053730 )
          {
            v21 = CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](v6, i);
            LogAdapter::TraceInfo<wchar_t [32],wchar_t [32]>(v22, v21, LockInfo);
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
        }
      }
    }
  }
  CritSecLocker::~CritSecLocker((CritSecLocker *)v23);
}

```

## disassembly

```asm
0x1400165a8  mov     [rsp+arg_0], rbx
0x1400165ad  mov     [rsp+arg_8], rsi
0x1400165b2  push    rdi
0x1400165b3  sub     rsp, 50h
0x1400165b7  mov     edi, r8d
0x1400165ba  lea     rcx, [rsp+58h+var_28]; this
0x1400165bf  mov     rbx, rdx
0x1400165c2  mov     r8b, 1; bool
0x1400165c5  lea     rdx, stru_140053560; struct AutoCritSec *
0x1400165cc  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1400165d1  mov     rdx, rbx
0x1400165d4  call    FindLockInfo
0x1400165d9  mov     rsi, rax
0x1400165dc  test    rax, rax
0x1400165df  jz      loc_140016699
0x1400165e5  test    edi, edi
0x1400165e7  jz      short loc_1400165F5
0x1400165e9  call    cs:__imp_GetCurrentThreadId
0x1400165ef  inc     dword ptr [rsi+54h]
0x1400165f2  mov     [rsi+50h], eax
0x1400165f5  cmp     dword ptr [rsi+54h], 1
0x1400165f9  jz      short loc_140016603
0x1400165fb  test    edi, edi
0x1400165fd  jnz     loc_140016699
0x140016603  xor     edi, edi
0x140016605  cmp     cs:qword_140053538, rdi
0x14001660c  jbe     loc_140016699
0x140016612  mov     rdx, rdi
0x140016615  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001661a  mov     ebx, [rax+50h]
0x14001661d  call    cs:__imp_GetCurrentThreadId
0x140016623  cmp     ebx, eax
0x140016625  jnz     short loc_140016689
0x140016627  mov     rdx, rdi
0x14001662a  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001662f  cmp     rsi, rax
0x140016632  jz      short loc_140016689
0x140016634  lea     r9, [rsi+40h]
0x140016638  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001663d  mov     eax, [rax+40h]
0x140016640  cmp     [r9], eax
0x140016643  jnb     short loc_140016668
0x140016645  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001664a  lea     r8, [rax+40h]
0x14001664e  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x140016653  mov     [rsp+58h+var_38], r9
0x140016658  mov     rdx, rax
0x14001665b  mov     r9, rsi
0x14001665e  call    ??$TraceInfo@$$BY0CA@_WI$$BY0CA@_WI@LogAdapter@@YAXQEBDAEAY0CA@$$CB_WAEBI12@Z; LogAdapter::TraceInfo<wchar_t [32],uint,wchar_t [32],uint>(char const * const,wchar_t const (&)[32],uint const &,wchar_t const (&)[32],uint const &)
0x140016663  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140016668  cmp     cs:dword_140053730, 0
0x14001666f  jz      short loc_140016689
0x140016671  mov     rdx, rdi
0x140016674  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x140016679  mov     rdx, rax
0x14001667c  mov     r8, rsi
0x14001667f  call    ??$TraceInfo@$$BY0CA@_W$$BY0CA@_W@LogAdapter@@YAXQEBDAEAY0CA@$$CB_W1@Z; LogAdapter::TraceInfo<wchar_t [32],wchar_t [32]>(char const * const,wchar_t const (&)[32],wchar_t const (&)[32])
0x140016684  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140016689  inc     rdi
0x14001668c  cmp     rdi, cs:qword_140053538
0x140016693  jb      loc_140016612
0x140016699  lea     rcx, [rsp+58h+var_28]; this
0x14001669e  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1400166a3  mov     rbx, [rsp+58h+arg_0]
0x1400166a8  mov     rsi, [rsp+58h+arg_8]
0x1400166ad  add     rsp, 50h
0x1400166b1  pop     rdi
0x1400166b2  retn
```
