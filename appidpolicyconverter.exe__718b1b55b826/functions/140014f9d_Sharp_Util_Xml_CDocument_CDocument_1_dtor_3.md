# _Sharp::Util::Xml::CDocument::CDocument_::_1_::dtor$3

- ea: `0x140014f9d`
- end: `0x140014fc3`
- name: `_Sharp::Util::Xml::CDocument::CDocument_::_1_::dtor$3`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140011a54`
- `0x140014f9d`

## pseudocode

```c
__int64 __fastcall Sharp::Util::Xml::CDocument::CDocument_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(a2 + 88);
  }
  return result;
}

```

## disassembly

```asm
0x140014f9d  push    rbp
0x140014f9f  sub     rsp, 20h
0x140014fa3  mov     rbp, rdx
0x140014fa6  mov     eax, [rbp+30h]
0x140014fa9  and     eax, 1
0x140014fac  test    eax, eax
0x140014fae  jz      short loc_140014FBD
0x140014fb0  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x140014fb4  lea     rcx, [rbp+58h]
0x140014fb8  call    ??1?$CComPtr@UIXMLDOMNamedNodeMap@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(void)
0x140014fbd  add     rsp, 20h
0x140014fc1  pop     rbp
0x140014fc2  retn
```
