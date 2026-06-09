# std::_Alloc_construct_ptr<std::allocator<std::_List_node<ATL::CComBSTR,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<ATL::CComBSTR,void *>>>(void)

- ea: `0x1400107e4`
- end: `0x140010800`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@VCComBSTR@ATL@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140015994`

## callees

- `0x1400107e4`
- `0x14001382c`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<ATL::CComBSTR,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<ATL::CComBSTR,void *>>>(
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
0x1400107e4  sub     rsp, 28h
0x1400107e8  mov     rcx, [rcx+8]; Block
0x1400107ec  test    rcx, rcx
0x1400107ef  jz      short loc_1400107FB
0x1400107f1  mov     edx, 18h
0x1400107f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400107fb  add     rsp, 28h
0x1400107ff  retn
```
