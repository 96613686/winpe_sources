# _FilterReplaceChar::CreateInstance_::_1_::catch$6

- ea: `0x180023766`
- end: `0x18002379c`
- name: `_FilterReplaceChar::CreateInstance_::_1_::catch$6`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b980`

## string_xrefs

- `0x180023777`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacechar.cpp`

## pseudocode

```c
__int64 __fastcall FilterReplaceChar::CreateInstance_::_1_::catch_6(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x45,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplacechar.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180023766  mov     [rsp+arg_8], rdx
0x18002376b  push    rbp
0x18002376c  sub     rsp, 20h
0x180023770  mov     rbp, rdx
0x180023773  mov     rcx, [rbp+48h]; this
0x180023777  lea     r8, aMincoreTextinp_23; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18002377e  mov     edx, 45h ; 'E'; void *
0x180023783  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180023788  mov     [rbp+50h], eax
0x18002378b  mov     rax, 0
0x180023795  add     rsp, 20h
0x180023799  pop     rbp
0x18002379a  retn
```
