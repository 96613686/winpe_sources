# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000e9ec`
- end: `0x18000ea66`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009fc0`
- `0x18000a238`
- `0x18000ae2c`
- `0x18000bcc8`
- `0x18000bf84`
- `0x180018590`

## callees

- `0x18000e9ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ea3f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ea3f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ea1c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ea1c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ea30`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ea30`

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
0x18000e9ec  push    rbx
0x18000e9ee  push    rbp
0x18000e9ef  push    rsi
0x18000e9f0  push    rdi
0x18000e9f1  sub     rsp, 28h
0x18000e9f5  mov     rsi, [rcx]
0x18000e9f8  mov     rbp, rdx
0x18000e9fb  mov     rdi, rcx
0x18000e9fe  test    rsi, rsi
0x18000ea01  jz      short loc_18000EA59
0x18000ea03  call    cs:__imp_GetLastError
0x18000ea0a  nop     dword ptr [rax+rax+00h]
0x18000ea0f  xor     r9d, r9d; msWindowLength
0x18000ea12  xor     r8d, r8d; msPeriod
0x18000ea15  xor     edx, edx; pftDueTime
0x18000ea17  mov     rcx, rsi; pti
0x18000ea1a  mov     ebx, eax
0x18000ea1c  call    cs:__imp_SetThreadpoolTimer
0x18000ea23  nop     dword ptr [rax+rax+00h]
0x18000ea28  mov     edx, 1; fCancelPendingCallbacks
0x18000ea2d  mov     rcx, rsi; pti
0x18000ea30  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ea37  nop     dword ptr [rax+rax+00h]
0x18000ea3c  mov     rcx, rsi; pti
0x18000ea3f  call    cs:__imp_CloseThreadpoolTimer
0x18000ea46  nop     dword ptr [rax+rax+00h]
0x18000ea4b  mov     ecx, ebx; dwErrCode
0x18000ea4d  call    cs:__imp_SetLastError
0x18000ea54  nop     dword ptr [rax+rax+00h]
0x18000ea59  mov     [rdi], rbp
0x18000ea5c  add     rsp, 28h
0x18000ea60  pop     rdi
0x18000ea61  pop     rsi
0x18000ea62  pop     rbp
0x18000ea63  pop     rbx
0x18000ea64  retn
```
