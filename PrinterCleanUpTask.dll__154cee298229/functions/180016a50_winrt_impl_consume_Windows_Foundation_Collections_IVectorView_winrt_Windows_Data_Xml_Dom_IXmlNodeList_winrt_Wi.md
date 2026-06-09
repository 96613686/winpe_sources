# _winrt::impl::consume_Windows_Foundation_Collections_IVectorView_winrt::Windows::Data::Xml::Dom::IXmlNodeList_winrt::Windows::Data::Xml::Dom::IXmlNode_::GetAt_::_1_::dtor$0

- ea: `0x180016a50`
- end: `0x180016a76`
- name: `_winrt::impl::consume_Windows_Foundation_Collections_IVectorView_winrt::Windows::Data::Xml::Dom::IXmlNodeList_winrt::Windows::Data::Xml::Dom::IXmlNode_::GetAt_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000a360`
- `0x180016a50`

## pseudocode

```c
void __fastcall winrt::impl::consume_Windows_Foundation_Collections_IVectorView_winrt::Windows::Data::Xml::Dom::IXmlNodeList_winrt::Windows::Data::Xml::Dom::IXmlNode_::GetAt_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(*(winrt::Windows::Devices::Enumeration::IDeviceInformation **)(a2 + 120));
  }
}

```

## disassembly

```asm
0x180016a50  push    rbp
0x180016a52  sub     rsp, 20h
0x180016a56  mov     rbp, rdx
0x180016a59  mov     eax, [rbp+20h]
0x180016a5c  and     eax, 1
0x180016a5f  test    eax, eax
0x180016a61  jz      short loc_180016A70
0x180016a63  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x180016a67  mov     rcx, [rbp+78h]; this
0x180016a6b  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180016a70  add     rsp, 20h
0x180016a74  pop     rbp
0x180016a75  retn
```
