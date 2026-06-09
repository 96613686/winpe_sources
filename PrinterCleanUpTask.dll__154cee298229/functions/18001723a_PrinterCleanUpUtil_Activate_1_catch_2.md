# _PrinterCleanUpUtil::Activate_::_1_::catch$2

- ea: `0x18001723a`
- end: `0x180017270`
- name: `_PrinterCleanUpUtil::Activate_::_1_::catch$2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x18001724b`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrinterCleanUpUtil::Activate_::_1_::catch_2(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x133,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001723a  mov     [rsp+arg_8], rdx
0x18001723f  push    rbp
0x180017240  sub     rsp, 20h
0x180017244  mov     rbp, rdx
0x180017247  mov     rcx, [rbp+58h]; this
0x18001724b  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180017252  mov     edx, 133h; void *
0x180017257  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001725c  mov     [rbp+20h], eax
0x18001725f  mov     rax, 0
0x180017269  add     rsp, 20h
0x18001726d  pop     rbp
0x18001726e  retn
```
