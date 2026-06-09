# XSLOCK::LockShared(int)

- ea: `0x1800167d8`
- end: `0x1800168f0`
- name: `?LockShared@XSLOCK@@QEAAHH@Z`
- size: `280`
- prototype: `int __fastcall(XSLOCK *this, int fWait)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001255c`
- `0x180014974`
- `0x180015394`
- `0x180015464`
- `0x180016114`
- `0x180018610`

## callees

- `0x1800167d8`
- `0x1800bd594`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001688e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001688e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016810`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016881`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016810`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016881`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800167f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800167f0`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001686a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001686a`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18001685b`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18001685b`

## pseudocode

```c
__int64 __fastcall XSLOCK::LockShared(XSLOCK *this, int fWait)
{
  DWORD CurrentThreadId; // eax
  DWORD v4; // edi
  unsigned int v5; // edi
  XSLOCK::OWNERENTRY *ThreadOrFree; // rsi
  HANDLE SemaphoreW; // rax
  XSLOCK::OWNERENTRY *v9; // rax

  EnterCriticalSection(&this->m_lock.critSec);
  CurrentThreadId = GetCurrentThreadId();
  v4 = CurrentThreadId;
  if ( !this->m_cOwner )
  {
    v5 = 1;
    this->m_ownerThreads[1].threadId._Storage._Value = CurrentThreadId;
    this->m_ownerThreads[1].ownerCount = 1;
    this->m_cOwner = 1;
LABEL_3:
    LeaveCriticalSection(&this->m_lock.critSec);
    return v5;
  }
  if ( !this->m_isOwnedExclusive )
    goto LABEL_14;
  if ( this->m_ownerThreads[0].threadId._Storage._Value == CurrentThreadId )
  {
    v5 = 1;
    ++this->m_ownerThreads[0].ownerCount;
    goto LABEL_3;
  }
  if ( this->m_isOwnedExclusive )
  {
    ThreadOrFree = XSLOCK::FindThreadOrFree(this, 0);
  }
  else
  {
LABEL_14:
    v9 = XSLOCK::FindThreadOrFree(this, CurrentThreadId);
    ThreadOrFree = v9;
    if ( !v9 )
    {
      v5 = 0;
      goto LABEL_3;
    }
    if ( v9->threadId._Storage._Value == v4 )
    {
      v5 = 1;
      ++v9->ownerCount;
      goto LABEL_3;
    }
    if ( !this->m_cExclusiveWaiters )
    {
      v9->threadId._Storage._Value = v4;
      v5 = 1;
      v9->ownerCount = 1;
      ++this->m_cOwner;
      goto LABEL_3;
    }
  }
  if ( !this->m_semaphoreSharedWaiters.m_hSem )
  {
    SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
    this->m_semaphoreSharedWaiters.m_hSem = SemaphoreW;
    if ( !SemaphoreW )
      DebugBreak();
  }
  ThreadOrFree->threadId._Storage._Value = v4;
  v5 = 1;
  ThreadOrFree->ownerCount = 1;
  ++this->m_cSharedWaiters;
  LeaveCriticalSection(&this->m_lock.critSec);
  WaitForSingleObject(this->m_semaphoreSharedWaiters.m_hSem, 0xFFFFFFFF);
  return v5;
}

```

## disassembly

```asm
0x1800167d8  mov     [rsp+arg_0], rbx
0x1800167dd  mov     [rsp+arg_8], rsi
0x1800167e2  push    rdi
0x1800167e3  sub     rsp, 20h
0x1800167e7  mov     rbx, this
0x1800167ea  call    cs:__imp_EnterCriticalSection
0x1800167f0  call    cs:__imp_GetCurrentThreadId
0x1800167f6  cmp     dword ptr [rbx+30h], 0
0x1800167fa  mov     edi, eax
0x1800167fc  jnz     short loc_180016818
0x1800167fe  nop
0x1800167ff  mov     edi, 1
0x180016804  mov     [rbx+3Ch], eax
0x180016807  mov     [rbx+40h], edi
0x18001680a  mov     [rbx+30h], edi
0x18001680d  mov     this, rbx; lpCriticalSection
0x180016810  call    cs:__imp_LeaveCriticalSection
0x180016816  jmp     short loc_180016894
0x180016818  cmp     dword ptr [rbx+68h], 0
0x18001681c  jz      loc_1800168A6
0x180016822  mov     eax, [rbx+34h]
0x180016825  nop
0x180016826  cmp     eax, edi
0x180016828  jnz     short loc_180016834
0x18001682a  mov     edi, 1
0x18001682f  add     [rbx+38h], edi
0x180016832  jmp     short loc_18001680D
0x180016834  cmp     dword ptr [rbx+68h], 0
0x180016838  jz      short loc_1800168A6
0x18001683a  xor     edx, edx; dwThreadId
0x18001683c  mov     this, rbx; this
0x18001683f  call    ?FindThreadOrFree@XSLOCK@@AEAAPEAUOWNERENTRY@1@K@Z; XSLOCK::FindThreadOrFree(ulong)
0x180016844  mov     rsi, rax
0x180016847  cmp     qword ptr [rbx+58h], 0
0x18001684c  jnz     short loc_180016870
0x18001684e  xor     r9d, r9d; lpName
0x180016851  xor     edx, edx; lInitialCount
0x180016853  xor     ecx, ecx; lpSemaphoreAttributes
0x180016855  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18001685b  call    cs:__imp_CreateSemaphoreW
0x180016861  mov     [rbx+58h], rax
0x180016865  test    rax, rax
0x180016868  jnz     short loc_180016870
0x18001686a  call    cs:__imp_DebugBreak
0x180016870  nop
0x180016871  mov     this, rbx; lpCriticalSection
0x180016874  mov     [rsi], edi
0x180016876  mov     edi, 1
0x18001687b  mov     [rsi+4], edi
0x18001687e  add     [rbx+64h], edi
0x180016881  call    cs:__imp_LeaveCriticalSection
0x180016887  mov     this, [rbx+58h]; hHandle
0x18001688b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001688e  call    cs:__imp_WaitForSingleObject
0x180016894  mov     rbx, [rsp+28h+arg_0]
0x180016899  mov     eax, edi
0x18001689b  mov     rsi, [rsp+28h+arg_8]
0x1800168a0  add     rsp, 20h
0x1800168a4  pop     rdi
0x1800168a5  retn
0x1800168a6  mov     edx, edi; dwThreadId
0x1800168a8  mov     this, rbx; this
0x1800168ab  call    ?FindThreadOrFree@XSLOCK@@AEAAPEAUOWNERENTRY@1@K@Z; XSLOCK::FindThreadOrFree(ulong)
0x1800168b0  mov     rsi, rax
0x1800168b3  test    rax, rax
0x1800168b6  jnz     short loc_1800168BF
0x1800168b8  xor     edi, edi
0x1800168ba  jmp     loc_18001680D
0x1800168bf  mov     eax, [rax]
0x1800168c1  nop
0x1800168c2  cmp     eax, edi
0x1800168c4  jnz     short loc_1800168D3
0x1800168c6  mov     edi, 1
0x1800168cb  add     [rsi+4], edi
0x1800168ce  jmp     loc_18001680D
0x1800168d3  cmp     dword ptr [rbx+60h], 0
0x1800168d7  ja      loc_180016847
0x1800168dd  nop
0x1800168de  mov     [rsi], edi
0x1800168e0  mov     edi, 1
0x1800168e5  mov     [rsi+4], edi
0x1800168e8  add     [rbx+30h], edi
0x1800168eb  jmp     loc_18001680D
```
