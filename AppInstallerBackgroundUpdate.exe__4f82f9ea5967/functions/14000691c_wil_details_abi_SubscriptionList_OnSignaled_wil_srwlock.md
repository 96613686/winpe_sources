# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000691c`
- end: `0x1400069d9`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400058a0`
- `0x1400058d0`
- `0x140005980`
- `0x140007ee0`

## callees

- `0x14000691c`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400069a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400069a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006962`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006962`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400069c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400069c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000694c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000694c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140006932`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140006932`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000696b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000696b`

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
0x14000691c  push    rbx
0x14000691e  push    rbp
0x14000691f  push    rsi
0x140006920  push    rdi
0x140006921  push    r14
0x140006923  push    r15
0x140006925  sub     rsp, 28h
0x140006929  mov     rbp, rdx
0x14000692c  mov     rsi, rcx
0x14000692f  mov     rcx, rdx; SRWLock
0x140006932  call    cs:__imp_AcquireSRWLockShared
0x140006938  mov     rdi, [rsi+30h]
0x14000693c  sub     rdi, [rsi+28h]
0x140006940  shr     rdi, 4
0x140006944  test    rbp, rbp
0x140006947  jz      short loc_140006952
0x140006949  mov     rcx, rbp; SRWLock
0x14000694c  call    cs:__imp_ReleaseSRWLockShared
0x140006952  xor     ebx, ebx
0x140006954  test    rdi, rdi
0x140006957  jz      short loc_1400069CC
0x140006959  xor     r14d, r14d
0x14000695c  xor     r15d, r15d
0x14000695f  mov     rcx, rsi; lpCriticalSection
0x140006962  call    cs:__imp_EnterCriticalSection
0x140006968  mov     rcx, rbp; SRWLock
0x14000696b  call    cs:__imp_AcquireSRWLockExclusive
0x140006971  cmp     rbx, rdi
0x140006974  jnb     short loc_14000699B
0x140006976  mov     rdx, [rsi+28h]
0x14000697a  lea     rax, [rbx+1]
0x14000697e  add     rbx, rbx
0x140006981  lea     rcx, [rdx+rbx*8]
0x140006985  mov     rbx, rax
0x140006988  cmp     [rcx], r14
0x14000698b  jnz     short loc_140006994
0x14000698d  cmp     rax, rdi
0x140006990  jb      short loc_14000697A
0x140006992  jmp     short loc_14000699B
0x140006994  mov     r14, [rcx]
0x140006997  mov     r15, [rcx+8]
0x14000699b  test    rbp, rbp
0x14000699e  jz      short loc_1400069A9
0x1400069a0  mov     rcx, rbp; SRWLock
0x1400069a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1400069a9  test    r14, r14
0x1400069ac  jz      short loc_1400069B9
0x1400069ae  mov     rcx, r15
0x1400069b1  mov     rax, r14
0x1400069b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400069b9  test    rsi, rsi
0x1400069bc  jz      short loc_1400069C7
0x1400069be  mov     rcx, rsi; lpCriticalSection
0x1400069c1  call    cs:__imp_LeaveCriticalSection
0x1400069c7  cmp     rbx, rdi
0x1400069ca  jb      short loc_140006959
0x1400069cc  add     rsp, 28h
0x1400069d0  pop     r15
0x1400069d2  pop     r14
0x1400069d4  pop     rdi
0x1400069d5  pop     rsi
0x1400069d6  pop     rbp
0x1400069d7  pop     rbx
0x1400069d8  retn
```
