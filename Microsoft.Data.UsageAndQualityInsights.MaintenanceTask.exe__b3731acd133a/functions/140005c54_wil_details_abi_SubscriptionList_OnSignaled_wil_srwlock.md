# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140005c54`
- end: `0x140005d11`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400023f0`
- `0x140002420`
- `0x140002450`
- `0x1400085b0`

## callees

- `0x140005c54`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005ca3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005ca3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140005c6a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140005c6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140005c84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140005c84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005cdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005cdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005c9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005c9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005cf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005cf9`

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
0x140005c54  push    rbx
0x140005c56  push    rbp
0x140005c57  push    rsi
0x140005c58  push    rdi
0x140005c59  push    r14
0x140005c5b  push    r15
0x140005c5d  sub     rsp, 28h
0x140005c61  mov     rbp, rdx
0x140005c64  mov     rsi, rcx
0x140005c67  mov     rcx, rdx; SRWLock
0x140005c6a  call    cs:__imp_AcquireSRWLockShared
0x140005c70  mov     rdi, [rsi+30h]
0x140005c74  sub     rdi, [rsi+28h]
0x140005c78  shr     rdi, 4
0x140005c7c  test    rbp, rbp
0x140005c7f  jz      short loc_140005C8A
0x140005c81  mov     rcx, rbp; SRWLock
0x140005c84  call    cs:__imp_ReleaseSRWLockShared
0x140005c8a  xor     ebx, ebx
0x140005c8c  test    rdi, rdi
0x140005c8f  jz      short loc_140005D04
0x140005c91  xor     r14d, r14d
0x140005c94  xor     r15d, r15d
0x140005c97  mov     rcx, rsi; lpCriticalSection
0x140005c9a  call    cs:__imp_EnterCriticalSection
0x140005ca0  mov     rcx, rbp; SRWLock
0x140005ca3  call    cs:__imp_AcquireSRWLockExclusive
0x140005ca9  cmp     rbx, rdi
0x140005cac  jnb     short loc_140005CD3
0x140005cae  mov     rdx, [rsi+28h]
0x140005cb2  lea     rax, [rbx+1]
0x140005cb6  add     rbx, rbx
0x140005cb9  lea     rcx, [rdx+rbx*8]
0x140005cbd  mov     rbx, rax
0x140005cc0  cmp     [rcx], r14
0x140005cc3  jnz     short loc_140005CCC
0x140005cc5  cmp     rax, rdi
0x140005cc8  jb      short loc_140005CB2
0x140005cca  jmp     short loc_140005CD3
0x140005ccc  mov     r14, [rcx]
0x140005ccf  mov     r15, [rcx+8]
0x140005cd3  test    rbp, rbp
0x140005cd6  jz      short loc_140005CE1
0x140005cd8  mov     rcx, rbp; SRWLock
0x140005cdb  call    cs:__imp_ReleaseSRWLockExclusive
0x140005ce1  test    r14, r14
0x140005ce4  jz      short loc_140005CF1
0x140005ce6  mov     rcx, r15
0x140005ce9  mov     rax, r14
0x140005cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cf1  test    rsi, rsi
0x140005cf4  jz      short loc_140005CFF
0x140005cf6  mov     rcx, rsi; lpCriticalSection
0x140005cf9  call    cs:__imp_LeaveCriticalSection
0x140005cff  cmp     rbx, rdi
0x140005d02  jb      short loc_140005C91
0x140005d04  add     rsp, 28h
0x140005d08  pop     r15
0x140005d0a  pop     r14
0x140005d0c  pop     rdi
0x140005d0d  pop     rsi
0x140005d0e  pop     rbp
0x140005d0f  pop     rbx
0x140005d10  retn
```
