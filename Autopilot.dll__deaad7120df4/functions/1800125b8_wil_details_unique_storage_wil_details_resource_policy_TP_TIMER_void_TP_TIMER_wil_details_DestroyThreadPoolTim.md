# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800125b8`
- end: `0x180012632`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ae14`
- `0x18000b048`
- `0x18000ca18`
- `0x18000e870`
- `0x18000ebe0`
- `0x18001c7d0`

## callees

- `0x1800125b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012619`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012619`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800125fc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800125fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001260b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001260b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800125e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800125e8`

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
0x1800125b8  push    rbx
0x1800125ba  push    rbp
0x1800125bb  push    rsi
0x1800125bc  push    rdi
0x1800125bd  sub     rsp, 28h
0x1800125c1  mov     rsi, [rcx]
0x1800125c4  mov     rbp, rdx
0x1800125c7  mov     rdi, rcx
0x1800125ca  test    rsi, rsi
0x1800125cd  jz      short loc_180012625
0x1800125cf  call    cs:__imp_GetLastError
0x1800125d6  nop     dword ptr [rax+rax+00h]
0x1800125db  xor     r9d, r9d; msWindowLength
0x1800125de  xor     r8d, r8d; msPeriod
0x1800125e1  xor     edx, edx; pftDueTime
0x1800125e3  mov     rcx, rsi; pti
0x1800125e6  mov     ebx, eax
0x1800125e8  call    cs:__imp_SetThreadpoolTimer
0x1800125ef  nop     dword ptr [rax+rax+00h]
0x1800125f4  mov     edx, 1; fCancelPendingCallbacks
0x1800125f9  mov     rcx, rsi; pti
0x1800125fc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012603  nop     dword ptr [rax+rax+00h]
0x180012608  mov     rcx, rsi; pti
0x18001260b  call    cs:__imp_CloseThreadpoolTimer
0x180012612  nop     dword ptr [rax+rax+00h]
0x180012617  mov     ecx, ebx; dwErrCode
0x180012619  call    cs:__imp_SetLastError
0x180012620  nop     dword ptr [rax+rax+00h]
0x180012625  mov     [rdi], rbp
0x180012628  add     rsp, 28h
0x18001262c  pop     rdi
0x18001262d  pop     rsi
0x18001262e  pop     rbp
0x18001262f  pop     rbx
0x180012630  retn
```
