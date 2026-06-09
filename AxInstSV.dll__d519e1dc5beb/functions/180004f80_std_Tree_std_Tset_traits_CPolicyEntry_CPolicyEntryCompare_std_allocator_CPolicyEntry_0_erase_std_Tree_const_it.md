# std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<CPolicyEntry *>>>)

- ea: `0x180004f80`
- end: `0x180004fc7`
- name: `?erase@?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVCPolicyEntry@@@std@@@std@@@2@V32@@Z`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000383c`
- `0x180003f7c`

## callees

- `0x180002774`
- `0x180002c5c`
- `0x180004afc`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::erase(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v4; // r9
  __int64 **v5; // r10
  __int64 *v6; // rax
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = a3;
  std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(
    &v8,
    (__int64)a2,
    a3,
    a3);
  v6 = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Extract(v5, v4);
  std::_Deallocate<16>(v6, 40);
  *a2 = v8;
  return a2;
}

```

## disassembly

```asm
0x180004f80  push    rbx
0x180004f82  sub     rsp, 20h
0x180004f86  mov     r10, rcx
0x180004f89  mov     [rsp+28h+arg_0], r8
0x180004f8e  lea     rcx, [rsp+28h+arg_0]
0x180004f93  mov     r9, r8
0x180004f96  mov     rbx, rdx
0x180004f99  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(void)
0x180004f9e  mov     rdx, r9
0x180004fa1  mov     rcx, r10
0x180004fa4  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>)
0x180004fa9  mov     edx, 28h ; '('
0x180004fae  mov     rcx, rax
0x180004fb1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180004fb6  mov     rax, [rsp+28h+arg_0]
0x180004fbb  mov     [rbx], rax
0x180004fbe  mov     rax, rbx
0x180004fc1  add     rsp, 20h
0x180004fc5  pop     rbx
0x180004fc6  retn
```
