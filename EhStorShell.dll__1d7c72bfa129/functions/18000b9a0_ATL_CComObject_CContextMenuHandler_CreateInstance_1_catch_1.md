# _ATL::CComObject_CContextMenuHandler_::CreateInstance_::_1_::catch$1

- ea: `0x18000b9a0`
- end: `0x18000b9be`
- name: `_ATL::CComObject_CContextMenuHandler_::CreateInstance_::_1_::catch$1`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c
__int64 ATL::CComObject_CContextMenuHandler_::CreateInstance_::_1_::catch_1()
{
  return 0;
}

```

## disassembly

```asm
0x18000b9a0  mov     [rsp+arg_8], rdx
0x18000b9a5  push    rbp
0x18000b9a6  sub     rsp, 20h
0x18000b9aa  mov     rbp, rdx
0x18000b9ad  mov     rax, 0
0x18000b9b7  add     rsp, 20h
0x18000b9bb  pop     rbp
0x18000b9bc  retn
```
