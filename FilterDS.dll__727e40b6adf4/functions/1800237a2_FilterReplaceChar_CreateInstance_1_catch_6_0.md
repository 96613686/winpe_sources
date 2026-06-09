# _FilterReplaceChar::CreateInstance_::_1_::catch$6_0

- ea: `0x1800237a2`
- end: `0x1800237d8`
- name: `_FilterReplaceChar::CreateInstance_::_1_::catch$6_0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b980`

## string_xrefs

- `0x1800237b3`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacechar.cpp`

## pseudocode

```c
__int64 __fastcall FilterReplaceChar::CreateInstance_::_1_::catch_6_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x4E,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplacechar.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800237a2  mov     [rsp+arg_8], rdx
0x1800237a7  push    rbp
0x1800237a8  sub     rsp, 20h
0x1800237ac  mov     rbp, rdx
0x1800237af  mov     rcx, [rbp+48h]; this
0x1800237b3  lea     r8, aMincoreTextinp_23; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x1800237ba  mov     edx, 4Eh ; 'N'; void *
0x1800237bf  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800237c4  mov     [rbp+50h], eax
0x1800237c7  mov     rax, 0
0x1800237d1  add     rsp, 20h
0x1800237d5  pop     rbp
0x1800237d6  retn
```
