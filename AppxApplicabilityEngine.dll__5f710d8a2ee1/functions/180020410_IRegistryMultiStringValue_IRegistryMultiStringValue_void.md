# IRegistryMultiStringValue::~IRegistryMultiStringValue(void)

- ea: `0x180020410`
- end: `0x18002041b`
- name: `??1IRegistryMultiStringValue@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(IRegistryMultiStringValue *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800245da`
- `0x1800248b9`
- `0x180024ae3`

## pseudocode

```c
void __fastcall IRegistryMultiStringValue::~IRegistryMultiStringValue(IRegistryMultiStringValue *this)
{
  *(_QWORD *)this = &IRegistryMultiStringValue::`vftable';
}

```

## disassembly

```asm
0x180020410  lea     rax, ??_7IRegistryMultiStringValue@@6B@; const IRegistryMultiStringValue::`vftable'
0x180020417  mov     [rcx], rax
0x18002041a  retn
```
