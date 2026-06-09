# _PrintCore::TokenHelpers::GetUserSid_::_1_::catch$7

- ea: `0x180028a53`
- end: `0x180028a89`
- name: `_PrintCore::TokenHelpers::GetUserSid_::_1_::catch$7`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180028a64`: `onecoreuap\internal\printscan\inc\TokenHelpers.h`

## pseudocode

```c
__int64 __fastcall PrintCore::TokenHelpers::GetUserSid_::_1_::catch_7(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0xA2,
                           (unsigned int)"onecoreuap\\internal\\printscan\\inc\\TokenHelpers.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180028a53  mov     [rsp+arg_8], rdx
0x180028a58  push    rbp
0x180028a59  sub     rsp, 20h
0x180028a5d  mov     rbp, rdx
0x180028a60  mov     rcx, [rbp+38h]; this
0x180028a64  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\printscan\\inc\\T"...
0x180028a6b  mov     edx, 0A2h; void *
0x180028a70  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180028a75  mov     [rbp+40h], eax
0x180028a78  mov     rax, 0
0x180028a82  add     rsp, 20h
0x180028a86  pop     rbp
0x180028a87  retn
```
