# _FilterReplaceCharSur::CreateInstance_::_1_::catch$6

- ea: `0x18002358a`
- end: `0x1800235c0`
- name: `_FilterReplaceCharSur::CreateInstance_::_1_::catch$6`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b980`

## string_xrefs

- `0x18002359b`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacecharsur.cpp`

## pseudocode

```c
__int64 __fastcall FilterReplaceCharSur::CreateInstance_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x4D,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplacecharsur.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002358a  mov     [rsp+arg_8], rdx
0x18002358f  push    rbp
0x180023590  sub     rsp, 20h
0x180023594  mov     rbp, rdx
0x180023597  mov     rcx, [rbp+48h]; this
0x18002359b  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x1800235a2  mov     edx, 4Dh ; 'M'; void *
0x1800235a7  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800235ac  mov     [rbp+50h], eax
0x1800235af  mov     rax, 0
0x1800235b9  add     rsp, 20h
0x1800235bd  pop     rbp
0x1800235be  retn
```
