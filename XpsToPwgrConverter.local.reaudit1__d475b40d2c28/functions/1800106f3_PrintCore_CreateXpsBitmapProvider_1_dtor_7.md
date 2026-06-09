# _PrintCore::CreateXpsBitmapProvider_::_1_::dtor$7

- ea: `0x1800106f3`
- end: `0x1800106ff`
- name: `_PrintCore::CreateXpsBitmapProvider_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800091d4`

## pseudocode

```c
_QWORD *__fastcall PrintCore::CreateXpsBitmapProvider_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IPDLConverter>::~ComPtr<IPDLConverter>(*(_QWORD **)(a2 + 136));
}

```

## disassembly

```asm
0x1800106f3  mov     rcx, [rdx+88h]
0x1800106fa  jmp     ??1?$ComPtr@UIPDLConverter@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IPDLConverter>::~ComPtr<IPDLConverter>(void)
```
