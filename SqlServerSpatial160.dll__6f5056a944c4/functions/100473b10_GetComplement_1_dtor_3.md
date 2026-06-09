# _GetComplement_::_1_::dtor$3

- ea: `0x100473b10`
- end: `0x100473b1c`
- name: `_GetComplement_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1004015c0`

## pseudocode

```c
void __fastcall GetComplement_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  CDecorator::~CDecorator((CDecorator *)(a2 + 336));
}

```

## disassembly

```asm
0x100473b10  lea     rcx, [rdx+150h]; this
0x100473b17  jmp     ??1CDecorator@@UEAA@XZ; CDecorator::~CDecorator(void)
```
