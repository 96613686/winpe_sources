# ReadOnlyPendingUserDisplayLanguageRegistryValue::~ReadOnlyPendingUserDisplayLanguageRegistryValue(void)

- ea: `0x180022258`
- end: `0x18002225d`
- name: `??1ReadOnlyPendingUserDisplayLanguageRegistryValue@@UEAA@XZ`
- size: `5`
- prototype: `void __fastcall(ReadOnlyPendingUserDisplayLanguageRegistryValue *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002359b`

## callees

- `0x180020474`

## pseudocode

```c
// attributes: thunk
void __fastcall ReadOnlyPendingUserDisplayLanguageRegistryValue::~ReadOnlyPendingUserDisplayLanguageRegistryValue(
        ReadOnlyPendingUserDisplayLanguageRegistryValue *this)
{
  RegistryMultiStringValue::~RegistryMultiStringValue(this);
}

```

## disassembly

```asm
0x180022258  jmp     ??1RegistryMultiStringValue@@UEAA@XZ; RegistryMultiStringValue::~RegistryMultiStringValue(void)
```
