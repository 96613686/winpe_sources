# _PrinterCleanUpUtil::CheckForUnusedRemovablePrinters_::_1_::catch$33

- ea: `0x18001736f`
- end: `0x1800173a8`
- name: `_PrinterCleanUpUtil::CheckForUnusedRemovablePrinters_::_1_::catch$33`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x180017383`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrinterCleanUpUtil::CheckForUnusedRemovablePrinters_::_1_::catch_33(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 424),
                           (void *)0xD6,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001736f  mov     [rsp+arg_8], rdx
0x180017374  push    rbp
0x180017375  sub     rsp, 40h
0x180017379  mov     rbp, rdx
0x18001737c  mov     rcx, [rbp+1A8h]; this
0x180017383  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x18001738a  mov     edx, 0D6h; void *
0x18001738f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017394  mov     [rbp+48h], eax
0x180017397  mov     rax, 0
0x1800173a1  add     rsp, 40h
0x1800173a5  pop     rbp
0x1800173a6  retn
```
