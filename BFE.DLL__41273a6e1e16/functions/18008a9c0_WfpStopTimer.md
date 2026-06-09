# WfpStopTimer

- ea: `0x18008a9c0`
- end: `0x18008aa86`
- name: `WfpStopTimer`
- size: `198`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18007b008`
- `0x18007f97c`
- `0x18008a84c`

## callees

- `0x1800135ac`
- `0x1800197d0`
- `0x18008a9c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008aa66`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008aa66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008aa45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008aa45`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008aa57`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008aa57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a9d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a9d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a9fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a9fd`

## pseudocode

```c
__int64 __fastcall WfpStopTimer(LPCRITICAL_SECTION lpCriticalSection, __int64 a2)
{
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbx

  EnterCriticalSection(lpCriticalSection);
  if ( *(_DWORD *)(a2 + 24) == 3 || *(_DWORD *)(a2 + 24) == 2 )
  {
    v4 = 0;
  }
  else
  {
    v4 = 1;
    *(_DWORD *)(a2 + 24) = 2;
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( v4 )
  {
    v7 = 0;
    SetThreadpoolTimer(*(PTP_TIMER *)a2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)a2, 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)a2);
  }
  else
  {
    v6 = WfpReportSysErrorAsNtStatus(v5, "WfpStopTimer", 259);
    v7 = v6;
    if ( v6 )
      WfpReportError(v6, "WfpStopTimer");
  }
  return v7;
}

```

## disassembly

```asm
0x18008a9c0  mov     [rsp+arg_0], rbx
0x18008a9c5  mov     [rsp+arg_8], rsi
0x18008a9ca  push    rdi
0x18008a9cb  sub     rsp, 20h
0x18008a9cf  mov     rdi, rdx
0x18008a9d2  mov     rsi, rcx
0x18008a9d5  call    cs:__imp_EnterCriticalSection
0x18008a9dc  nop     dword ptr [rax+rax+00h]
0x18008a9e1  cmp     dword ptr [rdi+18h], 3
0x18008a9e5  jz      short loc_18008A9ED
0x18008a9e7  cmp     dword ptr [rdi+18h], 2
0x18008a9eb  jnz     short loc_18008A9F1
0x18008a9ed  xor     bl, bl
0x18008a9ef  jmp     short loc_18008A9FA
0x18008a9f1  mov     bl, 1
0x18008a9f3  mov     dword ptr [rdi+18h], 2
0x18008a9fa  mov     rcx, rsi; lpCriticalSection
0x18008a9fd  call    cs:__imp_LeaveCriticalSection
0x18008aa04  nop     dword ptr [rax+rax+00h]
0x18008aa09  test    bl, bl
0x18008aa0b  jnz     short loc_18008AA38
0x18008aa0d  mov     r8d, 103h
0x18008aa13  lea     rdx, aWfpstoptimer; "WfpStopTimer"
0x18008aa1a  call    WfpReportSysErrorAsNtStatus
0x18008aa1f  mov     rbx, rax
0x18008aa22  test    rax, rax
0x18008aa25  jz      short loc_18008AA72
0x18008aa27  lea     rdx, aWfpstoptimer; "WfpStopTimer"
0x18008aa2e  mov     rcx, rax
0x18008aa31  call    WfpReportError
0x18008aa36  jmp     short loc_18008AA72
0x18008aa38  mov     rcx, [rdi]; pti
0x18008aa3b  xor     r9d, r9d; msWindowLength
0x18008aa3e  xor     r8d, r8d; msPeriod
0x18008aa41  xor     edx, edx; pftDueTime
0x18008aa43  xor     ebx, ebx
0x18008aa45  call    cs:__imp_SetThreadpoolTimer
0x18008aa4c  nop     dword ptr [rax+rax+00h]
0x18008aa51  mov     rcx, [rdi]; pti
0x18008aa54  lea     edx, [rbx+1]; fCancelPendingCallbacks
0x18008aa57  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18008aa5e  nop     dword ptr [rax+rax+00h]
0x18008aa63  mov     rcx, [rdi]; pti
0x18008aa66  call    cs:__imp_CloseThreadpoolTimer
0x18008aa6d  nop     dword ptr [rax+rax+00h]
0x18008aa72  mov     rsi, [rsp+28h+arg_8]
0x18008aa77  mov     rax, rbx
0x18008aa7a  mov     rbx, [rsp+28h+arg_0]
0x18008aa7f  add     rsp, 20h
0x18008aa83  pop     rdi
0x18008aa84  retn
```
