# pplx::task_completion_event<void>::set_exception(std::exception_ptr)

- ea: `0x180094cec`
- end: `0x180094d73`
- name: `?set_exception@?$task_completion_event@X@pplx@@QEBA_NVexception_ptr@std@@@Z`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026130`
- `0x180081f54`

## callees

- `0x18005b888`
- `0x18007cb30`
- `0x18008d520`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180094d54`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180094d54`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180094d28`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180094d28`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall pplx::task_completion_event<void>::set_exception(__int64 a1, void *a2)
{
  __int64 v4; // rbx
  __int128 v6; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-20h] BYREF
  void *retaddr; // [rsp+58h] [rbp+0h]

  v4 = pplx::details::_TaskCreationCallstack::_CaptureSingleFrameCallstack(&v7, retaddr);
  v6 = 0;
  __ExceptionPtrCopy(&v6, a2);
  LOBYTE(v4) = pplx::task_completion_event<bool>::_Cancel<std::exception_ptr>(a1, &v6, v4);
  std::vector<void *>::_Tidy(v8);
  __ExceptionPtrDestroy(a2);
  return v4;
}

```

## disassembly

```asm
0x180094cec  mov     rax, rsp
0x180094cef  mov     [rax+18h], rbx
0x180094cf3  mov     [rax+20h], rsi
0x180094cf7  mov     [rax+10h], rdx
0x180094cfb  push    rdi
0x180094cfc  sub     rsp, 50h
0x180094d00  mov     rsi, rdx
0x180094d03  mov     rdi, rcx
0x180094d06  mov     rdx, [rsp+58h]
0x180094d0b  lea     rcx, [rax-28h]
0x180094d0f  call    ?_CaptureSingleFrameCallstack@_TaskCreationCallstack@details@pplx@@SA?AV123@PEAX@Z; pplx::details::_TaskCreationCallstack::_CaptureSingleFrameCallstack(void *)
0x180094d14  mov     rbx, rax
0x180094d17  xorps   xmm0, xmm0
0x180094d1a  movdqu  [rsp+58h+var_38], xmm0
0x180094d20  mov     rdx, rsi
0x180094d23  lea     rcx, [rsp+58h+var_38]
0x180094d28  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180094d2f  nop     dword ptr [rax+rax+00h]
0x180094d34  mov     r8, rbx
0x180094d37  lea     rdx, [rsp+58h+var_38]
0x180094d3c  mov     rcx, rdi
0x180094d3f  call    ??$_Cancel@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; pplx::task_completion_event<bool>::_Cancel<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x180094d44  mov     bl, al
0x180094d46  lea     rcx, [rsp+58h+var_20]
0x180094d4b  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180094d50  nop
0x180094d51  mov     rcx, rsi
0x180094d54  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180094d5b  nop     dword ptr [rax+rax+00h]
0x180094d60  mov     al, bl
0x180094d62  mov     rbx, [rsp+58h+arg_10]
0x180094d67  mov     rsi, [rsp+58h+arg_18]
0x180094d6c  add     rsp, 50h
0x180094d70  pop     rdi
0x180094d71  retn
```
