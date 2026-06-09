# CTimer::Start(ulong)

- ea: `0x180027ef0`
- end: `0x180027fc2`
- name: `?Start@CTimer@@QEAAJK@Z`
- size: `210`
- prototype: `__int64 __fastcall(CTimer *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026d1c`

## callees

- `0x180027ef0`
- `0x18006a3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027f0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027f0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027fa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027fa3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027f73`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027f73`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180027f44`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180027f44`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180027f2d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180027f2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTimer::Start(CTimer *this, unsigned int a2)
{
  __int64 v2; // rbp
  signed int v4; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  signed int LastError; // eax
  _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  v2 = a2;
  v4 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  pftDueTime = (_FILETIME)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (_DWORD)v2 )
  {
    if ( *((_QWORD *)this + 7) )
      goto LABEL_17;
    *((_QWORD *)this + 7) = CreateThreadpoolTimer(CTimer::s_TimerTickProc, this, 0);
    if ( *((_QWORD *)this + 7) )
      goto LABEL_17;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_17:
      if ( IsThreadpoolTimerSet(*((PTP_TIMER *)this + 7)) )
      {
        v4 = -2147019873;
      }
      else
      {
        pftDueTime = (_FILETIME)(-10000 * v2);
        SetThreadpoolTimer(*((PTP_TIMER *)this + 7), &pftDueTime, 0, 0);
      }
    }
  }
  else
  {
    CTimer::_OnTimerCallback(this);
  }
  if ( v5 )
    LeaveCriticalSection(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180027ef0  push    rbx
0x180027ef2  push    rbp
0x180027ef3  push    rsi
0x180027ef4  push    rdi
0x180027ef5  sub     rsp, 28h
0x180027ef9  mov     ebp, edx
0x180027efb  mov     rdi, rcx
0x180027efe  xor     ebx, ebx
0x180027f00  lea     rsi, [rcx+10h]
0x180027f04  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rsi
0x180027f09  mov     rcx, rsi; lpCriticalSection
0x180027f0c  call    cs:__imp_EnterCriticalSection
0x180027f12  nop
0x180027f13  test    ebp, ebp
0x180027f15  jz      short loc_180027F93
0x180027f17  mov     rax, [rdi+38h]
0x180027f1b  test    rax, rax
0x180027f1e  jnz     short loc_180027F40
0x180027f20  xor     r8d, r8d; pcbe
0x180027f23  mov     rdx, rdi; pv
0x180027f26  lea     rcx, ?s_TimerTickProc@CTimer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180027f2d  call    cs:__imp_CreateThreadpoolTimer
0x180027f33  mov     [rdi+38h], rax
0x180027f37  mov     rax, [rdi+38h]
0x180027f3b  test    rax, rax
0x180027f3e  jz      short loc_180027FA3
0x180027f40  mov     rcx, [rdi+38h]; pti
0x180027f44  call    cs:__imp_IsThreadpoolTimerSet
0x180027f4a  test    eax, eax
0x180027f4c  jnz     short loc_180027FBA
0x180027f4e  imul    rax, rbp, 0FFFFFFFFFFFFD8F0h
0x180027f55  mov     rdx, rax
0x180027f58  shr     rdx, 20h
0x180027f5c  mov     [rsp+48h+pftDueTime.dwHighDateTime], edx
0x180027f60  mov     [rsp+48h+pftDueTime.dwLowDateTime], eax
0x180027f64  xor     r9d, r9d; msWindowLength
0x180027f67  xor     r8d, r8d; msPeriod
0x180027f6a  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180027f6f  mov     rcx, [rdi+38h]; pti
0x180027f73  call    cs:__imp_SetThreadpoolTimer
0x180027f79  nop
0x180027f7a  test    rsi, rsi
0x180027f7d  jz      short loc_180027F88
0x180027f7f  mov     rcx, rsi; lpCriticalSection
0x180027f82  call    cs:__imp_LeaveCriticalSection
0x180027f88  mov     eax, ebx
0x180027f8a  add     rsp, 28h
0x180027f8e  pop     rdi
0x180027f8f  pop     rsi
0x180027f90  pop     rbp
0x180027f91  pop     rbx
0x180027f92  retn
0x180027f93  mov     rcx, rdi; this
0x180027f96  call    ?_OnTimerCallback@CTimer@@AEAAXXZ; CTimer::_OnTimerCallback(void)
0x180027f9b  jmp     short loc_180027F7A
0x180027f9d  test    ebx, ebx
0x180027f9f  js      short loc_180027F7A
0x180027fa1  jmp     short loc_180027F40
0x180027fa3  call    cs:__imp_GetLastError
0x180027fa9  mov     ebx, eax
0x180027fab  test    eax, eax
0x180027fad  jle     short loc_180027F9D
0x180027faf  movzx   ebx, ax
0x180027fb2  or      ebx, 80070000h
0x180027fb8  jmp     short loc_180027F9D
0x180027fba  mov     ebx, 8007139Fh
0x180027fbf  jmp     short loc_180027F7A
```
