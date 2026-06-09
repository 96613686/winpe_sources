# WfpStartTimer

- ea: `0x18008790c`
- end: `0x180087a4a`
- name: `WfpStartTimer`
- size: `318`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18004e0e8`
- `0x1800781cc`
- `0x180078270`
- `0x18007cad0`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x18008790c`
- `0x180087a50`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180087987`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180087987`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180087a07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180087a07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087934`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087a10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087934`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087a10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087948`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087a20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087948`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087998`

## string_xrefs

- `0x1800879a1`: `CreateThreadpoolTimer`

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
0x18008790c  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], r8
0x180087911  push    rbx
0x180087912  push    rbp
0x180087913  push    rsi
0x180087914  push    rdi
0x180087915  push    r14
0x180087917  push    r15
0x180087919  sub     rsp, 28h
0x18008791d  mov     r15, rcx
0x180087920  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0
0x180087929  mov     rcx, r9; lpCriticalSection
0x18008792c  mov     rbp, r9
0x18008792f  mov     r14d, edx
0x180087932  xor     edi, edi
0x180087934  call    cs:__imp_EnterCriticalSection
0x18008793a  mov     rsi, [rsp+58h+pv]
0x180087942  mov     rcx, rbp; lpCriticalSection
0x180087945  mov     ebx, [rsi+18h]
0x180087948  call    cs:__imp_LeaveCriticalSection
0x18008794e  cmp     ebx, 1
0x180087951  jnz     short loc_18008796A
0x180087953  mov     rdx, rsi
0x180087956  mov     rcx, rbp; lpCriticalSection
0x180087959  call    WfpStopTimer
0x18008795e  mov     rdi, rax
0x180087961  test    rax, rax
0x180087964  jnz     loc_180087A26
0x18008796a  xorps   xmm0, xmm0
0x18008796d  lea     rcx, WfpUserModeTimerInternalCallback; pfnti
0x180087974  movups  xmmword ptr [rsi], xmm0
0x180087977  xor     eax, eax
0x180087979  xor     r8d, r8d; pcbe
0x18008797c  movups  xmmword ptr [rsi+10h], xmm0
0x180087980  mov     rdx, rsi; pv
0x180087983  mov     [rsi+20h], rax
0x180087987  call    cs:__imp_CreateThreadpoolTimer
0x18008798d  mov     [rsi], rax
0x180087990  mov     r10, rax
0x180087993  test    rax, rax
0x180087996  jnz     short loc_1800879B2
0x180087998  call    cs:__imp_GetLastError
0x18008799e  mov     r8d, eax
0x1800879a1  lea     rdx, aCreatethreadpo_0; "CreateThreadpoolTimer"
0x1800879a8  call    WfpReportSysErrorAsWinError
0x1800879ad  mov     rdi, rax
0x1800879b0  jmp     short loc_180087A26
0x1800879b2  imul    ecx, r14d, 5Fh ; '_'
0x1800879b6  mov     eax, 51EB851Fh
0x1800879bb  xor     r8d, r8d; msPeriod
0x1800879be  mov     [rsi+8], r15
0x1800879c2  mov     qword ptr [rsi+10h], 0
0x1800879ca  mov     [rsi+20h], rbp
0x1800879ce  mul     ecx
0x1800879d0  shr     edx, 5
0x1800879d3  mov     eax, edx
0x1800879d5  imul    rax, 0FFFFFFFFFF676980h
0x1800879dc  mov     rcx, rax
0x1800879df  mov     [rsp+58h+pftDueTime.dwLowDateTime], eax
0x1800879e3  shr     rcx, 20h
0x1800879e7  mov     eax, 0CCCCCCCDh
0x1800879ec  mov     [rsp+58h+pftDueTime.dwHighDateTime], ecx
0x1800879f0  imul    ecx, r14d, 3E8h
0x1800879f7  mul     ecx
0x1800879f9  mov     rcx, r10; pti
0x1800879fc  shr     edx, 4
0x1800879ff  mov     r9d, edx; msWindowLength
0x180087a02  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180087a07  call    cs:__imp_SetThreadpoolTimer
0x180087a0d  mov     rcx, rbp; lpCriticalSection
0x180087a10  call    cs:__imp_EnterCriticalSection
0x180087a16  mov     rcx, rbp; lpCriticalSection
0x180087a19  mov     dword ptr [rsi+18h], 1
0x180087a20  call    cs:__imp_LeaveCriticalSection
0x180087a26  test    rdi, rdi
0x180087a29  jz      short loc_180087A3A
0x180087a2b  lea     rdx, aWfpstarttimer; "WfpStartTimer"
0x180087a32  mov     rcx, rdi
0x180087a35  call    WfpReportError
0x180087a3a  mov     rax, rdi
0x180087a3d  add     rsp, 28h
0x180087a41  pop     r15
0x180087a43  pop     r14
0x180087a45  pop     rdi
0x180087a46  pop     rsi
0x180087a47  pop     rbp
0x180087a48  pop     rbx
0x180087a49  retn
```
