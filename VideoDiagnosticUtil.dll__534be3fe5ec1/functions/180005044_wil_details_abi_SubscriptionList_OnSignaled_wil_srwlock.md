# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005044`
- end: `0x18000512e`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `234`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002280`
- `0x1800022b0`
- `0x180002360`
- `0x1800074b0`

## callees

- `0x180005044`
- `0x18000a010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800050a9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800050a9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800050e7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800050e7`
- `KERNEL32!AcquireSRWLockShared` at `0x18000505a`
- `KERNEL32!AcquireSRWLockShared` at `0x18000505a`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000507a`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000507a`
- `KERNEL32!LeaveCriticalSection` at `0x18000510b`
- `KERNEL32!LeaveCriticalSection` at `0x18000510b`
- `KERNEL32!EnterCriticalSection` at `0x18000509a`
- `KERNEL32!EnterCriticalSection` at `0x18000509a`

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
0x180005044  push    rbx
0x180005046  push    rbp
0x180005047  push    rsi
0x180005048  push    rdi
0x180005049  push    r14
0x18000504b  push    r15
0x18000504d  sub     rsp, 28h
0x180005051  mov     rsi, rcx
0x180005054  mov     rbp, rdx
0x180005057  mov     rcx, rdx; SRWLock
0x18000505a  call    cs:__imp_AcquireSRWLockShared
0x180005061  nop     dword ptr [rax+rax+00h]
0x180005066  mov     rdi, [rsi+30h]
0x18000506a  sub     rdi, [rsi+28h]
0x18000506e  shr     rdi, 4
0x180005072  test    rbp, rbp
0x180005075  jz      short loc_180005086
0x180005077  mov     rcx, rbp; SRWLock
0x18000507a  call    cs:__imp_ReleaseSRWLockShared
0x180005081  nop     dword ptr [rax+rax+00h]
0x180005086  xor     ebx, ebx
0x180005088  test    rdi, rdi
0x18000508b  jz      loc_180005120
0x180005091  mov     rcx, rsi; lpCriticalSection
0x180005094  xor     r14d, r14d
0x180005097  xor     r15d, r15d
0x18000509a  call    cs:__imp_EnterCriticalSection
0x1800050a1  nop     dword ptr [rax+rax+00h]
0x1800050a6  mov     rcx, rbp; SRWLock
0x1800050a9  call    cs:__imp_AcquireSRWLockExclusive
0x1800050b0  nop     dword ptr [rax+rax+00h]
0x1800050b5  cmp     rbx, rdi
0x1800050b8  jnb     short loc_1800050DF
0x1800050ba  mov     rdx, [rsi+28h]
0x1800050be  lea     rax, [rbx+1]
0x1800050c2  add     rbx, rbx
0x1800050c5  lea     rcx, [rdx+rbx*8]
0x1800050c9  mov     rbx, rax
0x1800050cc  cmp     [rcx], r14
0x1800050cf  jnz     short loc_1800050D8
0x1800050d1  cmp     rax, rdi
0x1800050d4  jb      short loc_1800050BE
0x1800050d6  jmp     short loc_1800050DF
0x1800050d8  mov     r14, [rcx]
0x1800050db  mov     r15, [rcx+8]
0x1800050df  test    rbp, rbp
0x1800050e2  jz      short loc_1800050F3
0x1800050e4  mov     rcx, rbp; SRWLock
0x1800050e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800050ee  nop     dword ptr [rax+rax+00h]
0x1800050f3  test    r14, r14
0x1800050f6  jz      short loc_180005103
0x1800050f8  mov     rcx, r15
0x1800050fb  mov     rax, r14
0x1800050fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005103  test    rsi, rsi
0x180005106  jz      short loc_180005117
0x180005108  mov     rcx, rsi; lpCriticalSection
0x18000510b  call    cs:__imp_LeaveCriticalSection
0x180005112  nop     dword ptr [rax+rax+00h]
0x180005117  cmp     rbx, rdi
0x18000511a  jb      loc_180005091
0x180005120  add     rsp, 28h
0x180005124  pop     r15
0x180005126  pop     r14
0x180005128  pop     rdi
0x180005129  pop     rsi
0x18000512a  pop     rbp
0x18000512b  pop     rbx
0x18000512c  retn
```
