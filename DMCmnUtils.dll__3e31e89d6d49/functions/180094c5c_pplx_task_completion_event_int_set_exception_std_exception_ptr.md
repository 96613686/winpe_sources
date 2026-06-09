# pplx::task_completion_event<int>::set_exception(std::exception_ptr)

- ea: `0x180094c5c`
- end: `0x180094ce3`
- name: `?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z`
- size: `135`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018f30`
- `0x180081e9c`
- `0x18008200c`
- `0x1800820c4`
- `0x1800b3a80`

## callees

- `0x18005b888`
- `0x18007cb30`
- `0x18008d520`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180094cc4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180094cc4`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180094c98`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180094c98`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall pplx::task_completion_event<int>::set_exception(__int64 a1, void *a2)
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
0x180094c5c  mov     rax, rsp
0x180094c5f  mov     [rax+8], rbx
0x180094c63  mov     [rax+20h], rsi
0x180094c67  mov     [rax+10h], rdx
0x180094c6b  push    rdi
0x180094c6c  sub     rsp, 50h
0x180094c70  mov     rsi, rdx
0x180094c73  mov     rdi, rcx
0x180094c76  mov     rdx, [rsp+58h]
0x180094c7b  lea     rcx, [rax-28h]
0x180094c7f  call    ?_CaptureSingleFrameCallstack@_TaskCreationCallstack@details@pplx@@SA?AV123@PEAX@Z; pplx::details::_TaskCreationCallstack::_CaptureSingleFrameCallstack(void *)
0x180094c84  mov     rbx, rax
0x180094c87  xorps   xmm0, xmm0
0x180094c8a  movdqu  [rsp+58h+var_38], xmm0
0x180094c90  mov     rdx, rsi
0x180094c93  lea     rcx, [rsp+58h+var_38]
0x180094c98  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180094c9f  nop     dword ptr [rax+rax+00h]
0x180094ca4  mov     r8, rbx
0x180094ca7  lea     rdx, [rsp+58h+var_38]
0x180094cac  mov     rcx, rdi
0x180094caf  call    ??$_Cancel@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; pplx::task_completion_event<bool>::_Cancel<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x180094cb4  mov     bl, al
0x180094cb6  lea     rcx, [rsp+58h+var_20]
0x180094cbb  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180094cc0  nop
0x180094cc1  mov     rcx, rsi
0x180094cc4  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180094ccb  nop     dword ptr [rax+rax+00h]
0x180094cd0  mov     al, bl
0x180094cd2  mov     rbx, [rsp+58h+arg_0]
0x180094cd7  mov     rsi, [rsp+58h+arg_18]
0x180094cdc  add     rsp, 50h
0x180094ce0  pop     rdi
0x180094ce1  retn
```
