# _std::vector_std::shared_ptr_CConfigSet__std::allocator_std::shared_ptr_CConfigSet_____::_Reallocate_::_1_::catch$0

- ea: `0x180011a18`
- end: `0x180011a38`
- name: `_std::vector_std::shared_ptr_CConfigSet__std::allocator_std::shared_ptr_CConfigSet_____::_Reallocate_::_1_::catch$0`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000a64c`
- `0x180010e2c`

## pseudocode

```c
void __fastcall __noreturn std::vector_std::shared_ptr_CConfigSet__std::allocator_std::shared_ptr_CConfigSet_____::_Reallocate_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(a1, *(void **)(a2 + 104));
  throw;
}

```

## disassembly

```asm
0x180011a18  mov     [rsp+arg_8], rdx
0x180011a1d  push    rbp
0x180011a1e  sub     rsp, 30h
0x180011a22  mov     rbp, rdx
0x180011a25  mov     rdx, [rbp+68h]
0x180011a29  call    ?deallocate@?$_Wrap_alloc@V?$allocator@E@std@@@std@@QEAAXPEAE_K@Z; std::_Wrap_alloc<std::allocator<uchar>>::deallocate(uchar *,unsigned __int64)
0x180011a2e  xor     edx, edx; pThrowInfo
0x180011a30  xor     ecx, ecx; pExceptionObject
0x180011a32  call    _CxxThrowException_0
```
