# _AIXPolicyHelper::IsC2DAllowedOnDeviceByPolicy_::_1_::catch$2

- ea: `0x180030dd0`
- end: `0x180030e07`
- name: `_AIXPolicyHelper::IsC2DAllowedOnDeviceByPolicy_::_1_::catch$2`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001d368`

## string_xrefs

- `0x180030de4`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
__int64 __fastcall AIXPolicyHelper::IsC2DAllowedOnDeviceByPolicy_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 136),
    (void *)0x4EC,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180030dd0  mov     [rsp+arg_8], rdx
0x180030dd5  push    rbp
0x180030dd6  sub     rsp, 30h
0x180030dda  mov     rbp, rdx
0x180030ddd  mov     rcx, [rbp+88h]; this
0x180030de4  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x180030deb  mov     edx, 4ECh; void *
0x180030df0  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180030df5  nop
0x180030df6  mov     rax, 0
0x180030e00  add     rsp, 30h
0x180030e04  pop     rbp
0x180030e05  retn
```
