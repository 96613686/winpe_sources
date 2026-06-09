# pplx::task_completion_event<bool>::_Cancel<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)

- ea: `0x18007cb30`
- end: `0x18007cba9`
- name: `??$_Cancel@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042340`
- `0x1800424b0`
- `0x180094c5c`
- `0x180094cec`

## callees

- `0x18007cb30`
- `0x18007e210`
- `0x18008d3a4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18007cb8a`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18007cb8a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18007cb59`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18007cb59`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall pplx::task_completion_event<bool>::_Cancel<std::exception_ptr>(__int64 a1, void *a2, __int64 a3)
{
  char v6; // bl
  __int128 v8; // [rsp+20h] [rbp-18h] BYREF

  v8 = 0;
  __ExceptionPtrCopy(&v8, a2);
  if ( pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(a1, &v8, a3) )
    v6 = pplx::task_completion_event<unsigned __int64>::_CancelInternal(a1);
  else
    v6 = 0;
  __ExceptionPtrDestroy(a2);
  return v6;
}

```

## disassembly

```asm
0x18007cb30  mov     rax, rsp
0x18007cb33  mov     [rax+8], rbx
0x18007cb37  mov     [rax+18h], rsi
0x18007cb3b  mov     [rax+10h], rdx
0x18007cb3f  push    rdi
0x18007cb40  sub     rsp, 30h
0x18007cb44  mov     rbx, r8
0x18007cb47  mov     rdi, rdx
0x18007cb4a  mov     rsi, rcx
0x18007cb4d  xorps   xmm0, xmm0
0x18007cb50  movdqu  xmmword ptr [rax-18h], xmm0
0x18007cb55  lea     rcx, [rax-18h]
0x18007cb59  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18007cb60  nop     dword ptr [rax+rax+00h]
0x18007cb65  mov     r8, rbx
0x18007cb68  lea     rdx, [rsp+38h+var_18]
0x18007cb6d  mov     rcx, rsi
0x18007cb70  call    ??$_StoreException@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x18007cb75  test    al, al
0x18007cb77  jz      short loc_18007CB85
0x18007cb79  mov     rcx, rsi
0x18007cb7c  call    ?_CancelInternal@?$task_completion_event@_K@pplx@@AEBA_NXZ; pplx::task_completion_event<unsigned __int64>::_CancelInternal(void)
0x18007cb81  mov     bl, al
0x18007cb83  jmp     short loc_18007CB87
0x18007cb85  xor     bl, bl
0x18007cb87  mov     rcx, rdi
0x18007cb8a  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18007cb91  nop     dword ptr [rax+rax+00h]
0x18007cb96  mov     al, bl
0x18007cb98  mov     rbx, [rsp+38h+arg_0]
0x18007cb9d  mov     rsi, [rsp+38h+arg_10]
0x18007cba2  add     rsp, 30h
0x18007cba6  pop     rdi
0x18007cba7  retn
```
