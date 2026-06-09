# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180006180`
- end: `0x18000626a`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `234`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002070`
- `0x1800020a0`
- `0x180002150`
- `0x180009060`

## callees

- `0x180006180`
- `0x18003e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800061d6`
- `KERNEL32!EnterCriticalSection` at `0x1800061d6`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800061b6`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800061b6`
- `KERNEL32!AcquireSRWLockShared` at `0x180006196`
- `KERNEL32!AcquireSRWLockShared` at `0x180006196`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006223`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006223`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800061e5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800061e5`
- `KERNEL32!LeaveCriticalSection` at `0x180006247`
- `KERNEL32!LeaveCriticalSection` at `0x180006247`

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
0x180006180  push    rbx
0x180006182  push    rbp
0x180006183  push    rsi
0x180006184  push    rdi
0x180006185  push    r14
0x180006187  push    r15
0x180006189  sub     rsp, 28h
0x18000618d  mov     rbp, rdx
0x180006190  mov     rsi, rcx
0x180006193  mov     rcx, rdx; SRWLock
0x180006196  call    cs:__imp_AcquireSRWLockShared
0x18000619d  nop     dword ptr [rax+rax+00h]
0x1800061a2  mov     rdi, [rsi+30h]
0x1800061a6  sub     rdi, [rsi+28h]
0x1800061aa  shr     rdi, 4
0x1800061ae  test    rbp, rbp
0x1800061b1  jz      short loc_1800061C2
0x1800061b3  mov     rcx, rbp; SRWLock
0x1800061b6  call    cs:__imp_ReleaseSRWLockShared
0x1800061bd  nop     dword ptr [rax+rax+00h]
0x1800061c2  xor     ebx, ebx
0x1800061c4  test    rdi, rdi
0x1800061c7  jz      loc_18000625C
0x1800061cd  xor     r14d, r14d
0x1800061d0  xor     r15d, r15d
0x1800061d3  mov     rcx, rsi; lpCriticalSection
0x1800061d6  call    cs:__imp_EnterCriticalSection
0x1800061dd  nop     dword ptr [rax+rax+00h]
0x1800061e2  mov     rcx, rbp; SRWLock
0x1800061e5  call    cs:__imp_AcquireSRWLockExclusive
0x1800061ec  nop     dword ptr [rax+rax+00h]
0x1800061f1  cmp     rbx, rdi
0x1800061f4  jnb     short loc_18000621B
0x1800061f6  mov     rdx, [rsi+28h]
0x1800061fa  lea     rax, [rbx+1]
0x1800061fe  add     rbx, rbx
0x180006201  lea     rcx, [rdx+rbx*8]
0x180006205  mov     rbx, rax
0x180006208  cmp     [rcx], r14
0x18000620b  jnz     short loc_180006214
0x18000620d  cmp     rax, rdi
0x180006210  jb      short loc_1800061FA
0x180006212  jmp     short loc_18000621B
0x180006214  mov     r14, [rcx]
0x180006217  mov     r15, [rcx+8]
0x18000621b  test    rbp, rbp
0x18000621e  jz      short loc_18000622F
0x180006220  mov     rcx, rbp; SRWLock
0x180006223  call    cs:__imp_ReleaseSRWLockExclusive
0x18000622a  nop     dword ptr [rax+rax+00h]
0x18000622f  test    r14, r14
0x180006232  jz      short loc_18000623F
0x180006234  mov     rcx, r15
0x180006237  mov     rax, r14
0x18000623a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000623f  test    rsi, rsi
0x180006242  jz      short loc_180006253
0x180006244  mov     rcx, rsi; lpCriticalSection
0x180006247  call    cs:__imp_LeaveCriticalSection
0x18000624e  nop     dword ptr [rax+rax+00h]
0x180006253  cmp     rbx, rdi
0x180006256  jb      loc_1800061CD
0x18000625c  add     rsp, 28h
0x180006260  pop     r15
0x180006262  pop     r14
0x180006264  pop     rdi
0x180006265  pop     rsi
0x180006266  pop     rbp
0x180006267  pop     rbx
0x180006268  retn
```
