# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000f590`
- end: `0x18000f615`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000f8f0`
- `0x18002f7b0`
- `0x18002fc80`
- `0x18002fd80`
- `0x1800419a0`

## callees

- `0x18000f590`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000f5e4`
- `KERNEL32!SetLastError` at `0x18000f5e4`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f5c5`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f5c5`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000f5dc`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000f5dc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000f5d3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000f5d3`
- `KERNEL32!GetLastError` at `0x18000f5b2`
- `KERNEL32!GetLastError` at `0x18000f5b2`

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
    *a1 = a2;
  }
  else
  {
    *a1 = a2;
  }
}

```

## disassembly

```asm
0x18000f590  mov     [rsp+arg_8], rbp
0x18000f595  mov     [rsp+arg_10], rsi
0x18000f59a  push    rdi
0x18000f59b  sub     rsp, 20h
0x18000f59f  mov     rsi, [rcx]
0x18000f5a2  mov     rbp, rdx
0x18000f5a5  mov     rdi, rcx
0x18000f5a8  test    rsi, rsi
0x18000f5ab  jz      short loc_18000F602
0x18000f5ad  mov     [rsp+28h+arg_0], rbx
0x18000f5b2  call    cs:__imp_GetLastError
0x18000f5b8  xor     r9d, r9d; msWindowLength
0x18000f5bb  xor     r8d, r8d; msPeriod
0x18000f5be  xor     edx, edx; pftDueTime
0x18000f5c0  mov     rcx, rsi; pti
0x18000f5c3  mov     ebx, eax
0x18000f5c5  call    cs:__imp_SetThreadpoolTimer
0x18000f5cb  mov     edx, 1; fCancelPendingCallbacks
0x18000f5d0  mov     rcx, rsi; pti
0x18000f5d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f5d9  mov     rcx, rsi; pti
0x18000f5dc  call    cs:__imp_CloseThreadpoolTimer
0x18000f5e2  mov     ecx, ebx; dwErrCode
0x18000f5e4  call    cs:__imp_SetLastError
0x18000f5ea  mov     rbx, [rsp+28h+arg_0]
0x18000f5ef  mov     [rdi], rbp
0x18000f5f2  mov     rbp, [rsp+28h+arg_8]
0x18000f5f7  mov     rsi, [rsp+28h+arg_10]
0x18000f5fc  add     rsp, 20h
0x18000f600  pop     rdi
0x18000f601  retn
0x18000f602  mov     rsi, [rsp+28h+arg_10]
0x18000f607  mov     [rcx], rbp
0x18000f60a  mov     rbp, [rsp+28h+arg_8]
0x18000f60f  add     rsp, 20h
0x18000f613  pop     rdi
0x18000f614  retn
```
