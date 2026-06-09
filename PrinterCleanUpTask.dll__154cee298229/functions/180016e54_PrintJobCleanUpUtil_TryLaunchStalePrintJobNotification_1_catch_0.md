# _PrintJobCleanUpUtil::TryLaunchStalePrintJobNotification_::_1_::catch$0

- ea: `0x180016e54`
- end: `0x180016e8a`
- name: `_PrintJobCleanUpUtil::TryLaunchStalePrintJobNotification_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x180016e65`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrintJobCleanUpUtil::TryLaunchStalePrintJobNotification_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x163,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180016e54  mov     [rsp+arg_8], rdx
0x180016e59  push    rbp
0x180016e5a  sub     rsp, 20h
0x180016e5e  mov     rbp, rdx
0x180016e61  mov     rcx, [rbp+28h]; this
0x180016e65  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x180016e6c  mov     edx, 163h; void *
0x180016e71  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180016e76  mov     [rbp+30h], eax
0x180016e79  mov     rax, 0
0x180016e83  add     rsp, 20h
0x180016e87  pop     rbp
0x180016e88  retn
```
