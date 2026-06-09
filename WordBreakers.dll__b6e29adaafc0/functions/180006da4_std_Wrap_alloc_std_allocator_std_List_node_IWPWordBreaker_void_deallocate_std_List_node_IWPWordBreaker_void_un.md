# std::_Wrap_alloc<std::allocator<std::_List_node<IWPWordBreaker *,void *>>>::deallocate(std::_List_node<IWPWordBreaker *,void *> *,unsigned __int64)

- ea: `0x180006da4`
- end: `0x180006dae`
- name: `?deallocate@?$_Wrap_alloc@V?$allocator@U?$_List_node@PEAVIWPWordBreaker@@PEAX@std@@@std@@@std@@QEAAXPEAU?$_List_node@PEAVIWPWordBreaker@@PEAX@2@_K@Z`
- size: `10`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000bb19`
- `0x18000bbb7`
- `0x18000bbfd`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006da7`

## pseudocode

```c
void __fastcall std::_Wrap_alloc<std::allocator<std::_List_node<IWPWordBreaker *,void *>>>::deallocate(
        __int64 a1,
        void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x180006da4  mov     rcx, rdx
0x180006da7  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
