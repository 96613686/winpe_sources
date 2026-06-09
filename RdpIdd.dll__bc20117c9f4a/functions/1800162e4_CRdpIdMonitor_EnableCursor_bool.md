# CRdpIdMonitor::EnableCursor(bool)

- ea: `0x1800162e4`
- end: `0x180016386`
- name: `?EnableCursor@CRdpIdMonitor@@QEAAX_N@Z`
- size: `162`
- prototype: `void __fastcall(CRdpIdMonitor *__hidden this, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a784`
- `0x18001bb40`

## callees

- `0x18000d6d8`
- `0x18001dd70`
- `0x180030420`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001637a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001633e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001633e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRdpIdMonitor::EnableCursor(CRdpIdMonitor *this, bool a2)
{
  _QWORD *v4; // rdi
  const char *v5; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x69,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\Monitor.h",
    (const char *)0x80070057LL,
    *((_QWORD *)this + 3) == 0,
    (bool)"Cursor object is not initialized",
    v5);
  v4 = (_QWORD *)*((_QWORD *)this + 3);
  WaitForThreadpoolWaitCallbacks(*(PTP_WAIT *)(v4[3] + 8LL), 1);
  std::_Mutex_base::lock((std::_Mutex_base *)(v4 + 9));
  CRdpIdCursor::EnableHwCursorInternal((CRdpIdCursor *)v4, a2);
  _Mtx_unlock((_Mtx_t)(v4 + 9));
}

```

## disassembly

```asm
0x1800162e4  mov     [rsp+arg_8], rbx
0x1800162e9  mov     [rsp+arg_10], rsi
0x1800162ee  push    rdi; char *
0x1800162ef  sub     rsp, 30h
0x1800162f3  mov     sil, dl
0x1800162f6  mov     rdi, rcx
0x1800162f9  cmp     qword ptr [rcx+18h], 0
0x1800162fe  setz    al
0x180016301  mov     rcx, [rsp+38h]; this
0x180016306  lea     rdx, aCursorObjectIs; "Cursor object is not initialized"
0x18001630d  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x180016312  mov     [rsp+38h+var_18], al; char
0x180016316  mov     r9d, 80070057h; char *
0x18001631c  lea     r8, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180016323  mov     edx, 69h ; 'i'; void *
0x180016328  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001632d  mov     rdi, [rdi+18h]
0x180016331  mov     rcx, [rdi+18h]
0x180016335  mov     edx, 1; fCancelPendingCallbacks
0x18001633a  mov     rcx, [rcx+8]; pwa
0x18001633e  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180016345  nop     dword ptr [rax+rax+00h]
0x18001634a  lea     rbx, [rdi+48h]
0x18001634e  mov     [rsp+38h+arg_0], rbx
0x180016353  mov     rcx, rbx; this
0x180016356  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001635b  nop
0x18001635c  mov     dl, sil; bool
0x18001635f  mov     rcx, rdi; this
0x180016362  call    ?EnableHwCursorInternal@CRdpIdCursor@@AEAAX_N@Z; CRdpIdCursor::EnableHwCursorInternal(bool)
0x180016367  nop
0x180016368  mov     rcx, rbx
0x18001636b  mov     rbx, [rsp+38h+arg_8]
0x180016370  mov     rsi, [rsp+38h+arg_10]
0x180016375  add     rsp, 30h
0x180016379  pop     rdi
0x18001637a  jmp     cs:__imp__Mtx_unlock
```
