# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18003c954`
- end: `0x18003c9d7`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `131`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800397b8`
- `0x180039970`
- `0x18003a26c`
- `0x18003a898`
- `0x18003a9f4`
- `0x180094bdc`

## callees

- `0x18003c954`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c974`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c9be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c9be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003c98d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003c98d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003c9a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003c9a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003c9b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003c9b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v4; // rsi
  DWORD LastError; // ebx

  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18003c954  push    rbx
0x18003c956  push    rbp
0x18003c957  push    rsi
0x18003c958  push    rdi
0x18003c959  sub     rsp, 38h
0x18003c95d  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18003c966  mov     rbp, rdx
0x18003c969  mov     rdi, rcx
0x18003c96c  mov     rsi, [rcx]
0x18003c96f  test    rsi, rsi
0x18003c972  jz      short loc_18003C9CA
0x18003c974  call    cs:__imp_GetLastError
0x18003c97b  nop     dword ptr [rax+rax+00h]
0x18003c980  mov     ebx, eax
0x18003c982  xor     r9d, r9d; msWindowLength
0x18003c985  xor     r8d, r8d; msPeriod
0x18003c988  xor     edx, edx; pftDueTime
0x18003c98a  mov     rcx, rsi; pti
0x18003c98d  call    cs:__imp_SetThreadpoolTimer
0x18003c994  nop     dword ptr [rax+rax+00h]
0x18003c999  mov     edx, 1; fCancelPendingCallbacks
0x18003c99e  mov     rcx, rsi; pti
0x18003c9a1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003c9a8  nop     dword ptr [rax+rax+00h]
0x18003c9ad  mov     rcx, rsi; pti
0x18003c9b0  call    cs:__imp_CloseThreadpoolTimer
0x18003c9b7  nop     dword ptr [rax+rax+00h]
0x18003c9bc  mov     ecx, ebx; dwErrCode
0x18003c9be  call    cs:__imp_SetLastError
0x18003c9c5  nop     dword ptr [rax+rax+00h]
0x18003c9ca  mov     [rdi], rbp
0x18003c9cd  add     rsp, 38h
0x18003c9d1  pop     rdi
0x18003c9d2  pop     rsi
0x18003c9d3  pop     rbp
0x18003c9d4  pop     rbx
0x18003c9d5  retn
```
