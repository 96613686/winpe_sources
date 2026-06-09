# std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>> &,std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)

- ea: `0x180011ab0`
- end: `0x180011aff`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@1@@Z`
- size: `79`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011ab0`
- `0x180011c08`
- `0x180012034`

## callees

- `0x180011ab0`
- `0x180011b8c`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *i; // rbx
  __int64 *v6; // rdx
  __int64 v7; // rcx
  __int64 result; // rax

  for ( i = a3;
        !*((_BYTE *)i + 25);
        result = std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(
                   v7,
                   v6) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(
      a1,
      a2,
      i[2]);
    v6 = i;
    i = (__int64 *)*i;
  }
  return result;
}

```

## disassembly

```asm
0x180011ab0  mov     [rsp+arg_0], rbx
0x180011ab5  mov     [rsp+arg_8], rsi
0x180011aba  push    rdi
0x180011abb  sub     rsp, 20h
0x180011abf  cmp     byte ptr [r8+19h], 0
0x180011ac4  mov     rbx, r8
0x180011ac7  mov     rdi, rdx
0x180011aca  mov     rsi, rcx
0x180011acd  jnz     short loc_180011AEF
0x180011acf  mov     r8, [rbx+10h]
0x180011ad3  mov     rdx, rdi
0x180011ad6  mov     rcx, rsi
0x180011ad9  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>> &,std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)
0x180011ade  mov     rdx, rbx
0x180011ae1  mov     rbx, [rbx]
0x180011ae4  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>> &,std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *)
0x180011ae9  cmp     byte ptr [rbx+19h], 0
0x180011aed  jz      short loc_180011ACF
0x180011aef  mov     rbx, [rsp+28h+arg_0]
0x180011af4  mov     rsi, [rsp+28h+arg_8]
0x180011af9  add     rsp, 20h
0x180011afd  pop     rdi
0x180011afe  retn
```
