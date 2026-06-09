# pplx::task_completion_event<web::http::http_response>::set_exception(std::exception_ptr)

- ea: `0x18003a2bc`
- end: `0x18003a35f`
- name: `?set_exception@?$task_completion_event@Vhttp_response@http@web@@@pplx@@QEBA_NVexception_ptr@std@@@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800396e0`

## callees

- `0x180011dcc`
- `0x1800157f4`
- `0x180031d48`
- `0x180035188`
- `0x18003a2bc`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003a33b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003a34f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003a33b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003a34f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003a2f1`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003a30f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003a2f1`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003a30f`

## pseudocode

```c
char __fastcall pplx::task_completion_event<web::http::http_response>::set_exception(__int64 *a1, void *a2)
{
  __int64 v4; // r8
  char v5; // bl
  __int128 v7; // [rsp+20h] [rbp-40h] BYREF
  __int128 v8; // [rsp+30h] [rbp-30h] BYREF
  __int64 v9; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v10[24]; // [rsp+48h] [rbp-18h] BYREF

  pplx::details::_TaskCreationCallstack::_TaskCreationCallstack((pplx::details::_TaskCreationCallstack *)&v9);
  v9 = v4;
  v7 = 0;
  __ExceptionPtrCopy(&v7, a2);
  v8 = 0;
  __ExceptionPtrCopy(&v8, &v7);
  if ( pplx::task_completion_event<web::http::http_response>::_StoreException<std::exception_ptr>(a1, &v8, (__int64)&v9) )
    v5 = pplx::task_completion_event<web::http::http_response>::_CancelInternal(a1);
  else
    v5 = 0;
  __ExceptionPtrDestroy(&v7);
  std::vector<void *>::_Tidy(v10);
  __ExceptionPtrDestroy(a2);
  return v5;
}

```

## disassembly

```asm
0x18003a2bc  mov     [rsp-18h+arg_8], rdx
0x18003a2c1  push    rbp
0x18003a2c2  push    rbx
0x18003a2c3  push    rdi
0x18003a2c4  mov     rbp, rsp
0x18003a2c7  sub     rsp, 60h
0x18003a2cb  mov     rdi, rdx
0x18003a2ce  mov     rbx, rcx
0x18003a2d1  mov     r8, [rbp+18h]
0x18003a2d5  lea     rcx, [rbp+var_20]; this
0x18003a2d9  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@XZ; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x18003a2de  mov     [rbp+var_20], r8
0x18003a2e2  xorps   xmm0, xmm0
0x18003a2e5  movdqu  [rbp+var_40], xmm0
0x18003a2ea  mov     rdx, rdi
0x18003a2ed  lea     rcx, [rbp+var_40]
0x18003a2f1  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003a2f7  lea     rax, [rbp+var_40]
0x18003a2fb  mov     [rbp+arg_10], rax
0x18003a2ff  xorps   xmm0, xmm0
0x18003a302  movdqu  [rbp+var_30], xmm0
0x18003a307  lea     rdx, [rbp+var_40]
0x18003a30b  lea     rcx, [rbp+var_30]
0x18003a30f  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003a315  lea     r8, [rbp+var_20]
0x18003a319  lea     rdx, [rbp+var_30]
0x18003a31d  mov     rcx, rbx
0x18003a320  call    ??$_StoreException@Vexception_ptr@std@@@?$task_completion_event@Vhttp_response@http@web@@@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; pplx::task_completion_event<web::http::http_response>::_StoreException<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x18003a325  test    al, al
0x18003a327  jz      short loc_18003A335
0x18003a329  mov     rcx, rbx
0x18003a32c  call    ?_CancelInternal@?$task_completion_event@Vhttp_response@http@web@@@pplx@@AEBA_NXZ; pplx::task_completion_event<web::http::http_response>::_CancelInternal(void)
0x18003a331  mov     bl, al
0x18003a333  jmp     short loc_18003A337
0x18003a335  xor     bl, bl
0x18003a337  lea     rcx, [rbp+var_40]
0x18003a33b  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003a341  nop
0x18003a342  lea     rcx, [rbp+var_18]
0x18003a346  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18003a34b  nop
0x18003a34c  mov     rcx, rdi
0x18003a34f  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003a355  mov     al, bl
0x18003a357  add     rsp, 60h
0x18003a35b  pop     rdi
0x18003a35c  pop     rbx
0x18003a35d  pop     rbp
0x18003a35e  retn
```
