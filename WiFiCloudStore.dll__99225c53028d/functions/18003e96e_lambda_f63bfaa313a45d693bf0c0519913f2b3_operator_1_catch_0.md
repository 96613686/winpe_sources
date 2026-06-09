# __lambda_f63bfaa313a45d693bf0c0519913f2b3_::operator()_::_1_::catch$0

- ea: `0x18003e96e`
- end: `0x18003e9a2`
- name: `__lambda_f63bfaa313a45d693bf0c0519913f2b3_::operator()_::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800310a8`

## string_xrefs

- `0x18003e97f`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_f63bfaa313a45d693bf0c0519913f2b3_::operator()_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0xC4,
    (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003e96e  mov     [rsp+arg_8], rdx
0x18003e973  push    rbp
0x18003e974  sub     rsp, 20h
0x18003e978  mov     rbp, rdx
0x18003e97b  mov     rcx, [rbp+28h]; this
0x18003e97f  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x18003e986  mov     edx, 0C4h; void *
0x18003e98b  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003e990  nop
0x18003e991  mov     rax, 0
0x18003e99b  add     rsp, 20h
0x18003e99f  pop     rbp
0x18003e9a0  retn
```
