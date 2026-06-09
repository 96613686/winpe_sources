# WfpStartTimer

- ea: `0x18008a84c`
- end: `0x18008a9b8`
- name: `WfpStartTimer`
- size: `364`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18004fa04`
- `0x18007ad7c`
- `0x18007ae20`
- `0x18007f860`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x18008a84c`
- `0x18008a9c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18008a8d3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18008a8d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008a962`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008a962`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a874`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a971`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a874`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008a971`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a88e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a987`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a88e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008a987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a8ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a8ea`

## string_xrefs

- `0x18008a8f9`: `CreateThreadpoolTimer`

## pseudocode

```c
__int64 __fastcall WfpStartTimer(__int64 a1, int a2, __int64 a3, struct _RTL_CRITICAL_SECTION *a4, PVOID pv)
{
  __int64 v8; // rdi
  _OWORD *v9; // rsi
  int v10; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  DWORD LastError; // eax
  __int64 v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+18h] BYREF

  pftDueTime = 0;
  v8 = 0;
  EnterCriticalSection(a4);
  v9 = pv;
  v10 = *((_DWORD *)pv + 6);
  LeaveCriticalSection(a4);
  if ( v10 != 1 || (v8 = WfpStopTimer(a4, (__int64)v9)) == 0 )
  {
    *v9 = 0;
    v9[1] = 0;
    *((_QWORD *)v9 + 4) = 0;
    ThreadpoolTimer = CreateThreadpoolTimer(WfpUserModeTimerInternalCallback, v9, 0);
    *(_QWORD *)v9 = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      *((_QWORD *)v9 + 1) = a1;
      *((_QWORD *)v9 + 2) = 0;
      *((_QWORD *)v9 + 4) = a4;
      pftDueTime = (struct _FILETIME)(-10000000LL * (95 * a2 / 0x64u));
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 1000 * a2 / 0x14u);
      EnterCriticalSection(a4);
      *((_DWORD *)v9 + 6) = 1;
      LeaveCriticalSection(a4);
    }
    else
    {
      LastError = GetLastError();
      v8 = WfpReportSysErrorAsWinError(v13, "CreateThreadpoolTimer", LastError);
    }
  }
  if ( v8 )
    WfpReportError(v8, "WfpStartTimer");
  return v8;
}

```

## disassembly

```asm
0x18008a84c  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], r8
0x18008a851  push    rbx
0x18008a852  push    rbp
0x18008a853  push    rsi
0x18008a854  push    rdi
0x18008a855  push    r14
0x18008a857  push    r15
0x18008a859  sub     rsp, 28h
0x18008a85d  mov     r15, rcx
0x18008a860  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0
0x18008a869  mov     rcx, r9; lpCriticalSection
0x18008a86c  mov     rbp, r9
0x18008a86f  mov     r14d, edx
0x18008a872  xor     edi, edi
0x18008a874  call    cs:__imp_EnterCriticalSection
0x18008a87b  nop     dword ptr [rax+rax+00h]
0x18008a880  mov     rsi, [rsp+58h+pv]
0x18008a888  mov     rcx, rbp; lpCriticalSection
0x18008a88b  mov     ebx, [rsi+18h]
0x18008a88e  call    cs:__imp_LeaveCriticalSection
0x18008a895  nop     dword ptr [rax+rax+00h]
0x18008a89a  cmp     ebx, 1
0x18008a89d  jnz     short loc_18008A8B6
0x18008a89f  mov     rdx, rsi
0x18008a8a2  mov     rcx, rbp; lpCriticalSection
0x18008a8a5  call    WfpStopTimer
0x18008a8aa  mov     rdi, rax
0x18008a8ad  test    rax, rax
0x18008a8b0  jnz     loc_18008A993
0x18008a8b6  xorps   xmm0, xmm0
0x18008a8b9  lea     rcx, WfpUserModeTimerInternalCallback; pfnti
0x18008a8c0  movups  xmmword ptr [rsi], xmm0
0x18008a8c3  xor     eax, eax
0x18008a8c5  xor     r8d, r8d; pcbe
0x18008a8c8  movups  xmmword ptr [rsi+10h], xmm0
0x18008a8cc  mov     rdx, rsi; pv
0x18008a8cf  mov     [rsi+20h], rax
0x18008a8d3  call    cs:__imp_CreateThreadpoolTimer
0x18008a8da  nop     dword ptr [rax+rax+00h]
0x18008a8df  mov     [rsi], rax
0x18008a8e2  mov     r10, rax
0x18008a8e5  test    rax, rax
0x18008a8e8  jnz     short loc_18008A90D
0x18008a8ea  call    cs:__imp_GetLastError
0x18008a8f1  nop     dword ptr [rax+rax+00h]
0x18008a8f6  mov     r8d, eax
0x18008a8f9  lea     rdx, aCreatethreadpo_0; "CreateThreadpoolTimer"
0x18008a900  call    WfpReportSysErrorAsWinError
0x18008a905  mov     rdi, rax
0x18008a908  jmp     loc_18008A993
0x18008a90d  imul    ecx, r14d, 5Fh ; '_'
0x18008a911  mov     eax, 51EB851Fh
0x18008a916  xor     r8d, r8d; msPeriod
0x18008a919  mov     [rsi+8], r15
0x18008a91d  mov     qword ptr [rsi+10h], 0
0x18008a925  mov     [rsi+20h], rbp
0x18008a929  mul     ecx
0x18008a92b  shr     edx, 5
0x18008a92e  mov     eax, edx
0x18008a930  imul    rax, 0FFFFFFFFFF676980h
0x18008a937  mov     rcx, rax
0x18008a93a  mov     [rsp+58h+pftDueTime.dwLowDateTime], eax
0x18008a93e  shr     rcx, 20h
0x18008a942  mov     eax, 0CCCCCCCDh
0x18008a947  mov     [rsp+58h+pftDueTime.dwHighDateTime], ecx
0x18008a94b  imul    ecx, r14d, 3E8h
0x18008a952  mul     ecx
0x18008a954  mov     rcx, r10; pti
0x18008a957  shr     edx, 4
0x18008a95a  mov     r9d, edx; msWindowLength
0x18008a95d  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18008a962  call    cs:__imp_SetThreadpoolTimer
0x18008a969  nop     dword ptr [rax+rax+00h]
0x18008a96e  mov     rcx, rbp; lpCriticalSection
0x18008a971  call    cs:__imp_EnterCriticalSection
0x18008a978  nop     dword ptr [rax+rax+00h]
0x18008a97d  mov     rcx, rbp; lpCriticalSection
0x18008a980  mov     dword ptr [rsi+18h], 1
0x18008a987  call    cs:__imp_LeaveCriticalSection
0x18008a98e  nop     dword ptr [rax+rax+00h]
0x18008a993  test    rdi, rdi
0x18008a996  jz      short loc_18008A9A7
0x18008a998  lea     rdx, aWfpstarttimer; "WfpStartTimer"
0x18008a99f  mov     rcx, rdi
0x18008a9a2  call    WfpReportError
0x18008a9a7  mov     rax, rdi
0x18008a9aa  add     rsp, 28h
0x18008a9ae  pop     r15
0x18008a9b0  pop     r14
0x18008a9b2  pop     rdi
0x18008a9b3  pop     rsi
0x18008a9b4  pop     rbp
0x18008a9b5  pop     rbx
0x18008a9b6  retn
```
