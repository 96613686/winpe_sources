# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800067c0`
- end: `0x180006845`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006b20`
- `0x1800148e0`
- `0x180014980`
- `0x180014f90`
- `0x180065f70`

## callees

- `0x1800067c0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180006814`
- `KERNEL32!SetLastError` at `0x180006814`
- `KERNEL32!GetLastError` at `0x1800067e2`
- `KERNEL32!GetLastError` at `0x1800067e2`
- `KERNEL32!SetThreadpoolTimer` at `0x1800067f5`
- `KERNEL32!SetThreadpoolTimer` at `0x1800067f5`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000680c`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000680c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006803`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006803`

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
0x1800067c0  mov     [rsp+arg_8], rbp
0x1800067c5  mov     [rsp+arg_10], rsi
0x1800067ca  push    rdi
0x1800067cb  sub     rsp, 20h
0x1800067cf  mov     rsi, [rcx]
0x1800067d2  mov     rbp, rdx
0x1800067d5  mov     rdi, rcx
0x1800067d8  test    rsi, rsi
0x1800067db  jz      short loc_180006832
0x1800067dd  mov     [rsp+28h+arg_0], rbx
0x1800067e2  call    cs:__imp_GetLastError
0x1800067e8  xor     r9d, r9d; msWindowLength
0x1800067eb  xor     r8d, r8d; msPeriod
0x1800067ee  xor     edx, edx; pftDueTime
0x1800067f0  mov     rcx, rsi; pti
0x1800067f3  mov     ebx, eax
0x1800067f5  call    cs:__imp_SetThreadpoolTimer
0x1800067fb  mov     edx, 1; fCancelPendingCallbacks
0x180006800  mov     rcx, rsi; pti
0x180006803  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006809  mov     rcx, rsi; pti
0x18000680c  call    cs:__imp_CloseThreadpoolTimer
0x180006812  mov     ecx, ebx; dwErrCode
0x180006814  call    cs:__imp_SetLastError
0x18000681a  mov     rbx, [rsp+28h+arg_0]
0x18000681f  mov     [rdi], rbp
0x180006822  mov     rbp, [rsp+28h+arg_8]
0x180006827  mov     rsi, [rsp+28h+arg_10]
0x18000682c  add     rsp, 20h
0x180006830  pop     rdi
0x180006831  retn
0x180006832  mov     rsi, [rsp+28h+arg_10]
0x180006837  mov     [rcx], rbp
0x18000683a  mov     rbp, [rsp+28h+arg_8]
0x18000683f  add     rsp, 20h
0x180006843  pop     rdi
0x180006844  retn
```
