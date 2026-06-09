# _AuthHostWebInstance::SetBroker_::_1_::dtor$0

- ea: `0x140013295`
- end: `0x1400132a1`
- name: `_AuthHostWebInstance::SetBroker_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400048f8`

## pseudocode

```c
void __fastcall AuthHostWebInstance::SetBroker_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Windows::Internal::String::~String((HSTRING *)(a2 + 216));
}

```

## disassembly

```asm
0x140013295  lea     rcx, [rdx+0D8h]; this
0x14001329c  jmp     ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
```
