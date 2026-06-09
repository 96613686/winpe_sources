# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180008e38`
- end: `0x180008f0c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aab8`

## callees

- `0x180008e38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008eb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ec3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008eb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e85`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008eaf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008eaf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008e98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008eef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008e98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008eef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008e73`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008e73`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008ea6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008ea6`

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
0x180008e38  mov     [rsp+arg_8], rbx
0x180008e3d  mov     [rsp+arg_10], rbp
0x180008e42  push    rsi
0x180008e43  push    rdi
0x180008e44  push    r14
0x180008e46  sub     rsp, 20h
0x180008e4a  cmp     byte ptr [rcx+41h], 0
0x180008e4e  mov     rdi, rcx
0x180008e51  jnz     loc_180008EF9
0x180008e57  cmp     qword ptr [rcx+30h], 0
0x180008e5c  jnz     short loc_180008EC9
0x180008e5e  call    cs:__imp_GetLastError
0x180008e64  xor     r8d, r8d; pcbe
0x180008e67  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008e6e  mov     rdx, rdi; pv
0x180008e71  mov     ebp, eax
0x180008e73  call    cs:__imp_CreateThreadpoolTimer
0x180008e79  mov     rsi, [rdi+30h]
0x180008e7d  mov     r14, rax
0x180008e80  test    rsi, rsi
0x180008e83  jz      short loc_180008EBD
0x180008e85  call    cs:__imp_GetLastError
0x180008e8b  xor     r9d, r9d; msWindowLength
0x180008e8e  xor     r8d, r8d; msPeriod
0x180008e91  xor     edx, edx; pftDueTime
0x180008e93  mov     rcx, rsi; pti
0x180008e96  mov     ebx, eax
0x180008e98  call    cs:__imp_SetThreadpoolTimer
0x180008e9e  mov     edx, 1; fCancelPendingCallbacks
0x180008ea3  mov     rcx, rsi; pti
0x180008ea6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008eac  mov     rcx, rsi; pti
0x180008eaf  call    cs:__imp_CloseThreadpoolTimer
0x180008eb5  mov     ecx, ebx; dwErrCode
0x180008eb7  call    cs:__imp_SetLastError
0x180008ebd  mov     ecx, ebp; dwErrCode
0x180008ebf  mov     [rdi+30h], r14
0x180008ec3  call    cs:__imp_SetLastError
0x180008ec9  mov     rcx, [rdi+30h]; pti
0x180008ecd  test    rcx, rcx
0x180008ed0  jz      short loc_180008EF9
0x180008ed2  mov     rax, 0FFFFFFFF4D2FA200h
0x180008edc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180008ee1  mov     r9d, 124F8h; msWindowLength
0x180008ee7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180008eec  xor     r8d, r8d; msPeriod
0x180008eef  call    cs:__imp_SetThreadpoolTimer
0x180008ef5  mov     byte ptr [rdi+41h], 1
0x180008ef9  mov     rbx, [rsp+38h+arg_8]
0x180008efe  mov     rbp, [rsp+38h+arg_10]
0x180008f03  add     rsp, 20h
0x180008f07  pop     r14
0x180008f09  pop     rdi
0x180008f0a  pop     rsi
0x180008f0b  retn
```
