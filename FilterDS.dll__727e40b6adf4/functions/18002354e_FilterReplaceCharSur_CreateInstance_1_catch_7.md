# _FilterReplaceCharSur::CreateInstance_::_1_::catch$7

- ea: `0x18002354e`
- end: `0x180023584`
- name: `_FilterReplaceCharSur::CreateInstance_::_1_::catch$7`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b980`

## string_xrefs

- `0x18002355f`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacecharsur.cpp`

## pseudocode

```c
__int64 __fastcall FilterReplaceCharSur::CreateInstance_::_1_::catch_7(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x45,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplacecharsur.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002354e  mov     [rsp+arg_8], rdx
0x180023553  push    rbp
0x180023554  sub     rsp, 20h
0x180023558  mov     rbp, rdx
0x18002355b  mov     rcx, [rbp+48h]; this
0x18002355f  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180023566  mov     edx, 45h ; 'E'; void *
0x18002356b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180023570  mov     [rbp+50h], eax
0x180023573  mov     rax, 0
0x18002357d  add     rsp, 20h
0x180023581  pop     rbp
0x180023582  retn
```
