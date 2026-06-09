# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180024448`
- end: `0x18002451c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026004`

## callees

- `0x180024448`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180024483`
- `KERNEL32!CreateThreadpoolTimer` at `0x180024483`
- `KERNEL32!SetThreadpoolTimer` at `0x1800244a8`
- `KERNEL32!SetThreadpoolTimer` at `0x1800244ff`
- `KERNEL32!SetThreadpoolTimer` at `0x1800244a8`
- `KERNEL32!SetThreadpoolTimer` at `0x1800244ff`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800244bf`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800244bf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800244b6`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800244b6`
- `KERNEL32!SetLastError` at `0x1800244c7`
- `KERNEL32!SetLastError` at `0x1800244d3`
- `KERNEL32!SetLastError` at `0x1800244c7`
- `KERNEL32!SetLastError` at `0x1800244d3`
- `KERNEL32!GetLastError` at `0x18002446e`
- `KERNEL32!GetLastError` at `0x180024495`
- `KERNEL32!GetLastError` at `0x18002446e`
- `KERNEL32!GetLastError` at `0x180024495`

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
0x180024448  mov     [rsp+arg_8], rbx
0x18002444d  mov     [rsp+arg_10], rbp
0x180024452  push    rsi
0x180024453  push    rdi
0x180024454  push    r14
0x180024456  sub     rsp, 20h
0x18002445a  cmp     byte ptr [rcx+41h], 0
0x18002445e  mov     rdi, rcx
0x180024461  jnz     loc_180024509
0x180024467  cmp     qword ptr [rcx+30h], 0
0x18002446c  jnz     short loc_1800244D9
0x18002446e  call    cs:__imp_GetLastError
0x180024474  xor     r8d, r8d; pcbe
0x180024477  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002447e  mov     rdx, rdi; pv
0x180024481  mov     ebp, eax
0x180024483  call    cs:__imp_CreateThreadpoolTimer
0x180024489  mov     rsi, [rdi+30h]
0x18002448d  mov     r14, rax
0x180024490  test    rsi, rsi
0x180024493  jz      short loc_1800244CD
0x180024495  call    cs:__imp_GetLastError
0x18002449b  xor     r9d, r9d; msWindowLength
0x18002449e  xor     r8d, r8d; msPeriod
0x1800244a1  xor     edx, edx; pftDueTime
0x1800244a3  mov     rcx, rsi; pti
0x1800244a6  mov     ebx, eax
0x1800244a8  call    cs:__imp_SetThreadpoolTimer
0x1800244ae  mov     edx, 1; fCancelPendingCallbacks
0x1800244b3  mov     rcx, rsi; pti
0x1800244b6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800244bc  mov     rcx, rsi; pti
0x1800244bf  call    cs:__imp_CloseThreadpoolTimer
0x1800244c5  mov     ecx, ebx; dwErrCode
0x1800244c7  call    cs:__imp_SetLastError
0x1800244cd  mov     ecx, ebp; dwErrCode
0x1800244cf  mov     [rdi+30h], r14
0x1800244d3  call    cs:__imp_SetLastError
0x1800244d9  mov     rcx, [rdi+30h]; pti
0x1800244dd  test    rcx, rcx
0x1800244e0  jz      short loc_180024509
0x1800244e2  mov     rax, 0FFFFFFFF4D2FA200h
0x1800244ec  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800244f1  mov     r9d, 124F8h; msWindowLength
0x1800244f7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800244fc  xor     r8d, r8d; msPeriod
0x1800244ff  call    cs:__imp_SetThreadpoolTimer
0x180024505  mov     byte ptr [rdi+41h], 1
0x180024509  mov     rbx, [rsp+38h+arg_8]
0x18002450e  mov     rbp, [rsp+38h+arg_10]
0x180024513  add     rsp, 20h
0x180024517  pop     r14
0x180024519  pop     rdi
0x18002451a  pop     rsi
0x18002451b  retn
```
