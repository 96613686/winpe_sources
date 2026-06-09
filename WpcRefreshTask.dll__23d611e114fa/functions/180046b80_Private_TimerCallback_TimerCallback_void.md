# Private::TimerCallback::~TimerCallback(void)

- ea: `0x180046b80`
- end: `0x180046c39`
- name: `??1TimerCallback@Private@@UEAA@XZ`
- size: `185`
- prototype: `void __fastcall(Private::TimerCallback *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180046e50`

## callees

- `0x180046b80`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046bc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046bc1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180046bde`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180046bde`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180046bd4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180046bd4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046bb3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046bb3`

## pseudocode

```c
void __fastcall Private::TimerCallback::~TimerCallback(Private::TimerCallback *this)
{
  __int64 v2; // rbx
  volatile signed __int32 *v3; // rbx

  *(_QWORD *)this = &Private::TimerCallback::`vftable';
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1));
  SetThreadpoolTimer(*((PTP_TIMER *)this + 3), 0, 0, 0);
  v2 = *(_QWORD *)(*((_QWORD *)this + 1) + 64LL);
  if ( (_DWORD)v2 != GetCurrentThreadId() )
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 3), 1);
  CloseThreadpoolTimer(*((PTP_TIMER *)this + 3));
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  *(_QWORD *)this = &ITimerCallback::`vftable';
}

```

## disassembly

```asm
0x180046b80  mov     [rsp+arg_0], rbx
0x180046b85  push    rdi
0x180046b86  sub     rsp, 20h
0x180046b8a  mov     rdi, rcx
0x180046b8d  lea     rax, ??_7TimerCallback@Private@@6B@; const Private::TimerCallback::`vftable'
0x180046b94  mov     [rcx], rax
0x180046b97  mov     rcx, [rcx+8]
0x180046b9b  mov     rax, [rcx]
0x180046b9e  mov     rax, [rax+8]
0x180046ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ba7  xor     r9d, r9d; msWindowLength
0x180046baa  xor     r8d, r8d; msPeriod
0x180046bad  xor     edx, edx; pftDueTime
0x180046baf  mov     rcx, [rdi+18h]; pti
0x180046bb3  call    cs:__imp_SetThreadpoolTimer
0x180046bb9  mov     rbx, [rdi+8]
0x180046bbd  mov     rbx, [rbx+40h]
0x180046bc1  call    cs:__imp_GetCurrentThreadId
0x180046bc7  cmp     ebx, eax
0x180046bc9  jz      short loc_180046BDA
0x180046bcb  mov     edx, 1; fCancelPendingCallbacks
0x180046bd0  mov     rcx, [rdi+18h]; pti
0x180046bd4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180046bda  mov     rcx, [rdi+18h]; pti
0x180046bde  call    cs:__imp_CloseThreadpoolTimer
0x180046be4  mov     rbx, [rdi+10h]
0x180046be8  test    rbx, rbx
0x180046beb  jz      short loc_180046C24
0x180046bed  or      eax, 0FFFFFFFFh
0x180046bf0  lock xadd [rbx+8], eax
0x180046bf5  cmp     eax, 1
0x180046bf8  jnz     short loc_180046C24
0x180046bfa  mov     rax, [rbx]
0x180046bfd  mov     rcx, rbx
0x180046c00  mov     rax, [rax]
0x180046c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c08  or      eax, 0FFFFFFFFh
0x180046c0b  lock xadd [rbx+0Ch], eax
0x180046c10  cmp     eax, 1
0x180046c13  jnz     short loc_180046C24
0x180046c15  mov     rax, [rbx]
0x180046c18  mov     rcx, rbx
0x180046c1b  mov     rax, [rax+8]
0x180046c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c24  lea     rax, ??_7ITimerCallback@@6B@; const ITimerCallback::`vftable'
0x180046c2b  mov     [rdi], rax
0x180046c2e  mov     rbx, [rsp+28h+arg_0]
0x180046c33  add     rsp, 20h
0x180046c37  pop     rdi
0x180046c38  retn
```
