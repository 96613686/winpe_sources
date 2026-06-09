# std::_Tree<std::_Tmap_traits<IOperation *,Node<Empty>,std::less<IOperation *>,transport_allocator<std::pair<IOperation *,Node<Empty>>>,0>>::~_Tree<std::_Tmap_traits<IOperation *,Node<Empty>,std::less<IOperation *>,transport_allocator<std::pair<IOperation *,Node<Empty>>>,0>>(void)

- ea: `0x140002c1c`
- end: `0x140002c99`
- name: `??1?$_Tree@V?$_Tmap_traits@PEAVIOperation@@U?$Node@UEmpty@@@@U?$less@PEAVIOperation@@@std@@V?$transport_allocator@U?$pair@PEAVIOperation@@U?$Node@UEmpty@@@@@std@@@@$0A@@std@@@std@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002ab0`
- `0x140002b00`
- `0x140002e40`

## callees

- `0x140002c1c`
- `0x1400034f8`

## import_xrefs

- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002c52`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002c82`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002c52`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002c82`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<IOperation *,Node<Empty>,std::less<IOperation *>,transport_allocator<std::pair<IOperation *,Node<Empty>>>,0>>::~_Tree<std::_Tmap_traits<IOperation *,Node<Empty>,std::less<IOperation *>,transport_allocator<std::pair<IOperation *,Node<Empty>>>,0>>(
        void **a1)
{
  _QWORD *v2; // rdi
  _QWORD *i; // rsi

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  for ( i = v2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<PluginKey,Node<unsigned long>,std::less<PluginKey>,transport_allocator<std::pair<PluginKey,Node<unsigned long>>>,0>>::_Erase(
      a1,
      i[2]);
    i = (_QWORD *)*i;
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
0x140002c1c  mov     [rsp+arg_0], rbx
0x140002c21  mov     [rsp+arg_8], rsi
0x140002c26  push    rdi
0x140002c27  sub     rsp, 20h
0x140002c2b  mov     rbx, rcx
0x140002c2e  mov     rax, [rcx]
0x140002c31  mov     rdi, [rax+8]
0x140002c35  mov     rsi, rdi
0x140002c38  cmp     byte ptr [rdi+19h], 0
0x140002c3c  jnz     short loc_140002C61
0x140002c3e  mov     rdx, [rsi+10h]
0x140002c42  mov     rcx, rbx
0x140002c45  call    ?_Erase@?$_Tree@V?$_Tmap_traits@UPluginKey@@U?$Node@K@@U?$less@UPluginKey@@@std@@V?$transport_allocator@U?$pair@UPluginKey@@U?$Node@K@@@std@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBUPluginKey@@U?$Node@K@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<PluginKey,Node<ulong>,std::less<PluginKey>,transport_allocator<std::pair<PluginKey,Node<ulong>>>,0>>::_Erase(std::_Tree_node<std::pair<PluginKey const,Node<ulong>>,void *> *)
0x140002c4a  mov     rsi, [rsi]
0x140002c4d  xor     edx, edx
0x140002c4f  mov     rcx, rdi
0x140002c52  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x140002c58  mov     rdi, rsi
0x140002c5b  cmp     byte ptr [rsi+19h], 0
0x140002c5f  jz      short loc_140002C3E
0x140002c61  mov     rax, [rbx]
0x140002c64  mov     [rax+8], rax
0x140002c68  mov     rax, [rbx]
0x140002c6b  mov     [rax], rax
0x140002c6e  mov     rax, [rbx]
0x140002c71  mov     [rax+10h], rax
0x140002c75  mov     qword ptr [rbx+8], 0
0x140002c7d  xor     edx, edx
0x140002c7f  mov     rcx, [rbx]
0x140002c82  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x140002c88  nop
0x140002c89  mov     rbx, [rsp+28h+arg_0]
0x140002c8e  mov     rsi, [rsp+28h+arg_8]
0x140002c93  add     rsp, 20h
0x140002c97  pop     rdi
0x140002c98  retn
```
