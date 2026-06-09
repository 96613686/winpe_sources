# _GetComplement_::_1_::dtor$73

- ea: `0x100473b8f`
- end: `0x100473b9b`
- name: `_GetComplement_::_1_::dtor$73`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1004015c0`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_73(__int64 a1, __int64 a2)
{
  CDecorator::~CDecorator((CDecorator *)(a2 + 336));
}

```

## disassembly

```asm
0x100473b8f  lea     rcx, [rdx+150h]; this
0x100473b96  jmp     ??1CDecorator@@UEAA@XZ; CDecorator::~CDecorator(void)
```
