# _WritePage::XpsToTiffConverter::WritePage_::_1_::dtor$3

- ea: `0x18000d663`
- end: `0x18000d66f`
- name: `_WritePage::XpsToTiffConverter::WritePage_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009cb8`

## pseudocode

```c
double __fastcall WritePage::XpsToTiffConverter::WritePage_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return winrt::com_ptr<IPropertyBag2>::~com_ptr<IPropertyBag2>((_QWORD *)(a2 + 88));
}

```

## disassembly

```asm
0x18000d663  lea     rcx, [rdx+58h]
0x18000d66a  jmp     ??1?$com_ptr@UIPropertyBag2@@@winrt@@QEAA@XZ; winrt::com_ptr<IPropertyBag2>::~com_ptr<IPropertyBag2>(void)
```
