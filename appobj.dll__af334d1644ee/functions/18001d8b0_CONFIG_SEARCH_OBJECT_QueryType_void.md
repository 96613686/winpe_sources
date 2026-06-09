# CONFIG_SEARCH_OBJECT::QueryType(void)

- ea: `0x18001d8b0`
- end: `0x18001d8b8`
- name: `?QueryType@CONFIG_SEARCH_OBJECT@@UEBAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *__fastcall(CONFIG_SEARCH_OBJECT *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x18001d8b0`: `CONFIGSEARCH`

## pseudocode

```c
const unsigned __int16 *__fastcall CONFIG_SEARCH_OBJECT::QueryType(CONFIG_SEARCH_OBJECT *this)
{
  return L"CONFIGSEARCH";
}

```

## disassembly

```asm
0x18001d8b0  lea     rax, aConfigsearch; "CONFIGSEARCH"
0x18001d8b7  retn
```
