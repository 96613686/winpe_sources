# Sharp::Util::Xml::CNode::CNode(Sharp::Util::Xml::CNode const &)

- ea: `0x140011974`
- end: `0x1400119a2`
- name: `??0CNode@Xml@Util@Sharp@@QEAA@AEBV0123@@Z`
- size: `46`
- prototype: `Sharp::Util::Xml::CNode *__fastcall(Sharp::Util::Xml::CNode *this, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011ec0`
- `0x140013548`
- `0x140013808`

## callees

- `0x140011888`

## pseudocode

```c
Sharp::Util::Xml::CNode *__fastcall Sharp::Util::Xml::CNode::CNode(
        Sharp::Util::Xml::CNode *this,
        const struct Sharp::Util::Xml::CNode *a2)
{
  *(_QWORD *)this = &Sharp::Util::Xml::CNode::`vftable';
  ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>((__int64 *)this + 1, (__int64 *)a2 + 1);
  return this;
}

```

## disassembly

```asm
0x140011974  mov     [rsp+arg_0], rcx
0x140011979  push    rbx
0x14001197a  sub     rsp, 20h
0x14001197e  mov     rbx, rcx
0x140011981  lea     rax, ??_7CNode@Xml@Util@Sharp@@6B@; const Sharp::Util::Xml::CNode::`vftable'
0x140011988  mov     [rcx], rax
0x14001198b  add     rdx, 8
0x14001198f  add     rcx, 8
0x140011993  call    ??0?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(ATL::CComPtr<IXMLDOMNodeList> const &)
0x140011998  nop
0x140011999  mov     rax, rbx
0x14001199c  add     rsp, 20h
0x1400119a0  pop     rbx
0x1400119a1  retn
```
