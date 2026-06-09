# Sharp::Util::Xml::CNode::ToDom(void)

- ea: `0x140011e84`
- end: `0x140011eb8`
- name: `?ToDom@CNode@Xml@Util@Sharp@@QEBA?AV?$CComPtr@UIXMLDOMNode@@@ATL@@XZ`
- size: `52`
- prototype: `__int64 *__fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012b94`

## callees

- `0x140011888`

## pseudocode

```c
__int64 *__fastcall Sharp::Util::Xml::CNode::ToDom(__int64 a1, __int64 *a2)
{
  ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(a2, (__int64 *)(a1 + 8));
  return a2;
}

```

## disassembly

```asm
0x140011e84  mov     [rsp+arg_8], rdx
0x140011e89  push    rbx
0x140011e8a  sub     rsp, 30h
0x140011e8e  mov     rbx, rdx
0x140011e91  mov     [rsp+38h+var_18], 0
0x140011e99  lea     rdx, [rcx+8]
0x140011e9d  mov     rcx, rbx
0x140011ea0  call    ??0?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IXMLDOMNodeList>::CComPtr<IXMLDOMNodeList>(ATL::CComPtr<IXMLDOMNodeList> const &)
0x140011ea5  nop
0x140011ea6  mov     [rsp+38h+var_18], 1
0x140011eae  mov     rax, rbx
0x140011eb1  add     rsp, 30h
0x140011eb5  pop     rbx
0x140011eb6  retn
```
