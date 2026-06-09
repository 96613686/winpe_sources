# std::_List_buy<Sharp::Util::Xml::CNode,std::allocator<Sharp::Util::Xml::CNode>>::_List_buy<Sharp::Util::Xml::CNode,std::allocator<Sharp::Util::Xml::CNode>>(std::allocator<Sharp::Util::Xml::CNode> const &)

- ea: `0x140011f68`
- end: `0x140011f9a`
- name: `??0?$_List_buy@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAA@AEBV?$allocator@VCNode@Xml@Util@Sharp@@@1@@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140013524`

## callees

- `0x1400134a0`

## pseudocode

```c
_QWORD *__fastcall std::_List_buy<Sharp::Util::Xml::CNode>::_List_buy<Sharp::Util::Xml::CNode>(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  *a1 = std::_List_alloc<0,std::_List_base_types<Sharp::Util::Xml::CNode>>::_Buynode0(a1, 0, 0);
  return a1;
}

```

## disassembly

```asm
0x140011f68  mov     [rsp+arg_0], rcx
0x140011f6d  push    rbx
0x140011f6e  sub     rsp, 20h
0x140011f72  mov     rbx, rcx
0x140011f75  mov     qword ptr [rcx], 0
0x140011f7c  mov     qword ptr [rcx+8], 0
0x140011f84  xor     r8d, r8d
0x140011f87  xor     edx, edx
0x140011f89  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@@std@@QEAAPEAU?$_List_node@VCNode@Xml@Util@Sharp@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Sharp::Util::Xml::CNode>>::_Buynode0(std::_List_node<Sharp::Util::Xml::CNode,void *> *,std::_List_node<Sharp::Util::Xml::CNode,void *> *)
0x140011f8e  mov     [rbx], rax
0x140011f91  mov     rax, rbx
0x140011f94  add     rsp, 20h
0x140011f98  pop     rbx
0x140011f99  retn
```
