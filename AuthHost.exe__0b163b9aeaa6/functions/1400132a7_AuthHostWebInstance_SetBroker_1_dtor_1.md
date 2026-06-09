# _AuthHostWebInstance::SetBroker_::_1_::dtor$1

- ea: `0x1400132a7`
- end: `0x1400132b3`
- name: `_AuthHostWebInstance::SetBroker_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400048f8`

## pseudocode

```c
void __fastcall AuthHostWebInstance::SetBroker_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  Windows::Internal::String::~String((HSTRING *)(a2 + 96));
}

```

## disassembly

```asm
0x1400132a7  lea     rcx, [rdx+60h]; this
0x1400132ae  jmp     ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
```
