# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000981c`
- end: `0x180009896`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002e68`
- `0x18000309c`
- `0x1800042bc`
- `0x180006528`
- `0x180006790`

## callees

- `0x18000981c`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x18000986f`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000986f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009860`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009860`
- `KERNEL32!SetThreadpoolTimer` at `0x18000984c`
- `KERNEL32!SetThreadpoolTimer` at `0x18000984c`
- `KERNEL32!SetLastError` at `0x18000987d`
- `KERNEL32!SetLastError` at `0x18000987d`
- `KERNEL32!GetLastError` at `0x180009833`
- `KERNEL32!GetLastError` at `0x180009833`

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
0x18000981c  push    rbx
0x18000981e  push    rbp
0x18000981f  push    rsi
0x180009820  push    rdi
0x180009821  sub     rsp, 28h
0x180009825  mov     rsi, [rcx]
0x180009828  mov     rbp, rdx
0x18000982b  mov     rdi, rcx
0x18000982e  test    rsi, rsi
0x180009831  jz      short loc_180009889
0x180009833  call    cs:__imp_GetLastError
0x18000983a  nop     dword ptr [rax+rax+00h]
0x18000983f  xor     r9d, r9d; msWindowLength
0x180009842  xor     r8d, r8d; msPeriod
0x180009845  xor     edx, edx; pftDueTime
0x180009847  mov     rcx, rsi; pti
0x18000984a  mov     ebx, eax
0x18000984c  call    cs:__imp_SetThreadpoolTimer
0x180009853  nop     dword ptr [rax+rax+00h]
0x180009858  mov     edx, 1; fCancelPendingCallbacks
0x18000985d  mov     rcx, rsi; pti
0x180009860  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009867  nop     dword ptr [rax+rax+00h]
0x18000986c  mov     rcx, rsi; pti
0x18000986f  call    cs:__imp_CloseThreadpoolTimer
0x180009876  nop     dword ptr [rax+rax+00h]
0x18000987b  mov     ecx, ebx; dwErrCode
0x18000987d  call    cs:__imp_SetLastError
0x180009884  nop     dword ptr [rax+rax+00h]
0x180009889  mov     [rdi], rbp
0x18000988c  add     rsp, 28h
0x180009890  pop     rdi
0x180009891  pop     rsi
0x180009892  pop     rbp
0x180009893  pop     rbx
0x180009894  retn
```
