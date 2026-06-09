# std::vector<AppUriHandlerRegistrationInfo,std::allocator<AppUriHandlerRegistrationInfo>>::_Xlength(void)

- ea: `0x14000fd44`
- end: `0x14000fd56`
- name: `?_Xlength@?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400092ec`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000fd4f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000fd4f`

## pseudocode

```c
void __noreturn std::vector<AppUriHandlerRegistrationInfo>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x14000fd44  sub     rsp, 28h
0x14000fd48  lea     rcx, aVectorTooLong; "vector too long"
0x14000fd4f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
