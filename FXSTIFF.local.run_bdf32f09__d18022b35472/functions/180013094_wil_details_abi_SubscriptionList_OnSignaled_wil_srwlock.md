# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180013094`
- end: `0x180013153`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `191`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f7b0`
- `0x18000f7e0`
- `0x18000f890`
- `0x180015630`

## callees

- `0x180013094`
- `0x180019010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800130dc`
- `KERNEL32!EnterCriticalSection` at `0x1800130dc`
- `KERNEL32!LeaveCriticalSection` at `0x18001313b`
- `KERNEL32!LeaveCriticalSection` at `0x18001313b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001311d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001311d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800130e5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800130e5`
- `KERNEL32!AcquireSRWLockShared` at `0x1800130aa`
- `KERNEL32!AcquireSRWLockShared` at `0x1800130aa`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800130c5`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800130c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180013094  push    rbx
0x180013096  push    rbp
0x180013097  push    rsi
0x180013098  push    rdi
0x180013099  push    r14
0x18001309b  push    r15
0x18001309d  sub     rsp, 28h
0x1800130a1  mov     rbp, rdx
0x1800130a4  mov     rsi, rcx
0x1800130a7  mov     rcx, rdx; SRWLock
0x1800130aa  call    cs:__imp_AcquireSRWLockShared
0x1800130b0  nop
0x1800130b1  mov     rdi, [rsi+30h]
0x1800130b5  sub     rdi, [rsi+28h]
0x1800130b9  shr     rdi, 4
0x1800130bd  test    rbp, rbp
0x1800130c0  jz      short loc_1800130CC
0x1800130c2  mov     rcx, rbp; SRWLock
0x1800130c5  call    cs:__imp_ReleaseSRWLockShared
0x1800130cb  nop
0x1800130cc  xor     ebx, ebx
0x1800130ce  test    rdi, rdi
0x1800130d1  jz      short loc_180013146
0x1800130d3  xor     r14d, r14d
0x1800130d6  xor     r15d, r15d
0x1800130d9  mov     rcx, rsi; lpCriticalSection
0x1800130dc  call    cs:__imp_EnterCriticalSection
0x1800130e2  mov     rcx, rbp; SRWLock
0x1800130e5  call    cs:__imp_AcquireSRWLockExclusive
0x1800130eb  cmp     rbx, rdi
0x1800130ee  jnb     short loc_180013115
0x1800130f0  mov     rdx, [rsi+28h]
0x1800130f4  lea     rax, [rbx+1]
0x1800130f8  add     rbx, rbx
0x1800130fb  lea     rcx, [rdx+rbx*8]
0x1800130ff  mov     rbx, rax
0x180013102  cmp     [rcx], r14
0x180013105  jnz     short loc_18001310E
0x180013107  cmp     rax, rdi
0x18001310a  jb      short loc_1800130F4
0x18001310c  jmp     short loc_180013115
0x18001310e  mov     r14, [rcx]
0x180013111  mov     r15, [rcx+8]
0x180013115  test    rbp, rbp
0x180013118  jz      short loc_180013123
0x18001311a  mov     rcx, rbp; SRWLock
0x18001311d  call    cs:__imp_ReleaseSRWLockExclusive
0x180013123  test    r14, r14
0x180013126  jz      short loc_180013133
0x180013128  mov     rcx, r15
0x18001312b  mov     rax, r14
0x18001312e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013133  test    rsi, rsi
0x180013136  jz      short loc_180013141
0x180013138  mov     rcx, rsi; lpCriticalSection
0x18001313b  call    cs:__imp_LeaveCriticalSection
0x180013141  cmp     rbx, rdi
0x180013144  jb      short loc_1800130D3
0x180013146  add     rsp, 28h
0x18001314a  pop     r15
0x18001314c  pop     r14
0x18001314e  pop     rdi
0x18001314f  pop     rsi
0x180013150  pop     rbp
0x180013151  pop     rbx
0x180013152  retn
```
