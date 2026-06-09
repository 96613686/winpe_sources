# PaymentBackgroundManager::Uninitialize(void)

- ea: `0x18007fdc4`
- end: `0x18007fe82`
- name: `?Uninitialize@PaymentBackgroundManager@@IEAAXXZ`
- size: `190`
- prototype: `void __fastcall(PaymentBackgroundManager *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011a64`
- `0x180012368`
- `0x18007f928`

## callees

- `0x18007fdc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fe4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fe4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fe28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007fe28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fe59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fe59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007fe11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007fe6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007fe11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007fe6c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007fe00`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007fe00`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007fdf2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007fdf2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007fe09`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007fe09`
- `BrokerLib!BrDeleteBrokerInstance` at `0x18007fe64`
- `BrokerLib!BrDeleteBrokerInstance` at `0x18007fe64`

## pseudocode

```c
void __fastcall PaymentBackgroundManager::Uninitialize(PaymentBackgroundManager *this)
{
  struct _TP_TIMER *v1; // rsi
  DWORD LastError; // ebx
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // rbx
  char *v6; // rdi
  DWORD v7; // edi
  char v8; // [rsp+20h] [rbp-18h] BYREF

  v1 = (struct _TP_TIMER *)*((_QWORD *)this + 8);
  if ( v1 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v1, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v1, 1);
    CloseThreadpoolTimer(v1);
    SetLastError(LastError);
  }
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  *((_QWORD *)this + 8) = 0;
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v6 = (char *)this + 48;
  if ( &v8 != v6 )
  {
    v5 = *(_QWORD *)v6;
    *(_QWORD *)v6 = 0;
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  if ( v5 )
  {
    v7 = GetLastError();
    BrDeleteBrokerInstance(v5);
    SetLastError(v7);
  }
}

```

## disassembly

```asm
0x18007fdc4  mov     [rsp+arg_0], rbx
0x18007fdc9  mov     [rsp+arg_8], rsi
0x18007fdce  push    rdi
0x18007fdcf  sub     rsp, 30h
0x18007fdd3  mov     rsi, [rcx+40h]
0x18007fdd7  mov     rdi, rcx
0x18007fdda  test    rsi, rsi
0x18007fddd  jz      short loc_18007FE17
0x18007fddf  call    cs:__imp_GetLastError
0x18007fde5  xor     r9d, r9d; msWindowLength
0x18007fde8  xor     r8d, r8d; msPeriod
0x18007fdeb  xor     edx, edx; pftDueTime
0x18007fded  mov     rcx, rsi; pti
0x18007fdf0  mov     ebx, eax
0x18007fdf2  call    cs:__imp_SetThreadpoolTimer
0x18007fdf8  mov     edx, 1; fCancelPendingCallbacks
0x18007fdfd  mov     rcx, rsi; pti
0x18007fe00  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007fe06  mov     rcx, rsi; pti
0x18007fe09  call    cs:__imp_CloseThreadpoolTimer
0x18007fe0f  mov     ecx, ebx; dwErrCode
0x18007fe11  call    cs:__imp_SetLastError
0x18007fe17  lea     rsi, [rdi+8]
0x18007fe1b  mov     qword ptr [rdi+40h], 0
0x18007fe23  mov     rcx, rsi; lpCriticalSection
0x18007fe26  xor     ebx, ebx
0x18007fe28  call    cs:__imp_EnterCriticalSection
0x18007fe2e  lea     rax, [rsp+38h+var_18]
0x18007fe33  add     rdi, 30h ; '0'
0x18007fe37  cmp     rax, rdi
0x18007fe3a  jz      short loc_18007FE46
0x18007fe3c  mov     rbx, [rdi]
0x18007fe3f  mov     qword ptr [rdi], 0
0x18007fe46  test    rsi, rsi
0x18007fe49  jz      short loc_18007FE54
0x18007fe4b  mov     rcx, rsi; lpCriticalSection
0x18007fe4e  call    cs:__imp_LeaveCriticalSection
0x18007fe54  test    rbx, rbx
0x18007fe57  jz      short loc_18007FE72
0x18007fe59  call    cs:__imp_GetLastError
0x18007fe5f  mov     rcx, rbx
0x18007fe62  mov     edi, eax
0x18007fe64  call    cs:__imp_BrDeleteBrokerInstance
0x18007fe6a  mov     ecx, edi; dwErrCode
0x18007fe6c  call    cs:__imp_SetLastError
0x18007fe72  mov     rbx, [rsp+38h+arg_0]
0x18007fe77  mov     rsi, [rsp+38h+arg_8]
0x18007fe7c  add     rsp, 30h
0x18007fe80  pop     rdi
0x18007fe81  retn
```
