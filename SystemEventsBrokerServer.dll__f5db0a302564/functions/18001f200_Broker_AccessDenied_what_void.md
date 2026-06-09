# Broker::AccessDenied::what(void)

- ea: `0x18001f200`
- end: `0x18001f208`
- name: `?what@AccessDenied@Broker@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(Broker::AccessDenied *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x18001f200`: `AccessDenied`

## pseudocode

```c
const char *__fastcall Broker::AccessDenied::what(Broker::AccessDenied *this)
{
  return "AccessDenied";
}

```

## disassembly

```asm
0x18001f200  lea     rax, aAccessdenied; "AccessDenied"
0x18001f207  retn
```
