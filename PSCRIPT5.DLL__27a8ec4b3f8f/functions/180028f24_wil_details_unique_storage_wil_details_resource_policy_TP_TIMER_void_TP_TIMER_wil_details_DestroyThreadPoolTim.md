# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180028f24`
- end: `0x180028f9e`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180024110`
- `0x180025068`
- `0x180026940`

## callees

- `0x180028f24`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180028f54`
- `KERNEL32!SetThreadpoolTimer` at `0x180028f54`
- `KERNEL32!CloseThreadpoolTimer` at `0x180028f77`
- `KERNEL32!CloseThreadpoolTimer` at `0x180028f77`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180028f68`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180028f68`
- `KERNEL32!SetLastError` at `0x180028f85`
- `KERNEL32!SetLastError` at `0x180028f85`
- `KERNEL32!GetLastError` at `0x180028f3b`
- `KERNEL32!GetLastError` at `0x180028f3b`

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
0x180028f24  push    rbx
0x180028f26  push    rbp
0x180028f27  push    rsi
0x180028f28  push    rdi
0x180028f29  sub     rsp, 28h
0x180028f2d  mov     rsi, [rcx]
0x180028f30  mov     rbp, rdx
0x180028f33  mov     rdi, rcx
0x180028f36  test    rsi, rsi
0x180028f39  jz      short loc_180028F91
0x180028f3b  call    cs:__imp_GetLastError
0x180028f42  nop     dword ptr [rax+rax+00h]
0x180028f47  xor     r9d, r9d; msWindowLength
0x180028f4a  xor     r8d, r8d; msPeriod
0x180028f4d  xor     edx, edx; pftDueTime
0x180028f4f  mov     rcx, rsi; pti
0x180028f52  mov     ebx, eax
0x180028f54  call    cs:__imp_SetThreadpoolTimer
0x180028f5b  nop     dword ptr [rax+rax+00h]
0x180028f60  mov     edx, 1; fCancelPendingCallbacks
0x180028f65  mov     rcx, rsi; pti
0x180028f68  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180028f6f  nop     dword ptr [rax+rax+00h]
0x180028f74  mov     rcx, rsi; pti
0x180028f77  call    cs:__imp_CloseThreadpoolTimer
0x180028f7e  nop     dword ptr [rax+rax+00h]
0x180028f83  mov     ecx, ebx; dwErrCode
0x180028f85  call    cs:__imp_SetLastError
0x180028f8c  nop     dword ptr [rax+rax+00h]
0x180028f91  mov     [rdi], rbp
0x180028f94  add     rsp, 28h
0x180028f98  pop     rdi
0x180028f99  pop     rsi
0x180028f9a  pop     rbp
0x180028f9b  pop     rbx
0x180028f9c  retn
```
