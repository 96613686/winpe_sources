# XSLOCK::LockExclusive(void)

- ea: `0x180014cd8`
- end: `0x180014d96`
- name: `?LockExclusive@XSLOCK@@QEAAXXZ`
- size: `190`
- prototype: `void __fastcall(XSLOCK *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001255c`
- `0x180014974`
- `0x180014cac`
- `0x180016028`

## callees

- `0x180014cd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014d0b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014d0b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014d8a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014d8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d32`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014d1a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180014d1a`

## pseudocode

```c
void __fastcall XSLOCK::LockExclusive(XSLOCK *this)
{
  XSLOCK *i; // rbx
  HANDLE EventW; // rax
  DWORD CurrentThreadId; // eax
  DWORD v4; // esi

  for ( i = this; ; this = i )
  {
    EnterCriticalSection(&this->m_lock.critSec);
    CurrentThreadId = GetCurrentThreadId();
    v4 = CurrentThreadId;
    if ( !i->m_cOwner )
    {
      i->m_isOwnedExclusive = 1;
      i->m_ownerThreads[0].threadId._Storage._Value = CurrentThreadId;
      i->m_ownerThreads[0].ownerCount = 1;
      i->m_cOwner = 1;
LABEL_10:
      LeaveCriticalSection(&i->m_lock.critSec);
      return;
    }
    if ( i->m_isOwnedExclusive && i->m_ownerThreads[0].threadId._Storage._Value == CurrentThreadId )
    {
      ++i->m_ownerThreads[0].ownerCount;
      goto LABEL_10;
    }
    if ( i->m_eventExclusiveWaiters.m_hEvent )
      break;
    EventW = CreateEventW(0, 0, 0, 0);
    i->m_eventExclusiveWaiters.m_hEvent = EventW;
    if ( !EventW )
      DebugBreak();
    LeaveCriticalSection(&i->m_lock.critSec);
  }
  ++i->m_cExclusiveWaiters;
  LeaveCriticalSection(&i->m_lock.critSec);
  WaitForSingleObject(i->m_eventExclusiveWaiters.m_hEvent, 0xFFFFFFFF);
  i->m_ownerThreads[0].threadId._Storage._Value = v4;
}

```

## disassembly

```asm
0x180014cd8  mov     [rsp+arg_0], rbx
0x180014cdd  mov     [rsp+arg_8], rsi
0x180014ce2  push    rdi
0x180014ce3  sub     rsp, 20h
0x180014ce7  mov     rbx, this
0x180014cea  jmp     short loc_180014D2C
0x180014cec  cmp     dword ptr [rbx+68h], 0
0x180014cf0  jz      short loc_180014CFA
0x180014cf2  mov     eax, [rbx+34h]
0x180014cf5  nop
0x180014cf6  cmp     eax, esi
0x180014cf8  jz      short loc_180014D72
0x180014cfa  cmp     qword ptr [rbx+50h], 0
0x180014cff  jnz     short loc_180014D77
0x180014d01  xor     r9d, r9d; lpName
0x180014d04  xor     r8d, r8d; bInitialState
0x180014d07  xor     edx, edx; bManualReset
0x180014d09  xor     ecx, ecx; lpEventAttributes
0x180014d0b  call    cs:__imp_CreateEventW
0x180014d11  mov     [rbx+50h], rax
0x180014d15  test    rax, rax
0x180014d18  jnz     short loc_180014D20
0x180014d1a  call    cs:__imp_DebugBreak
0x180014d20  mov     this, rbx; lpCriticalSection
0x180014d23  call    cs:__imp_LeaveCriticalSection
0x180014d29  mov     this, rbx; lpCriticalSection
0x180014d2c  call    cs:__imp_EnterCriticalSection
0x180014d32  call    cs:__imp_GetCurrentThreadId
0x180014d38  cmp     dword ptr [rbx+30h], 0
0x180014d3c  mov     esi, eax
0x180014d3e  jnz     short loc_180014CEC
0x180014d40  mov     dword ptr [rbx+68h], 1
0x180014d47  nop
0x180014d48  mov     [rbx+34h], eax
0x180014d4b  mov     dword ptr [rbx+38h], 1
0x180014d52  mov     dword ptr [rbx+30h], 1
0x180014d59  mov     this, rbx; lpCriticalSection
0x180014d5c  call    cs:__imp_LeaveCriticalSection
0x180014d62  mov     rbx, [rsp+28h+arg_0]
0x180014d67  mov     rsi, [rsp+28h+arg_8]
0x180014d6c  add     rsp, 20h
0x180014d70  pop     rdi
0x180014d71  retn
0x180014d72  inc     dword ptr [rbx+38h]
0x180014d75  jmp     short loc_180014D59
0x180014d77  inc     dword ptr [rbx+60h]
0x180014d7a  mov     this, rbx; lpCriticalSection
0x180014d7d  call    cs:__imp_LeaveCriticalSection
0x180014d83  mov     this, [rbx+50h]; hHandle
0x180014d87  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014d8a  call    cs:__imp_WaitForSingleObject
0x180014d90  nop
0x180014d91  mov     [rbx+34h], esi
0x180014d94  jmp     short loc_180014D62
```
