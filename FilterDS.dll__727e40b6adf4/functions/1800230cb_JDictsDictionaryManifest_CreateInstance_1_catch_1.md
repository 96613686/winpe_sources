# _JDictsDictionaryManifest::CreateInstance_::_1_::catch$1

- ea: `0x1800230cb`
- end: `0x180023101`
- name: `_JDictsDictionaryManifest::CreateInstance_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000b980`

## string_xrefs

- `0x1800230dc`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\jdictsdictionarymanifest.cpp`

## pseudocode

```c
__int64 __fastcall JDictsDictionaryManifest::CreateInstance_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x2C,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\jdi"
                                         "ctsdictionarymanifest.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800230cb  mov     [rsp+arg_8], rdx
0x1800230d0  push    rbp
0x1800230d1  sub     rsp, 20h
0x1800230d5  mov     rbp, rdx
0x1800230d8  mov     rcx, [rbp+28h]; this
0x1800230dc  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x1800230e3  mov     edx, 2Ch ; ','; void *
0x1800230e8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800230ed  mov     [rbp+30h], eax
0x1800230f0  mov     rax, 0
0x1800230fa  add     rsp, 20h
0x1800230fe  pop     rbp
0x1800230ff  retn
```
