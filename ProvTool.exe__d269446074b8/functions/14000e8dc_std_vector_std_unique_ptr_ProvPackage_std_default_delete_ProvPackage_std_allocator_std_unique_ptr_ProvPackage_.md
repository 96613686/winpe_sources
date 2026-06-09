# _std::vector_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage____std::allocator_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage_______::_Reallocate_::_1_::catch$0

- ea: `0x14000e8dc`
- end: `0x14000e8fc`
- name: `_std::vector_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage____std::allocator_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage_______::_Reallocate_::_1_::catch$0`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000904c`
- `0x14000dd7c`

## pseudocode

```c
void __fastcall __noreturn std::vector_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage____std::allocator_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage_______::_Reallocate_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(a1, *(_QWORD *)(a2 + 104));
  throw;
}

```

## disassembly

```asm
0x14000e8dc  mov     [rsp+arg_8], rdx
0x14000e8e1  push    rbp
0x14000e8e2  sub     rsp, 30h
0x14000e8e6  mov     rbp, rdx
0x14000e8e9  mov     rdx, [rbp+68h]
0x14000e8ed  call    ?deallocate@?$_Wrap_alloc@V?$allocator@G@std@@@std@@QEAAXPEAG_K@Z; std::_Wrap_alloc<std::allocator<ushort>>::deallocate(ushort *,unsigned __int64)
0x14000e8f2  xor     edx, edx; pThrowInfo
0x14000e8f4  xor     ecx, ecx; pExceptionObject
0x14000e8f6  call    _CxxThrowException_0
```
