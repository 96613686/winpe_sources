# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000897c`
- end: `0x1800089f6`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002f20`
- `0x180003db0`
- `0x1800055b8`

## callees

- `0x18000897c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008993`
- `KERNEL32!GetLastError` at `0x180008993`
- `KERNEL32!SetLastError` at `0x1800089dd`
- `KERNEL32!SetLastError` at `0x1800089dd`
- `KERNEL32!SetThreadpoolTimer` at `0x1800089ac`
- `KERNEL32!SetThreadpoolTimer` at `0x1800089ac`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800089c0`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800089c0`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800089cf`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800089cf`

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
0x18000897c  push    rbx
0x18000897e  push    rbp
0x18000897f  push    rsi
0x180008980  push    rdi
0x180008981  sub     rsp, 28h
0x180008985  mov     rsi, [rcx]
0x180008988  mov     rbp, rdx
0x18000898b  mov     rdi, rcx
0x18000898e  test    rsi, rsi
0x180008991  jz      short loc_1800089E9
0x180008993  call    cs:__imp_GetLastError
0x18000899a  nop     dword ptr [rax+rax+00h]
0x18000899f  xor     r9d, r9d; msWindowLength
0x1800089a2  xor     r8d, r8d; msPeriod
0x1800089a5  xor     edx, edx; pftDueTime
0x1800089a7  mov     rcx, rsi; pti
0x1800089aa  mov     ebx, eax
0x1800089ac  call    cs:__imp_SetThreadpoolTimer
0x1800089b3  nop     dword ptr [rax+rax+00h]
0x1800089b8  mov     edx, 1; fCancelPendingCallbacks
0x1800089bd  mov     rcx, rsi; pti
0x1800089c0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800089c7  nop     dword ptr [rax+rax+00h]
0x1800089cc  mov     rcx, rsi; pti
0x1800089cf  call    cs:__imp_CloseThreadpoolTimer
0x1800089d6  nop     dword ptr [rax+rax+00h]
0x1800089db  mov     ecx, ebx; dwErrCode
0x1800089dd  call    cs:__imp_SetLastError
0x1800089e4  nop     dword ptr [rax+rax+00h]
0x1800089e9  mov     [rdi], rbp
0x1800089ec  add     rsp, 28h
0x1800089f0  pop     rdi
0x1800089f1  pop     rsi
0x1800089f2  pop     rbp
0x1800089f3  pop     rbx
0x1800089f4  retn
```
