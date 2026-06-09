# wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)

- ea: `0x1800055c8`
- end: `0x180005643`
- name: `?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z`
- size: `123`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005914`
- `0x1800065f0`

## callees

- `0x1800055c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800055ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800055ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000561f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000561f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800055e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800055e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000562d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000562d`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::Unsubscribe(
        LPCRITICAL_SECTION lpCriticalSection,
        PSRWLOCK SRWLock,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a3)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx

  if ( a3 )
  {
    EnterCriticalSection(lpCriticalSection);
    AcquireSRWLockExclusive(SRWLock);
    DebugInfo = lpCriticalSection[1].DebugInfo;
    if ( (unsigned __int64)a3 - 1 < (*(_QWORD *)&lpCriticalSection[1].LockCount - (_QWORD)DebugInfo) >> 4 )
      *((_OWORD *)&DebugInfo->Type + (unsigned __int64)a3 - 1) = 0;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x1800055c8  test    r8, r8
0x1800055cb  jz      short locret_180005642
0x1800055cd  mov     [rsp+arg_0], rbx
0x1800055d2  mov     [rsp+arg_8], rsi
0x1800055d7  push    rdi
0x1800055d8  sub     rsp, 20h
0x1800055dc  mov     rsi, r8
0x1800055df  mov     rdi, rdx
0x1800055e2  mov     rbx, rcx
0x1800055e5  call    cs:__imp_EnterCriticalSection
0x1800055eb  mov     rcx, rdi; SRWLock
0x1800055ee  call    cs:__imp_AcquireSRWLockExclusive
0x1800055f4  mov     rdx, [rbx+28h]
0x1800055f8  lea     rcx, [rsi-1]
0x1800055fc  mov     rax, [rbx+30h]
0x180005600  sub     rax, rdx
0x180005603  shr     rax, 4
0x180005607  cmp     rcx, rax
0x18000560a  jnb     short loc_180005617
0x18000560c  add     rcx, rcx
0x18000560f  xorps   xmm0, xmm0
0x180005612  movdqu  xmmword ptr [rdx+rcx*8], xmm0
0x180005617  test    rdi, rdi
0x18000561a  jz      short loc_180005625
0x18000561c  mov     rcx, rdi; SRWLock
0x18000561f  call    cs:__imp_ReleaseSRWLockExclusive
0x180005625  test    rbx, rbx
0x180005628  jz      short loc_180005633
0x18000562a  mov     rcx, rbx; lpCriticalSection
0x18000562d  call    cs:__imp_LeaveCriticalSection
0x180005633  mov     rbx, [rsp+28h+arg_0]
0x180005638  mov     rsi, [rsp+28h+arg_8]
0x18000563d  add     rsp, 20h
0x180005641  pop     rdi
0x180005642  retn
```
