# PimIMService::_ScheduleAggregateCacheBackup(int,int)

- ea: `0x18000bf5c`
- end: `0x18000c04d`
- name: `?_ScheduleAggregateCacheBackup@PimIMService@@AEAAJHH@Z`
- size: `241`
- prototype: `__int64 __fastcall(PimIMService *this, __int32, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180005084`
- `0x180006070`
- `0x18000ba6c`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x18000bf5c`
- `0x18000d63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bf9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bf9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c035`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c035`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bfea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c026`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bfea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c026`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000bfd1`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000bfd1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bffc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bffc`

## string_xrefs

- `0x18000bf8b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000bfb5`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::_ScheduleAggregateCacheBackup(PimIMService *this, __int32 a2, int a3)
{
  int v5; // eax
  unsigned int v6; // edi
  struct _FILETIME *v7; // rdx

  if ( a2 )
    _InterlockedExchange((volatile __int32 *)this + 114, a2);
  if ( !*((_QWORD *)this + 61) )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      3437);
  EnterCriticalSection(&g_shutdownLock);
  v5 = FailOnServiceShutdown();
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( IsThreadpoolTimerSet(*((PTP_TIMER *)this + 61)) )
    {
      SetThreadpoolTimer(*((PTP_TIMER *)this + 61), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 61), 1);
    }
    v7 = (struct _FILETIME *)&qword_18002D238;
    if ( !a3 )
      v7 = &pftDueTime;
    SetThreadpoolTimer(*((PTP_TIMER *)this + 61), v7, 0, 0xEA60u);
    v6 = 0;
  }
  else
  {
    Log_HREvent(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      3440);
  }
  LeaveCriticalSection(&g_shutdownLock);
  return v6;
}

```

## disassembly

```asm
0x18000bf5c  mov     [rsp+arg_0], rbx
0x18000bf61  mov     [rsp+arg_8], rsi
0x18000bf66  push    rdi
0x18000bf67  sub     rsp, 30h
0x18000bf6b  mov     esi, r8d
0x18000bf6e  mov     rbx, rcx
0x18000bf71  test    edx, edx
0x18000bf73  jz      short loc_18000BF7B
0x18000bf75  xchg    edx, [rcx+1C8h]
0x18000bf7b  cmp     qword ptr [rcx+1E8h], 0
0x18000bf83  jnz     short loc_18000BF97
0x18000bf85  mov     r8d, 0D6Dh
0x18000bf8b  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bf92  call    Log_AssertionEvent
0x18000bf97  lea     rcx, ?g_shutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000bf9e  call    cs:__imp_EnterCriticalSection
0x18000bfa4  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x18000bfa9  mov     edi, eax
0x18000bfab  test    eax, eax
0x18000bfad  jns     short loc_18000BFCA
0x18000bfaf  mov     r9d, 0D70h
0x18000bfb5  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bfbc  mov     edx, 1
0x18000bfc1  mov     ecx, eax
0x18000bfc3  call    Log_HREvent
0x18000bfc8  jmp     short loc_18000C02E
0x18000bfca  mov     rcx, [rbx+1E8h]; pti
0x18000bfd1  call    cs:__imp_IsThreadpoolTimerSet
0x18000bfd7  test    eax, eax
0x18000bfd9  jz      short loc_18000C002
0x18000bfdb  mov     rcx, [rbx+1E8h]; pti
0x18000bfe2  xor     r9d, r9d; msWindowLength
0x18000bfe5  xor     r8d, r8d; msPeriod
0x18000bfe8  xor     edx, edx; pftDueTime
0x18000bfea  call    cs:__imp_SetThreadpoolTimer
0x18000bff0  mov     rcx, [rbx+1E8h]; pti
0x18000bff7  mov     edx, 1; fCancelPendingCallbacks
0x18000bffc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c002  mov     rcx, [rbx+1E8h]; pti
0x18000c009  lea     rax, pftDueTime
0x18000c010  test    esi, esi
0x18000c012  lea     rdx, qword_18002D238
0x18000c019  mov     r9d, 0EA60h; msWindowLength
0x18000c01f  cmovz   rdx, rax; pftDueTime
0x18000c023  xor     r8d, r8d; msPeriod
0x18000c026  call    cs:__imp_SetThreadpoolTimer
0x18000c02c  xor     edi, edi
0x18000c02e  lea     rcx, ?g_shutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000c035  call    cs:__imp_LeaveCriticalSection
0x18000c03b  mov     rbx, [rsp+38h+arg_0]
0x18000c040  mov     eax, edi
0x18000c042  mov     rsi, [rsp+38h+arg_8]
0x18000c047  add     rsp, 30h
0x18000c04b  pop     rdi
0x18000c04c  retn
```
