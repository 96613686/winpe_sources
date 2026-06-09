# _FilterReplaceWord::CreateInstance_::_1_::catch$7

- ea: `0x1800235c6`
- end: `0x1800235fc`
- name: `_FilterReplaceWord::CreateInstance_::_1_::catch$7`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b980`

## string_xrefs

- `0x1800235d7`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplaceword.cpp`

## pseudocode

```c
__int64 __fastcall FilterReplaceWord::CreateInstance_::_1_::catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x43,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplaceword.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800235c6  mov     [rsp+arg_8], rdx
0x1800235cb  push    rbp
0x1800235cc  sub     rsp, 20h
0x1800235d0  mov     rbp, rdx
0x1800235d3  mov     rcx, [rbp+48h]; this
0x1800235d7  lea     r8, aMincoreTextinp_12; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x1800235de  mov     edx, 43h ; 'C'; void *
0x1800235e3  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800235e8  mov     [rbp+50h], eax
0x1800235eb  mov     rax, 0
0x1800235f5  add     rsp, 20h
0x1800235f9  pop     rbp
0x1800235fa  retn
```
