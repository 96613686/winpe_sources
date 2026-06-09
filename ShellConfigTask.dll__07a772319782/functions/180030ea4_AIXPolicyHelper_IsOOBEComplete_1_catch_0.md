# _AIXPolicyHelper::IsOOBEComplete_::_1_::catch$0

- ea: `0x180030ea4`
- end: `0x180030ed8`
- name: `_AIXPolicyHelper::IsOOBEComplete_::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001d368`

## string_xrefs

- `0x180030eb5`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
__int64 __fastcall AIXPolicyHelper::IsOOBEComplete_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0xE3,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180030ea4  mov     [rsp+arg_8], rdx
0x180030ea9  push    rbp
0x180030eaa  sub     rsp, 20h
0x180030eae  mov     rbp, rdx
0x180030eb1  mov     rcx, [rbp+28h]; this
0x180030eb5  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x180030ebc  mov     edx, 0E3h; void *
0x180030ec1  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180030ec6  nop
0x180030ec7  mov     rax, 0
0x180030ed1  add     rsp, 20h
0x180030ed5  pop     rbp
0x180030ed6  retn
```
