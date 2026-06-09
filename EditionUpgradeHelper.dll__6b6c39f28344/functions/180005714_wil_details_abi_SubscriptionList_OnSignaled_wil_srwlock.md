# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005714`
- end: `0x1800057d1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002550`
- `0x180002580`
- `0x180002630`
- `0x180007640`

## callees

- `0x180005714`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000575a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000575a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800057b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800057b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000572a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000572a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005744`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005744`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005763`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005763`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000579b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000579b`

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
0x180005714  push    rbx
0x180005716  push    rbp
0x180005717  push    rsi
0x180005718  push    rdi
0x180005719  push    r14
0x18000571b  push    r15
0x18000571d  sub     rsp, 28h
0x180005721  mov     rsi, rcx
0x180005724  mov     rbp, rdx
0x180005727  mov     rcx, rdx; SRWLock
0x18000572a  call    cs:__imp_AcquireSRWLockShared
0x180005730  mov     rdi, [rsi+30h]
0x180005734  sub     rdi, [rsi+28h]
0x180005738  shr     rdi, 4
0x18000573c  test    rbp, rbp
0x18000573f  jz      short loc_18000574A
0x180005741  mov     rcx, rbp; SRWLock
0x180005744  call    cs:__imp_ReleaseSRWLockShared
0x18000574a  xor     ebx, ebx
0x18000574c  test    rdi, rdi
0x18000574f  jz      short loc_1800057C4
0x180005751  mov     rcx, rsi; lpCriticalSection
0x180005754  xor     r14d, r14d
0x180005757  xor     r15d, r15d
0x18000575a  call    cs:__imp_EnterCriticalSection
0x180005760  mov     rcx, rbp; SRWLock
0x180005763  call    cs:__imp_AcquireSRWLockExclusive
0x180005769  cmp     rbx, rdi
0x18000576c  jnb     short loc_180005793
0x18000576e  mov     rdx, [rsi+28h]
0x180005772  lea     rax, [rbx+1]
0x180005776  add     rbx, rbx
0x180005779  lea     rcx, [rdx+rbx*8]
0x18000577d  mov     rbx, rax
0x180005780  cmp     [rcx], r14
0x180005783  jnz     short loc_18000578C
0x180005785  cmp     rax, rdi
0x180005788  jb      short loc_180005772
0x18000578a  jmp     short loc_180005793
0x18000578c  mov     r14, [rcx]
0x18000578f  mov     r15, [rcx+8]
0x180005793  test    rbp, rbp
0x180005796  jz      short loc_1800057A1
0x180005798  mov     rcx, rbp; SRWLock
0x18000579b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800057a1  test    r14, r14
0x1800057a4  jz      short loc_1800057B1
0x1800057a6  mov     rcx, r15
0x1800057a9  mov     rax, r14
0x1800057ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b1  test    rsi, rsi
0x1800057b4  jz      short loc_1800057BF
0x1800057b6  mov     rcx, rsi; lpCriticalSection
0x1800057b9  call    cs:__imp_LeaveCriticalSection
0x1800057bf  cmp     rbx, rdi
0x1800057c2  jb      short loc_180005751
0x1800057c4  add     rsp, 28h
0x1800057c8  pop     r15
0x1800057ca  pop     r14
0x1800057cc  pop     rdi
0x1800057cd  pop     rsi
0x1800057ce  pop     rbp
0x1800057cf  pop     rbx
0x1800057d0  retn
```
