# std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>::~unique_ptr<CInformationNode,std::default_delete<CInformationNode>>(void)

- ea: `0x18000caa4`
- end: `0x18000cac9`
- name: `??1?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CInformationNode **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001ed57`
- `0x18001ee94`

## callees

- `0x18000caa4`
- `0x180010150`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cabd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cabd`

## pseudocode

```c
void __fastcall std::unique_ptr<CInformationNode>::~unique_ptr<CInformationNode>(CInformationNode **a1)
{
  CInformationNode *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    CInformationNode::~CInformationNode(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000caa4  push    rbx
0x18000caa6  sub     rsp, 20h
0x18000caaa  mov     rbx, [rcx]
0x18000caad  test    rbx, rbx
0x18000cab0  jz      short loc_18000CAC3
0x18000cab2  mov     rcx, rbx; this
0x18000cab5  call    ??1CInformationNode@@QEAA@XZ; CInformationNode::~CInformationNode(void)
0x18000caba  mov     rcx, rbx
0x18000cabd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cac3  add     rsp, 20h
0x18000cac7  pop     rbx
0x18000cac8  retn
```
