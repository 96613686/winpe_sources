# std::allocator<std::_Tree_nod<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::_Node>::deallocate(std::_Tree_nod<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::_Node *,unsigned __int64)

- ea: `0x18000c3dc`
- end: `0x18000c3ef`
- name: `?deallocate@?$allocator@U_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@@std@@@2@$00@std@@@std@@@std@@QEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@URpcHandleInfo@@@std@@@2@$00@std@@@2@_K@Z`
- size: `19`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fcbe`
- `0x18000fce4`
- `0x18000fdb8`
- `0x18000fe09`

## import_xrefs

- `msvcrt!free` at `0x18000c3e3`
- `msvcrt!free` at `0x18000c3e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::allocator<std::_Tree_nod<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::_Node>::deallocate(
        __int64 a1,
        void *a2)
{
  free(a2);
}

```

## disassembly

```asm
0x18000c3dc  sub     rsp, 28h
0x18000c3e0  mov     rcx, rdx; Block
0x18000c3e3  call    cs:__imp_free
0x18000c3e9  nop
0x18000c3ea  add     rsp, 28h
0x18000c3ee  retn
```
