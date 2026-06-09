# _std::_List_alloc_0_std::_List_base_types_std::unique_ptr_CInformationNode_std::default_delete_CInformationNode____std::allocator_std::unique_ptr_CInformationNode_std::default_delete_CInformationNode_________::_Buynode0_::_1_::catch$0

- ea: `0x18001ecf0`
- end: `0x18001ed11`
- name: `_std::_List_alloc_0_std::_List_base_types_std::unique_ptr_CInformationNode_std::default_delete_CInformationNode____std::allocator_std::unique_ptr_CInformationNode_std::default_delete_CInformationNode_________::_Buynode0_::_1_::catch$0`
- size: `33`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001f0c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ed01`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ed01`

## pseudocode

```c
void __fastcall __noreturn std::_List_alloc_0_std::_List_base_types_std::unique_ptr_CInformationNode_std::default_delete_CInformationNode____std::allocator_std::unique_ptr_CInformationNode_std::default_delete_CInformationNode_________::_Buynode0_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
  throw;
}

```

## disassembly

```asm
0x18001ecf0  mov     [rsp+arg_8], rdx
0x18001ecf5  push    rbp
0x18001ecf6  sub     rsp, 20h
0x18001ecfa  mov     rbp, rdx
0x18001ecfd  mov     rcx, [rbp+30h]
0x18001ed01  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ed07  xor     edx, edx; pThrowInfo
0x18001ed09  xor     ecx, ecx; pExceptionObject
0x18001ed0b  call    _CxxThrowException_0
```
