# Sharp::Util::Xml::CNodeCollection::Add(Sharp::Util::Xml::CNode)

- ea: `0x1400137d8`
- end: `0x140013802`
- name: `?Add@CNodeCollection@Xml@Util@Sharp@@QEAAXVCNode@234@@Z`
- size: `42`
- prototype: `void __fastcall(__int64, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140013548`
- `0x140013808`

## callees

- `0x140011f00`
- `0x140012138`

## pseudocode

```c
void __fastcall Sharp::Util::Xml::CNodeCollection::Add(__int64 a1, const struct Sharp::Util::Xml::CNode *a2)
{
  std::list<Sharp::Util::Xml::CNode>::_Insert<Sharp::Util::Xml::CNode const &>(a1 + 8, *(_QWORD *)(a1 + 8), a2);
  Sharp::Util::Xml::CNode::~CNode(a2);
}

```

## disassembly

```asm
0x1400137d8  mov     [rsp+arg_8], rdx
0x1400137dd  push    rbx
0x1400137de  sub     rsp, 20h
0x1400137e2  mov     rbx, rdx
0x1400137e5  add     rcx, 8
0x1400137e9  mov     r8, rdx
0x1400137ec  mov     rdx, [rcx]
0x1400137ef  call    ??$_Insert@AEBVCNode@Xml@Util@Sharp@@@?$list@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@VCNode@Xml@Util@Sharp@@@std@@@std@@U_Iterator_base0@2@@1@AEBVCNode@Xml@Util@Sharp@@@Z; std::list<Sharp::Util::Xml::CNode>::_Insert<Sharp::Util::Xml::CNode const &>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Sharp::Util::Xml::CNode>>,std::_Iterator_base0>,Sharp::Util::Xml::CNode const &)
0x1400137f4  nop
0x1400137f5  mov     rcx, rbx; this
0x1400137f8  add     rsp, 20h
0x1400137fc  pop     rbx
0x1400137fd  jmp     ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
```
