# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005ad4`
- end: `0x180005b91`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800021e0`
- `0x180002210`
- `0x1800022c0`
- `0x180008230`

## callees

- `0x180005ad4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005b23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005b23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005b5b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005aea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005aea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005b04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005b04`

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
0x180005ad4  push    rbx
0x180005ad6  push    rbp
0x180005ad7  push    rsi
0x180005ad8  push    rdi
0x180005ad9  push    r14
0x180005adb  push    r15
0x180005add  sub     rsp, 28h
0x180005ae1  mov     rbp, rdx
0x180005ae4  mov     rsi, rcx
0x180005ae7  mov     rcx, rdx; SRWLock
0x180005aea  call    cs:__imp_AcquireSRWLockShared
0x180005af0  mov     rdi, [rsi+30h]
0x180005af4  sub     rdi, [rsi+28h]
0x180005af8  shr     rdi, 4
0x180005afc  test    rbp, rbp
0x180005aff  jz      short loc_180005B0A
0x180005b01  mov     rcx, rbp; SRWLock
0x180005b04  call    cs:__imp_ReleaseSRWLockShared
0x180005b0a  xor     ebx, ebx
0x180005b0c  test    rdi, rdi
0x180005b0f  jz      short loc_180005B84
0x180005b11  xor     r14d, r14d
0x180005b14  xor     r15d, r15d
0x180005b17  mov     rcx, rsi; lpCriticalSection
0x180005b1a  call    cs:__imp_EnterCriticalSection
0x180005b20  mov     rcx, rbp; SRWLock
0x180005b23  call    cs:__imp_AcquireSRWLockExclusive
0x180005b29  cmp     rbx, rdi
0x180005b2c  jnb     short loc_180005B53
0x180005b2e  mov     rdx, [rsi+28h]
0x180005b32  lea     rax, [rbx+1]
0x180005b36  add     rbx, rbx
0x180005b39  lea     rcx, [rdx+rbx*8]
0x180005b3d  mov     rbx, rax
0x180005b40  cmp     [rcx], r14
0x180005b43  jnz     short loc_180005B4C
0x180005b45  cmp     rax, rdi
0x180005b48  jb      short loc_180005B32
0x180005b4a  jmp     short loc_180005B53
0x180005b4c  mov     r14, [rcx]
0x180005b4f  mov     r15, [rcx+8]
0x180005b53  test    rbp, rbp
0x180005b56  jz      short loc_180005B61
0x180005b58  mov     rcx, rbp; SRWLock
0x180005b5b  call    cs:__imp_ReleaseSRWLockExclusive
0x180005b61  test    r14, r14
0x180005b64  jz      short loc_180005B71
0x180005b66  mov     rcx, r15
0x180005b69  mov     rax, r14
0x180005b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b71  test    rsi, rsi
0x180005b74  jz      short loc_180005B7F
0x180005b76  mov     rcx, rsi; lpCriticalSection
0x180005b79  call    cs:__imp_LeaveCriticalSection
0x180005b7f  cmp     rbx, rdi
0x180005b82  jb      short loc_180005B11
0x180005b84  add     rsp, 28h
0x180005b88  pop     r15
0x180005b8a  pop     r14
0x180005b8c  pop     rdi
0x180005b8d  pop     rsi
0x180005b8e  pop     rbp
0x180005b8f  pop     rbx
0x180005b90  retn
```
