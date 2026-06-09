# std::_Alloc_construct_ptr<std::allocator<std::_List_node<CThread *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<CThread *,void *>>>(void)

- ea: `0x18000698c`
- end: `0x1800069a8`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAVCThread@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a493`

## callees

- `0x1800019e0`
- `0x18000698c`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<CThread *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<CThread *,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000698c  sub     rsp, 28h
0x180006990  mov     rcx, [rcx+8]; void *
0x180006994  test    rcx, rcx
0x180006997  jz      short loc_1800069A3
0x180006999  mov     edx, 18h; unsigned __int64
0x18000699e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800069a3  add     rsp, 28h
0x1800069a7  retn
```
