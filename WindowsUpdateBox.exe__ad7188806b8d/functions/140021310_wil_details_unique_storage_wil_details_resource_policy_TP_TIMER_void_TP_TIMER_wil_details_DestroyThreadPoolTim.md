# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x140021310`
- end: `0x1400213a1`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140004484`
- `0x14000c794`
- `0x14001b6f4`

## callees

- `0x140021310`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x14002134b`
- `KERNEL32!SetThreadpoolTimer` at `0x14002134b`
- `KERNEL32!CloseThreadpoolTimer` at `0x14002136e`
- `KERNEL32!CloseThreadpoolTimer` at `0x14002136e`
- `KERNEL32!GetLastError` at `0x140021332`
- `KERNEL32!GetLastError` at `0x140021332`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14002135f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14002135f`
- `KERNEL32!SetLastError` at `0x14002137c`
- `KERNEL32!SetLastError` at `0x14002137c`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x140021310  mov     [rsp+arg_0], rbx
0x140021315  mov     [rsp+arg_8], rbp
0x14002131a  mov     [rsp+arg_10], rsi
0x14002131f  push    rdi
0x140021320  sub     rsp, 20h
0x140021324  mov     rsi, [rcx]
0x140021327  mov     rbp, rdx
0x14002132a  mov     rdi, rcx
0x14002132d  test    rsi, rsi
0x140021330  jz      short loc_140021388
0x140021332  call    cs:__imp_GetLastError
0x140021339  nop     dword ptr [rax+rax+00h]
0x14002133e  xor     r9d, r9d; msWindowLength
0x140021341  xor     r8d, r8d; msPeriod
0x140021344  xor     edx, edx; pftDueTime
0x140021346  mov     rcx, rsi; pti
0x140021349  mov     ebx, eax
0x14002134b  call    cs:__imp_SetThreadpoolTimer
0x140021352  nop     dword ptr [rax+rax+00h]
0x140021357  mov     edx, 1; fCancelPendingCallbacks
0x14002135c  mov     rcx, rsi; pti
0x14002135f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140021366  nop     dword ptr [rax+rax+00h]
0x14002136b  mov     rcx, rsi; pti
0x14002136e  call    cs:__imp_CloseThreadpoolTimer
0x140021375  nop     dword ptr [rax+rax+00h]
0x14002137a  mov     ecx, ebx; dwErrCode
0x14002137c  call    cs:__imp_SetLastError
0x140021383  nop     dword ptr [rax+rax+00h]
0x140021388  mov     rbx, [rsp+28h+arg_0]
0x14002138d  mov     rsi, [rsp+28h+arg_10]
0x140021392  mov     [rdi], rbp
0x140021395  mov     rbp, [rsp+28h+arg_8]
0x14002139a  add     rsp, 20h
0x14002139e  pop     rdi
0x14002139f  retn
```
