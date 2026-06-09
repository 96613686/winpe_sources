# _PrintCore::CreateXpsBitmapProvider_::_1_::dtor$0

- ea: `0x18000d77a`
- end: `0x18000d786`
- name: `_PrintCore::CreateXpsBitmapProvider_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009c18`

## pseudocode

```c
_QWORD *__fastcall PrintCore::CreateXpsBitmapProvider_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IXpsOMPage>::~ComPtr<IXpsOMPage>(*(_QWORD **)(a2 + 120));
}

```

## disassembly

```asm
0x18000d77a  mov     rcx, [rdx+78h]
0x18000d781  jmp     ??1?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IXpsOMPage>::~ComPtr<IXpsOMPage>(void)
```
