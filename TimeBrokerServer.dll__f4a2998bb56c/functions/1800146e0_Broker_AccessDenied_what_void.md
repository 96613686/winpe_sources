# Broker::AccessDenied::what(void)

- ea: `0x1800146e0`
- end: `0x1800146e8`
- name: `?what@AccessDenied@Broker@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(Broker::AccessDenied *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x1800146e0`: `AccessDenied`

## pseudocode

```c
const char *__fastcall Broker::AccessDenied::what(Broker::AccessDenied *this)
{
  return "AccessDenied";
}

```

## disassembly

```asm
0x1800146e0  lea     rax, aAccessdenied; "AccessDenied"
0x1800146e7  retn
```
