# pplx::task_completion_event<int>::set_exception(std::exception_ptr)

- ea: `0x1800301d4`
- end: `0x180030277`
- name: `?set_exception@?$task_completion_event@H@pplx@@QEBA_NVexception_ptr@std@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023128`
- `0x1800232a4`
- `0x180023364`
- `0x180025c6c`
- `0x180047234`
- `0x18005ae1d`

## callees

- `0x180011dcc`
- `0x1800157f4`
- `0x18001f528`
- `0x18002723c`
- `0x1800301d4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030253`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030267`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030253`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030267`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180030209`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180030227`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180030209`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180030227`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall pplx::task_completion_event<int>::set_exception(__int64 *a1, void *a2)
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
  if ( pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(a1, &v8, (__int64)&v9) )
    v5 = pplx::task_completion_event<unsigned __int64>::_CancelInternal(a1);
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
0x1800301d4  mov     [rsp-18h+arg_8], rdx
0x1800301d9  push    rbp
0x1800301da  push    rbx
0x1800301db  push    rdi
0x1800301dc  mov     rbp, rsp
0x1800301df  sub     rsp, 60h
0x1800301e3  mov     rdi, rdx
0x1800301e6  mov     rbx, rcx
0x1800301e9  mov     r8, [rbp+18h]
0x1800301ed  lea     rcx, [rbp+var_20]; this
0x1800301f1  call    ??0_TaskCreationCallstack@details@pplx@@QEAA@XZ; pplx::details::_TaskCreationCallstack::_TaskCreationCallstack(void)
0x1800301f6  mov     [rbp+var_20], r8
0x1800301fa  xorps   xmm0, xmm0
0x1800301fd  movdqu  [rbp+var_40], xmm0
0x180030202  mov     rdx, rdi
0x180030205  lea     rcx, [rbp+var_40]
0x180030209  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003020f  lea     rax, [rbp+var_40]
0x180030213  mov     [rbp+arg_10], rax
0x180030217  xorps   xmm0, xmm0
0x18003021a  movdqu  [rbp+var_30], xmm0
0x18003021f  lea     rdx, [rbp+var_40]
0x180030223  lea     rcx, [rbp+var_30]
0x180030227  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003022d  lea     r8, [rbp+var_20]
0x180030231  lea     rdx, [rbp+var_30]
0x180030235  mov     rcx, rbx
0x180030238  call    ??$_StoreException@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x18003023d  test    al, al
0x18003023f  jz      short loc_18003024D
0x180030241  mov     rcx, rbx
0x180030244  call    ?_CancelInternal@?$task_completion_event@_K@pplx@@AEBA_NXZ; pplx::task_completion_event<unsigned __int64>::_CancelInternal(void)
0x180030249  mov     bl, al
0x18003024b  jmp     short loc_18003024F
0x18003024d  xor     bl, bl
0x18003024f  lea     rcx, [rbp+var_40]
0x180030253  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180030259  nop
0x18003025a  lea     rcx, [rbp+var_18]
0x18003025e  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180030263  nop
0x180030264  mov     rcx, rdi
0x180030267  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003026d  mov     al, bl
0x18003026f  add     rsp, 60h
0x180030273  pop     rdi
0x180030274  pop     rbx
0x180030275  pop     rbp
0x180030276  retn
```
