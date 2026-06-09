# _CheckUserPrefMergeForProfileType_::_1_::catch$7

- ea: `0x18002bd76`
- end: `0x18002bdaa`
- name: `_CheckUserPrefMergeForProfileType_::_1_::catch$7`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012ce4`

## string_xrefs

- `0x18002bd87`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`

## pseudocode

```c
__int64 __fastcall CheckUserPrefMergeForProfileType_::_1_::catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0x8A,
    (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18002bd76  mov     [rsp+arg_8], rdx
0x18002bd7b  push    rbp
0x18002bd7c  sub     rsp, 30h
0x18002bd80  mov     rbp, rdx
0x18002bd83  mov     rcx, [rbp+48h]; this
0x18002bd87  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x18002bd8e  mov     edx, 8Ah; void *
0x18002bd93  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18002bd98  nop
0x18002bd99  mov     rax, 0
0x18002bda3  add     rsp, 30h
0x18002bda7  pop     rbp
0x18002bda8  retn
```
