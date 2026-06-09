# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1400717b8`
- end: `0x140071832`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14006bf98`
- `0x14006d148`
- `0x14006eaf0`

## callees

- `0x1400717b8`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x1400717e8`
- `KERNEL32!SetThreadpoolTimer` at `0x1400717e8`
- `KERNEL32!CloseThreadpoolTimer` at `0x14007180b`
- `KERNEL32!CloseThreadpoolTimer` at `0x14007180b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400717fc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400717fc`
- `KERNEL32!GetLastError` at `0x1400717cf`
- `KERNEL32!GetLastError` at `0x1400717cf`
- `KERNEL32!SetLastError` at `0x140071819`
- `KERNEL32!SetLastError` at `0x140071819`

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
0x1400717b8  push    rbx
0x1400717ba  push    rbp
0x1400717bb  push    rsi
0x1400717bc  push    rdi
0x1400717bd  sub     rsp, 28h
0x1400717c1  mov     rsi, [rcx]
0x1400717c4  mov     rbp, rdx
0x1400717c7  mov     rdi, rcx
0x1400717ca  test    rsi, rsi
0x1400717cd  jz      short loc_140071825
0x1400717cf  call    cs:__imp_GetLastError
0x1400717d6  nop     dword ptr [rax+rax+00h]
0x1400717db  xor     r9d, r9d; msWindowLength
0x1400717de  xor     r8d, r8d; msPeriod
0x1400717e1  xor     edx, edx; pftDueTime
0x1400717e3  mov     rcx, rsi; pti
0x1400717e6  mov     ebx, eax
0x1400717e8  call    cs:__imp_SetThreadpoolTimer
0x1400717ef  nop     dword ptr [rax+rax+00h]
0x1400717f4  mov     edx, 1; fCancelPendingCallbacks
0x1400717f9  mov     rcx, rsi; pti
0x1400717fc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140071803  nop     dword ptr [rax+rax+00h]
0x140071808  mov     rcx, rsi; pti
0x14007180b  call    cs:__imp_CloseThreadpoolTimer
0x140071812  nop     dword ptr [rax+rax+00h]
0x140071817  mov     ecx, ebx; dwErrCode
0x140071819  call    cs:__imp_SetLastError
0x140071820  nop     dword ptr [rax+rax+00h]
0x140071825  mov     [rdi], rbp
0x140071828  add     rsp, 28h
0x14007182c  pop     rdi
0x14007182d  pop     rsi
0x14007182e  pop     rbp
0x14007182f  pop     rbx
0x140071830  retn
```
