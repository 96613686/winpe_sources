# _PrinterCleanUpUtil::SnoozePrinterCleanUpTask_::_1_::catch$0

- ea: `0x1800174dc`
- end: `0x180017512`
- name: `_PrinterCleanUpUtil::SnoozePrinterCleanUpTask_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x1800174ed`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrinterCleanUpUtil::SnoozePrinterCleanUpTask_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0xE3,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800174dc  mov     [rsp+arg_8], rdx
0x1800174e1  push    rbp
0x1800174e2  sub     rsp, 30h
0x1800174e6  mov     rbp, rdx
0x1800174e9  mov     rcx, [rbp+38h]; this
0x1800174ed  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x1800174f4  mov     edx, 0E3h; void *
0x1800174f9  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800174fe  mov     [rbp+40h], eax
0x180017501  mov     rax, 0
0x18001750b  add     rsp, 30h
0x18001750f  pop     rbp
0x180017510  retn
```
