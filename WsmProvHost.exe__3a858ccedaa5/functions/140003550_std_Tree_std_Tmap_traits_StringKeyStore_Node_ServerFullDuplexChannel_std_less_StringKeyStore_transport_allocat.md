# std::_Tree<std::_Tmap_traits<StringKeyStore,Node<ServerFullDuplexChannel *>,std::less<StringKeyStore>,transport_allocator<std::pair<StringKeyStore,Node<ServerFullDuplexChannel *>>>,0>>::_Erase(std::_Tree_node<std::pair<StringKeyStore const,Node<ServerFullDuplexChannel *>>,void *> *)

- ea: `0x140003550`
- end: `0x1400035b3`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@VStringKeyStore@@U?$Node@PEAVServerFullDuplexChannel@@@@U?$less@VStringKeyStore@@@std@@V?$transport_allocator@U?$pair@VStringKeyStore@@U?$Node@PEAVServerFullDuplexChannel@@@@@std@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBVStringKeyStore@@U?$Node@PEAVServerFullDuplexChannel@@@@@std@@PEAX@2@@Z`
- size: `99`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002ca0`
- `0x140003550`

## callees

- `0x140003550`

## import_xrefs

- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140003588`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140003594`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140003588`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140003594`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<StringKeyStore,Node<ServerFullDuplexChannel *>,std::less<StringKeyStore>,transport_allocator<std::pair<StringKeyStore,Node<ServerFullDuplexChannel *>>>,0>>::_Erase(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v2; // rbx
  _QWORD *i; // rdi
  void *v5; // rcx

  v2 = a2;
  for ( i = a2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<StringKeyStore,Node<ServerFullDuplexChannel *>,std::less<StringKeyStore>,transport_allocator<std::pair<StringKeyStore,Node<ServerFullDuplexChannel *>>>,0>>::_Erase(
      a1,
      i[2]);
    i = (_QWORD *)*i;
    v5 = (void *)v2[4];
    if ( v5 )
      WSManMemory::Free(v5, 0);
    WSManMemory::Free(v2, 0);
  }
}

```

## disassembly

```asm
0x140003550  mov     [rsp+arg_0], rbx
0x140003555  mov     [rsp+arg_8], rsi
0x14000355a  push    rdi
0x14000355b  sub     rsp, 20h
0x14000355f  mov     rbx, rdx
0x140003562  mov     rsi, rcx
0x140003565  mov     rdi, rdx
0x140003568  cmp     byte ptr [rdx+19h], 0
0x14000356c  jnz     short loc_1400035A3
0x14000356e  mov     rdx, [rdi+10h]
0x140003572  mov     rcx, rsi
0x140003575  call    ?_Erase@?$_Tree@V?$_Tmap_traits@VStringKeyStore@@U?$Node@PEAVServerFullDuplexChannel@@@@U?$less@VStringKeyStore@@@std@@V?$transport_allocator@U?$pair@VStringKeyStore@@U?$Node@PEAVServerFullDuplexChannel@@@@@std@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBVStringKeyStore@@U?$Node@PEAVServerFullDuplexChannel@@@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<StringKeyStore,Node<ServerFullDuplexChannel *>,std::less<StringKeyStore>,transport_allocator<std::pair<StringKeyStore,Node<ServerFullDuplexChannel *>>>,0>>::_Erase(std::_Tree_node<std::pair<StringKeyStore const,Node<ServerFullDuplexChannel *>>,void *> *)
0x14000357a  mov     rdi, [rdi]
0x14000357d  mov     rcx, [rbx+20h]
0x140003581  test    rcx, rcx
0x140003584  jz      short loc_14000358F
0x140003586  xor     edx, edx
0x140003588  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x14000358e  nop
0x14000358f  xor     edx, edx
0x140003591  mov     rcx, rbx
0x140003594  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x14000359a  mov     rbx, rdi
0x14000359d  cmp     byte ptr [rdi+19h], 0
0x1400035a1  jz      short loc_14000356E
0x1400035a3  mov     rbx, [rsp+28h+arg_0]
0x1400035a8  mov     rsi, [rsp+28h+arg_8]
0x1400035ad  add     rsp, 20h
0x1400035b1  pop     rdi
0x1400035b2  retn
```
