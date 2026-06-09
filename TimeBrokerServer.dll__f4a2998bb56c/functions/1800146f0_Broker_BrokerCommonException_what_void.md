# Broker::BrokerCommonException::what(void)

- ea: `0x1800146f0`
- end: `0x1800146f8`
- name: `?what@BrokerCommonException@Broker@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(Broker::BrokerCommonException *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x1800146f0`: `BrokerCommonException`

## pseudocode

```c
const char *__fastcall Broker::BrokerCommonException::what(Broker::BrokerCommonException *this)
{
  return "BrokerCommonException";
}

```

## disassembly

```asm
0x1800146f0  lea     rax, aBrokercommonex; "BrokerCommonException"
0x1800146f7  retn
```
