# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000bbcc`
- end: `0x14000bc89`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140006bf0`
- `0x140006c20`
- `0x140006cd0`
- `0x14000e420`

## callees

- `0x14000bbcc`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000bc71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000bc71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000bc1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000bc1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000bc12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000bc12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000bbe2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000bbe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000bbfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000bbfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000bc53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000bc53`

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
0x14000bbcc  push    rbx
0x14000bbce  push    rbp
0x14000bbcf  push    rsi
0x14000bbd0  push    rdi
0x14000bbd1  push    r14
0x14000bbd3  push    r15
0x14000bbd5  sub     rsp, 28h
0x14000bbd9  mov     rbp, rdx
0x14000bbdc  mov     rsi, rcx
0x14000bbdf  mov     rcx, rdx; SRWLock
0x14000bbe2  call    cs:__imp_AcquireSRWLockShared
0x14000bbe8  mov     rdi, [rsi+30h]
0x14000bbec  sub     rdi, [rsi+28h]
0x14000bbf0  shr     rdi, 4
0x14000bbf4  test    rbp, rbp
0x14000bbf7  jz      short loc_14000BC02
0x14000bbf9  mov     rcx, rbp; SRWLock
0x14000bbfc  call    cs:__imp_ReleaseSRWLockShared
0x14000bc02  xor     ebx, ebx
0x14000bc04  test    rdi, rdi
0x14000bc07  jz      short loc_14000BC7C
0x14000bc09  xor     r14d, r14d
0x14000bc0c  xor     r15d, r15d
0x14000bc0f  mov     rcx, rsi; lpCriticalSection
0x14000bc12  call    cs:__imp_EnterCriticalSection
0x14000bc18  mov     rcx, rbp; SRWLock
0x14000bc1b  call    cs:__imp_AcquireSRWLockExclusive
0x14000bc21  cmp     rbx, rdi
0x14000bc24  jnb     short loc_14000BC4B
0x14000bc26  mov     rdx, [rsi+28h]
0x14000bc2a  lea     rax, [rbx+1]
0x14000bc2e  add     rbx, rbx
0x14000bc31  lea     rcx, [rdx+rbx*8]
0x14000bc35  mov     rbx, rax
0x14000bc38  cmp     [rcx], r14
0x14000bc3b  jnz     short loc_14000BC44
0x14000bc3d  cmp     rax, rdi
0x14000bc40  jb      short loc_14000BC2A
0x14000bc42  jmp     short loc_14000BC4B
0x14000bc44  mov     r14, [rcx]
0x14000bc47  mov     r15, [rcx+8]
0x14000bc4b  test    rbp, rbp
0x14000bc4e  jz      short loc_14000BC59
0x14000bc50  mov     rcx, rbp; SRWLock
0x14000bc53  call    cs:__imp_ReleaseSRWLockExclusive
0x14000bc59  test    r14, r14
0x14000bc5c  jz      short loc_14000BC69
0x14000bc5e  mov     rcx, r15
0x14000bc61  mov     rax, r14
0x14000bc64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc69  test    rsi, rsi
0x14000bc6c  jz      short loc_14000BC77
0x14000bc6e  mov     rcx, rsi; lpCriticalSection
0x14000bc71  call    cs:__imp_LeaveCriticalSection
0x14000bc77  cmp     rbx, rdi
0x14000bc7a  jb      short loc_14000BC09
0x14000bc7c  add     rsp, 28h
0x14000bc80  pop     r15
0x14000bc82  pop     r14
0x14000bc84  pop     rdi
0x14000bc85  pop     rsi
0x14000bc86  pop     rbp
0x14000bc87  pop     rbx
0x14000bc88  retn
```
