# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x14000cec8`
- end: `0x14000cf42`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140005a44`
- `0x140005c78`
- `0x140006e94`
- `0x140008da8`
- `0x140008e60`
- `0x140008fc4`

## callees

- `0x14000cec8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cedf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cedf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cf29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cf29`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000cf1b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000cf1b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000cf0c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000cf0c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000cef8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000cef8`

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
0x14000cec8  push    rbx
0x14000ceca  push    rbp
0x14000cecb  push    rsi
0x14000cecc  push    rdi
0x14000cecd  sub     rsp, 28h
0x14000ced1  mov     rsi, [rcx]
0x14000ced4  mov     rbp, rdx
0x14000ced7  mov     rdi, rcx
0x14000ceda  test    rsi, rsi
0x14000cedd  jz      short loc_14000CF35
0x14000cedf  call    cs:__imp_GetLastError
0x14000cee6  nop     dword ptr [rax+rax+00h]
0x14000ceeb  xor     r9d, r9d; msWindowLength
0x14000ceee  xor     r8d, r8d; msPeriod
0x14000cef1  xor     edx, edx; pftDueTime
0x14000cef3  mov     rcx, rsi; pti
0x14000cef6  mov     ebx, eax
0x14000cef8  call    cs:__imp_SetThreadpoolTimer
0x14000ceff  nop     dword ptr [rax+rax+00h]
0x14000cf04  mov     edx, 1; fCancelPendingCallbacks
0x14000cf09  mov     rcx, rsi; pti
0x14000cf0c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000cf13  nop     dword ptr [rax+rax+00h]
0x14000cf18  mov     rcx, rsi; pti
0x14000cf1b  call    cs:__imp_CloseThreadpoolTimer
0x14000cf22  nop     dword ptr [rax+rax+00h]
0x14000cf27  mov     ecx, ebx; dwErrCode
0x14000cf29  call    cs:__imp_SetLastError
0x14000cf30  nop     dword ptr [rax+rax+00h]
0x14000cf35  mov     [rdi], rbp
0x14000cf38  add     rsp, 28h
0x14000cf3c  pop     rdi
0x14000cf3d  pop     rsi
0x14000cf3e  pop     rbp
0x14000cf3f  pop     rbx
0x14000cf40  retn
```
