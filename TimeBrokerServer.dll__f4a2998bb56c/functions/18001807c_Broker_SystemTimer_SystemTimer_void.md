# Broker::SystemTimer::~SystemTimer(void)

- ea: `0x18001807c`
- end: `0x180018115`
- name: `??1SystemTimer@Broker@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(Broker::SystemTimer *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016580`

## callees

- `0x18000d1d4`
- `0x18000e70c`
- `0x180013eb0`
- `0x18001807c`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800180ba`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800180ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800180d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800180d8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800180ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800180ce`

## pseudocode

```c
void __fastcall Broker::SystemTimer::~SystemTimer(Broker::SystemTimer *this)
{
  PPEB_LDR_DATA Ldr; // rdx
  __int64 v3; // rcx
  struct _TP_WAIT *v4; // rcx
  char *v5; // rcx
  char *v6; // rbx
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+28h] [rbp-10h]

  Ldr = NtCurrentPeb()->Ldr;
  if ( !Ldr->ShutdownInProgress )
  {
    Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)&v7, (struct _RTL_SRWLOCK *)this + 12);
    BciCloseWaitableTimer(*(void **)this);
    v3 = v7;
    *(_QWORD *)this = 0;
    RtlReleaseSRWLockExclusive(v3);
    v4 = (struct _TP_WAIT *)*((_QWORD *)this + 1);
    v8 = 0;
    WaitForThreadpoolWaitCallbacks(v4, 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 1));
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)&v7);
  }
  v5 = (char *)*((_QWORD *)this + 11);
  v6 = (char *)this + 32;
  if ( v5 )
  {
    LOBYTE(Ldr) = v5 != v6;
    (*(void (__fastcall **)(char *, PPEB_LDR_DATA))(*(_QWORD *)v5 + 32LL))(v5, Ldr);
    *((_QWORD *)v6 + 7) = 0;
  }
}

```

## disassembly

```asm
0x18001807c  push    rbx
0x18001807e  sub     rsp, 30h
0x180018082  mov     rax, gs:60h
0x18001808b  mov     rbx, rcx
0x18001808e  mov     rdx, [rax+18h]
0x180018092  cmp     byte ptr [rdx+48h], 0
0x180018096  jnz     short loc_1800180E8
0x180018098  lea     rdx, [rcx+60h]; struct _RTL_SRWLOCK *
0x18001809c  lea     rcx, [rsp+38h+var_18]; this
0x1800180a1  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x1800180a6  mov     rcx, [rbx]; void *
0x1800180a9  call    ?BciCloseWaitableTimer@@YAHPEAX@Z; BciCloseWaitableTimer(void *)
0x1800180ae  mov     rcx, [rsp+38h+var_18]
0x1800180b3  mov     qword ptr [rbx], 0
0x1800180ba  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800180c0  mov     rcx, [rbx+8]; pwa
0x1800180c4  mov     edx, 1; fCancelPendingCallbacks
0x1800180c9  mov     [rsp+38h+var_10], 0
0x1800180ce  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800180d4  mov     rcx, [rbx+8]; pwa
0x1800180d8  call    cs:__imp_CloseThreadpoolWait
0x1800180de  lea     rcx, [rsp+38h+var_18]; this
0x1800180e3  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x1800180e8  mov     rcx, [rbx+58h]
0x1800180ec  add     rbx, 20h ; ' '
0x1800180f0  test    rcx, rcx
0x1800180f3  jz      short loc_18001810F
0x1800180f5  mov     rax, [rcx]
0x1800180f8  cmp     rcx, rbx
0x1800180fb  setnz   dl
0x1800180fe  mov     rax, [rax+20h]
0x180018102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018107  mov     qword ptr [rbx+38h], 0
0x18001810f  add     rsp, 30h
0x180018113  pop     rbx
0x180018114  retn
```
