# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18001695c`
- end: `0x1800169d8`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `124`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010e6c`
- `0x1800110a0`
- `0x1800121cc`
- `0x1800139fc`
- `0x180013c64`

## callees

- `0x18001695c`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800169a0`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800169a0`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800169af`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800169af`
- `KERNEL32!SetThreadpoolTimer` at `0x18001698c`
- `KERNEL32!SetThreadpoolTimer` at `0x18001698c`
- `KERNEL32!GetLastError` at `0x180016973`
- `KERNEL32!GetLastError` at `0x180016973`
- `KERNEL32!SetLastError` at `0x1800169be`
- `KERNEL32!SetLastError` at `0x1800169be`

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
0x18001695c  push    rbx
0x18001695e  push    rbp
0x18001695f  push    rsi
0x180016960  push    rdi
0x180016961  sub     rsp, 28h
0x180016965  mov     rbp, rdx
0x180016968  mov     rdi, rcx
0x18001696b  mov     rsi, [rcx]
0x18001696e  test    rsi, rsi
0x180016971  jz      short loc_1800169CB
0x180016973  call    cs:__imp_GetLastError
0x18001697a  nop     dword ptr [rax+rax+00h]
0x18001697f  mov     ebx, eax
0x180016981  xor     r9d, r9d; msWindowLength
0x180016984  xor     r8d, r8d; msPeriod
0x180016987  xor     edx, edx; pftDueTime
0x180016989  mov     rcx, rsi; pti
0x18001698c  call    cs:__imp_SetThreadpoolTimer
0x180016993  nop     dword ptr [rax+rax+00h]
0x180016998  mov     edx, 1; fCancelPendingCallbacks
0x18001699d  mov     rcx, rsi; pti
0x1800169a0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800169a7  nop     dword ptr [rax+rax+00h]
0x1800169ac  mov     rcx, rsi; pti
0x1800169af  call    cs:__imp_CloseThreadpoolTimer
0x1800169b6  nop     dword ptr [rax+rax+00h]
0x1800169bb  nop
0x1800169bc  mov     ecx, ebx; dwErrCode
0x1800169be  call    cs:__imp_SetLastError
0x1800169c5  nop     dword ptr [rax+rax+00h]
0x1800169ca  nop
0x1800169cb  mov     [rdi], rbp
0x1800169ce  add     rsp, 28h
0x1800169d2  pop     rdi
0x1800169d3  pop     rsi
0x1800169d4  pop     rbp
0x1800169d5  pop     rbx
0x1800169d6  retn
```
