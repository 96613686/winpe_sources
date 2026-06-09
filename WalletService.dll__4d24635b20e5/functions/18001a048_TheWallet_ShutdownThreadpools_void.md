# TheWallet::ShutdownThreadpools(void)

- ea: `0x18001a048`
- end: `0x18001a100`
- name: `?ShutdownThreadpools@TheWallet@@AEAAJXZ`
- size: `184`
- prototype: `__int64 __fastcall(TheWallet *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008f60`
- `0x180017680`

## callees

- `0x1800172d8`
- `0x180017560`
- `0x1800182fc`
- `0x18001a048`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001a08c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001a08c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001a0bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001a0bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001a0b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001a0b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001a096`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001a096`

## pseudocode

```c
__int64 __fastcall TheWallet::ShutdownThreadpools(TheWallet *this)
{
  ULONG_PTR ThreadPoolData; // rdi
  struct _TP_WAIT *v3; // rcx
  struct _TP_TIMER *v4; // rcx
  unsigned int v5; // esi
  unsigned int i; // edi
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  ThreadPoolData = NtCurrentTeb()->ThreadPoolData;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>((__int64)v8);
  v3 = (struct _TP_WAIT *)*((_QWORD *)this + 10);
  *((_DWORD *)this + 25) = 1;
  if ( v3 )
  {
    if ( !ThreadPoolData )
      WaitForThreadpoolWaitCallbacks(v3, 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 10));
    *((_QWORD *)this + 10) = 0;
  }
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 11);
  if ( v4 )
  {
    if ( !ThreadPoolData )
      WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 11));
    *((_QWORD *)this + 11) = 0;
  }
  v5 = *((_DWORD *)this + 24);
  for ( i = 0; i < v5; ++i )
    TheWallet::DecrementDelayedReferenceCount(this);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>((__int64)v8);
  return 0;
}

```

## disassembly

```asm
0x18001a048  mov     [rsp+arg_0], rbx
0x18001a04d  mov     [rsp+arg_8], rsi
0x18001a052  push    rdi
0x18001a053  sub     rsp, 30h
0x18001a057  mov     rax, gs:30h
0x18001a060  mov     rbx, rcx
0x18001a063  lea     rcx, [rsp+38h+var_18]
0x18001a068  mov     rdi, [rax+1778h]
0x18001a06f  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18001a074  mov     rcx, [rbx+50h]; pwa
0x18001a078  mov     dword ptr [rbx+64h], 1
0x18001a07f  test    rcx, rcx
0x18001a082  jz      short loc_18001A0A4
0x18001a084  test    rdi, rdi
0x18001a087  jnz     short loc_18001A092
0x18001a089  lea     edx, [rdi+1]; fCancelPendingCallbacks
0x18001a08c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18001a092  mov     rcx, [rbx+50h]; pwa
0x18001a096  call    cs:__imp_CloseThreadpoolWait
0x18001a09c  mov     qword ptr [rbx+50h], 0
0x18001a0a4  mov     rcx, [rbx+58h]; pti
0x18001a0a8  test    rcx, rcx
0x18001a0ab  jz      short loc_18001A0CD
0x18001a0ad  test    rdi, rdi
0x18001a0b0  jnz     short loc_18001A0BB
0x18001a0b2  lea     edx, [rdi+1]; fCancelPendingCallbacks
0x18001a0b5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001a0bb  mov     rcx, [rbx+58h]; pti
0x18001a0bf  call    cs:__imp_CloseThreadpoolTimer
0x18001a0c5  mov     qword ptr [rbx+58h], 0
0x18001a0cd  mov     esi, [rbx+60h]
0x18001a0d0  xor     edi, edi
0x18001a0d2  test    esi, esi
0x18001a0d4  jz      short loc_18001A0E4
0x18001a0d6  mov     rcx, rbx; this
0x18001a0d9  call    ?DecrementDelayedReferenceCount@TheWallet@@AEAAXXZ; TheWallet::DecrementDelayedReferenceCount(void)
0x18001a0de  inc     edi
0x18001a0e0  cmp     edi, esi
0x18001a0e2  jb      short loc_18001A0D6
0x18001a0e4  lea     rcx, [rsp+38h+var_18]
0x18001a0e9  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18001a0ee  mov     rbx, [rsp+38h+arg_0]
0x18001a0f3  xor     eax, eax
0x18001a0f5  mov     rsi, [rsp+38h+arg_8]
0x18001a0fa  add     rsp, 30h
0x18001a0fe  pop     rdi
0x18001a0ff  retn
```
