# Broker::BrokerCommonException::what(void)

- ea: `0x180019190`
- end: `0x180019198`
- name: `?what@BrokerCommonException@Broker@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(Broker::BrokerCommonException *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x180019190`: `BrokerCommonException`

## pseudocode

```c
const char *__fastcall Broker::BrokerCommonException::what(Broker::BrokerCommonException *this)
{
  return "BrokerCommonException";
}

```

## disassembly

```asm
0x180019190  lea     rax, aBrokercommonex; "BrokerCommonException"
0x180019197  retn
```
