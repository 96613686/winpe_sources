# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1800093ec`
- end: `0x1800094a9`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007600`
- `0x180007630`
- `0x1800076e0`
- `0x18000abf0`

## callees

- `0x1800093ec`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009473`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009473`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009491`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009491`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009402`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009402`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000941c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000941c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000943b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000943b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009432`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009432`

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
0x1800093ec  push    rbx
0x1800093ee  push    rbp
0x1800093ef  push    rsi
0x1800093f0  push    rdi
0x1800093f1  push    r14
0x1800093f3  push    r15
0x1800093f5  sub     rsp, 28h
0x1800093f9  mov     rbp, rdx
0x1800093fc  mov     rsi, rcx
0x1800093ff  mov     rcx, rdx; SRWLock
0x180009402  call    cs:__imp_AcquireSRWLockShared
0x180009408  mov     rdi, [rsi+30h]
0x18000940c  sub     rdi, [rsi+28h]
0x180009410  shr     rdi, 4
0x180009414  test    rbp, rbp
0x180009417  jz      short loc_180009422
0x180009419  mov     rcx, rbp; SRWLock
0x18000941c  call    cs:__imp_ReleaseSRWLockShared
0x180009422  xor     ebx, ebx
0x180009424  test    rdi, rdi
0x180009427  jz      short loc_18000949C
0x180009429  xor     r14d, r14d
0x18000942c  xor     r15d, r15d
0x18000942f  mov     rcx, rsi; lpCriticalSection
0x180009432  call    cs:__imp_EnterCriticalSection
0x180009438  mov     rcx, rbp; SRWLock
0x18000943b  call    cs:__imp_AcquireSRWLockExclusive
0x180009441  cmp     rbx, rdi
0x180009444  jnb     short loc_18000946B
0x180009446  mov     rdx, [rsi+28h]
0x18000944a  lea     rax, [rbx+1]
0x18000944e  add     rbx, rbx
0x180009451  lea     rcx, [rdx+rbx*8]
0x180009455  mov     rbx, rax
0x180009458  cmp     [rcx], r14
0x18000945b  jnz     short loc_180009464
0x18000945d  cmp     rax, rdi
0x180009460  jb      short loc_18000944A
0x180009462  jmp     short loc_18000946B
0x180009464  mov     r14, [rcx]
0x180009467  mov     r15, [rcx+8]
0x18000946b  test    rbp, rbp
0x18000946e  jz      short loc_180009479
0x180009470  mov     rcx, rbp; SRWLock
0x180009473  call    cs:__imp_ReleaseSRWLockExclusive
0x180009479  test    r14, r14
0x18000947c  jz      short loc_180009489
0x18000947e  mov     rcx, r15
0x180009481  mov     rax, r14
0x180009484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009489  test    rsi, rsi
0x18000948c  jz      short loc_180009497
0x18000948e  mov     rcx, rsi; lpCriticalSection
0x180009491  call    cs:__imp_LeaveCriticalSection
0x180009497  cmp     rbx, rdi
0x18000949a  jb      short loc_180009429
0x18000949c  add     rsp, 28h
0x1800094a0  pop     r15
0x1800094a2  pop     r14
0x1800094a4  pop     rdi
0x1800094a5  pop     rsi
0x1800094a6  pop     rbp
0x1800094a7  pop     rbx
0x1800094a8  retn
```
