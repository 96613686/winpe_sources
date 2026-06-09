# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180007430`
- end: `0x1800074b5`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c270`
- `0x18025d660`

## callees

- `0x180007430`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007484`
- `KERNEL32!SetLastError` at `0x180007484`
- `KERNEL32!GetLastError` at `0x180007452`
- `KERNEL32!GetLastError` at `0x180007452`
- `KERNEL32!SetThreadpoolTimer` at `0x180007465`
- `KERNEL32!SetThreadpoolTimer` at `0x180007465`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000747c`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000747c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180007473`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180007473`

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
0x180007430  mov     [rsp+arg_8], rbp
0x180007435  mov     [rsp+arg_10], rsi
0x18000743a  push    rdi
0x18000743b  sub     rsp, 20h
0x18000743f  mov     rsi, [rcx]
0x180007442  mov     rbp, rdx
0x180007445  mov     rdi, rcx
0x180007448  test    rsi, rsi
0x18000744b  jz      short loc_1800074A2
0x18000744d  mov     [rsp+28h+arg_0], rbx
0x180007452  call    cs:__imp_GetLastError
0x180007458  xor     r9d, r9d; msWindowLength
0x18000745b  xor     r8d, r8d; msPeriod
0x18000745e  xor     edx, edx; pftDueTime
0x180007460  mov     rcx, rsi; pti
0x180007463  mov     ebx, eax
0x180007465  call    cs:__imp_SetThreadpoolTimer
0x18000746b  mov     edx, 1; fCancelPendingCallbacks
0x180007470  mov     rcx, rsi; pti
0x180007473  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007479  mov     rcx, rsi; pti
0x18000747c  call    cs:__imp_CloseThreadpoolTimer
0x180007482  mov     ecx, ebx; dwErrCode
0x180007484  call    cs:__imp_SetLastError
0x18000748a  mov     rbx, [rsp+28h+arg_0]
0x18000748f  mov     [rdi], rbp
0x180007492  mov     rbp, [rsp+28h+arg_8]
0x180007497  mov     rsi, [rsp+28h+arg_10]
0x18000749c  add     rsp, 20h
0x1800074a0  pop     rdi
0x1800074a1  retn
0x1800074a2  mov     rsi, [rsp+28h+arg_10]
0x1800074a7  mov     [rcx], rbp
0x1800074aa  mov     rbp, [rsp+28h+arg_8]
0x1800074af  add     rsp, 20h
0x1800074b3  pop     rdi
0x1800074b4  retn
```
