# wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)

- ea: `0x140007e50`
- end: `0x140007ecb`
- name: `?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z`
- size: `123`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005cc0`
- `0x140008130`

## callees

- `0x140007e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007ea7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007ea7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007e6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007e6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007eb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007eb5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007e76`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007e76`

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
0x140007e50  test    r8, r8
0x140007e53  jz      short locret_140007ECA
0x140007e55  mov     [rsp+arg_0], rbx
0x140007e5a  mov     [rsp+arg_8], rsi
0x140007e5f  push    rdi
0x140007e60  sub     rsp, 20h
0x140007e64  mov     rsi, r8
0x140007e67  mov     rdi, rdx
0x140007e6a  mov     rbx, rcx
0x140007e6d  call    cs:__imp_EnterCriticalSection
0x140007e73  mov     rcx, rdi; SRWLock
0x140007e76  call    cs:__imp_AcquireSRWLockExclusive
0x140007e7c  mov     rdx, [rbx+28h]
0x140007e80  lea     rcx, [rsi-1]
0x140007e84  mov     rax, [rbx+30h]
0x140007e88  sub     rax, rdx
0x140007e8b  shr     rax, 4
0x140007e8f  cmp     rcx, rax
0x140007e92  jnb     short loc_140007E9F
0x140007e94  add     rcx, rcx
0x140007e97  xorps   xmm0, xmm0
0x140007e9a  movdqu  xmmword ptr [rdx+rcx*8], xmm0
0x140007e9f  test    rdi, rdi
0x140007ea2  jz      short loc_140007EAD
0x140007ea4  mov     rcx, rdi; SRWLock
0x140007ea7  call    cs:__imp_ReleaseSRWLockExclusive
0x140007ead  test    rbx, rbx
0x140007eb0  jz      short loc_140007EBB
0x140007eb2  mov     rcx, rbx; lpCriticalSection
0x140007eb5  call    cs:__imp_LeaveCriticalSection
0x140007ebb  mov     rbx, [rsp+28h+arg_0]
0x140007ec0  mov     rsi, [rsp+28h+arg_8]
0x140007ec5  add     rsp, 20h
0x140007ec9  pop     rdi
0x140007eca  retn
```
