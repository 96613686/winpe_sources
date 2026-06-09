# Broker::BrokerCommonException::what(void)

- ea: `0x18001f210`
- end: `0x18001f218`
- name: `?what@BrokerCommonException@Broker@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(Broker::BrokerCommonException *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x18001f210`: `BrokerCommonException`

## pseudocode

```c
const char *__fastcall Broker::BrokerCommonException::what(Broker::BrokerCommonException *this)
{
  return "BrokerCommonException";
}

```

## disassembly

```asm
0x18001f210  lea     rax, aBrokercommonex; "BrokerCommonException"
0x18001f217  retn
```
