# pplx::task_completion_event<void>::set_exception(std::exception_ptr)

- ea: `0x180030280`
- end: `0x1800302f5`
- name: `?set_exception@?$task_completion_event@X@pplx@@QEBA_NVexception_ptr@std@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800231e8`

## callees

- `0x180011dcc`
- `0x1800157f4`
- `0x18001eab8`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800302e2`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800302e2`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800302ba`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800302ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall pplx::task_completion_event<void>::set_exception(__int64 a1, void *a2)
{
  __int64 v4; // r8
  __int128 v6; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-20h] BYREF

  pplx::details::_TaskCreationCallstack::_TaskCreationCallstack((pplx::details::_TaskCreationCallstack *)&v7);
  v7 = v4;
  v6 = 0;
  __ExceptionPtrCopy(&v6, a2);
  LOBYTE(a1) = pplx::task_completion_event<unsigned char>::_Cancel<std::exception_ptr>(a1, &v6, (__int64)&v7);
  std::vector<void *>::_Tidy(v8);
  __ExceptionPtrDestroy(a2);
  return a1;
}

```

## disassembly

```asm
0x180030280  mov     [rsp+arg_10], rbx
0x180030285  mov     [rsp+arg_8], rdx
0x18003028a  push    rdi
0x18003028b  sub     rsp, 50h
0x18003028f  mov     rdi, rdx
0x180030292  mov     rbx, rcx
0x180030295  mov     r8, [rsp+58h]
0x18003029a  lea     rcx, [rsp+58h+var_28]; this
0x18003029f  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@XZ; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x1800302a4  mov     [rsp+58h+var_28], r8
0x1800302a9  xorps   xmm0, xmm0
0x1800302ac  movdqu  [rsp+58h+var_38], xmm0
0x1800302b2  mov     rdx, rdi
0x1800302b5  lea     rcx, [rsp+58h+var_38]
0x1800302ba  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800302c0  lea     r8, [rsp+58h+var_28]
0x1800302c5  lea     rdx, [rsp+58h+var_38]
0x1800302ca  mov     rcx, rbx
0x1800302cd  call    ??$_Cancel@Vexception_ptr@std@@@?$task_completion_event@E@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; pplx::task_completion_event<uchar>::_Cancel<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x1800302d2  mov     bl, al
0x1800302d4  lea     rcx, [rsp+58h+var_20]
0x1800302d9  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x1800302de  nop
0x1800302df  mov     rcx, rdi
0x1800302e2  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800302e8  mov     al, bl
0x1800302ea  mov     rbx, [rsp+58h+arg_10]
0x1800302ef  add     rsp, 50h
0x1800302f3  pop     rdi
0x1800302f4  retn
```
