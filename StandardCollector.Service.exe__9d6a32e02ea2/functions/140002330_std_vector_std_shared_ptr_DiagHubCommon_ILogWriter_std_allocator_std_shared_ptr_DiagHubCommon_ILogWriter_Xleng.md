# std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>::_Xlength(void)

- ea: `0x140002330`
- end: `0x140002342`
- name: `?_Xlength@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001388`
- `0x140008ef4`
- `0x14000b824`
- `0x14000d87c`
- `0x14000da28`
- `0x14000dec8`
- `0x14000f364`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000233b`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000233b`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __noreturn std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x140002330  sub     rsp, 28h
0x140002334  lea     rcx, aVectorTooLong; "vector too long"
0x14000233b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
