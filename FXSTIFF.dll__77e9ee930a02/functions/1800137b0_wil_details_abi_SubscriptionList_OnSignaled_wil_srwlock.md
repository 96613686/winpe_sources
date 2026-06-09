# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1800137b0`
- end: `0x18001389c`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `236`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ffc0`
- `0x18000fff0`
- `0x1800100a0`
- `0x1800161a0`

## callees

- `0x1800137b0`
- `0x180019010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180013808`
- `KERNEL32!EnterCriticalSection` at `0x180013808`
- `KERNEL32!LeaveCriticalSection` at `0x180013879`
- `KERNEL32!LeaveCriticalSection` at `0x180013879`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180013855`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180013855`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013817`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013817`
- `KERNEL32!AcquireSRWLockShared` at `0x1800137c6`
- `KERNEL32!AcquireSRWLockShared` at `0x1800137c6`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800137e7`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800137e7`

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
0x1800137b0  push    rbx
0x1800137b2  push    rbp
0x1800137b3  push    rsi
0x1800137b4  push    rdi
0x1800137b5  push    r14
0x1800137b7  push    r15
0x1800137b9  sub     rsp, 28h
0x1800137bd  mov     rbp, rdx
0x1800137c0  mov     rsi, rcx
0x1800137c3  mov     rcx, rdx; SRWLock
0x1800137c6  call    cs:__imp_AcquireSRWLockShared
0x1800137cd  nop     dword ptr [rax+rax+00h]
0x1800137d2  nop
0x1800137d3  mov     rdi, [rsi+30h]
0x1800137d7  sub     rdi, [rsi+28h]
0x1800137db  shr     rdi, 4
0x1800137df  test    rbp, rbp
0x1800137e2  jz      short loc_1800137F4
0x1800137e4  mov     rcx, rbp; SRWLock
0x1800137e7  call    cs:__imp_ReleaseSRWLockShared
0x1800137ee  nop     dword ptr [rax+rax+00h]
0x1800137f3  nop
0x1800137f4  xor     ebx, ebx
0x1800137f6  test    rdi, rdi
0x1800137f9  jz      loc_18001388E
0x1800137ff  xor     r14d, r14d
0x180013802  xor     r15d, r15d
0x180013805  mov     rcx, rsi; lpCriticalSection
0x180013808  call    cs:__imp_EnterCriticalSection
0x18001380f  nop     dword ptr [rax+rax+00h]
0x180013814  mov     rcx, rbp; SRWLock
0x180013817  call    cs:__imp_AcquireSRWLockExclusive
0x18001381e  nop     dword ptr [rax+rax+00h]
0x180013823  cmp     rbx, rdi
0x180013826  jnb     short loc_18001384D
0x180013828  mov     rdx, [rsi+28h]
0x18001382c  lea     rax, [rbx+1]
0x180013830  add     rbx, rbx
0x180013833  lea     rcx, [rdx+rbx*8]
0x180013837  mov     rbx, rax
0x18001383a  cmp     [rcx], r14
0x18001383d  jnz     short loc_180013846
0x18001383f  cmp     rax, rdi
0x180013842  jb      short loc_18001382C
0x180013844  jmp     short loc_18001384D
0x180013846  mov     r14, [rcx]
0x180013849  mov     r15, [rcx+8]
0x18001384d  test    rbp, rbp
0x180013850  jz      short loc_180013861
0x180013852  mov     rcx, rbp; SRWLock
0x180013855  call    cs:__imp_ReleaseSRWLockExclusive
0x18001385c  nop     dword ptr [rax+rax+00h]
0x180013861  test    r14, r14
0x180013864  jz      short loc_180013871
0x180013866  mov     rcx, r15
0x180013869  mov     rax, r14
0x18001386c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013871  test    rsi, rsi
0x180013874  jz      short loc_180013885
0x180013876  mov     rcx, rsi; lpCriticalSection
0x180013879  call    cs:__imp_LeaveCriticalSection
0x180013880  nop     dword ptr [rax+rax+00h]
0x180013885  cmp     rbx, rdi
0x180013888  jb      loc_1800137FF
0x18001388e  add     rsp, 28h
0x180013892  pop     r15
0x180013894  pop     r14
0x180013896  pop     rdi
0x180013897  pop     rsi
0x180013898  pop     rbp
0x180013899  pop     rbx
0x18001389a  retn
```
