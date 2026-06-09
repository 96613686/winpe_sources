# _anonymous_namespace_::com_timeout_t_wil::err_exception_policy_::com_timeout_t_wil::err_exception_policy_

- ea: `0x18009c660`
- end: `0x18009c761`
- name: `_anonymous_namespace_::com_timeout_t_wil::err_exception_policy_::com_timeout_t_wil::err_exception_policy_`
- size: `257`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a2d80`

## callees

- `0x18003ac98`
- `0x18003acb8`
- `0x18006b260`
- `0x18009aed0`
- `0x18009c660`
- `0x1800a0d6c`
- `0x1800ac31c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18009c6c1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18009c6c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009c747`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009c747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c67a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c67a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009c711`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009c711`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18009c68d`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18009c68d`

## string_xrefs

- `0x18009c69f`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
PVOID __fastcall anonymous_namespace_::com_timeout_t_wil::err_exception_policy_::com_timeout_t_wil::err_exception_policy_(
        PVOID pv)
{
  HRESULT v2; // eax
  void *v3; // rdx
  PTP_TIMER ThreadpoolTimer; // rdi
  unsigned int v5; // r8d
  const char *v6; // r9
  struct _TP_TIMER *v7; // rsi
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+18h] BYREF

  pftDueTime = (struct _FILETIME)pv;
  *(_BYTE *)pv = 0;
  *((_DWORD *)pv + 1) = GetCurrentThreadId();
  *((_QWORD *)pv + 1) = 0;
  v2 = CoEnableCallCancellation(0);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)v2,
      v9);
  *(_BYTE *)pv = 1;
  ThreadpoolTimer = CreateThreadpoolTimer(
                      anonymous_namespace_::com_timeout_t_wil::err_exception_policy_::timer_callback,
                      pv,
                      0);
  v7 = (struct _TP_TIMER *)*((_QWORD *)pv + 1);
  if ( v7 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&SystemTimeAsFileTime);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,1>::Destroy(v7);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&SystemTimeAsFileTime);
  }
  *((_QWORD *)pv + 1) = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v5, v6);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  pftDueTime = SystemTimeAsFileTime;
  pftDueTime = (struct _FILETIME)std::vector<unsigned char>::operator[](&pftDueTime, 5000000);
  SetThreadpoolTimer(*((PTP_TIMER *)pv + 1), &pftDueTime, 0x1F4u, 0);
  return pv;
}

```

## disassembly

```asm
0x18009c660  mov     [rsp+arg_8], rbx
0x18009c665  mov     [rsp+arg_18], rsi
0x18009c66a  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], rcx
0x18009c66f  push    rdi; int
0x18009c670  sub     rsp, 20h
0x18009c674  mov     rbx, rcx
0x18009c677  mov     byte ptr [rcx], 0
0x18009c67a  call    cs:__imp_GetCurrentThreadId
0x18009c680  mov     [rbx+4], eax
0x18009c683  mov     qword ptr [rbx+8], 0
0x18009c68b  xor     ecx, ecx; pReserved
0x18009c68d  call    cs:__imp_CoEnableCallCancellation
0x18009c693  mov     rcx, [rsp+28h]; this
0x18009c698  test    eax, eax
0x18009c69a  jns     short loc_18009C6B1
0x18009c69c  mov     r9d, eax; char *
0x18009c69f  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009c6a6  mov     edx, 1CBEh; void *
0x18009c6ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009c6b1  mov     byte ptr [rbx], 1
0x18009c6b4  xor     r8d, r8d; pcbe
0x18009c6b7  mov     rdx, rbx; pv
0x18009c6ba  lea     rcx, _anonymous_namespace___com_timeout_t_wil__err_exception_policy___timer_callback; pfnti
0x18009c6c1  call    cs:__imp_CreateThreadpoolTimer
0x18009c6c7  mov     rdi, rax
0x18009c6ca  mov     rsi, [rbx+8]
0x18009c6ce  test    rsi, rsi
0x18009c6d1  jz      short loc_18009C6EF
0x18009c6d3  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; this
0x18009c6d8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18009c6dd  mov     rcx, rsi; pti
0x18009c6e0  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$00@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,1>::Destroy(_TP_TIMER *)
0x18009c6e5  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; this
0x18009c6ea  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18009c6ef  mov     [rbx+8], rdi
0x18009c6f3  test    rdi, rdi
0x18009c6f6  jnz     short loc_18009C703
0x18009c6f8  mov     rcx, [rsp+28h]; this
0x18009c6fd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009c703  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18009c70c  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18009c711  call    cs:__imp_GetSystemTimeAsFileTime
0x18009c717  mov     rax, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x18009c71c  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18009c721  mov     edx, 4C4B40h
0x18009c726  lea     rcx, [rsp+28h+pftDueTime]
0x18009c72b  call    ??A?$vector@EV?$allocator@E@std@@@std@@QEAAAEAE_K@Z; std::vector<uchar>::operator[](unsigned __int64)
0x18009c730  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18009c735  xor     r9d, r9d; msWindowLength
0x18009c738  mov     r8d, 1F4h; msPeriod
0x18009c73e  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18009c743  mov     rcx, [rbx+8]; pti
0x18009c747  call    cs:__imp_SetThreadpoolTimer
0x18009c74d  nop
0x18009c74e  mov     rax, rbx
0x18009c751  mov     rbx, [rsp+28h+arg_8]
0x18009c756  mov     rsi, [rsp+28h+arg_18]
0x18009c75b  add     rsp, 20h
0x18009c75f  pop     rdi
0x18009c760  retn
```
