# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000cacc`
- end: `0x18000cb89`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009390`
- `0x1800093c0`
- `0x180009470`
- `0x18000e610`

## callees

- `0x18000cacc`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cb71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cb71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cae2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cae2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cb12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cb12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cb53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cb53`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cb1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cb1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cafc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cafc`

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
0x18000cacc  push    rbx
0x18000cace  push    rbp
0x18000cacf  push    rsi
0x18000cad0  push    rdi
0x18000cad1  push    r14
0x18000cad3  push    r15
0x18000cad5  sub     rsp, 28h
0x18000cad9  mov     rbp, rdx
0x18000cadc  mov     rsi, rcx
0x18000cadf  mov     rcx, rdx; SRWLock
0x18000cae2  call    cs:__imp_AcquireSRWLockShared
0x18000cae8  mov     rdi, [rsi+30h]
0x18000caec  sub     rdi, [rsi+28h]
0x18000caf0  shr     rdi, 4
0x18000caf4  test    rbp, rbp
0x18000caf7  jz      short loc_18000CB02
0x18000caf9  mov     rcx, rbp; SRWLock
0x18000cafc  call    cs:__imp_ReleaseSRWLockShared
0x18000cb02  xor     ebx, ebx
0x18000cb04  test    rdi, rdi
0x18000cb07  jz      short loc_18000CB7C
0x18000cb09  xor     r14d, r14d
0x18000cb0c  xor     r15d, r15d
0x18000cb0f  mov     rcx, rsi; lpCriticalSection
0x18000cb12  call    cs:__imp_EnterCriticalSection
0x18000cb18  mov     rcx, rbp; SRWLock
0x18000cb1b  call    cs:__imp_AcquireSRWLockExclusive
0x18000cb21  cmp     rbx, rdi
0x18000cb24  jnb     short loc_18000CB4B
0x18000cb26  mov     rdx, [rsi+28h]
0x18000cb2a  lea     rax, [rbx+1]
0x18000cb2e  add     rbx, rbx
0x18000cb31  lea     rcx, [rdx+rbx*8]
0x18000cb35  mov     rbx, rax
0x18000cb38  cmp     [rcx], r14
0x18000cb3b  jnz     short loc_18000CB44
0x18000cb3d  cmp     rax, rdi
0x18000cb40  jb      short loc_18000CB2A
0x18000cb42  jmp     short loc_18000CB4B
0x18000cb44  mov     r14, [rcx]
0x18000cb47  mov     r15, [rcx+8]
0x18000cb4b  test    rbp, rbp
0x18000cb4e  jz      short loc_18000CB59
0x18000cb50  mov     rcx, rbp; SRWLock
0x18000cb53  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cb59  test    r14, r14
0x18000cb5c  jz      short loc_18000CB69
0x18000cb5e  mov     rcx, r15
0x18000cb61  mov     rax, r14
0x18000cb64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb69  test    rsi, rsi
0x18000cb6c  jz      short loc_18000CB77
0x18000cb6e  mov     rcx, rsi; lpCriticalSection
0x18000cb71  call    cs:__imp_LeaveCriticalSection
0x18000cb77  cmp     rbx, rdi
0x18000cb7a  jb      short loc_18000CB09
0x18000cb7c  add     rsp, 28h
0x18000cb80  pop     r15
0x18000cb82  pop     r14
0x18000cb84  pop     rdi
0x18000cb85  pop     rsi
0x18000cb86  pop     rbp
0x18000cb87  pop     rbx
0x18000cb88  retn
```
