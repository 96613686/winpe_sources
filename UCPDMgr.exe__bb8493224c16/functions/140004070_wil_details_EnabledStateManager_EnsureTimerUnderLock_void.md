# wil::details::EnabledStateManager::EnsureTimerUnderLock(void)

- ea: `0x140004070`
- end: `0x140004160`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004318`

## callees

- `0x140004070`
- `0x14000a390`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400040fe`
- `KERNEL32!SetLastError` at `0x14000410a`
- `KERNEL32!SetLastError` at `0x1400040fe`
- `KERNEL32!SetLastError` at `0x14000410a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400040ed`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400040ed`
- `KERNEL32!GetLastError` at `0x1400040a5`
- `KERNEL32!GetLastError` at `0x1400040cc`
- `KERNEL32!GetLastError` at `0x1400040a5`
- `KERNEL32!GetLastError` at `0x1400040cc`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400040f6`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400040f6`
- `KERNEL32!SetThreadpoolTimer` at `0x1400040df`
- `KERNEL32!SetThreadpoolTimer` at `0x140004136`
- `KERNEL32!SetThreadpoolTimer` at `0x1400040df`
- `KERNEL32!SetThreadpoolTimer` at `0x140004136`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400040ba`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400040ba`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 24) )
  {
    if ( !pv[2] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[2];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[2] = v5;
      SetLastError(LastError);
    }
    v7 = pv[2];
    if ( v7 )
    {
      pftDueTime = (_FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 24) = 1;
    }
  }
}

```

## disassembly

```asm
0x140004070  mov     [rsp+arg_8], rbx
0x140004075  mov     [rsp+arg_10], rbp
0x14000407a  push    rsi
0x14000407b  push    rdi
0x14000407c  push    r14
0x14000407e  sub     rsp, 30h
0x140004082  mov     rax, cs:__security_cookie
0x140004089  xor     rax, rsp
0x14000408c  mov     [rsp+48h+var_20], rax
0x140004091  cmp     byte ptr [rcx+18h], 0
0x140004095  mov     rdi, rcx
0x140004098  jnz     loc_140004140
0x14000409e  cmp     qword ptr [rcx+10h], 0
0x1400040a3  jnz     short loc_140004110
0x1400040a5  call    cs:__imp_GetLastError
0x1400040ab  xor     r8d, r8d; pcbe
0x1400040ae  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400040b5  mov     rdx, rdi; pv
0x1400040b8  mov     ebp, eax
0x1400040ba  call    cs:__imp_CreateThreadpoolTimer
0x1400040c0  mov     rsi, [rdi+10h]
0x1400040c4  mov     r14, rax
0x1400040c7  test    rsi, rsi
0x1400040ca  jz      short loc_140004104
0x1400040cc  call    cs:__imp_GetLastError
0x1400040d2  xor     r9d, r9d; msWindowLength
0x1400040d5  xor     r8d, r8d; msPeriod
0x1400040d8  xor     edx, edx; pftDueTime
0x1400040da  mov     rcx, rsi; pti
0x1400040dd  mov     ebx, eax
0x1400040df  call    cs:__imp_SetThreadpoolTimer
0x1400040e5  mov     edx, 1; fCancelPendingCallbacks
0x1400040ea  mov     rcx, rsi; pti
0x1400040ed  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400040f3  mov     rcx, rsi; pti
0x1400040f6  call    cs:__imp_CloseThreadpoolTimer
0x1400040fc  mov     ecx, ebx; dwErrCode
0x1400040fe  call    cs:__imp_SetLastError
0x140004104  mov     ecx, ebp; dwErrCode
0x140004106  mov     [rdi+10h], r14
0x14000410a  call    cs:__imp_SetLastError
0x140004110  mov     rcx, [rdi+10h]; pti
0x140004114  test    rcx, rcx
0x140004117  jz      short loc_140004140
0x140004119  mov     rax, 0FFFFFFFF4D2FA200h
0x140004123  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x140004128  mov     r9d, 124F8h; msWindowLength
0x14000412e  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x140004133  xor     r8d, r8d; msPeriod
0x140004136  call    cs:__imp_SetThreadpoolTimer
0x14000413c  mov     byte ptr [rdi+18h], 1
0x140004140  mov     rcx, [rsp+48h+var_20]
0x140004145  xor     rcx, rsp; StackCookie
0x140004148  call    __security_check_cookie
0x14000414d  mov     rbx, [rsp+48h+arg_8]
0x140004152  mov     rbp, [rsp+48h+arg_10]
0x140004157  add     rsp, 30h
0x14000415b  pop     r14
0x14000415d  pop     rdi
0x14000415e  pop     rsi
0x14000415f  retn
```
