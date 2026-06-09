# _CursorUtils::CreateAndApplyCustomCursor_::_1_::catch$0

- ea: `0x180033f9d`
- end: `0x180033fd3`
- name: `_CursorUtils::CreateAndApplyCustomCursor_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000e9d4`

## string_xrefs

- `0x180033fae`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`

## pseudocode

```c
__int64 __fastcall CursorUtils::CreateAndApplyCustomCursor_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 104) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 88),
                            (void *)0x203,
                            (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180033f9d  mov     [rsp+arg_8], rdx
0x180033fa2  push    rbp
0x180033fa3  sub     rsp, 20h
0x180033fa7  mov     rbp, rdx
0x180033faa  mov     rcx, [rbp+58h]; this
0x180033fae  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x180033fb5  mov     edx, 203h; void *
0x180033fba  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180033fbf  mov     [rbp+68h], eax
0x180033fc2  mov     rax, 0
0x180033fcc  add     rsp, 20h
0x180033fd0  pop     rbp
0x180033fd1  retn
```
