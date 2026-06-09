# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180007778`
- end: `0x18000784c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009424`

## callees

- `0x180007778`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000779e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000779e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800077f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007803`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800077f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007803`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800077e6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800077e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800077d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000782f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800077d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000782f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800077b3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800077b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800077ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800077ef`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[6];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[6] = v5;
      SetLastError(LastError);
    }
    v7 = pv[6];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x180007778  mov     [rsp+arg_8], rbx
0x18000777d  mov     [rsp+arg_10], rbp
0x180007782  push    rsi
0x180007783  push    rdi
0x180007784  push    r14
0x180007786  sub     rsp, 20h
0x18000778a  cmp     byte ptr [rcx+41h], 0
0x18000778e  mov     rdi, rcx
0x180007791  jnz     loc_180007839
0x180007797  cmp     qword ptr [rcx+30h], 0
0x18000779c  jnz     short loc_180007809
0x18000779e  call    cs:__imp_GetLastError
0x1800077a4  xor     r8d, r8d; pcbe
0x1800077a7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800077ae  mov     rdx, rdi; pv
0x1800077b1  mov     ebp, eax
0x1800077b3  call    cs:__imp_CreateThreadpoolTimer
0x1800077b9  mov     rsi, [rdi+30h]
0x1800077bd  mov     r14, rax
0x1800077c0  test    rsi, rsi
0x1800077c3  jz      short loc_1800077FD
0x1800077c5  call    cs:__imp_GetLastError
0x1800077cb  xor     r9d, r9d; msWindowLength
0x1800077ce  xor     r8d, r8d; msPeriod
0x1800077d1  xor     edx, edx; pftDueTime
0x1800077d3  mov     rcx, rsi; pti
0x1800077d6  mov     ebx, eax
0x1800077d8  call    cs:__imp_SetThreadpoolTimer
0x1800077de  mov     edx, 1; fCancelPendingCallbacks
0x1800077e3  mov     rcx, rsi; pti
0x1800077e6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800077ec  mov     rcx, rsi; pti
0x1800077ef  call    cs:__imp_CloseThreadpoolTimer
0x1800077f5  mov     ecx, ebx; dwErrCode
0x1800077f7  call    cs:__imp_SetLastError
0x1800077fd  mov     ecx, ebp; dwErrCode
0x1800077ff  mov     [rdi+30h], r14
0x180007803  call    cs:__imp_SetLastError
0x180007809  mov     rcx, [rdi+30h]; pti
0x18000780d  test    rcx, rcx
0x180007810  jz      short loc_180007839
0x180007812  mov     rax, 0FFFFFFFF4D2FA200h
0x18000781c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180007821  mov     r9d, 124F8h; msWindowLength
0x180007827  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000782c  xor     r8d, r8d; msPeriod
0x18000782f  call    cs:__imp_SetThreadpoolTimer
0x180007835  mov     byte ptr [rdi+41h], 1
0x180007839  mov     rbx, [rsp+38h+arg_8]
0x18000783e  mov     rbp, [rsp+38h+arg_10]
0x180007843  add     rsp, 20h
0x180007847  pop     r14
0x180007849  pop     rdi
0x18000784a  pop     rsi
0x18000784b  retn
```
