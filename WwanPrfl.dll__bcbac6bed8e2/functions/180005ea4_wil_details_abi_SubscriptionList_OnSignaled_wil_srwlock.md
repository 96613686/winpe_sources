# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005ea4`
- end: `0x180005f61`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002360`
- `0x180002390`
- `0x180002420`
- `0x180008c30`

## callees

- `0x180005ea4`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005eba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005eba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005ed4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005ed4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005eea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005eea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ef3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ef3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f49`

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
0x180005ea4  push    rbx
0x180005ea6  push    rbp
0x180005ea7  push    rsi
0x180005ea8  push    rdi
0x180005ea9  push    r14
0x180005eab  push    r15
0x180005ead  sub     rsp, 28h
0x180005eb1  mov     rbp, rdx
0x180005eb4  mov     rsi, rcx
0x180005eb7  mov     rcx, rdx; SRWLock
0x180005eba  call    cs:__imp_AcquireSRWLockShared
0x180005ec0  mov     rdi, [rsi+30h]
0x180005ec4  sub     rdi, [rsi+28h]
0x180005ec8  shr     rdi, 4
0x180005ecc  test    rbp, rbp
0x180005ecf  jz      short loc_180005EDA
0x180005ed1  mov     rcx, rbp; SRWLock
0x180005ed4  call    cs:__imp_ReleaseSRWLockShared
0x180005eda  xor     ebx, ebx
0x180005edc  test    rdi, rdi
0x180005edf  jz      short loc_180005F54
0x180005ee1  xor     r14d, r14d
0x180005ee4  xor     r15d, r15d
0x180005ee7  mov     rcx, rsi; lpCriticalSection
0x180005eea  call    cs:__imp_EnterCriticalSection
0x180005ef0  mov     rcx, rbp; SRWLock
0x180005ef3  call    cs:__imp_AcquireSRWLockExclusive
0x180005ef9  cmp     rbx, rdi
0x180005efc  jnb     short loc_180005F23
0x180005efe  mov     rdx, [rsi+28h]
0x180005f02  lea     rax, [rbx+1]
0x180005f06  add     rbx, rbx
0x180005f09  lea     rcx, [rdx+rbx*8]
0x180005f0d  mov     rbx, rax
0x180005f10  cmp     [rcx], r14
0x180005f13  jnz     short loc_180005F1C
0x180005f15  cmp     rax, rdi
0x180005f18  jb      short loc_180005F02
0x180005f1a  jmp     short loc_180005F23
0x180005f1c  mov     r14, [rcx]
0x180005f1f  mov     r15, [rcx+8]
0x180005f23  test    rbp, rbp
0x180005f26  jz      short loc_180005F31
0x180005f28  mov     rcx, rbp; SRWLock
0x180005f2b  call    cs:__imp_ReleaseSRWLockExclusive
0x180005f31  test    r14, r14
0x180005f34  jz      short loc_180005F41
0x180005f36  mov     rcx, r15
0x180005f39  mov     rax, r14
0x180005f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f41  test    rsi, rsi
0x180005f44  jz      short loc_180005F4F
0x180005f46  mov     rcx, rsi; lpCriticalSection
0x180005f49  call    cs:__imp_LeaveCriticalSection
0x180005f4f  cmp     rbx, rdi
0x180005f52  jb      short loc_180005EE1
0x180005f54  add     rsp, 28h
0x180005f58  pop     r15
0x180005f5a  pop     r14
0x180005f5c  pop     rdi
0x180005f5d  pop     rsi
0x180005f5e  pop     rbp
0x180005f5f  pop     rbx
0x180005f60  retn
```
