# _std::_List_alloc_0_std::_List_base_types_Sharp::Util::Xml::CNode_std::allocator_Sharp::Util::Xml::CNode_____::_Buynode0_::_1_::catch$0

- ea: `0x1400142de`
- end: `0x1400142fe`
- name: `_std::_List_alloc_0_std::_List_base_types_Sharp::Util::Xml::CNode_std::allocator_Sharp::Util::Xml::CNode_____::_Buynode0_::_1_::catch$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x14000157c`
- `0x140001d1c`

## pseudocode

```c
void __fastcall __noreturn std::_List_alloc_0_std::_List_base_types_Sharp::Util::Xml::CNode_std::allocator_Sharp::Util::Xml::CNode_____::_Buynode0_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
  throw;
}

```

## disassembly

```asm
0x1400142de  mov     [rsp+arg_8], rdx
0x1400142e3  push    rbp
0x1400142e4  sub     rsp, 20h
0x1400142e8  mov     rbp, rdx
0x1400142eb  mov     rcx, [rbp+30h]; Block
0x1400142ef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400142f4  xor     edx, edx; pThrowInfo
0x1400142f6  xor     ecx, ecx; pExceptionObject
0x1400142f8  call    _CxxThrowException_0
```
