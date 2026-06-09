# _Windows::Security::Isolation::BrokerUtils::AddBfsPolicyEntryForTokenAndFilepath_::_1_::catch$4

- ea: `0x140013896`
- end: `0x1400138b9`
- name: `_Windows::Security::Isolation::BrokerUtils::AddBfsPolicyEntryForTokenAndFilepath_::_1_::catch$4`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000f794`

## string_xrefs

- `0x1400138a7`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`

## pseudocode

```c
void __fastcall __noreturn Windows::Security::Isolation::BrokerUtils::AddBfsPolicyEntryForTokenAndFilepath_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Throw_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0x42,
    (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
    a4);
}

```

## disassembly

```asm
0x140013896  mov     [rsp+arg_8], rdx
0x14001389b  push    rbp
0x14001389c  sub     rsp, 30h
0x1400138a0  mov     rbp, rdx
0x1400138a3  mov     rcx, [rbp+48h]; this
0x1400138a7  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x1400138ae  mov     edx, 42h ; 'B'; void *
0x1400138b3  call    ?Throw_CaughtException@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_CaughtException(void *,uint,char const *)
```
