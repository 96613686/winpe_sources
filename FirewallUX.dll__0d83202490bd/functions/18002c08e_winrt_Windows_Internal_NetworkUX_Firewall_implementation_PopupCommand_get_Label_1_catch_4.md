# _winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand::get_Label_::_1_::catch$4

- ea: `0x18002c08e`
- end: `0x18002c0c4`
- name: `_winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand::get_Label_::_1_::catch$4`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002917c`

## string_xrefs

- `0x18002c09f`: `shellcommon\shell\networkux\firewallux\lib\popupcommand.cpp`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand::get_Label_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x17,
                           (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\popupcommand.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002c08e  mov     [rsp+arg_8], rdx
0x18002c093  push    rbp
0x18002c094  sub     rsp, 20h
0x18002c098  mov     rbp, rdx
0x18002c09b  mov     rcx, [rbp+28h]; this
0x18002c09f  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\networkux\\firewall"...
0x18002c0a6  mov     edx, 17h; void *
0x18002c0ab  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002c0b0  mov     [rbp+30h], eax
0x18002c0b3  mov     rax, 0
0x18002c0bd  add     rsp, 20h
0x18002c0c1  pop     rbp
0x18002c0c2  retn
```
