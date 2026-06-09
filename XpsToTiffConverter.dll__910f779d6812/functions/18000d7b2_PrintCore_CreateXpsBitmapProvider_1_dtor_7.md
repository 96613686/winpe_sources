# _PrintCore::CreateXpsBitmapProvider_::_1_::dtor$7

- ea: `0x18000d7b2`
- end: `0x18000d7be`
- name: `_PrintCore::CreateXpsBitmapProvider_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009c18`

## pseudocode

```c
_QWORD *__fastcall PrintCore::CreateXpsBitmapProvider_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IXpsOMPage>::~ComPtr<IXpsOMPage>(*(_QWORD **)(a2 + 136));
}

```

## disassembly

```asm
0x18000d7b2  mov     rcx, [rdx+88h]
0x18000d7b9  jmp     ??1?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IXpsOMPage>::~ComPtr<IXpsOMPage>(void)
```
