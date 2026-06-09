# _PrintJobCleanUpUtil::LaunchStalePrintJobNotification_::_1_::catch$59

- ea: `0x180016de9`
- end: `0x180016e22`
- name: `_PrintJobCleanUpUtil::LaunchStalePrintJobNotification_::_1_::catch$59`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x180016dfd`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrintJobCleanUpUtil::LaunchStalePrintJobNotification_::_1_::catch_59(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 312),
                           (void *)0x154,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180016de9  mov     [rsp+arg_8], rdx
0x180016dee  push    rbp
0x180016def  sub     rsp, 20h
0x180016df3  mov     rbp, rdx
0x180016df6  mov     rcx, [rbp+138h]; this
0x180016dfd  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x180016e04  mov     edx, 154h; void *
0x180016e09  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180016e0e  mov     [rbp+30h], eax
0x180016e11  mov     rax, 0
0x180016e1b  add     rsp, 20h
0x180016e1f  pop     rbp
0x180016e20  retn
```
