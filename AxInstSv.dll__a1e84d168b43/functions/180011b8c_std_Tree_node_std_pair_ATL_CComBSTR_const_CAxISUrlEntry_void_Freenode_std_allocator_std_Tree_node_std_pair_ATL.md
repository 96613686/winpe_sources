# std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>> &,std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)

- ea: `0x180011b8c`
- end: `0x180011bb1`
- name: `??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@1@PEAU01@@Z`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011ab0`
- `0x180012034`

## callees

- `0x180002774`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011b99`
- `OLEAUT32!__imp_SysFreeString` at `0x180011b99`

## pseudocode

```c
__int64 __fastcall std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(
        __int64 a1,
        __int64 a2)
{
  SysFreeString(*(BSTR *)(a2 + 32));
  return std::_Deallocate<16>(a2, 48);
}

```

## disassembly

```asm
0x180011b8c  push    rbx
0x180011b8e  sub     rsp, 20h
0x180011b92  mov     rcx, [rdx+20h]; bstrString
0x180011b96  mov     rbx, rdx
0x180011b99  call    cs:__imp_SysFreeString
0x180011b9f  mov     edx, 30h ; '0'
0x180011ba4  mov     rcx, rbx
0x180011ba7  add     rsp, 20h
0x180011bab  pop     rbx
0x180011bac  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
