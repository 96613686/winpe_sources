# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(void)

- ea: `0x180011c38`
- end: `0x180011c61`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800119a4`

## callees

- `0x180011be4`
- `0x180011c38`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011c4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c4e`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    SysFreeString(*(BSTR *)(v2 + 32));
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(a1);
}

```

## disassembly

```asm
0x180011c38  push    rbx
0x180011c3a  sub     rsp, 20h
0x180011c3e  mov     rbx, rcx
0x180011c41  mov     rcx, [rcx+8]
0x180011c45  test    rcx, rcx
0x180011c48  jz      short loc_180011C54
0x180011c4a  mov     rcx, [rcx+20h]; bstrString
0x180011c4e  call    cs:__imp_SysFreeString
0x180011c54  mov     rcx, rbx
0x180011c57  add     rsp, 20h
0x180011c5b  pop     rbx
0x180011c5c  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(void)
```
