# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180012de0`
- end: `0x180012e65`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `133`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004970`
- `0x180010f40`
- `0x180010fe0`
- `0x1800115f0`
- `0x18001fba0`

## callees

- `0x180012de0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012e02`
- `KERNEL32!GetLastError` at `0x180012e02`
- `KERNEL32!SetThreadpoolTimer` at `0x180012e15`
- `KERNEL32!SetThreadpoolTimer` at `0x180012e15`
- `KERNEL32!SetLastError` at `0x180012e34`
- `KERNEL32!SetLastError` at `0x180012e34`
- `KERNEL32!CloseThreadpoolTimer` at `0x180012e2c`
- `KERNEL32!CloseThreadpoolTimer` at `0x180012e2c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180012e23`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180012e23`

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
0x180012de0  mov     [rsp+arg_8], rbp
0x180012de5  mov     [rsp+arg_10], rsi
0x180012dea  push    rdi
0x180012deb  sub     rsp, 20h
0x180012def  mov     rsi, [rcx]
0x180012df2  mov     rbp, rdx
0x180012df5  mov     rdi, rcx
0x180012df8  test    rsi, rsi
0x180012dfb  jz      short loc_180012E52
0x180012dfd  mov     [rsp+28h+arg_0], rbx
0x180012e02  call    cs:__imp_GetLastError
0x180012e08  xor     r9d, r9d; msWindowLength
0x180012e0b  xor     r8d, r8d; msPeriod
0x180012e0e  xor     edx, edx; pftDueTime
0x180012e10  mov     rcx, rsi; pti
0x180012e13  mov     ebx, eax
0x180012e15  call    cs:__imp_SetThreadpoolTimer
0x180012e1b  mov     edx, 1; fCancelPendingCallbacks
0x180012e20  mov     rcx, rsi; pti
0x180012e23  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012e29  mov     rcx, rsi; pti
0x180012e2c  call    cs:__imp_CloseThreadpoolTimer
0x180012e32  mov     ecx, ebx; dwErrCode
0x180012e34  call    cs:__imp_SetLastError
0x180012e3a  mov     rbx, [rsp+28h+arg_0]
0x180012e3f  mov     [rdi], rbp
0x180012e42  mov     rbp, [rsp+28h+arg_8]
0x180012e47  mov     rsi, [rsp+28h+arg_10]
0x180012e4c  add     rsp, 20h
0x180012e50  pop     rdi
0x180012e51  retn
0x180012e52  mov     rsi, [rsp+28h+arg_10]
0x180012e57  mov     [rcx], rbp
0x180012e5a  mov     rbp, [rsp+28h+arg_8]
0x180012e5f  add     rsp, 20h
0x180012e63  pop     rdi
0x180012e64  retn
```
