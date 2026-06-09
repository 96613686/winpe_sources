# _BthServHandleHCIConnectionEvent_::_1_::catch$14

- ea: `0x180033256`
- end: `0x18003328d`
- name: `_BthServHandleHCIConnectionEvent_::_1_::catch$14`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000f760`

## string_xrefs

- `0x18003326a`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\bthserv.cpp`

## pseudocode

```c
__int64 __fastcall BthServHandleHCIConnectionEvent_::_1_::catch_14(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 168),
    (void *)0x55C,
    (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\bthserv.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180033256  mov     [rsp+arg_8], rdx
0x18003325b  push    rbp
0x18003325c  sub     rsp, 60h
0x180033260  mov     rbp, rdx
0x180033263  mov     rcx, [rbp+0A8h]; this
0x18003326a  lea     r8, aOnecoreDrivers_9; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x180033271  mov     edx, 55Ch; void *
0x180033276  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003327b  nop
0x18003327c  mov     rax, 0
0x180033286  add     rsp, 60h
0x18003328a  pop     rbp
0x18003328b  retn
```
