# _AIXPolicyHelper::IsC2DAllowedByITPolicy_::_1_::catch$28

- ea: `0x180030d81`
- end: `0x180030db8`
- name: `_AIXPolicyHelper::IsC2DAllowedByITPolicy_::_1_::catch$28`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001d368`

## string_xrefs

- `0x180030d95`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
__int64 __fastcall AIXPolicyHelper::IsC2DAllowedByITPolicy_::_1_::catch_28(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 232),
    (void *)0x4C9,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180030d81  mov     [rsp+arg_8], rdx
0x180030d86  push    rbp
0x180030d87  sub     rsp, 30h
0x180030d8b  mov     rbp, rdx
0x180030d8e  mov     rcx, [rbp+0E8h]; this
0x180030d95  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x180030d9c  mov     edx, 4C9h; void *
0x180030da1  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180030da6  nop
0x180030da7  mov     rax, 0
0x180030db1  add     rsp, 30h
0x180030db5  pop     rbp
0x180030db6  retn
```
