# Concurrency::task_completion_event<DockedClient::AppInstallResult>::set_exception(std::exception_ptr)

- ea: `0x18003bb8c`
- end: `0x18003bc20`
- name: `?set_exception@?$task_completion_event@UAppInstallResult@DockedClient@@@Concurrency@@QEBA_NVexception_ptr@std@@@Z`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006b47d`
- `0x18006baf7`

## callees

- `0x180007660`
- `0x180027460`
- `0x18002bce4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003bbfd`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003bbfd`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003bbd5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003bbd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Concurrency::task_completion_event<DockedClient::AppInstallResult>::set_exception(
        __int64 *a1,
        void *a2)
{
  __int128 v5; // [rsp+20h] [rbp-48h] BYREF
  void *v6; // [rsp+30h] [rbp-38h] BYREF
  __int128 v7; // [rsp+38h] [rbp-30h] BYREF
  __int64 v8; // [rsp+48h] [rbp-20h]
  void *v9; // [rsp+50h] [rbp-18h]
  void *retaddr; // [rsp+68h] [rbp+0h]

  v9 = a2;
  v7 = 0;
  v8 = 0;
  v6 = retaddr;
  v5 = 0;
  __ExceptionPtrCopy(&v5, a2);
  LOBYTE(a1) = Concurrency::task_completion_event<DockedClient::AppInstallResult>::_Cancel<std::exception_ptr>(
                 a1,
                 &v5,
                 (const struct Concurrency::details::_TaskCreationCallstack *)&v6);
  std::vector<void *>::~vector<void *>(&v7);
  __ExceptionPtrDestroy(a2);
  return (char)a1;
}

```

## disassembly

```asm
0x18003bb8c  mov     r11, rsp
0x18003bb8f  mov     [r11+18h], rbx
0x18003bb93  push    rdi
0x18003bb94  sub     rsp, 60h
0x18003bb98  mov     rax, cs:__security_cookie
0x18003bb9f  xor     rax, rsp
0x18003bba2  mov     [rsp+68h+var_10], rax
0x18003bba7  mov     rdi, rdx
0x18003bbaa  mov     rbx, rcx
0x18003bbad  mov     [r11-18h], rdx
0x18003bbb1  mov     rax, [rsp+68h]
0x18003bbb6  xorps   xmm0, xmm0
0x18003bbb9  movdqu  [rsp+68h+var_30], xmm0
0x18003bbbf  mov     qword ptr [r11-20h], 0
0x18003bbc7  mov     [r11-38h], rax
0x18003bbcb  movdqu  [rsp+68h+var_48], xmm0
0x18003bbd1  lea     rcx, [r11-48h]
0x18003bbd5  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003bbdb  lea     r8, [rsp+68h+var_38]
0x18003bbe0  lea     rdx, [rsp+68h+var_48]
0x18003bbe5  mov     rcx, rbx
0x18003bbe8  call    ??$_Cancel@Vexception_ptr@std@@@?$task_completion_event@UAppInstallResult@DockedClient@@@Concurrency@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z; Concurrency::task_completion_event<DockedClient::AppInstallResult>::_Cancel<std::exception_ptr>(std::exception_ptr,Concurrency::details::_TaskCreationCallstack const &)
0x18003bbed  mov     bl, al
0x18003bbef  lea     rcx, [rsp+68h+var_30]
0x18003bbf4  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x18003bbf9  nop
0x18003bbfa  mov     rcx, rdi
0x18003bbfd  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003bc03  mov     al, bl
0x18003bc05  mov     rcx, [rsp+68h+var_10]
0x18003bc0a  xor     rcx, rsp; StackCookie
0x18003bc0d  call    __security_check_cookie
0x18003bc12  mov     rbx, [rsp+68h+arg_10]
0x18003bc1a  add     rsp, 60h
0x18003bc1e  pop     rdi
0x18003bc1f  retn
```
