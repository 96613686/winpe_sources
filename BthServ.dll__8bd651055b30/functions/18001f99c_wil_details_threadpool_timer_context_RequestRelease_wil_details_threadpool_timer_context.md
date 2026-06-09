# wil::details::threadpool_timer_context::RequestRelease(wil::details::threadpool_timer_context *)

- ea: `0x18001f99c`
- end: `0x18001fa48`
- name: `?RequestRelease@threadpool_timer_context@details@wil@@SAXPEAU123@@Z`
- size: `172`
- prototype: `void __fastcall(struct wil::details::threadpool_timer_context *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001ec40`
- `0x18001f1c8`

## callees

- `0x180001b60`
- `0x18001e6c8`
- `0x18001f99c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f9d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f9d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f9b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f9b8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f9f6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f9f6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f9e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f9e7`

## pseudocode

```c
void __fastcall wil::details::threadpool_timer_context::RequestRelease(
        struct wil::details::threadpool_timer_context *this)
{
  RTL_SRWLOCK *v1; // rdi
  char v3; // si
  __int64 v4; // rdx
  struct _TP_TIMER *v5; // rcx
  __int64 v6; // rcx

  v1 = (RTL_SRWLOCK *)((char *)this + 88);
  v3 = 1;
  AcquireSRWLockExclusive((PSRWLOCK)this + 11);
  if ( *((_DWORD *)this + 24) )
  {
    *((_BYTE *)this + 100) = 1;
    v3 = 0;
  }
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  if ( v3 )
  {
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 10), 1);
    v5 = (struct _TP_TIMER *)*((_QWORD *)this + 10);
    if ( v5 )
      CloseThreadpoolTimer(v5);
    v6 = *((_QWORD *)this + 9);
    if ( v6 )
    {
      LOBYTE(v4) = v6 != (_QWORD)this + 16;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 32LL))(v6, v4);
      *((_QWORD *)this + 9) = 0;
    }
    wil::details::threadpool_object_context::~threadpool_object_context(this);
    operator delete(this, (const struct std::nothrow_t *)0x68);
  }
}

```

## disassembly

```asm
0x18001f99c  mov     [rsp+arg_0], rbx
0x18001f9a1  mov     [rsp+arg_8], rsi
0x18001f9a6  push    rdi
0x18001f9a7  sub     rsp, 20h
0x18001f9ab  lea     rdi, [rcx+58h]
0x18001f9af  mov     rbx, rcx
0x18001f9b2  mov     rcx, rdi; SRWLock
0x18001f9b5  mov     sil, 1
0x18001f9b8  call    cs:__imp_AcquireSRWLockExclusive
0x18001f9be  cmp     dword ptr [rbx+60h], 0
0x18001f9c2  jz      short loc_18001F9CB
0x18001f9c4  mov     [rbx+64h], sil
0x18001f9c8  xor     sil, sil
0x18001f9cb  test    rdi, rdi
0x18001f9ce  jz      short loc_18001F9D9
0x18001f9d0  mov     rcx, rdi; SRWLock
0x18001f9d3  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f9d9  test    sil, sil
0x18001f9dc  jz      short loc_18001FA38
0x18001f9de  mov     rcx, [rbx+50h]; pti
0x18001f9e2  mov     edx, 1; fCancelPendingCallbacks
0x18001f9e7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001f9ed  mov     rcx, [rbx+50h]; pti
0x18001f9f1  test    rcx, rcx
0x18001f9f4  jz      short loc_18001F9FC
0x18001f9f6  call    cs:__imp_CloseThreadpoolTimer
0x18001f9fc  lea     rdi, [rbx+10h]
0x18001fa00  mov     rcx, [rdi+38h]
0x18001fa04  test    rcx, rcx
0x18001fa07  jz      short loc_18001FA23
0x18001fa09  mov     rax, [rcx]
0x18001fa0c  cmp     rcx, rdi
0x18001fa0f  setnz   dl
0x18001fa12  mov     rax, [rax+20h]
0x18001fa16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa1b  mov     qword ptr [rdi+38h], 0
0x18001fa23  mov     rcx, rbx; this
0x18001fa26  call    ??1threadpool_object_context@details@wil@@QEAA@XZ; wil::details::threadpool_object_context::~threadpool_object_context(void)
0x18001fa2b  mov     edx, 68h ; 'h'; struct std::nothrow_t *
0x18001fa30  mov     rcx, rbx; void *
0x18001fa33  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fa38  mov     rbx, [rsp+28h+arg_0]
0x18001fa3d  mov     rsi, [rsp+28h+arg_8]
0x18001fa42  add     rsp, 20h
0x18001fa46  pop     rdi
0x18001fa47  retn
```
