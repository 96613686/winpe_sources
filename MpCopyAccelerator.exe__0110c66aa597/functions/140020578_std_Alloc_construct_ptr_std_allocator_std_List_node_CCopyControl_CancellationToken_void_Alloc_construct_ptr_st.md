# std::_Alloc_construct_ptr<std::allocator<std::_List_node<CCopyControl::CancellationToken *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<CCopyControl::CancellationToken *,void *>>>(void)

- ea: `0x140020578`
- end: `0x140020594`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAUCancellationToken@CCopyControl@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400262ff`

## callees

- `0x140005c40`
- `0x140020578`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<CCopyControl::CancellationToken *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<CCopyControl::CancellationToken *,void *>>>(
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
0x140020578  sub     rsp, 28h
0x14002057c  mov     rcx, [rcx+8]; void *
0x140020580  test    rcx, rcx
0x140020583  jz      short loc_14002058F
0x140020585  mov     edx, 18h; unsigned __int64
0x14002058a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002058f  add     rsp, 28h
0x140020593  retn
```
