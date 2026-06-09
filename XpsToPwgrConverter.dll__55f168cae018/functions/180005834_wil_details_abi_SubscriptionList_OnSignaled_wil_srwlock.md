# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005834`
- end: `0x1800058f1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002280`
- `0x1800022b0`
- `0x180002360`
- `0x180007f20`

## callees

- `0x180005834`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005883`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005883`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800058bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800058bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000587a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000587a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005864`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005864`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000584a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000584a`

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
0x180005834  push    rbx
0x180005836  push    rbp
0x180005837  push    rsi
0x180005838  push    rdi
0x180005839  push    r14
0x18000583b  push    r15
0x18000583d  sub     rsp, 28h
0x180005841  mov     rbp, rdx
0x180005844  mov     rsi, rcx
0x180005847  mov     rcx, rdx; SRWLock
0x18000584a  call    cs:__imp_AcquireSRWLockShared
0x180005850  mov     rdi, [rsi+30h]
0x180005854  sub     rdi, [rsi+28h]
0x180005858  shr     rdi, 4
0x18000585c  test    rbp, rbp
0x18000585f  jz      short loc_18000586A
0x180005861  mov     rcx, rbp; SRWLock
0x180005864  call    cs:__imp_ReleaseSRWLockShared
0x18000586a  xor     ebx, ebx
0x18000586c  test    rdi, rdi
0x18000586f  jz      short loc_1800058E4
0x180005871  xor     r14d, r14d
0x180005874  xor     r15d, r15d
0x180005877  mov     rcx, rsi; lpCriticalSection
0x18000587a  call    cs:__imp_EnterCriticalSection
0x180005880  mov     rcx, rbp; SRWLock
0x180005883  call    cs:__imp_AcquireSRWLockExclusive
0x180005889  cmp     rbx, rdi
0x18000588c  jnb     short loc_1800058B3
0x18000588e  mov     rdx, [rsi+28h]
0x180005892  lea     rax, [rbx+1]
0x180005896  add     rbx, rbx
0x180005899  lea     rcx, [rdx+rbx*8]
0x18000589d  mov     rbx, rax
0x1800058a0  cmp     [rcx], r14
0x1800058a3  jnz     short loc_1800058AC
0x1800058a5  cmp     rax, rdi
0x1800058a8  jb      short loc_180005892
0x1800058aa  jmp     short loc_1800058B3
0x1800058ac  mov     r14, [rcx]
0x1800058af  mov     r15, [rcx+8]
0x1800058b3  test    rbp, rbp
0x1800058b6  jz      short loc_1800058C1
0x1800058b8  mov     rcx, rbp; SRWLock
0x1800058bb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800058c1  test    r14, r14
0x1800058c4  jz      short loc_1800058D1
0x1800058c6  mov     rcx, r15
0x1800058c9  mov     rax, r14
0x1800058cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d1  test    rsi, rsi
0x1800058d4  jz      short loc_1800058DF
0x1800058d6  mov     rcx, rsi; lpCriticalSection
0x1800058d9  call    cs:__imp_LeaveCriticalSection
0x1800058df  cmp     rbx, rdi
0x1800058e2  jb      short loc_180005871
0x1800058e4  add     rsp, 28h
0x1800058e8  pop     r15
0x1800058ea  pop     r14
0x1800058ec  pop     rdi
0x1800058ed  pop     rsi
0x1800058ee  pop     rbp
0x1800058ef  pop     rbx
0x1800058f0  retn
```
