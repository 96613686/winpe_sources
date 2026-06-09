# _FilterReplaceWord::CreateInstance_::_1_::catch$6

- ea: `0x180023602`
- end: `0x180023638`
- name: `_FilterReplaceWord::CreateInstance_::_1_::catch$6`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b980`

## string_xrefs

- `0x180023613`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplaceword.cpp`

## pseudocode

```c
__int64 __fastcall FilterReplaceWord::CreateInstance_::_1_::catch_6(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x4B,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplaceword.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180023602  mov     [rsp+arg_8], rdx
0x180023607  push    rbp
0x180023608  sub     rsp, 20h
0x18002360c  mov     rbp, rdx
0x18002360f  mov     rcx, [rbp+38h]; this
0x180023613  lea     r8, aMincoreTextinp_12; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18002361a  mov     edx, 4Bh ; 'K'; void *
0x18002361f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180023624  mov     [rbp+40h], eax
0x180023627  mov     rax, 0
0x180023631  add     rsp, 20h
0x180023635  pop     rbp
0x180023636  retn
```
