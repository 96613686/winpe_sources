# _CommonUtil::CSecurityAttributesHolder::CSecurityAttributesHolder_::_1_::dtor$0

- ea: `0x180009a90`
- end: `0x180009a9c`
- name: `_CommonUtil::CSecurityAttributesHolder::CSecurityAttributesHolder_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007ef0`

## pseudocode

```c
void __fastcall CommonUtil::CSecurityAttributesHolder::CSecurityAttributesHolder_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CommonUtil::ISecurityAttributes::~ISecurityAttributes(*(CommonUtil::ISecurityAttributes **)(a2 + 64));
}

```

## disassembly

```asm
0x180009a90  mov     rcx, [rdx+40h]; this
0x180009a97  jmp     ??1ISecurityAttributes@CommonUtil@@UEAA@XZ; CommonUtil::ISecurityAttributes::~ISecurityAttributes(void)
```
