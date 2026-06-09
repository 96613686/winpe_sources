# std::_List_buy<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>,std::allocator<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>>>::_Freenode(std::_List_node<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>,void *> *)

- ea: `0x18000dd5c`
- end: `0x18000dd97`
- name: `?_Freenode@?$_List_buy@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@V?$allocator@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@@2@@std@@QEAAXPEAU?$_List_node@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@PEAX@2@@Z`
- size: `59`
- prototype: `void __fastcall(__int64, CInformationNode **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c9c4`
- `0x18000d604`
- `0x18000d754`

## callees

- `0x18000dd5c`
- `0x180010150`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000dd7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dd7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dd90`

## pseudocode

```c
void __fastcall std::_List_buy<std::unique_ptr<CInformationNode>>::_Freenode(__int64 a1, CInformationNode **a2)
{
  CInformationNode *v2; // rbx

  v2 = a2[2];
  if ( v2 )
  {
    CInformationNode::~CInformationNode(a2[2]);
    operator delete(v2);
  }
  operator delete(a2);
}

```

## disassembly

```asm
0x18000dd5c  mov     [rsp+arg_0], rbx
0x18000dd61  push    rdi
0x18000dd62  sub     rsp, 20h
0x18000dd66  mov     rbx, [rdx+10h]
0x18000dd6a  mov     rdi, rdx
0x18000dd6d  test    rbx, rbx
0x18000dd70  jz      short loc_18000DD83
0x18000dd72  mov     rcx, rbx; this
0x18000dd75  call    ??1CInformationNode@@QEAA@XZ; CInformationNode::~CInformationNode(void)
0x18000dd7a  mov     rcx, rbx
0x18000dd7d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000dd83  mov     rcx, rdi
0x18000dd86  mov     rbx, [rsp+28h+arg_0]
0x18000dd8b  add     rsp, 20h
0x18000dd8f  pop     rdi
0x18000dd90  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
