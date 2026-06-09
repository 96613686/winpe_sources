# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000566c`
- end: `0x180005740`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007594`

## callees

- `0x18000566c`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1800056a7`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800056a7`
- `KERNEL32!SetThreadpoolTimer` at `0x1800056cc`
- `KERNEL32!SetThreadpoolTimer` at `0x180005723`
- `KERNEL32!SetThreadpoolTimer` at `0x1800056cc`
- `KERNEL32!SetThreadpoolTimer` at `0x180005723`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800056e3`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800056e3`
- `KERNEL32!GetLastError` at `0x180005692`
- `KERNEL32!GetLastError` at `0x1800056b9`
- `KERNEL32!GetLastError` at `0x180005692`
- `KERNEL32!GetLastError` at `0x1800056b9`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800056da`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800056da`
- `KERNEL32!SetLastError` at `0x1800056eb`
- `KERNEL32!SetLastError` at `0x1800056f7`
- `KERNEL32!SetLastError` at `0x1800056eb`
- `KERNEL32!SetLastError` at `0x1800056f7`

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
0x18000566c  mov     [rsp+arg_8], rbx
0x180005671  mov     [rsp+arg_10], rbp
0x180005676  push    rsi
0x180005677  push    rdi
0x180005678  push    r14
0x18000567a  sub     rsp, 20h
0x18000567e  cmp     byte ptr [rcx+41h], 0
0x180005682  mov     rdi, rcx
0x180005685  jnz     loc_18000572D
0x18000568b  cmp     qword ptr [rcx+30h], 0
0x180005690  jnz     short loc_1800056FD
0x180005692  call    cs:__imp_GetLastError
0x180005698  xor     r8d, r8d; pcbe
0x18000569b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800056a2  mov     rdx, rdi; pv
0x1800056a5  mov     ebp, eax
0x1800056a7  call    cs:__imp_CreateThreadpoolTimer
0x1800056ad  mov     rsi, [rdi+30h]
0x1800056b1  mov     r14, rax
0x1800056b4  test    rsi, rsi
0x1800056b7  jz      short loc_1800056F1
0x1800056b9  call    cs:__imp_GetLastError
0x1800056bf  xor     r9d, r9d; msWindowLength
0x1800056c2  xor     r8d, r8d; msPeriod
0x1800056c5  xor     edx, edx; pftDueTime
0x1800056c7  mov     rcx, rsi; pti
0x1800056ca  mov     ebx, eax
0x1800056cc  call    cs:__imp_SetThreadpoolTimer
0x1800056d2  mov     edx, 1; fCancelPendingCallbacks
0x1800056d7  mov     rcx, rsi; pti
0x1800056da  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800056e0  mov     rcx, rsi; pti
0x1800056e3  call    cs:__imp_CloseThreadpoolTimer
0x1800056e9  mov     ecx, ebx; dwErrCode
0x1800056eb  call    cs:__imp_SetLastError
0x1800056f1  mov     ecx, ebp; dwErrCode
0x1800056f3  mov     [rdi+30h], r14
0x1800056f7  call    cs:__imp_SetLastError
0x1800056fd  mov     rcx, [rdi+30h]; pti
0x180005701  test    rcx, rcx
0x180005704  jz      short loc_18000572D
0x180005706  mov     rax, 0FFFFFFFF4D2FA200h
0x180005710  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005715  mov     r9d, 124F8h; msWindowLength
0x18000571b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005720  xor     r8d, r8d; msPeriod
0x180005723  call    cs:__imp_SetThreadpoolTimer
0x180005729  mov     byte ptr [rdi+41h], 1
0x18000572d  mov     rbx, [rsp+38h+arg_8]
0x180005732  mov     rbp, [rsp+38h+arg_10]
0x180005737  add     rsp, 20h
0x18000573b  pop     r14
0x18000573d  pop     rdi
0x18000573e  pop     rsi
0x18000573f  retn
```
