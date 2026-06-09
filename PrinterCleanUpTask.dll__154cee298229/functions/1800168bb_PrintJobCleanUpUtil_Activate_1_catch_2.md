# _PrintJobCleanUpUtil::Activate_::_1_::catch$2

- ea: `0x1800168bb`
- end: `0x1800168f1`
- name: `_PrintJobCleanUpUtil::Activate_::_1_::catch$2`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x1800168cc`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrintJobCleanUpUtil::Activate_::_1_::catch_2(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x188,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800168bb  mov     [rsp+arg_8], rdx
0x1800168c0  push    rbp
0x1800168c1  sub     rsp, 20h
0x1800168c5  mov     rbp, rdx
0x1800168c8  mov     rcx, [rbp+58h]; this
0x1800168cc  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x1800168d3  mov     edx, 188h; void *
0x1800168d8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800168dd  mov     [rbp+20h], eax
0x1800168e0  mov     rax, 0
0x1800168ea  add     rsp, 20h
0x1800168ee  pop     rbp
0x1800168ef  retn
```
