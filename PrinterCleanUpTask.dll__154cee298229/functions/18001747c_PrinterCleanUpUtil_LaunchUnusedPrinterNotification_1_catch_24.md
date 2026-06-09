# _PrinterCleanUpUtil::LaunchUnusedPrinterNotification_::_1_::catch$24

- ea: `0x18001747c`
- end: `0x1800174b2`
- name: `_PrinterCleanUpUtil::LaunchUnusedPrinterNotification_::_1_::catch$24`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x18001748d`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrinterCleanUpUtil::LaunchUnusedPrinterNotification_::_1_::catch_24(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x10C,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001747c  mov     [rsp+arg_8], rdx
0x180017481  push    rbp
0x180017482  sub     rsp, 20h
0x180017486  mov     rbp, rdx
0x180017489  mov     rcx, [rbp+58h]; this
0x18001748d  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180017494  mov     edx, 10Ch; void *
0x180017499  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001749e  mov     [rbp+60h], eax
0x1800174a1  mov     rax, 0
0x1800174ab  add     rsp, 20h
0x1800174af  pop     rbp
0x1800174b0  retn
```
