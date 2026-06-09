# std::list<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>,std::allocator<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>>>::~list<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>,std::allocator<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>>>(void)

- ea: `0x18000c9c4`
- end: `0x18000ca15`
- name: `??1?$list@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@V?$allocator@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `81`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000cb00`

## callees

- `0x18000c9c4`
- `0x18000dd5c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ca0e`

## pseudocode

```c
void __fastcall std::list<std::unique_ptr<CInformationNode>>::~list<std::unique_ptr<CInformationNode>>(__int64 a1)
{
  _QWORD *v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  v2 = **(_QWORD ***)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  *(_QWORD *)(a1 + 8) = 0;
  v3 = *(_QWORD **)a1;
  if ( v2 != v3 )
  {
    do
    {
      v4 = (_QWORD *)*v2;
      std::_List_buy<std::unique_ptr<CInformationNode>>::_Freenode();
      v3 = *(_QWORD **)a1;
      v2 = v4;
    }
    while ( v4 != *(_QWORD **)a1 );
  }
  operator delete(v3);
}

```

## disassembly

```asm
0x18000c9c4  mov     [rsp+arg_0], rbx
0x18000c9c9  push    rdi
0x18000c9ca  sub     rsp, 20h
0x18000c9ce  mov     rax, [rcx]
0x18000c9d1  mov     rdi, rcx
0x18000c9d4  mov     rdx, [rax]
0x18000c9d7  mov     [rax], rax
0x18000c9da  mov     rax, [rcx]
0x18000c9dd  mov     [rax+8], rax
0x18000c9e1  mov     qword ptr [rcx+8], 0
0x18000c9e9  mov     rcx, [rcx]
0x18000c9ec  cmp     rdx, rcx
0x18000c9ef  jz      short loc_18000CA04
0x18000c9f1  mov     rbx, [rdx]
0x18000c9f4  call    ?_Freenode@?$_List_buy@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@V?$allocator@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@@2@@std@@QEAAXPEAU?$_List_node@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@PEAX@2@@Z; std::_List_buy<std::unique_ptr<CInformationNode>>::_Freenode(std::_List_node<std::unique_ptr<CInformationNode>,void *> *)
0x18000c9f9  mov     rcx, [rdi]
0x18000c9fc  mov     rdx, rbx
0x18000c9ff  cmp     rbx, rcx
0x18000ca02  jnz     short loc_18000C9F1
0x18000ca04  mov     rbx, [rsp+28h+arg_0]
0x18000ca09  add     rsp, 20h
0x18000ca0d  pop     rdi
0x18000ca0e  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
