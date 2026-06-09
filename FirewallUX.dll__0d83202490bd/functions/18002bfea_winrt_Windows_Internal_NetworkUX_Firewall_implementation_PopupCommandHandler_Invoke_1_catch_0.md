# _winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler::Invoke_::_1_::catch$0

- ea: `0x18002bfea`
- end: `0x18002c020`
- name: `_winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler::Invoke_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002917c`

## string_xrefs

- `0x18002bffb`: `shellcommon\shell\networkux\firewallux\lib\PopupCommand.h`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler::Invoke_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x11,
                           (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\PopupCommand.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002bfea  mov     [rsp+arg_8], rdx
0x18002bfef  push    rbp
0x18002bff0  sub     rsp, 20h
0x18002bff4  mov     rbp, rdx
0x18002bff7  mov     rcx, [rbp+28h]; this
0x18002bffb  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\networkux\\firewall"...
0x18002c002  mov     edx, 11h; void *
0x18002c007  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002c00c  mov     [rbp+30h], eax
0x18002c00f  mov     rax, 0
0x18002c019  add     rsp, 20h
0x18002c01d  pop     rbp
0x18002c01e  retn
```
