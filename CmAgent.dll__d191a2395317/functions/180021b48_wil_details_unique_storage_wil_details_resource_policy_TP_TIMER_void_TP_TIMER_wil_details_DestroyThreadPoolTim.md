# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180021b48`
- end: `0x180021bc2`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015258`
- `0x18001548c`
- `0x180016b3c`
- `0x18001956c`
- `0x1800197cc`

## callees

- `0x180021b48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021ba9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021ba9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021b8c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021b8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180021b9b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180021b9b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021b78`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021b78`

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
0x180021b48  push    rbx
0x180021b4a  push    rbp
0x180021b4b  push    rsi
0x180021b4c  push    rdi
0x180021b4d  sub     rsp, 28h
0x180021b51  mov     rsi, [rcx]
0x180021b54  mov     rbp, rdx
0x180021b57  mov     rdi, rcx
0x180021b5a  test    rsi, rsi
0x180021b5d  jz      short loc_180021BB5
0x180021b5f  call    cs:__imp_GetLastError
0x180021b66  nop     dword ptr [rax+rax+00h]
0x180021b6b  xor     r9d, r9d; msWindowLength
0x180021b6e  xor     r8d, r8d; msPeriod
0x180021b71  xor     edx, edx; pftDueTime
0x180021b73  mov     rcx, rsi; pti
0x180021b76  mov     ebx, eax
0x180021b78  call    cs:__imp_SetThreadpoolTimer
0x180021b7f  nop     dword ptr [rax+rax+00h]
0x180021b84  mov     edx, 1; fCancelPendingCallbacks
0x180021b89  mov     rcx, rsi; pti
0x180021b8c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180021b93  nop     dword ptr [rax+rax+00h]
0x180021b98  mov     rcx, rsi; pti
0x180021b9b  call    cs:__imp_CloseThreadpoolTimer
0x180021ba2  nop     dword ptr [rax+rax+00h]
0x180021ba7  mov     ecx, ebx; dwErrCode
0x180021ba9  call    cs:__imp_SetLastError
0x180021bb0  nop     dword ptr [rax+rax+00h]
0x180021bb5  mov     [rdi], rbp
0x180021bb8  add     rsp, 28h
0x180021bbc  pop     rdi
0x180021bbd  pop     rsi
0x180021bbe  pop     rbp
0x180021bbf  pop     rbx
0x180021bc0  retn
```
