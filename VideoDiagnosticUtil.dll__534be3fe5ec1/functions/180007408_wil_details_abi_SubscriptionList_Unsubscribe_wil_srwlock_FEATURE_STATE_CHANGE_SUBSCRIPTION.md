# wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)

- ea: `0x180007408`
- end: `0x1800074a0`
- name: `?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z`
- size: `152`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f20`
- `0x180007640`

## callees

- `0x180007408`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180007438`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007438`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000746f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000746f`
- `KERNEL32!LeaveCriticalSection` at `0x180007483`
- `KERNEL32!LeaveCriticalSection` at `0x180007483`
- `KERNEL32!EnterCriticalSection` at `0x180007429`
- `KERNEL32!EnterCriticalSection` at `0x180007429`

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
0x180007408  test    r8, r8
0x18000740b  jz      locret_18000749E
0x180007411  mov     [rsp+arg_0], rbx
0x180007416  mov     [rsp+arg_8], rsi
0x18000741b  push    rdi
0x18000741c  sub     rsp, 20h
0x180007420  mov     rsi, r8
0x180007423  mov     rdi, rdx
0x180007426  mov     rbx, rcx
0x180007429  call    cs:__imp_EnterCriticalSection
0x180007430  nop     dword ptr [rax+rax+00h]
0x180007435  mov     rcx, rdi; SRWLock
0x180007438  call    cs:__imp_AcquireSRWLockExclusive
0x18000743f  nop     dword ptr [rax+rax+00h]
0x180007444  mov     rdx, [rbx+28h]
0x180007448  lea     rcx, [rsi-1]
0x18000744c  mov     rax, [rbx+30h]
0x180007450  sub     rax, rdx
0x180007453  shr     rax, 4
0x180007457  cmp     rcx, rax
0x18000745a  jnb     short loc_180007467
0x18000745c  add     rcx, rcx
0x18000745f  xorps   xmm0, xmm0
0x180007462  movdqu  xmmword ptr [rdx+rcx*8], xmm0
0x180007467  test    rdi, rdi
0x18000746a  jz      short loc_18000747B
0x18000746c  mov     rcx, rdi; SRWLock
0x18000746f  call    cs:__imp_ReleaseSRWLockExclusive
0x180007476  nop     dword ptr [rax+rax+00h]
0x18000747b  test    rbx, rbx
0x18000747e  jz      short loc_18000748F
0x180007480  mov     rcx, rbx; lpCriticalSection
0x180007483  call    cs:__imp_LeaveCriticalSection
0x18000748a  nop     dword ptr [rax+rax+00h]
0x18000748f  mov     rbx, [rsp+28h+arg_0]
0x180007494  mov     rsi, [rsp+28h+arg_8]
0x180007499  add     rsp, 20h
0x18000749d  pop     rdi
0x18000749e  retn
```
