# _AuthHostWebInstance::SetBroker_::_1_::dtor$3

- ea: `0x1400132cb`
- end: `0x1400132d7`
- name: `_AuthHostWebInstance::SetBroker_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400048f8`

## pseudocode

```c
void __fastcall AuthHostWebInstance::SetBroker_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  Windows::Internal::String::~String((HSTRING *)(a2 + 88));
}

```

## disassembly

```asm
0x1400132cb  lea     rcx, [rdx+58h]; this
0x1400132d2  jmp     ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
```
