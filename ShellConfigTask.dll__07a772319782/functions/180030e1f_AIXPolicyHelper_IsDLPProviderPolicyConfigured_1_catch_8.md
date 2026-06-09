# _AIXPolicyHelper::IsDLPProviderPolicyConfigured_::_1_::catch$8

- ea: `0x180030e1f`
- end: `0x180030e56`
- name: `_AIXPolicyHelper::IsDLPProviderPolicyConfigured_::_1_::catch$8`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001d368`

## string_xrefs

- `0x180030e33`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
__int64 __fastcall AIXPolicyHelper::IsDLPProviderPolicyConfigured_::_1_::catch_8(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 152),
    (void *)0x360,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180030e1f  mov     [rsp+arg_8], rdx
0x180030e24  push    rbp
0x180030e25  sub     rsp, 20h
0x180030e29  mov     rbp, rdx
0x180030e2c  mov     rcx, [rbp+98h]; this
0x180030e33  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x180030e3a  mov     edx, 360h; void *
0x180030e3f  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180030e44  nop
0x180030e45  mov     rax, 0
0x180030e4f  add     rsp, 20h
0x180030e53  pop     rbp
0x180030e54  retn
```
