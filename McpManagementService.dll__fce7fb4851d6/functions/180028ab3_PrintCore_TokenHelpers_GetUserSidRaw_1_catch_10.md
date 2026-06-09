# _PrintCore::TokenHelpers::GetUserSidRaw_::_1_::catch$10

- ea: `0x180028ab3`
- end: `0x180028aec`
- name: `_PrintCore::TokenHelpers::GetUserSidRaw_::_1_::catch$10`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180028ac4`: `onecoreuap\internal\printscan\inc\TokenHelpers.h`

## pseudocode

```c
__int64 __fastcall PrintCore::TokenHelpers::GetUserSidRaw_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 136) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 120),
                            (void *)0x85,
                            (unsigned int)"onecoreuap\\internal\\printscan\\inc\\TokenHelpers.h",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180028ab3  mov     [rsp+arg_8], rdx
0x180028ab8  push    rbp
0x180028ab9  sub     rsp, 30h
0x180028abd  mov     rbp, rdx
0x180028ac0  mov     rcx, [rbp+78h]; this
0x180028ac4  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\printscan\\inc\\T"...
0x180028acb  mov     edx, 85h; void *
0x180028ad0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180028ad5  mov     [rbp+88h], eax
0x180028adb  mov     rax, 0
0x180028ae5  add     rsp, 30h
0x180028ae9  pop     rbp
0x180028aea  retn
```
