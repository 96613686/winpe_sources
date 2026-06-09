# _PrintJobCleanupTask::Worker_::_1_::catch$0

- ea: `0x180016400`
- end: `0x180016436`
- name: `_PrintJobCleanupTask::Worker_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x180016411`: `printscan\print\shared\printercleanuptask\dll\printjobcleanuptask.cpp`

## pseudocode

```c
__int64 __fastcall PrintJobCleanupTask::Worker_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0xD,
                           (int)"printscan\\print\\shared\\printercleanuptask\\dll\\printjobcleanuptask.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180016400  mov     [rsp+arg_8], rdx
0x180016405  push    rbp
0x180016406  sub     rsp, 20h
0x18001640a  mov     rbp, rdx
0x18001640d  mov     rcx, [rbp+28h]; this
0x180016411  lea     r8, aPrintscanPrint_0; "printscan\\print\\shared\\printercleanu"...
0x180016418  mov     edx, 0Dh; void *
0x18001641d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180016422  mov     [rbp+38h], eax
0x180016425  mov     rax, 0
0x18001642f  add     rsp, 20h
0x180016433  pop     rbp
0x180016434  retn
```
