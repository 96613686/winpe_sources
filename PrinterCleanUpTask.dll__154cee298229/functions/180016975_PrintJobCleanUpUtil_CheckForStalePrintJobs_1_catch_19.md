# _PrintJobCleanUpUtil::CheckForStalePrintJobs_::_1_::catch$19

- ea: `0x180016975`
- end: `0x1800169ae`
- name: `_PrintJobCleanUpUtil::CheckForStalePrintJobs_::_1_::catch$19`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x180016989`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrintJobCleanUpUtil::CheckForStalePrintJobs_::_1_::catch_19(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 76) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 360),
                           (void *)0x121,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180016975  mov     [rsp+arg_8], rdx
0x18001697a  push    rbp
0x18001697b  sub     rsp, 40h
0x18001697f  mov     rbp, rdx
0x180016982  mov     rcx, [rbp+168h]; this
0x180016989  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x180016990  mov     edx, 121h; void *
0x180016995  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001699a  mov     [rbp+4Ch], eax
0x18001699d  mov     rax, 0
0x1800169a7  add     rsp, 40h
0x1800169ab  pop     rbp
0x1800169ac  retn
```
