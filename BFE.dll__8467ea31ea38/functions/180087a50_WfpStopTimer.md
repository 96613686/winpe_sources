# WfpStopTimer

- ea: `0x180087a50`
- end: `0x180087af7`
- name: `WfpStopTimer`
- size: `167`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180078440`
- `0x18007cbdc`
- `0x18008790c`

## callees

- `0x180012b54`
- `0x180018b74`
- `0x180087a50`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180087ade`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180087ade`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180087ac9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180087ac9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180087ad5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180087ad5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087a65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087a65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087a87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087a87`

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
0x180087a50  mov     [rsp+arg_0], rbx
0x180087a55  mov     [rsp+arg_8], rsi
0x180087a5a  push    rdi
0x180087a5b  sub     rsp, 20h
0x180087a5f  mov     rdi, rdx
0x180087a62  mov     rsi, rcx
0x180087a65  call    cs:__imp_EnterCriticalSection
0x180087a6b  cmp     dword ptr [rdi+18h], 3
0x180087a6f  jz      short loc_180087A77
0x180087a71  cmp     dword ptr [rdi+18h], 2
0x180087a75  jnz     short loc_180087A7B
0x180087a77  xor     bl, bl
0x180087a79  jmp     short loc_180087A84
0x180087a7b  mov     bl, 1
0x180087a7d  mov     dword ptr [rdi+18h], 2
0x180087a84  mov     rcx, rsi; lpCriticalSection
0x180087a87  call    cs:__imp_LeaveCriticalSection
0x180087a8d  test    bl, bl
0x180087a8f  jnz     short loc_180087ABC
0x180087a91  mov     r8d, 103h
0x180087a97  lea     rdx, aWfpstoptimer; "WfpStopTimer"
0x180087a9e  call    WfpReportSysErrorAsNtStatus
0x180087aa3  mov     rbx, rax
0x180087aa6  test    rax, rax
0x180087aa9  jz      short loc_180087AE4
0x180087aab  lea     rdx, aWfpstoptimer; "WfpStopTimer"
0x180087ab2  mov     rcx, rax
0x180087ab5  call    WfpReportError
0x180087aba  jmp     short loc_180087AE4
0x180087abc  mov     rcx, [rdi]; pti
0x180087abf  xor     r9d, r9d; msWindowLength
0x180087ac2  xor     r8d, r8d; msPeriod
0x180087ac5  xor     edx, edx; pftDueTime
0x180087ac7  xor     ebx, ebx
0x180087ac9  call    cs:__imp_SetThreadpoolTimer
0x180087acf  mov     rcx, [rdi]; pti
0x180087ad2  lea     edx, [rbx+1]; fCancelPendingCallbacks
0x180087ad5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180087adb  mov     rcx, [rdi]; pti
0x180087ade  call    cs:__imp_CloseThreadpoolTimer
0x180087ae4  mov     rsi, [rsp+28h+arg_8]
0x180087ae9  mov     rax, rbx
0x180087aec  mov     rbx, [rsp+28h+arg_0]
0x180087af1  add     rsp, 20h
0x180087af5  pop     rdi
0x180087af6  retn
```
