# _winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand::get_Handler_::_1_::catch$3

- ea: `0x18002c026`
- end: `0x18002c05c`
- name: `_winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand::get_Handler_::_1_::catch$3`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002917c`

## string_xrefs

- `0x18002c037`: `shellcommon\shell\networkux\firewallux\lib\popupcommand.cpp`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand::get_Handler_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x25,
                           (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\popupcommand.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002c026  mov     [rsp+arg_8], rdx
0x18002c02b  push    rbp
0x18002c02c  sub     rsp, 20h
0x18002c030  mov     rbp, rdx
0x18002c033  mov     rcx, [rbp+48h]; this
0x18002c037  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\networkux\\firewall"...
0x18002c03e  mov     edx, 25h ; '%'; void *
0x18002c043  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002c048  mov     [rbp+50h], eax
0x18002c04b  mov     rax, 0
0x18002c055  add     rsp, 20h
0x18002c059  pop     rbp
0x18002c05a  retn
```
