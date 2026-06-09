# std::list<Sharp::Util::Xml::CNode,std::allocator<Sharp::Util::Xml::CNode>>::list<Sharp::Util::Xml::CNode,std::allocator<Sharp::Util::Xml::CNode>>(void)

- ea: `0x140013524`
- end: `0x140013540`
- name: `??0?$list@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140013548`
- `0x140013808`

## callees

- `0x140011f68`

## pseudocode

```c
_QWORD *__fastcall std::list<Sharp::Util::Xml::CNode>::list<Sharp::Util::Xml::CNode>(_QWORD *a1)
{
  std::_List_buy<Sharp::Util::Xml::CNode>::_List_buy<Sharp::Util::Xml::CNode>(a1);
  return a1;
}

```

## disassembly

```asm
0x140013524  mov     [rsp+arg_0], rcx
0x140013529  push    rbx
0x14001352a  sub     rsp, 20h
0x14001352e  mov     rbx, rcx
0x140013531  call    ??0?$_List_buy@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAA@AEBV?$allocator@VCNode@Xml@Util@Sharp@@@1@@Z; std::_List_buy<Sharp::Util::Xml::CNode>::_List_buy<Sharp::Util::Xml::CNode>(std::allocator<Sharp::Util::Xml::CNode> const &)
0x140013536  nop
0x140013537  mov     rax, rbx
0x14001353a  add     rsp, 20h
0x14001353e  pop     rbx
0x14001353f  retn
```
