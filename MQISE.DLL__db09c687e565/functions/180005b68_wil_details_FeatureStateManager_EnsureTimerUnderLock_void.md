# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180005b68`
- end: `0x180005c42`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `218`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008704`

## callees

- `0x180005b68`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180005ba5`
- `KERNEL32!CreateThreadpoolTimer` at `0x180005ba5`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005be3`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005be3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005bd9`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005bd9`
- `KERNEL32!SetThreadpoolTimer` at `0x180005bca`
- `KERNEL32!SetThreadpoolTimer` at `0x180005c25`
- `KERNEL32!SetThreadpoolTimer` at `0x180005bca`
- `KERNEL32!SetThreadpoolTimer` at `0x180005c25`
- `KERNEL32!SetLastError` at `0x180005bec`
- `KERNEL32!SetLastError` at `0x180005bf9`
- `KERNEL32!SetLastError` at `0x180005bec`
- `KERNEL32!SetLastError` at `0x180005bf9`
- `KERNEL32!GetLastError` at `0x180005b90`
- `KERNEL32!GetLastError` at `0x180005bb7`
- `KERNEL32!GetLastError` at `0x180005b90`
- `KERNEL32!GetLastError` at `0x180005bb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(_QWORD *pv)
{
  struct _TP_TIMER *v2; // rcx
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // r14
  struct _TP_TIMER *v5; // rsi
  DWORD v6; // ebx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    v2 = (struct _TP_TIMER *)pv[6];
    if ( v2 )
      goto LABEL_6;
    LastError = GetLastError();
    ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
    v5 = (struct _TP_TIMER *)pv[6];
    if ( v5 )
    {
      v6 = GetLastError();
      SetThreadpoolTimer(v5, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v5, 1);
      CloseThreadpoolTimer(v5);
      SetLastError(v6);
    }
    pv[6] = ThreadpoolTimer;
    SetLastError(LastError);
    v2 = (struct _TP_TIMER *)pv[6];
    if ( v2 )
    {
LABEL_6:
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v2, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x180005b68  mov     [rsp+arg_8], rbx
0x180005b6d  mov     [rsp+arg_10], rbp
0x180005b72  push    rsi
0x180005b73  push    rdi
0x180005b74  push    r14
0x180005b76  sub     rsp, 20h
0x180005b7a  mov     rdi, rcx
0x180005b7d  cmp     byte ptr [rcx+41h], 0
0x180005b81  jnz     loc_180005C2F
0x180005b87  mov     rcx, [rcx+30h]
0x180005b8b  test    rcx, rcx
0x180005b8e  jnz     short loc_180005C08
0x180005b90  call    cs:__imp_GetLastError
0x180005b96  mov     ebp, eax
0x180005b98  xor     r8d, r8d; pcbe
0x180005b9b  mov     rdx, rdi; pv
0x180005b9e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005ba5  call    cs:__imp_CreateThreadpoolTimer
0x180005bab  mov     r14, rax
0x180005bae  mov     rsi, [rdi+30h]
0x180005bb2  test    rsi, rsi
0x180005bb5  jz      short loc_180005BF3
0x180005bb7  call    cs:__imp_GetLastError
0x180005bbd  mov     ebx, eax
0x180005bbf  xor     r9d, r9d; msWindowLength
0x180005bc2  xor     r8d, r8d; msPeriod
0x180005bc5  xor     edx, edx; pftDueTime
0x180005bc7  mov     rcx, rsi; pti
0x180005bca  call    cs:__imp_SetThreadpoolTimer
0x180005bd0  nop
0x180005bd1  mov     edx, 1; fCancelPendingCallbacks
0x180005bd6  mov     rcx, rsi; pti
0x180005bd9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005bdf  nop
0x180005be0  mov     rcx, rsi; pti
0x180005be3  call    cs:__imp_CloseThreadpoolTimer
0x180005be9  nop
0x180005bea  mov     ecx, ebx; dwErrCode
0x180005bec  call    cs:__imp_SetLastError
0x180005bf2  nop
0x180005bf3  mov     [rdi+30h], r14
0x180005bf7  mov     ecx, ebp; dwErrCode
0x180005bf9  call    cs:__imp_SetLastError
0x180005bff  mov     rcx, [rdi+30h]; pti
0x180005c03  test    rcx, rcx
0x180005c06  jz      short loc_180005C2F
0x180005c08  mov     rax, 0FFFFFFFF4D2FA200h
0x180005c12  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005c17  mov     r9d, 124F8h; msWindowLength
0x180005c1d  xor     r8d, r8d; msPeriod
0x180005c20  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005c25  call    cs:__imp_SetThreadpoolTimer
0x180005c2b  mov     byte ptr [rdi+41h], 1
0x180005c2f  mov     rbx, [rsp+38h+arg_8]
0x180005c34  mov     rbp, [rsp+38h+arg_10]
0x180005c39  add     rsp, 20h
0x180005c3d  pop     r14
0x180005c3f  pop     rdi
0x180005c40  pop     rsi
0x180005c41  retn
```
