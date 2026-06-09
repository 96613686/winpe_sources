# _Sharp::Util::Xml::CNode::ToDom_::_1_::dtor$0

- ea: `0x140015053`
- end: `0x140015079`
- name: `_Sharp::Util::Xml::CNode::ToDom_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140011a54`
- `0x140015053`

## pseudocode

```c
__int64 __fastcall Sharp::Util::Xml::CNode::ToDom_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(*(_QWORD *)(a2 + 72));
  }
  return result;
}

```

## disassembly

```asm
0x140015053  push    rbp
0x140015055  sub     rsp, 20h
0x140015059  mov     rbp, rdx
0x14001505c  mov     eax, [rbp+20h]
0x14001505f  and     eax, 1
0x140015062  test    eax, eax
0x140015064  jz      short loc_140015073
0x140015066  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x14001506a  mov     rcx, [rbp+48h]
0x14001506e  call    ??1?$CComPtr@UIXMLDOMNamedNodeMap@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(void)
0x140015073  add     rsp, 20h
0x140015077  pop     rbp
0x140015078  retn
```
