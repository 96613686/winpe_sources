# _PrinterCleanupTask::Worker_::_1_::catch$0

- ea: `0x1800163c4`
- end: `0x1800163fa`
- name: `_PrinterCleanupTask::Worker_::_1_::catch$0`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x1800163d5`: `printscan\print\shared\printercleanuptask\dll\printercleanuptask.cpp`

## pseudocode

```c
__int64 __fastcall PrinterCleanupTask::Worker_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0xD,
                           (int)"printscan\\print\\shared\\printercleanuptask\\dll\\printercleanuptask.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800163c4  mov     [rsp+arg_8], rdx
0x1800163c9  push    rbp
0x1800163ca  sub     rsp, 20h
0x1800163ce  mov     rbp, rdx
0x1800163d1  mov     rcx, [rbp+28h]; this
0x1800163d5  lea     r8, aPrintscanPrint_2; "printscan\\print\\shared\\printercleanu"...
0x1800163dc  mov     edx, 0Dh; void *
0x1800163e1  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800163e6  mov     [rbp+38h], eax
0x1800163e9  mov     rax, 0
0x1800163f3  add     rsp, 20h
0x1800163f7  pop     rbp
0x1800163f8  retn
```
