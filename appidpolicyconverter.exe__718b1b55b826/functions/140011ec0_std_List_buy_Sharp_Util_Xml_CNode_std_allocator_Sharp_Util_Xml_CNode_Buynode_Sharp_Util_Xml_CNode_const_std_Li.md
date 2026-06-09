# std::_List_buy<Sharp::Util::Xml::CNode,std::allocator<Sharp::Util::Xml::CNode>>::_Buynode<Sharp::Util::Xml::CNode const &>(std::_List_node<Sharp::Util::Xml::CNode,void *> *,std::_List_node<Sharp::Util::Xml::CNode,void *> *,Sharp::Util::Xml::CNode const &)

- ea: `0x140011ec0`
- end: `0x140011efa`
- name: `??$_Buynode@AEBVCNode@Xml@Util@Sharp@@@?$_List_buy@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAAPEAU?$_List_node@VCNode@Xml@Util@Sharp@@PEAX@1@PEAU21@0AEBVCNode@Xml@Util@Sharp@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140011f00`

## callees

- `0x140011974`
- `0x1400134a0`

## pseudocode

```c
__int64 __fastcall std::_List_buy<Sharp::Util::Xml::CNode>::_Buynode<Sharp::Util::Xml::CNode const &>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const struct Sharp::Util::Xml::CNode *a4)
{
  __int64 v6; // [rsp+30h] [rbp+8h]

  v6 = std::_List_alloc<0,std::_List_base_types<Sharp::Util::Xml::CNode>>::_Buynode0();
  Sharp::Util::Xml::CNode::CNode((Sharp::Util::Xml::CNode *)(v6 + 16), a4);
  return v6;
}

```

## disassembly

```asm
0x140011ec0  mov     [rsp+arg_8], rbx
0x140011ec5  mov     [rsp+arg_0], rcx
0x140011eca  push    rdi
0x140011ecb  sub     rsp, 20h
0x140011ecf  mov     rdi, r9
0x140011ed2  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@@std@@QEAAPEAU?$_List_node@VCNode@Xml@Util@Sharp@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Sharp::Util::Xml::CNode>>::_Buynode0(std::_List_node<Sharp::Util::Xml::CNode,void *> *,std::_List_node<Sharp::Util::Xml::CNode,void *> *)
0x140011ed7  mov     rbx, rax
0x140011eda  mov     [rsp+28h+arg_0], rax
0x140011edf  lea     rcx, [rax+10h]; this
0x140011ee3  mov     rdx, rdi; struct Sharp::Util::Xml::CNode *
0x140011ee6  call    ??0CNode@Xml@Util@Sharp@@QEAA@AEBV0123@@Z; Sharp::Util::Xml::CNode::CNode(Sharp::Util::Xml::CNode const &)
0x140011eeb  nop
0x140011eec  mov     rax, rbx
0x140011eef  mov     rbx, [rsp+28h+arg_8]
0x140011ef4  add     rsp, 20h
0x140011ef8  pop     rdi
0x140011ef9  retn
```
