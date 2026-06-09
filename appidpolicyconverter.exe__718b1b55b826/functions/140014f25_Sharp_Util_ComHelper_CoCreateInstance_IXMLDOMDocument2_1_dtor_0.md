# _Sharp::Util::ComHelper::CoCreateInstance_IXMLDOMDocument2__::_1_::dtor$0

- ea: `0x140014f25`
- end: `0x140014f4b`
- name: `_Sharp::Util::ComHelper::CoCreateInstance_IXMLDOMDocument2__::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140011a54`
- `0x140014f25`

## pseudocode

```c
__int64 __fastcall Sharp::Util::ComHelper::CoCreateInstance_IXMLDOMDocument2__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(*(_QWORD *)(a2 + 56));
  }
  return result;
}

```

## disassembly

```asm
0x140014f25  push    rbp
0x140014f27  sub     rsp, 20h
0x140014f2b  mov     rbp, rdx
0x140014f2e  mov     eax, [rbp+30h]
0x140014f31  and     eax, 1
0x140014f34  test    eax, eax
0x140014f36  jz      short loc_140014F45
0x140014f38  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x140014f3c  mov     rcx, [rbp+38h]
0x140014f40  call    ??1?$CComPtr@UIXMLDOMNamedNodeMap@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(void)
0x140014f45  add     rsp, 20h
0x140014f49  pop     rbp
0x140014f4a  retn
```
