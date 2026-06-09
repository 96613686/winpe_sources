# std::vector<std::shared_ptr<CConfigSource>,std::allocator<std::shared_ptr<CConfigSource>>>::_Xlen(void)

- ea: `0x18000a398`
- end: `0x18000a3aa`
- name: `?_Xlen@?$vector@V?$shared_ptr@VCConfigSource@@@std@@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@@std@@IEBAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000a268`
- `0x18000f790`
- `0x18000fd14`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a3a3`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a3a3`

## pseudocode

```c
void __noreturn std::vector<std::shared_ptr<CConfigSource>>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x18000a398  sub     rsp, 28h
0x18000a39c  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x18000a3a3  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
