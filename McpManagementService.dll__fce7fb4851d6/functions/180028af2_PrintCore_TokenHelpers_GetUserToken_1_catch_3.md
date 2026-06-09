# _PrintCore::TokenHelpers::GetUserToken_::_1_::catch$3

- ea: `0x180028af2`
- end: `0x180028b28`
- name: `_PrintCore::TokenHelpers::GetUserToken_::_1_::catch$3`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001b08c`

## string_xrefs

- `0x180028b03`: `onecoreuap\internal\printscan\inc\TokenHelpers.h`

## pseudocode

```c
__int64 __fastcall PrintCore::TokenHelpers::GetUserToken_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x3B,
                           (unsigned int)"onecoreuap\\internal\\printscan\\inc\\TokenHelpers.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180028af2  mov     [rsp+arg_8], rdx
0x180028af7  push    rbp
0x180028af8  sub     rsp, 20h
0x180028afc  mov     rbp, rdx
0x180028aff  mov     rcx, [rbp+28h]; this
0x180028b03  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\printscan\\inc\\T"...
0x180028b0a  mov     edx, 3Bh ; ';'; void *
0x180028b0f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180028b14  mov     [rbp+38h], eax
0x180028b17  mov     rax, 0
0x180028b21  add     rsp, 20h
0x180028b25  pop     rbp
0x180028b26  retn
```
