# _PrintCore::CreateXpsBitmapProvider_::_1_::dtor$0

- ea: `0x1800106bb`
- end: `0x1800106c7`
- name: `_PrintCore::CreateXpsBitmapProvider_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800091d4`

## pseudocode

```c
_QWORD *__fastcall PrintCore::CreateXpsBitmapProvider_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IPDLConverter>::~ComPtr<IPDLConverter>(*(_QWORD **)(a2 + 120));
}

```

## disassembly

```asm
0x1800106bb  mov     rcx, [rdx+78h]
0x1800106c2  jmp     ??1?$ComPtr@UIPDLConverter@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IPDLConverter>::~ComPtr<IPDLConverter>(void)
```
