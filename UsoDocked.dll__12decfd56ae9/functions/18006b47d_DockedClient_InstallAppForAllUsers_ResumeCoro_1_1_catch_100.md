# _DockedClient::InstallAppForAllUsers$_ResumeCoro$1_::_1_::catch$100

- ea: `0x18006b47d`
- end: `0x18006b4ec`
- name: `_DockedClient::InstallAppForAllUsers$_ResumeCoro$1_::_1_::catch$100`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18003bb8c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006b4b6`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006b4b6`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006b4c3`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18006b4c3`

## pseudocode

```c
__int64 __fastcall DockedClient::InstallAppForAllUsers__ResumeCoro_1_::_1_::catch_100(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 368);
  *(_WORD *)(v2 + 8) = -1;
  *(_QWORD *)(v2 + 352) = 0;
  *(_QWORD *)(v2 + 360) = 0;
  __ExceptionPtrCreate((void *)(v2 + 352));
  __ExceptionPtrCurrentException((void *)(v2 + 352));
  Concurrency::task_completion_event<DockedClient::AppInstallResult>::set_exception(
    (__int64 *)(v2 - 16),
    (void *)(v2 + 352));
  return 0;
}

```

## disassembly

```asm
0x18006b47d  mov     [rsp+arg_8], rdx
0x18006b482  push    rbx
0x18006b483  push    rbp
0x18006b484  sub     rsp, 38h
0x18006b488  mov     rbp, rdx
0x18006b48b  or      eax, 0FFFFFFFFh
0x18006b48e  mov     rbx, [rbp+170h]
0x18006b495  mov     [rbx+8], ax
0x18006b499  mov     qword ptr [rbx+160h], 0
0x18006b4a4  mov     qword ptr [rbx+168h], 0
0x18006b4af  lea     rcx, [rbx+160h]
0x18006b4b6  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18006b4bc  lea     rcx, [rbx+160h]
0x18006b4c3  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18006b4c9  lea     rcx, [rbx-10h]
0x18006b4cd  lea     rdx, [rbx+160h]
0x18006b4d4  call    ?set_exception@?$task_completion_event@UAppInstallResult@DockedClient@@@Concurrency@@QEBA_NVexception_ptr@std@@@Z; Concurrency::task_completion_event<DockedClient::AppInstallResult>::set_exception(std::exception_ptr)
0x18006b4d9  nop
0x18006b4da  mov     rax, 0
0x18006b4e4  add     rsp, 38h
0x18006b4e8  pop     rbp
0x18006b4e9  pop     rbx
0x18006b4ea  retn
```
