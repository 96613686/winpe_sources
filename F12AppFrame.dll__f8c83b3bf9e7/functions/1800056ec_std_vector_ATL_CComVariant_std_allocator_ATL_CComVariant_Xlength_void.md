# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::_Xlength(void)

- ea: `0x1800056ec`
- end: `0x1800056fe`
- name: `?_Xlength@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800029dc`
- `0x180002b60`
- `0x18001e3f0`
- `0x18001e704`
- `0x18001e894`
- `0x18002e670`
- `0x18002f73c`
- `0x180030460`
- `0x180032234`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800056f7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800056f7`

## pseudocode

```c
void __noreturn std::vector<ATL::CComVariant>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x1800056ec  sub     rsp, 28h
0x1800056f0  lea     rcx, aVectorTooLong; "vector too long"
0x1800056f7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
