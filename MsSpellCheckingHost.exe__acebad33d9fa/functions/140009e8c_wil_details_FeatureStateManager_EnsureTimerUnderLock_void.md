# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140009e8c`
- end: `0x140009f60`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c364`

## callees

- `0x140009e8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009ed9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009f0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009f17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009f0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009f17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009eec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009f43`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009eec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009f43`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009efa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009efa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009f03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009f03`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140009ec7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140009ec7`

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
0x140009e8c  mov     [rsp+arg_8], rbx
0x140009e91  mov     [rsp+arg_10], rbp
0x140009e96  push    rsi
0x140009e97  push    rdi
0x140009e98  push    r14
0x140009e9a  sub     rsp, 20h
0x140009e9e  cmp     byte ptr [rcx+41h], 0
0x140009ea2  mov     rdi, rcx
0x140009ea5  jnz     loc_140009F4D
0x140009eab  cmp     qword ptr [rcx+30h], 0
0x140009eb0  jnz     short loc_140009F1D
0x140009eb2  call    cs:__imp_GetLastError
0x140009eb8  xor     r8d, r8d; pcbe
0x140009ebb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140009ec2  mov     rdx, rdi; pv
0x140009ec5  mov     ebp, eax
0x140009ec7  call    cs:__imp_CreateThreadpoolTimer
0x140009ecd  mov     rsi, [rdi+30h]
0x140009ed1  mov     r14, rax
0x140009ed4  test    rsi, rsi
0x140009ed7  jz      short loc_140009F11
0x140009ed9  call    cs:__imp_GetLastError
0x140009edf  xor     r9d, r9d; msWindowLength
0x140009ee2  xor     r8d, r8d; msPeriod
0x140009ee5  xor     edx, edx; pftDueTime
0x140009ee7  mov     rcx, rsi; pti
0x140009eea  mov     ebx, eax
0x140009eec  call    cs:__imp_SetThreadpoolTimer
0x140009ef2  mov     edx, 1; fCancelPendingCallbacks
0x140009ef7  mov     rcx, rsi; pti
0x140009efa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009f00  mov     rcx, rsi; pti
0x140009f03  call    cs:__imp_CloseThreadpoolTimer
0x140009f09  mov     ecx, ebx; dwErrCode
0x140009f0b  call    cs:__imp_SetLastError
0x140009f11  mov     ecx, ebp; dwErrCode
0x140009f13  mov     [rdi+30h], r14
0x140009f17  call    cs:__imp_SetLastError
0x140009f1d  mov     rcx, [rdi+30h]; pti
0x140009f21  test    rcx, rcx
0x140009f24  jz      short loc_140009F4D
0x140009f26  mov     rax, 0FFFFFFFF4D2FA200h
0x140009f30  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140009f35  mov     r9d, 124F8h; msWindowLength
0x140009f3b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140009f40  xor     r8d, r8d; msPeriod
0x140009f43  call    cs:__imp_SetThreadpoolTimer
0x140009f49  mov     byte ptr [rdi+41h], 1
0x140009f4d  mov     rbx, [rsp+38h+arg_8]
0x140009f52  mov     rbp, [rsp+38h+arg_10]
0x140009f57  add     rsp, 20h
0x140009f5b  pop     r14
0x140009f5d  pop     rdi
0x140009f5e  pop     rsi
0x140009f5f  retn
```
