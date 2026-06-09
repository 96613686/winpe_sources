# UQIService::~UQIService(void)

- ea: `0x18001afd8`
- end: `0x18001b12c`
- name: `??1UQIService@@QEAA@XZ`
- size: `340`
- prototype: `void __fastcall(UQIService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180107990`

## callees

- `0x18001afd8`
- `0x18001bddc`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b125`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b01a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b01a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b003`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b003`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b011`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b011`

## pseudocode

```c
void __fastcall UQIService::~UQIService(PTP_TIMER *this)
{
  struct _TP_TIMER *v2; // rbx
  volatile signed __int32 *v3; // rbx
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rbx
  volatile signed __int32 *v6; // rbx

  UQIService::OnShutdown((UQIService *)this);
  v2 = this[14];
  if ( v2 )
  {
    SetThreadpoolTimer(this[14], 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
  }
  v3 = (volatile signed __int32 *)this[13];
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  v4 = (volatile signed __int32 *)this[10];
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  v5 = (volatile signed __int32 *)this[8];
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v6 = (volatile signed __int32 *)this[6];
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18001afd8  mov     [rsp+arg_0], rbx
0x18001afdd  mov     [rsp+arg_8], rsi
0x18001afe2  push    rdi
0x18001afe3  sub     rsp, 20h
0x18001afe7  mov     rdi, rcx
0x18001afea  call    ?OnShutdown@UQIService@@QEAAXXZ; UQIService::OnShutdown(void)
0x18001afef  mov     rbx, [rdi+70h]
0x18001aff3  test    rbx, rbx
0x18001aff6  jz      short loc_18001B020
0x18001aff8  xor     r9d, r9d; msWindowLength
0x18001affb  xor     r8d, r8d; msPeriod
0x18001affe  xor     edx, edx; pftDueTime
0x18001b000  mov     rcx, rbx; pti
0x18001b003  call    cs:__imp_SetThreadpoolTimer
0x18001b009  mov     edx, 1; fCancelPendingCallbacks
0x18001b00e  mov     rcx, rbx; pti
0x18001b011  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001b017  mov     rcx, rbx; pti
0x18001b01a  call    cs:__imp_CloseThreadpoolTimer
0x18001b020  mov     rbx, [rdi+68h]
0x18001b024  or      esi, 0FFFFFFFFh
0x18001b027  test    rbx, rbx
0x18001b02a  jz      short loc_18001B05F
0x18001b02c  mov     eax, esi
0x18001b02e  lock xadd [rbx+8], eax
0x18001b033  add     eax, esi
0x18001b035  jnz     short loc_18001B05F
0x18001b037  mov     rax, [rbx]
0x18001b03a  mov     rcx, rbx
0x18001b03d  mov     rax, [rax]
0x18001b040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b045  mov     eax, esi
0x18001b047  lock xadd [rbx+0Ch], eax
0x18001b04c  add     eax, esi
0x18001b04e  jnz     short loc_18001B05F
0x18001b050  mov     rax, [rbx]
0x18001b053  mov     rcx, rbx
0x18001b056  mov     rax, [rax+8]
0x18001b05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b05f  mov     rbx, [rdi+50h]
0x18001b063  test    rbx, rbx
0x18001b066  jz      short loc_18001B09B
0x18001b068  mov     eax, esi
0x18001b06a  lock xadd [rbx+8], eax
0x18001b06f  add     eax, esi
0x18001b071  jnz     short loc_18001B09B
0x18001b073  mov     rax, [rbx]
0x18001b076  mov     rcx, rbx
0x18001b079  mov     rax, [rax]
0x18001b07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b081  mov     eax, esi
0x18001b083  lock xadd [rbx+0Ch], eax
0x18001b088  add     eax, esi
0x18001b08a  jnz     short loc_18001B09B
0x18001b08c  mov     rax, [rbx]
0x18001b08f  mov     rcx, rbx
0x18001b092  mov     rax, [rax+8]
0x18001b096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b09b  mov     rbx, [rdi+40h]
0x18001b09f  test    rbx, rbx
0x18001b0a2  jz      short loc_18001B0D7
0x18001b0a4  mov     eax, esi
0x18001b0a6  lock xadd [rbx+8], eax
0x18001b0ab  add     eax, esi
0x18001b0ad  jnz     short loc_18001B0D7
0x18001b0af  mov     rax, [rbx]
0x18001b0b2  mov     rcx, rbx
0x18001b0b5  mov     rax, [rax]
0x18001b0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0bd  mov     eax, esi
0x18001b0bf  lock xadd [rbx+0Ch], eax
0x18001b0c4  add     eax, esi
0x18001b0c6  jnz     short loc_18001B0D7
0x18001b0c8  mov     rax, [rbx]
0x18001b0cb  mov     rcx, rbx
0x18001b0ce  mov     rax, [rax+8]
0x18001b0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0d7  mov     rbx, [rdi+30h]
0x18001b0db  test    rbx, rbx
0x18001b0de  jz      short loc_18001B113
0x18001b0e0  mov     eax, esi
0x18001b0e2  lock xadd [rbx+8], eax
0x18001b0e7  add     eax, esi
0x18001b0e9  jnz     short loc_18001B113
0x18001b0eb  mov     rax, [rbx]
0x18001b0ee  mov     rcx, rbx
0x18001b0f1  mov     rax, [rax]
0x18001b0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0f9  mov     eax, esi
0x18001b0fb  lock xadd [rbx+0Ch], eax
0x18001b100  add     eax, esi
0x18001b102  jnz     short loc_18001B113
0x18001b104  mov     rax, [rbx]
0x18001b107  mov     rcx, rbx
0x18001b10a  mov     rax, [rax+8]
0x18001b10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b113  mov     rcx, rdi
0x18001b116  mov     rbx, [rsp+28h+arg_0]
0x18001b11b  mov     rsi, [rsp+28h+arg_8]
0x18001b120  add     rsp, 20h
0x18001b124  pop     rdi
0x18001b125  jmp     cs:__imp_DeleteCriticalSection
```
