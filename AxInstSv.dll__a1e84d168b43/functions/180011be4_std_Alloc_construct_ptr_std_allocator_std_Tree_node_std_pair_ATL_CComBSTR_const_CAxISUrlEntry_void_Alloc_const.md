# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(void)

- ea: `0x180011be4`
- end: `0x180011c00`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011c38`
- `0x180011c68`
- `0x180014abb`

## callees

- `0x180002774`
- `0x180011be4`

## pseudocode

```c
__int64 __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
    return std::_Deallocate<16>(v1, 48);
  return result;
}

```

## disassembly

```asm
0x180011be4  sub     rsp, 28h
0x180011be8  mov     rcx, [rcx+8]
0x180011bec  test    rcx, rcx
0x180011bef  jz      short loc_180011BFB
0x180011bf1  mov     edx, 30h ; '0'
0x180011bf6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011bfb  add     rsp, 28h
0x180011bff  retn
```
