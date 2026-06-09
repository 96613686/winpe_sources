# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1800053f4`
- end: `0x1800054b1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ee0`
- `0x180001f10`
- `0x180001fc0`
- `0x180007710`

## callees

- `0x1800053f4`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005499`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005499`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005424`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005424`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000543a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000543a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000547b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000547b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000540a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000540a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005443`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005443`

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
0x1800053f4  push    rbx
0x1800053f6  push    rbp
0x1800053f7  push    rsi
0x1800053f8  push    rdi
0x1800053f9  push    r14
0x1800053fb  push    r15
0x1800053fd  sub     rsp, 28h
0x180005401  mov     rsi, rcx
0x180005404  mov     rbp, rdx
0x180005407  mov     rcx, rdx; SRWLock
0x18000540a  call    cs:__imp_AcquireSRWLockShared
0x180005410  mov     rdi, [rsi+30h]
0x180005414  sub     rdi, [rsi+28h]
0x180005418  shr     rdi, 4
0x18000541c  test    rbp, rbp
0x18000541f  jz      short loc_18000542A
0x180005421  mov     rcx, rbp; SRWLock
0x180005424  call    cs:__imp_ReleaseSRWLockShared
0x18000542a  xor     ebx, ebx
0x18000542c  test    rdi, rdi
0x18000542f  jz      short loc_1800054A4
0x180005431  mov     rcx, rsi; lpCriticalSection
0x180005434  xor     r14d, r14d
0x180005437  xor     r15d, r15d
0x18000543a  call    cs:__imp_EnterCriticalSection
0x180005440  mov     rcx, rbp; SRWLock
0x180005443  call    cs:__imp_AcquireSRWLockExclusive
0x180005449  cmp     rbx, rdi
0x18000544c  jnb     short loc_180005473
0x18000544e  mov     rdx, [rsi+28h]
0x180005452  lea     rax, [rbx+1]
0x180005456  add     rbx, rbx
0x180005459  lea     rcx, [rdx+rbx*8]
0x18000545d  mov     rbx, rax
0x180005460  cmp     [rcx], r14
0x180005463  jnz     short loc_18000546C
0x180005465  cmp     rax, rdi
0x180005468  jb      short loc_180005452
0x18000546a  jmp     short loc_180005473
0x18000546c  mov     r14, [rcx]
0x18000546f  mov     r15, [rcx+8]
0x180005473  test    rbp, rbp
0x180005476  jz      short loc_180005481
0x180005478  mov     rcx, rbp; SRWLock
0x18000547b  call    cs:__imp_ReleaseSRWLockExclusive
0x180005481  test    r14, r14
0x180005484  jz      short loc_180005491
0x180005486  mov     rcx, r15
0x180005489  mov     rax, r14
0x18000548c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005491  test    rsi, rsi
0x180005494  jz      short loc_18000549F
0x180005496  mov     rcx, rsi; lpCriticalSection
0x180005499  call    cs:__imp_LeaveCriticalSection
0x18000549f  cmp     rbx, rdi
0x1800054a2  jb      short loc_180005431
0x1800054a4  add     rsp, 28h
0x1800054a8  pop     r15
0x1800054aa  pop     r14
0x1800054ac  pop     rdi
0x1800054ad  pop     rsi
0x1800054ae  pop     rbp
0x1800054af  pop     rbx
0x1800054b0  retn
```
