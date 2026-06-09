# UQIService::OnShutdown(void)

- ea: `0x18001bddc`
- end: `0x18001bf8d`
- name: `?OnShutdown@UQIService@@QEAAXXZ`
- size: `433`
- prototype: `void __fastcall(UQIService *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000d360`
- `0x18001afd8`

## callees

- `0x18001bddc`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bf86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bdee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bdee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001be2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001be2f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001be27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001be27`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001be10`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001be10`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001be1e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001be1e`

## pseudocode

```c
void __fastcall UQIService::OnShutdown(struct _RTL_CRITICAL_SECTION *this)
{
  struct _TP_TIMER *SpinCount; // rsi
  DWORD LastError; // ebx
  volatile signed __int32 *LockSemaphore; // rbx
  volatile signed __int32 *DebugInfo; // rbx
  volatile signed __int32 *v6; // rbx
  volatile signed __int32 *v7; // rbx

  EnterCriticalSection(this);
  SpinCount = (struct _TP_TIMER *)this[2].SpinCount;
  if ( SpinCount )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(SpinCount, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(SpinCount, 1);
    CloseThreadpoolTimer(SpinCount);
    SetLastError(LastError);
  }
  this[2].SpinCount = 0;
  LockSemaphore = (volatile signed __int32 *)this[2].LockSemaphore;
  this[2].OwningThread = 0;
  this[2].LockSemaphore = 0;
  if ( LockSemaphore )
  {
    if ( _InterlockedExchangeAdd(LockSemaphore + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))LockSemaphore)(LockSemaphore);
      if ( _InterlockedExchangeAdd(LockSemaphore + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)LockSemaphore + 8LL))(LockSemaphore);
    }
  }
  DebugInfo = (volatile signed __int32 *)this[2].DebugInfo;
  this[1].SpinCount = 0;
  this[2].DebugInfo = 0;
  if ( DebugInfo )
  {
    if ( _InterlockedExchangeAdd(DebugInfo + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))DebugInfo)(DebugInfo);
      if ( _InterlockedExchangeAdd(DebugInfo + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)DebugInfo + 8LL))(DebugInfo);
    }
  }
  v6 = *(volatile signed __int32 **)&this[1].LockCount;
  this[1].DebugInfo = 0;
  *(_QWORD *)&this[1].LockCount = 0;
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v7 = (volatile signed __int32 *)this[1].LockSemaphore;
  this[1].OwningThread = 0;
  this[1].LockSemaphore = 0;
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  LOBYTE(this[2].LockCount) = 0;
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x18001bddc  mov     [rsp+arg_0], rbx
0x18001bde1  mov     [rsp+arg_8], rsi
0x18001bde6  push    rdi
0x18001bde7  sub     rsp, 20h
0x18001bdeb  mov     rdi, rcx
0x18001bdee  call    cs:__imp_EnterCriticalSection
0x18001bdf4  mov     rsi, [rdi+70h]
0x18001bdf8  test    rsi, rsi
0x18001bdfb  jz      short loc_18001BE35
0x18001bdfd  call    cs:__imp_GetLastError
0x18001be03  xor     r9d, r9d; msWindowLength
0x18001be06  xor     r8d, r8d; msPeriod
0x18001be09  xor     edx, edx; pftDueTime
0x18001be0b  mov     rcx, rsi; pti
0x18001be0e  mov     ebx, eax
0x18001be10  call    cs:__imp_SetThreadpoolTimer
0x18001be16  mov     edx, 1; fCancelPendingCallbacks
0x18001be1b  mov     rcx, rsi; pti
0x18001be1e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001be24  mov     rcx, rsi; pti
0x18001be27  call    cs:__imp_CloseThreadpoolTimer
0x18001be2d  mov     ecx, ebx; dwErrCode
0x18001be2f  call    cs:__imp_SetLastError
0x18001be35  mov     qword ptr [rdi+70h], 0
0x18001be3d  or      esi, 0FFFFFFFFh
0x18001be40  mov     rbx, [rdi+68h]
0x18001be44  mov     qword ptr [rdi+60h], 0
0x18001be4c  mov     qword ptr [rdi+68h], 0
0x18001be54  test    rbx, rbx
0x18001be57  jz      short loc_18001BE8C
0x18001be59  mov     eax, esi
0x18001be5b  lock xadd [rbx+8], eax
0x18001be60  add     eax, esi
0x18001be62  jnz     short loc_18001BE8C
0x18001be64  mov     rax, [rbx]
0x18001be67  mov     rcx, rbx
0x18001be6a  mov     rax, [rax]
0x18001be6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be72  mov     eax, esi
0x18001be74  lock xadd [rbx+0Ch], eax
0x18001be79  add     eax, esi
0x18001be7b  jnz     short loc_18001BE8C
0x18001be7d  mov     rax, [rbx]
0x18001be80  mov     rcx, rbx
0x18001be83  mov     rax, [rax+8]
0x18001be87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be8c  mov     rbx, [rdi+50h]
0x18001be90  mov     qword ptr [rdi+48h], 0
0x18001be98  mov     qword ptr [rdi+50h], 0
0x18001bea0  test    rbx, rbx
0x18001bea3  jz      short loc_18001BED8
0x18001bea5  mov     eax, esi
0x18001bea7  lock xadd [rbx+8], eax
0x18001beac  add     eax, esi
0x18001beae  jnz     short loc_18001BED8
0x18001beb0  mov     rax, [rbx]
0x18001beb3  mov     rcx, rbx
0x18001beb6  mov     rax, [rax]
0x18001beb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bebe  mov     eax, esi
0x18001bec0  lock xadd [rbx+0Ch], eax
0x18001bec5  add     eax, esi
0x18001bec7  jnz     short loc_18001BED8
0x18001bec9  mov     rax, [rbx]
0x18001becc  mov     rcx, rbx
0x18001becf  mov     rax, [rax+8]
0x18001bed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bed8  mov     rbx, [rdi+30h]
0x18001bedc  mov     qword ptr [rdi+28h], 0
0x18001bee4  mov     qword ptr [rdi+30h], 0
0x18001beec  test    rbx, rbx
0x18001beef  jz      short loc_18001BF24
0x18001bef1  mov     eax, esi
0x18001bef3  lock xadd [rbx+8], eax
0x18001bef8  add     eax, esi
0x18001befa  jnz     short loc_18001BF24
0x18001befc  mov     rax, [rbx]
0x18001beff  mov     rcx, rbx
0x18001bf02  mov     rax, [rax]
0x18001bf05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf0a  mov     eax, esi
0x18001bf0c  lock xadd [rbx+0Ch], eax
0x18001bf11  add     eax, esi
0x18001bf13  jnz     short loc_18001BF24
0x18001bf15  mov     rax, [rbx]
0x18001bf18  mov     rcx, rbx
0x18001bf1b  mov     rax, [rax+8]
0x18001bf1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf24  mov     rbx, [rdi+40h]
0x18001bf28  mov     qword ptr [rdi+38h], 0
0x18001bf30  mov     qword ptr [rdi+40h], 0
0x18001bf38  test    rbx, rbx
0x18001bf3b  jz      short loc_18001BF70
0x18001bf3d  mov     eax, esi
0x18001bf3f  lock xadd [rbx+8], eax
0x18001bf44  add     eax, esi
0x18001bf46  jnz     short loc_18001BF70
0x18001bf48  mov     rax, [rbx]
0x18001bf4b  mov     rcx, rbx
0x18001bf4e  mov     rax, [rax]
0x18001bf51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf56  mov     eax, esi
0x18001bf58  lock xadd [rbx+0Ch], eax
0x18001bf5d  add     eax, esi
0x18001bf5f  jnz     short loc_18001BF70
0x18001bf61  mov     rax, [rbx]
0x18001bf64  mov     rcx, rbx
0x18001bf67  mov     rax, [rax+8]
0x18001bf6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf70  mov     rcx, rdi
0x18001bf73  mov     byte ptr [rdi+58h], 0
0x18001bf77  mov     rbx, [rsp+28h+arg_0]
0x18001bf7c  mov     rsi, [rsp+28h+arg_8]
0x18001bf81  add     rsp, 20h
0x18001bf85  pop     rdi
0x18001bf86  jmp     cs:__imp_LeaveCriticalSection
```
