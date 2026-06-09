# std::_Tree<std::_Tmap_traits<PluginKey,Node<ulong>,std::less<PluginKey>,transport_allocator<std::pair<PluginKey,Node<ulong>>>,0>>::_Erase(std::_Tree_node<std::pair<PluginKey const,Node<ulong>>,void *> *)

- ea: `0x1400034f8`
- end: `0x140003549`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@UPluginKey@@U?$Node@K@@U?$less@UPluginKey@@@std@@V?$transport_allocator@U?$pair@UPluginKey@@U?$Node@K@@@std@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBUPluginKey@@U?$Node@K@@@std@@PEAX@2@@Z`
- size: `81`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140002c1c`
- `0x1400034f8`

## callees

- `0x1400034f8`

## import_xrefs

- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x14000352a`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x14000352a`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<PluginKey,Node<unsigned long>,std::less<PluginKey>,transport_allocator<std::pair<PluginKey,Node<unsigned long>>>,0>>::_Erase(
        __int64 a1,
        void *a2)
{
  void *v2; // rbx
  _QWORD *v4; // rdi

  v2 = a2;
  v4 = a2;
  if ( !*((_BYTE *)a2 + 25) )
  {
    do
    {
      std::_Tree<std::_Tmap_traits<PluginKey,Node<unsigned long>,std::less<PluginKey>,transport_allocator<std::pair<PluginKey,Node<unsigned long>>>,0>>::_Erase(
        a1,
        v4[2]);
      v4 = (_QWORD *)*v4;
      WSManMemory::Free(v2, 0);
      v2 = v4;
    }
    while ( !*((_BYTE *)v4 + 25) );
  }
}

```

## disassembly

```asm
0x1400034f8  mov     [rsp+arg_0], rbx
0x1400034fd  mov     [rsp+arg_8], rsi
0x140003502  push    rdi
0x140003503  sub     rsp, 20h
0x140003507  cmp     byte ptr [rdx+19h], 0
0x14000350b  mov     rbx, rdx
0x14000350e  mov     rsi, rcx
0x140003511  mov     rdi, rdx
0x140003514  jnz     short loc_140003539
0x140003516  mov     rdx, [rdi+10h]
0x14000351a  mov     rcx, rsi
0x14000351d  call    ?_Erase@?$_Tree@V?$_Tmap_traits@UPluginKey@@U?$Node@K@@U?$less@UPluginKey@@@std@@V?$transport_allocator@U?$pair@UPluginKey@@U?$Node@K@@@std@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBUPluginKey@@U?$Node@K@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<PluginKey,Node<ulong>,std::less<PluginKey>,transport_allocator<std::pair<PluginKey,Node<ulong>>>,0>>::_Erase(std::_Tree_node<std::pair<PluginKey const,Node<ulong>>,void *> *)
0x140003522  mov     rdi, [rdi]
0x140003525  xor     edx, edx
0x140003527  mov     rcx, rbx
0x14000352a  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x140003530  cmp     byte ptr [rdi+19h], 0
0x140003534  mov     rbx, rdi
0x140003537  jz      short loc_140003516
0x140003539  mov     rbx, [rsp+28h+arg_0]
0x14000353e  mov     rsi, [rsp+28h+arg_8]
0x140003543  add     rsp, 20h
0x140003547  pop     rdi
0x140003548  retn
```
