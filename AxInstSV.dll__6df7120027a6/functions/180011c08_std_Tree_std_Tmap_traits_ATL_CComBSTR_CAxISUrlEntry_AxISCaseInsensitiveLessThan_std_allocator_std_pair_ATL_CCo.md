# std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::~_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>(void)

- ea: `0x180011c08`
- end: `0x180011c32`
- name: `??1?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011c74`

## callees

- `0x180002774`
- `0x180011ab0`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::~_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>(
        void **a1)
{
  std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(
    (__int64)a1,
    (__int64)a1,
    *((__int64 **)*a1 + 1));
  std::_Deallocate<16>(*a1, 0x30u);
}

```

## disassembly

```asm
0x180011c08  push    rbx
0x180011c0a  sub     rsp, 20h
0x180011c0e  mov     r8, [rcx]
0x180011c11  mov     rdx, rcx
0x180011c14  mov     rbx, rcx
0x180011c17  mov     r8, [r8+8]
0x180011c1b  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>> &,std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)
0x180011c20  mov     rcx, [rbx]
0x180011c23  mov     edx, 30h ; '0'
0x180011c28  add     rsp, 20h
0x180011c2c  pop     rbx
0x180011c2d  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
