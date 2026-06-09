# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140009164`
- end: `0x140009221`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140006910`
- `0x140006940`
- `0x1400069f0`
- `0x14000b650`

## callees

- `0x140009164`
- `0x140011010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140009209`
- `KERNEL32!LeaveCriticalSection` at `0x140009209`
- `KERNEL32!EnterCriticalSection` at `0x1400091aa`
- `KERNEL32!EnterCriticalSection` at `0x1400091aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400091eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400091eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400091b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400091b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140009194`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140009194`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000917a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000917a`

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
0x140009164  push    rbx
0x140009166  push    rbp
0x140009167  push    rsi
0x140009168  push    rdi
0x140009169  push    r14
0x14000916b  push    r15
0x14000916d  sub     rsp, 28h
0x140009171  mov     rbp, rdx
0x140009174  mov     rsi, rcx
0x140009177  mov     rcx, rdx; SRWLock
0x14000917a  call    cs:__imp_AcquireSRWLockShared
0x140009180  mov     rdi, [rsi+30h]
0x140009184  sub     rdi, [rsi+28h]
0x140009188  shr     rdi, 4
0x14000918c  test    rbp, rbp
0x14000918f  jz      short loc_14000919A
0x140009191  mov     rcx, rbp; SRWLock
0x140009194  call    cs:__imp_ReleaseSRWLockShared
0x14000919a  xor     ebx, ebx
0x14000919c  test    rdi, rdi
0x14000919f  jz      short loc_140009214
0x1400091a1  xor     r14d, r14d
0x1400091a4  xor     r15d, r15d
0x1400091a7  mov     rcx, rsi; lpCriticalSection
0x1400091aa  call    cs:__imp_EnterCriticalSection
0x1400091b0  mov     rcx, rbp; SRWLock
0x1400091b3  call    cs:__imp_AcquireSRWLockExclusive
0x1400091b9  cmp     rbx, rdi
0x1400091bc  jnb     short loc_1400091E3
0x1400091be  mov     rdx, [rsi+28h]
0x1400091c2  lea     rax, [rbx+1]
0x1400091c6  add     rbx, rbx
0x1400091c9  lea     rcx, [rdx+rbx*8]
0x1400091cd  mov     rbx, rax
0x1400091d0  cmp     [rcx], r14
0x1400091d3  jnz     short loc_1400091DC
0x1400091d5  cmp     rax, rdi
0x1400091d8  jb      short loc_1400091C2
0x1400091da  jmp     short loc_1400091E3
0x1400091dc  mov     r14, [rcx]
0x1400091df  mov     r15, [rcx+8]
0x1400091e3  test    rbp, rbp
0x1400091e6  jz      short loc_1400091F1
0x1400091e8  mov     rcx, rbp; SRWLock
0x1400091eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1400091f1  test    r14, r14
0x1400091f4  jz      short loc_140009201
0x1400091f6  mov     rcx, r15
0x1400091f9  mov     rax, r14
0x1400091fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009201  test    rsi, rsi
0x140009204  jz      short loc_14000920F
0x140009206  mov     rcx, rsi; lpCriticalSection
0x140009209  call    cs:__imp_LeaveCriticalSection
0x14000920f  cmp     rbx, rdi
0x140009212  jb      short loc_1400091A1
0x140009214  add     rsp, 28h
0x140009218  pop     r15
0x14000921a  pop     r14
0x14000921c  pop     rdi
0x14000921d  pop     rsi
0x14000921e  pop     rbp
0x14000921f  pop     rbx
0x140009220  retn
```
