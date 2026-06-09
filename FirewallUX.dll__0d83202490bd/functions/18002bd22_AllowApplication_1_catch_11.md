# _AllowApplication_::_1_::catch$11

- ea: `0x18002bd22`
- end: `0x18002bd5e`
- name: `_AllowApplication_::_1_::catch$11`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002917c`

## string_xrefs

- `0x18002bd36`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`

## pseudocode

```c
__int64 __fastcall AllowApplication_::_1_::catch_11(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 128) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 296),
                            (void *)0x11A,
                            (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18002bd22  mov     [rsp+arg_8], rdx
0x18002bd27  push    rbp
0x18002bd28  sub     rsp, 50h
0x18002bd2c  mov     rbp, rdx
0x18002bd2f  mov     rcx, [rbp+128h]; this
0x18002bd36  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x18002bd3d  mov     edx, 11Ah; void *
0x18002bd42  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002bd47  mov     [rbp+80h], eax
0x18002bd4d  mov     rax, 0
0x18002bd57  add     rsp, 50h
0x18002bd5b  pop     rbp
0x18002bd5c  retn
```
