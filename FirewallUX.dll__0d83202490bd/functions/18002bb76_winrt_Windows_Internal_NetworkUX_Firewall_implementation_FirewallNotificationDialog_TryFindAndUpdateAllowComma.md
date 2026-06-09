# _winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_TryFindAndUpdateAllowCommandEnabled_::_1_::catch$10

- ea: `0x18002bb76`
- end: `0x18002bbaa`
- name: `_winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_TryFindAndUpdateAllowCommandEnabled_::_1_::catch$10`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180012ce4`

## string_xrefs

- `0x18002bb87`: `shellcommon\shell\networkux\firewallux\lib\firewallnotificationdialog.cpp`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_TryFindAndUpdateAllowCommandEnabled_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0x249,
    (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18002bb76  mov     [rsp+arg_8], rdx
0x18002bb7b  push    rbp
0x18002bb7c  sub     rsp, 20h
0x18002bb80  mov     rbp, rdx
0x18002bb83  mov     rcx, [rbp+48h]; this
0x18002bb87  lea     r8, aShellcommonShe; "shellcommon\\shell\\networkux\\firewall"...
0x18002bb8e  mov     edx, 249h; void *
0x18002bb93  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18002bb98  nop
0x18002bb99  mov     rax, 0
0x18002bba3  add     rsp, 20h
0x18002bba7  pop     rbp
0x18002bba8  retn
```
