# Broker::AccessDenied::what(void)

- ea: `0x180019180`
- end: `0x180019188`
- name: `?what@AccessDenied@Broker@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(Broker::AccessDenied *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x180019180`: `AccessDenied`

## pseudocode

```c
const char *__fastcall Broker::AccessDenied::what(Broker::AccessDenied *this)
{
  return "AccessDenied";
}

```

## disassembly

```asm
0x180019180  lea     rax, aAccessdenied; "AccessDenied"
0x180019187  retn
```
