# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14001461c`
- end: `0x1400146d9`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400122b0`
- `0x1400122e0`
- `0x140012310`
- `0x140015eb0`

## callees

- `0x14001461c`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400146c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400146c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001466b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001466b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140014632`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140014632`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001464c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001464c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140014662`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140014662`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400146a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400146a3`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // r14
  __int64 v7; // r15
  unsigned __int64 v8; // rax
  WORD *v9; // rcx

  AcquireSRWLockShared(SRWLock);
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = 0;
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    AcquireSRWLockExclusive(SRWLock);
    if ( v5 < v4 )
    {
      while ( 1 )
      {
        v8 = v5 + 1;
        v9 = &lpCriticalSection[1].DebugInfo->Type + 8 * v5++;
        if ( *(_QWORD *)v9 )
          break;
        if ( v8 >= v4 )
          goto LABEL_9;
      }
      v6 = *(void (__fastcall **)(__int64))v9;
      v7 = *((_QWORD *)v9 + 1);
    }
LABEL_9:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( v6 )
      v6(v7);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x14001461c  push    rbx
0x14001461e  push    rbp
0x14001461f  push    rsi
0x140014620  push    rdi
0x140014621  push    r14
0x140014623  push    r15
0x140014625  sub     rsp, 28h
0x140014629  mov     rbp, rdx
0x14001462c  mov     rsi, rcx
0x14001462f  mov     rcx, rdx; SRWLock
0x140014632  call    cs:__imp_AcquireSRWLockShared
0x140014638  mov     rdi, [rsi+30h]
0x14001463c  sub     rdi, [rsi+28h]
0x140014640  shr     rdi, 4
0x140014644  test    rbp, rbp
0x140014647  jz      short loc_140014652
0x140014649  mov     rcx, rbp; SRWLock
0x14001464c  call    cs:__imp_ReleaseSRWLockShared
0x140014652  xor     ebx, ebx
0x140014654  test    rdi, rdi
0x140014657  jz      short loc_1400146CC
0x140014659  xor     r14d, r14d
0x14001465c  xor     r15d, r15d
0x14001465f  mov     rcx, rsi; lpCriticalSection
0x140014662  call    cs:__imp_EnterCriticalSection
0x140014668  mov     rcx, rbp; SRWLock
0x14001466b  call    cs:__imp_AcquireSRWLockExclusive
0x140014671  cmp     rbx, rdi
0x140014674  jnb     short loc_14001469B
0x140014676  mov     rdx, [rsi+28h]
0x14001467a  lea     rax, [rbx+1]
0x14001467e  add     rbx, rbx
0x140014681  lea     rcx, [rdx+rbx*8]
0x140014685  mov     rbx, rax
0x140014688  cmp     [rcx], r14
0x14001468b  jnz     short loc_140014694
0x14001468d  cmp     rax, rdi
0x140014690  jb      short loc_14001467A
0x140014692  jmp     short loc_14001469B
0x140014694  mov     r14, [rcx]
0x140014697  mov     r15, [rcx+8]
0x14001469b  test    rbp, rbp
0x14001469e  jz      short loc_1400146A9
0x1400146a0  mov     rcx, rbp; SRWLock
0x1400146a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1400146a9  test    r14, r14
0x1400146ac  jz      short loc_1400146B9
0x1400146ae  mov     rcx, r15
0x1400146b1  mov     rax, r14
0x1400146b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400146b9  test    rsi, rsi
0x1400146bc  jz      short loc_1400146C7
0x1400146be  mov     rcx, rsi; lpCriticalSection
0x1400146c1  call    cs:__imp_LeaveCriticalSection
0x1400146c7  cmp     rbx, rdi
0x1400146ca  jb      short loc_140014659
0x1400146cc  add     rsp, 28h
0x1400146d0  pop     r15
0x1400146d2  pop     r14
0x1400146d4  pop     rdi
0x1400146d5  pop     rsi
0x1400146d6  pop     rbp
0x1400146d7  pop     rbx
0x1400146d8  retn
```
