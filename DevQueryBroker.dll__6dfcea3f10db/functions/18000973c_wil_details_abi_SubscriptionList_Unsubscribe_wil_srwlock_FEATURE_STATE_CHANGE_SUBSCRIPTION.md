# wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)

- ea: `0x18000973c`
- end: `0x1800097b7`
- name: `?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z`
- size: `123`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800055bc`
- `0x180009a20`

## callees

- `0x18000973c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009793`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800097a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800097a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009759`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009759`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009762`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009762`

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
0x18000973c  test    r8, r8
0x18000973f  jz      short locret_1800097B6
0x180009741  mov     [rsp+arg_0], rbx
0x180009746  mov     [rsp+arg_8], rsi
0x18000974b  push    rdi
0x18000974c  sub     rsp, 20h
0x180009750  mov     rsi, r8
0x180009753  mov     rdi, rdx
0x180009756  mov     rbx, rcx
0x180009759  call    cs:__imp_EnterCriticalSection
0x18000975f  mov     rcx, rdi; SRWLock
0x180009762  call    cs:__imp_AcquireSRWLockExclusive
0x180009768  mov     rdx, [rbx+28h]
0x18000976c  lea     rcx, [rsi-1]
0x180009770  mov     rax, [rbx+30h]
0x180009774  sub     rax, rdx
0x180009777  shr     rax, 4
0x18000977b  cmp     rcx, rax
0x18000977e  jnb     short loc_18000978B
0x180009780  add     rcx, rcx
0x180009783  xorps   xmm0, xmm0
0x180009786  movdqu  xmmword ptr [rdx+rcx*8], xmm0
0x18000978b  test    rdi, rdi
0x18000978e  jz      short loc_180009799
0x180009790  mov     rcx, rdi; SRWLock
0x180009793  call    cs:__imp_ReleaseSRWLockExclusive
0x180009799  test    rbx, rbx
0x18000979c  jz      short loc_1800097A7
0x18000979e  mov     rcx, rbx; lpCriticalSection
0x1800097a1  call    cs:__imp_LeaveCriticalSection
0x1800097a7  mov     rbx, [rsp+28h+arg_0]
0x1800097ac  mov     rsi, [rsp+28h+arg_8]
0x1800097b1  add     rsp, 20h
0x1800097b5  pop     rdi
0x1800097b6  retn
```
