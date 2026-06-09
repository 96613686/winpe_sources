# CSurrogateTimeout::StartTimer(uint,void (*)(void *))

- ea: `0x180042778`
- end: `0x18004286f`
- name: `?StartTimer@CSurrogateTimeout@@QEAAJIP6AXPEAX@Z@Z`
- size: `247`
- prototype: `__int64 __fastcall(PVOID pv, unsigned int, void (*)(void *))`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180041fe0`
- `0x180042120`

## callees

- `0x18003aa84`
- `0x180042778`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800427aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800427aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800427a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800427b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800427a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800427b3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800427dd`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800427dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004283b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004283b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800427fd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800427fd`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180042852`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180042852`

## pseudocode

```c
__int64 __fastcall CSurrogateTimeout::StartTimer(struct _TP_TIMER **pv, __int64 a2, void (*a3)(void *))
{
  int Error; // ebx
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v7; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v9; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+18h] BYREF

  pftDueTime = (struct _FILETIME)a3;
  Error = -2147175934;
  if ( !CSurrogateTimeout::s_fTerminated )
  {
    CurrentProcess = GetCurrentProcess();
    CurrentThread = GetCurrentThread();
    v7 = GetCurrentProcess();
    if ( DuplicateHandle(v7, CurrentThread, CurrentProcess, (LPHANDLE)pv, 0x1FFFFFu, 1, 0)
      || (int)ResultFromKnownLastError() >= 0 )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(CSurrogateTimeout::_s_TimeOutThreadProc, pv, 0);
      pv[1] = ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        Error = 0;
LABEL_7:
        v9 = pv[1];
        pv[2] = 0;
        pftDueTime = (struct _FILETIME)-1200000000LL;
        SetThreadpoolTimer(v9, &pftDueTime, 0, 0);
        return (unsigned int)Error;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_7;
    }
    SHCreateThread(CSurrogateTimeout::_s_ReportTimeout, 0, 0, 0);
    return (unsigned int)-2147175934;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180042778  mov     [rsp+arg_0], rbx
0x18004277d  mov     [rsp+arg_8], rsi
0x180042782  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], r8
0x180042787  push    rdi
0x180042788  sub     rsp, 40h
0x18004278c  cmp     cs:?s_fTerminated@CSurrogateTimeout@@0_NA, 0; bool CSurrogateTimeout::s_fTerminated
0x180042793  mov     rsi, rcx
0x180042796  mov     ebx, 8004B202h
0x18004279b  jnz     loc_18004285D
0x1800427a1  call    cs:__imp_GetCurrentProcess
0x1800427a7  mov     rdi, rax
0x1800427aa  call    cs:__imp_GetCurrentThread
0x1800427b0  mov     rbx, rax
0x1800427b3  call    cs:__imp_GetCurrentProcess
0x1800427b9  mov     [rsp+48h+dwOptions], 0; dwOptions
0x1800427c1  mov     r9, rsi; lpTargetHandle
0x1800427c4  mov     rcx, rax; hSourceProcessHandle
0x1800427c7  mov     [rsp+48h+bInheritHandle], 1; bInheritHandle
0x1800427cf  mov     r8, rdi; hTargetProcessHandle
0x1800427d2  mov     [rsp+48h+dwDesiredAccess], 1FFFFFh; dwDesiredAccess
0x1800427da  mov     rdx, rbx; hSourceHandle
0x1800427dd  call    cs:__imp_DuplicateHandle
0x1800427e3  test    eax, eax
0x1800427e5  jnz     short loc_1800427F0
0x1800427e7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800427ec  test    eax, eax
0x1800427ee  js      short loc_180042843
0x1800427f0  xor     r8d, r8d; pcbe
0x1800427f3  lea     rcx, ?_s_TimeOutThreadProc@CSurrogateTimeout@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800427fa  mov     rdx, rsi; pv
0x1800427fd  call    cs:__imp_CreateThreadpoolTimer
0x180042803  mov     [rsi+8], rax
0x180042807  test    rax, rax
0x18004280a  jz      short loc_180042810
0x18004280c  xor     ebx, ebx
0x18004280e  jmp     short loc_18004281B
0x180042810  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180042815  mov     ebx, eax
0x180042817  test    eax, eax
0x180042819  js      short loc_180042843
0x18004281b  mov     rcx, [rsi+8]; pti
0x18004281f  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180042824  xor     r9d, r9d; msWindowLength
0x180042827  mov     qword ptr [rsi+10h], 0
0x18004282f  xor     r8d, r8d; msPeriod
0x180042832  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFB8797400h
0x18004283b  call    cs:__imp_SetThreadpoolTimer
0x180042841  jmp     short loc_18004285D
0x180042843  xor     r9d, r9d; pfnCallback
0x180042846  lea     rcx, ?_s_ReportTimeout@CSurrogateTimeout@@CAKPEAX@Z; pfnThreadProc
0x18004284d  xor     r8d, r8d; flags
0x180042850  xor     edx, edx; pData
0x180042852  call    cs:__imp_SHCreateThread
0x180042858  mov     ebx, 8004B202h
0x18004285d  mov     rsi, [rsp+48h+arg_8]
0x180042862  mov     eax, ebx
0x180042864  mov     rbx, [rsp+48h+arg_0]
0x180042869  add     rsp, 40h
0x18004286d  pop     rdi
0x18004286e  retn
```
