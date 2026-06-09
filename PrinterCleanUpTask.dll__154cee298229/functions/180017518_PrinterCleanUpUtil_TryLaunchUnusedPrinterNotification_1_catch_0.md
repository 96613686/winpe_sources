# _PrinterCleanUpUtil::TryLaunchUnusedPrinterNotification_::_1_::catch$0

- ea: `0x180017518`
- end: `0x18001754e`
- name: `_PrinterCleanUpUtil::TryLaunchUnusedPrinterNotification_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x180017529`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrinterCleanUpUtil::TryLaunchUnusedPrinterNotification_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x124,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180017518  mov     [rsp+arg_8], rdx
0x18001751d  push    rbp
0x18001751e  sub     rsp, 40h
0x180017522  mov     rbp, rdx
0x180017525  mov     rcx, [rbp+48h]; this
0x180017529  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180017530  mov     edx, 124h; void *
0x180017535  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001753a  mov     [rbp+50h], eax
0x18001753d  mov     rax, 0
0x180017547  add     rsp, 40h
0x18001754b  pop     rbp
0x18001754c  retn
```
