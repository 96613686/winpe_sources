# _AuthHostWebInstance::SetBroker_::_1_::dtor$2

- ea: `0x1400132b9`
- end: `0x1400132c5`
- name: `_AuthHostWebInstance::SetBroker_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400048f8`

## pseudocode

```c
void __fastcall AuthHostWebInstance::SetBroker_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  Windows::Internal::String::~String((HSTRING *)(a2 + 208));
}

```

## disassembly

```asm
0x1400132b9  lea     rcx, [rdx+0D0h]; this
0x1400132c0  jmp     ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
```
