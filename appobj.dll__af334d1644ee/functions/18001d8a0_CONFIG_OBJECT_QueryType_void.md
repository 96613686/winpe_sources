# CONFIG_OBJECT::QueryType(void)

- ea: `0x18001d8a0`
- end: `0x18001d8a8`
- name: `?QueryType@CONFIG_OBJECT@@UEBAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *__fastcall(CONFIG_OBJECT *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x18001d8a0`: `CONFIG`

## pseudocode

```c
const unsigned __int16 *__fastcall CONFIG_OBJECT::QueryType(CONFIG_OBJECT *this)
{
  return L"CONFIG";
}

```

## disassembly

```asm
0x18001d8a0  lea     rax, aConfig; "CONFIG"
0x18001d8a7  retn
```
