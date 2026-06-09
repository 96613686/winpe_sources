# std::_Tree<std::_Tmap_traits<StringKeyStore,Node<ServerFullDuplexChannel *>,std::less<StringKeyStore>,transport_allocator<std::pair<StringKeyStore,Node<ServerFullDuplexChannel *>>>,0>>::~_Tree<std::_Tmap_traits<StringKeyStore,Node<ServerFullDuplexChannel *>,std::less<StringKeyStore>,transport_allocator<std::pair<StringKeyStore,Node<ServerFullDuplexChannel *>>>,0>>(void)

- ea: `0x140002ca0`
- end: `0x140002d2f`
- name: `??1?$_Tree@V?$_Tmap_traits@VStringKeyStore@@U?$Node@PEAVServerFullDuplexChannel@@@@U?$less@VStringKeyStore@@@std@@V?$transport_allocator@U?$pair@VStringKeyStore@@U?$Node@PEAVServerFullDuplexChannel@@@@@std@@@@$0A@@std@@@std@@QEAA@XZ`
- size: `143`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002eb0`

## callees

- `0x140002ca0`
- `0x140003550`

## import_xrefs

- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002cdc`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002ce8`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002d18`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002cdc`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002ce8`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002d18`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<StringKeyStore,Node<ServerFullDuplexChannel *>,std::less<StringKeyStore>,transport_allocator<std::pair<StringKeyStore,Node<ServerFullDuplexChannel *>>>,0>>::~_Tree<std::_Tmap_traits<StringKeyStore,Node<ServerFullDuplexChannel *>,std::less<StringKeyStore>,transport_allocator<std::pair<StringKeyStore,Node<ServerFullDuplexChannel *>>>,0>>(
        void **a1)
{
  _QWORD *v2; // rdi
  _QWORD *i; // rsi
  void *v4; // rcx

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  for ( i = v2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<StringKeyStore,Node<ServerFullDuplexChannel *>,std::less<StringKeyStore>,transport_allocator<std::pair<StringKeyStore,Node<ServerFullDuplexChannel *>>>,0>>::_Erase(
      a1,
      i[2]);
    i = (_QWORD *)*i;
    v4 = (void *)v2[4];
    if ( v4 )
      WSManMemory::Free(v4, 0);
    WSManMemory::Free(v2, 0);
  }
  *((_QWORD *)*a1 + 1) = *a1;
  *(_QWORD *)*a1 = *a1;
  *((_QWORD *)*a1 + 2) = *a1;
  a1[1] = 0;
  WSManMemory::Free(*a1, 0);
}

```

## disassembly

```asm
0x140002ca0  mov     [rsp+arg_0], rbx
0x140002ca5  mov     [rsp+arg_8], rsi
0x140002caa  push    rdi
0x140002cab  sub     rsp, 20h
0x140002caf  mov     rbx, rcx
0x140002cb2  mov     rax, [rcx]
0x140002cb5  mov     rdi, [rax+8]
0x140002cb9  mov     rsi, rdi
0x140002cbc  cmp     byte ptr [rdi+19h], 0
0x140002cc0  jnz     short loc_140002CF7
0x140002cc2  mov     rdx, [rsi+10h]
0x140002cc6  mov     rcx, rbx
0x140002cc9  call    ?_Erase@?$_Tree@V?$_Tmap_traits@VStringKeyStore@@U?$Node@PEAVServerFullDuplexChannel@@@@U?$less@VStringKeyStore@@@std@@V?$transport_allocator@U?$pair@VStringKeyStore@@U?$Node@PEAVServerFullDuplexChannel@@@@@std@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBVStringKeyStore@@U?$Node@PEAVServerFullDuplexChannel@@@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<StringKeyStore,Node<ServerFullDuplexChannel *>,std::less<StringKeyStore>,transport_allocator<std::pair<StringKeyStore,Node<ServerFullDuplexChannel *>>>,0>>::_Erase(std::_Tree_node<std::pair<StringKeyStore const,Node<ServerFullDuplexChannel *>>,void *> *)
0x140002cce  mov     rsi, [rsi]
0x140002cd1  mov     rcx, [rdi+20h]
0x140002cd5  test    rcx, rcx
0x140002cd8  jz      short loc_140002CE3
0x140002cda  xor     edx, edx
0x140002cdc  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x140002ce2  nop
0x140002ce3  xor     edx, edx
0x140002ce5  mov     rcx, rdi
0x140002ce8  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x140002cee  mov     rdi, rsi
0x140002cf1  cmp     byte ptr [rsi+19h], 0
0x140002cf5  jz      short loc_140002CC2
0x140002cf7  mov     rax, [rbx]
0x140002cfa  mov     [rax+8], rax
0x140002cfe  mov     rax, [rbx]
0x140002d01  mov     [rax], rax
0x140002d04  mov     rax, [rbx]
0x140002d07  mov     [rax+10h], rax
0x140002d0b  mov     qword ptr [rbx+8], 0
0x140002d13  xor     edx, edx
0x140002d15  mov     rcx, [rbx]
0x140002d18  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x140002d1e  nop
0x140002d1f  mov     rbx, [rsp+28h+arg_0]
0x140002d24  mov     rsi, [rsp+28h+arg_8]
0x140002d29  add     rsp, 20h
0x140002d2d  pop     rdi
0x140002d2e  retn
```
