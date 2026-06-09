# CCbsLockMonitor::EnterCriticalSection(_RTL_CRITICAL_SECTION *,int)

- ea: `0x14001c160`
- end: `0x14001c26b`
- name: `?EnterCriticalSection@CCbsLockMonitor@@QEAAXPEAU_RTL_CRITICAL_SECTION@@H@Z`
- size: `267`
- prototype: `void __fastcall(CCbsLockMonitor *__hidden this, struct _RTL_CRITICAL_SECTION *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001c360`
- `0x14001c680`

## callees

- `0x140006778`
- `0x14000e2ac`
- `0x140016948`
- `0x14001bca8`
- `0x14001bcd4`
- `0x14001bf30`
- `0x14001c160`
- `0x14001c274`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c1a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c1d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c1a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c1d5`

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

  CritSecLocker::CritSecLocker((CritSecLocker *)v23, (struct AutoCritSec *)&stru_1400406D0, 1);
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
      for ( i = 0; i < qword_1400406A8; ++i )
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
          if ( dword_1400408D0 )
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
0x14001c160  mov     [rsp+arg_0], rbx
0x14001c165  mov     [rsp+arg_8], rsi
0x14001c16a  push    rdi
0x14001c16b  sub     rsp, 50h
0x14001c16f  mov     edi, r8d
0x14001c172  lea     rcx, [rsp+58h+var_28]; this
0x14001c177  mov     rbx, rdx
0x14001c17a  mov     r8b, 1; bool
0x14001c17d  lea     rdx, stru_1400406D0; struct AutoCritSec *
0x14001c184  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x14001c189  mov     rdx, rbx
0x14001c18c  call    FindLockInfo
0x14001c191  mov     rsi, rax
0x14001c194  test    rax, rax
0x14001c197  jz      loc_14001C251
0x14001c19d  test    edi, edi
0x14001c19f  jz      short loc_14001C1AD
0x14001c1a1  call    cs:__imp_GetCurrentThreadId
0x14001c1a7  inc     dword ptr [rsi+54h]
0x14001c1aa  mov     [rsi+50h], eax
0x14001c1ad  cmp     dword ptr [rsi+54h], 1
0x14001c1b1  jz      short loc_14001C1BB
0x14001c1b3  test    edi, edi
0x14001c1b5  jnz     loc_14001C251
0x14001c1bb  xor     edi, edi
0x14001c1bd  cmp     cs:qword_1400406A8, rdi
0x14001c1c4  jbe     loc_14001C251
0x14001c1ca  mov     rdx, rdi
0x14001c1cd  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001c1d2  mov     ebx, [rax+50h]
0x14001c1d5  call    cs:__imp_GetCurrentThreadId
0x14001c1db  cmp     ebx, eax
0x14001c1dd  jnz     short loc_14001C241
0x14001c1df  mov     rdx, rdi
0x14001c1e2  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001c1e7  cmp     rsi, rax
0x14001c1ea  jz      short loc_14001C241
0x14001c1ec  lea     r9, [rsi+40h]
0x14001c1f0  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001c1f5  mov     eax, [rax+40h]
0x14001c1f8  cmp     [r9], eax
0x14001c1fb  jnb     short loc_14001C220
0x14001c1fd  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001c202  lea     r8, [rax+40h]
0x14001c206  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001c20b  mov     [rsp+58h+var_38], r9
0x14001c210  mov     rdx, rax
0x14001c213  mov     r9, rsi
0x14001c216  call    ??$TraceInfo@$$BY0CA@_WI$$BY0CA@_WI@LogAdapter@@YAXQEBDAEAY0CA@$$CB_WAEBI12@Z; LogAdapter::TraceInfo<wchar_t [32],uint,wchar_t [32],uint>(char const * const,wchar_t const (&)[32],uint const &,wchar_t const (&)[32],uint const &)
0x14001c21b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001c220  cmp     cs:dword_1400408D0, 0
0x14001c227  jz      short loc_14001C241
0x14001c229  mov     rdx, rdi
0x14001c22c  call    ??A?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@QEAAAEAUCCbsLock@@_K@Z; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::operator[](unsigned __int64)
0x14001c231  mov     rdx, rax
0x14001c234  mov     r8, rsi
0x14001c237  call    ??$TraceInfo@$$BY0CA@_W$$BY0CA@_W@LogAdapter@@YAXQEBDAEAY0CA@$$CB_W1@Z; LogAdapter::TraceInfo<wchar_t [32],wchar_t [32]>(char const * const,wchar_t const (&)[32],wchar_t const (&)[32])
0x14001c23c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001c241  inc     rdi
0x14001c244  cmp     rdi, cs:qword_1400406A8
0x14001c24b  jb      loc_14001C1CA
0x14001c251  lea     rcx, [rsp+58h+var_28]; this
0x14001c256  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x14001c25b  mov     rbx, [rsp+58h+arg_0]
0x14001c260  mov     rsi, [rsp+58h+arg_8]
0x14001c265  add     rsp, 50h
0x14001c269  pop     rdi
0x14001c26a  retn
```
