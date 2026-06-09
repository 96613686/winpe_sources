# _dynamic_atexit_destructor_for__RegistryManager::s_defaultRedirectionMap__

- ea: `0x140007650`
- end: `0x1400076aa`
- name: `_dynamic_atexit_destructor_for__RegistryManager::s_defaultRedirectionMap__`
- size: `90`
- prototype: `void()`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140001714`
- `0x140006314`
- `0x140007650`

## pseudocode

```c
void dynamic_atexit_destructor_for__RegistryManager::s_defaultRedirectionMap__()
{
  void *v0; // rcx
  _QWORD *v1; // rbx
  void *v2; // rcx

  v0 = RegistryManager::s_defaultRedirectionMap;
  v1 = (_QWORD *)*((_QWORD *)RegistryManager::s_defaultRedirectionMap + 1);
  if ( !*((_BYTE *)v1 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,unsigned short const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,unsigned short const *>,void *>>>(
        (__int64)&RegistryManager::s_defaultRedirectionMap,
        (__int64)&RegistryManager::s_defaultRedirectionMap,
        v1[2]);
      v2 = v1;
      v1 = (_QWORD *)*v1;
      operator delete(v2);
    }
    while ( !*((_BYTE *)v1 + 25) );
    v0 = RegistryManager::s_defaultRedirectionMap;
  }
  operator delete(v0);
}

```

## disassembly

```asm
0x140007650  push    rbx
0x140007652  sub     rsp, 20h
0x140007656  mov     rcx, cs:?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A; std::map<ushort const *,ushort const *> RegistryManager::s_defaultRedirectionMap
0x14000765d  mov     rbx, [rcx+8]
0x140007661  cmp     byte ptr [rbx+19h], 0
0x140007665  jnz     short loc_14000769B
0x140007667  mov     r8, [rbx+10h]
0x14000766b  lea     rdx, ?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A; std::map<ushort const *,ushort const *> RegistryManager::s_defaultRedirectionMap
0x140007672  lea     rcx, ?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A; std::map<ushort const *,ushort const *> RegistryManager::s_defaultRedirectionMap
0x140007679  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBG@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBG@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBG@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBG@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,ushort const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,ushort const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,ushort const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,ushort const *>,void *> *)
0x14000767e  mov     rcx, rbx; Block
0x140007681  mov     edx, 30h ; '0'
0x140007686  mov     rbx, [rbx]
0x140007689  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000768e  cmp     byte ptr [rbx+19h], 0
0x140007692  jz      short loc_140007667
0x140007694  mov     rcx, cs:?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A; Block
0x14000769b  mov     edx, 30h ; '0'
0x1400076a0  add     rsp, 20h
0x1400076a4  pop     rbx
0x1400076a5  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
