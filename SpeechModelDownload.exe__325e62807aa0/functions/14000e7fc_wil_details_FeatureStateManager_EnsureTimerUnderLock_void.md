# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x14000e7fc`
- end: `0x14000e8d0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011150`

## callees

- `0x14000e7fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e849`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e87b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e87b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e887`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000e837`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000e837`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e85c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e8b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e85c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e8b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e873`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e873`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e86a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e86a`

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
0x14000e7fc  mov     [rsp+arg_8], rbx
0x14000e801  mov     [rsp+arg_10], rbp
0x14000e806  push    rsi
0x14000e807  push    rdi
0x14000e808  push    r14
0x14000e80a  sub     rsp, 20h
0x14000e80e  cmp     byte ptr [rcx+41h], 0
0x14000e812  mov     rdi, rcx
0x14000e815  jnz     loc_14000E8BD
0x14000e81b  cmp     qword ptr [rcx+30h], 0
0x14000e820  jnz     short loc_14000E88D
0x14000e822  call    cs:__imp_GetLastError
0x14000e828  xor     r8d, r8d; pcbe
0x14000e82b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000e832  mov     rdx, rdi; pv
0x14000e835  mov     ebp, eax
0x14000e837  call    cs:__imp_CreateThreadpoolTimer
0x14000e83d  mov     rsi, [rdi+30h]
0x14000e841  mov     r14, rax
0x14000e844  test    rsi, rsi
0x14000e847  jz      short loc_14000E881
0x14000e849  call    cs:__imp_GetLastError
0x14000e84f  xor     r9d, r9d; msWindowLength
0x14000e852  xor     r8d, r8d; msPeriod
0x14000e855  xor     edx, edx; pftDueTime
0x14000e857  mov     rcx, rsi; pti
0x14000e85a  mov     ebx, eax
0x14000e85c  call    cs:__imp_SetThreadpoolTimer
0x14000e862  mov     edx, 1; fCancelPendingCallbacks
0x14000e867  mov     rcx, rsi; pti
0x14000e86a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000e870  mov     rcx, rsi; pti
0x14000e873  call    cs:__imp_CloseThreadpoolTimer
0x14000e879  mov     ecx, ebx; dwErrCode
0x14000e87b  call    cs:__imp_SetLastError
0x14000e881  mov     ecx, ebp; dwErrCode
0x14000e883  mov     [rdi+30h], r14
0x14000e887  call    cs:__imp_SetLastError
0x14000e88d  mov     rcx, [rdi+30h]; pti
0x14000e891  test    rcx, rcx
0x14000e894  jz      short loc_14000E8BD
0x14000e896  mov     rax, 0FFFFFFFF4D2FA200h
0x14000e8a0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x14000e8a5  mov     r9d, 124F8h; msWindowLength
0x14000e8ab  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x14000e8b0  xor     r8d, r8d; msPeriod
0x14000e8b3  call    cs:__imp_SetThreadpoolTimer
0x14000e8b9  mov     byte ptr [rdi+41h], 1
0x14000e8bd  mov     rbx, [rsp+38h+arg_8]
0x14000e8c2  mov     rbp, [rsp+38h+arg_10]
0x14000e8c7  add     rsp, 20h
0x14000e8cb  pop     r14
0x14000e8cd  pop     rdi
0x14000e8ce  pop     rsi
0x14000e8cf  retn
```
