# __anonymous_namespace_::SetRegistryBoolValue_::_1_::catch$3

- ea: `0x18003431f`
- end: `0x180034353`
- name: `__anonymous_namespace_::SetRegistryBoolValue_::_1_::catch$3`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800150c0`

## string_xrefs

- `0x180034330`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::SetRegistryBoolValue_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 56),
    (void *)0xAA,
    (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003431f  mov     [rsp+arg_8], rdx
0x180034324  push    rbp
0x180034325  sub     rsp, 30h
0x180034329  mov     rbp, rdx
0x18003432c  mov     rcx, [rbp+38h]; this
0x180034330  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x180034337  mov     edx, 0AAh; void *
0x18003433c  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180034341  nop
0x180034342  mov     rax, 0
0x18003434c  add     rsp, 30h
0x180034350  pop     rbp
0x180034351  retn
```
