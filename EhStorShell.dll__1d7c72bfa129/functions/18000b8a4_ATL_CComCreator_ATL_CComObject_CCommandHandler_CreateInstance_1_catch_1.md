# _ATL::CComCreator_ATL::CComObject_CCommandHandler___::CreateInstance_::_1_::catch$1

- ea: `0x18000b8a4`
- end: `0x18000b8c2`
- name: `_ATL::CComCreator_ATL::CComObject_CCommandHandler___::CreateInstance_::_1_::catch$1`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c
__int64 ATL::CComCreator_ATL::CComObject_CCommandHandler___::CreateInstance_::_1_::catch_1()
{
  return 0;
}

```

## disassembly

```asm
0x18000b8a4  mov     [rsp+arg_8], rdx
0x18000b8a9  push    rbp
0x18000b8aa  sub     rsp, 20h
0x18000b8ae  mov     rbp, rdx
0x18000b8b1  mov     rax, 0
0x18000b8bb  add     rsp, 20h
0x18000b8bf  pop     rbp
0x18000b8c0  retn
```
