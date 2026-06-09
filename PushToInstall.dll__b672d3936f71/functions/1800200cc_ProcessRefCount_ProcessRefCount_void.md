# ProcessRefCount::~ProcessRefCount(void)

- ea: `0x1800200cc`
- end: `0x1800201b7`
- name: `??1ProcessRefCount@@QEAA@XZ`
- size: `235`
- prototype: `void __fastcall(ProcessRefCount *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800201c0`
- `0x1800212ac`
- `0x18004c657`

## callees

- `0x180011afc`
- `0x1800200cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002013d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002013d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002016f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002016f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020186`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020167`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020167`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002012e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002015e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002012e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002015e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002011f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020150`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002011f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020150`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180020109`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180020109`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x1800200ea`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x1800200ea`

## string_xrefs

- `0x1800201a5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ProcessRefCount::~ProcessRefCount(ProcessRefCount *this)
{
  struct _TP_TIMER *v2; // rcx
  struct _TP_TIMER *v3; // rsi
  DWORD LastError; // ebx
  void *v5; // rcx
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &ProcessRefCount::`vftable';
  SetProcessReference(0);
  if ( *((_QWORD *)this + 4) )
  {
    _InterlockedExchange((volatile __int32 *)this + 2, 0);
    v2 = (struct _TP_TIMER *)*((_QWORD *)this + 4);
    if ( v2 && IsThreadpoolTimerSet(v2) )
    {
      SetThreadpoolTimer(*((PTP_TIMER *)this + 4), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 4), 1);
    }
    v3 = (struct _TP_TIMER *)*((_QWORD *)this + 4);
    if ( v3 )
    {
      LastError = GetLastError();
      SetThreadpoolTimer(v3, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v3, 1);
      CloseThreadpoolTimer(v3);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 4) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
  {
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v6);
  }
}

```

## disassembly

```asm
0x1800200cc  mov     [rsp+arg_0], rbx
0x1800200d1  mov     [rsp+arg_8], rsi
0x1800200d6  push    rdi
0x1800200d7  sub     rsp, 20h
0x1800200db  lea     rax, ??_7ProcessRefCount@@6B@; const ProcessRefCount::`vftable'
0x1800200e2  mov     rdi, rcx
0x1800200e5  mov     [rcx], rax
0x1800200e8  xor     ecx, ecx
0x1800200ea  call    cs:__imp_SetProcessReference
0x1800200f0  cmp     qword ptr [rdi+20h], 0
0x1800200f5  jz      loc_18002017D
0x1800200fb  xor     eax, eax
0x1800200fd  xchg    eax, [rdi+8]
0x180020100  mov     rcx, [rdi+20h]; pti
0x180020104  test    rcx, rcx
0x180020107  jz      short loc_180020134
0x180020109  call    cs:__imp_IsThreadpoolTimerSet
0x18002010f  test    eax, eax
0x180020111  jz      short loc_180020134
0x180020113  mov     rcx, [rdi+20h]; pti
0x180020117  xor     r9d, r9d; msWindowLength
0x18002011a  xor     r8d, r8d; msPeriod
0x18002011d  xor     edx, edx; pftDueTime
0x18002011f  call    cs:__imp_SetThreadpoolTimer
0x180020125  mov     rcx, [rdi+20h]; pti
0x180020129  mov     edx, 1; fCancelPendingCallbacks
0x18002012e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180020134  mov     rsi, [rdi+20h]
0x180020138  test    rsi, rsi
0x18002013b  jz      short loc_180020175
0x18002013d  call    cs:__imp_GetLastError
0x180020143  xor     r9d, r9d; msWindowLength
0x180020146  xor     r8d, r8d; msPeriod
0x180020149  xor     edx, edx; pftDueTime
0x18002014b  mov     rcx, rsi; pti
0x18002014e  mov     ebx, eax
0x180020150  call    cs:__imp_SetThreadpoolTimer
0x180020156  mov     edx, 1; fCancelPendingCallbacks
0x18002015b  mov     rcx, rsi; pti
0x18002015e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180020164  mov     rcx, rsi; pti
0x180020167  call    cs:__imp_CloseThreadpoolTimer
0x18002016d  mov     ecx, ebx; dwErrCode
0x18002016f  call    cs:__imp_SetLastError
0x180020175  mov     qword ptr [rdi+20h], 0
0x18002017d  mov     rcx, [rdi+18h]; hObject
0x180020181  test    rcx, rcx
0x180020184  jz      short loc_180020190
0x180020186  call    cs:__imp_CloseHandle
0x18002018c  test    eax, eax
0x18002018e  jz      short loc_1800201A0
0x180020190  mov     rbx, [rsp+28h+arg_0]
0x180020195  mov     rsi, [rsp+28h+arg_8]
0x18002019a  add     rsp, 20h
0x18002019e  pop     rdi
0x18002019f  retn
0x1800201a0  mov     rcx, [rsp+28h]; this
0x1800201a5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800201ac  mov     edx, 0A0Bh; void *
0x1800201b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
