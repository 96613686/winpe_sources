# std::vector<std::unique_ptr<NASignal,std::default_delete<NASignal>>,std::allocator<std::unique_ptr<NASignal,std::default_delete<NASignal>>>>::_Xlength(void)

- ea: `0x18001aea4`
- end: `0x18001aeb6`
- name: `?_Xlength@?$vector@V?$unique_ptr@VNASignal@@U?$default_delete@VNASignal@@@std@@@std@@V?$allocator@V?$unique_ptr@VNASignal@@U?$default_delete@VNASignal@@@std@@@std@@@2@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e1c0`
- `0x18000e244`
- `0x18000e2bc`
- `0x18000ea2c`
- `0x18000eb58`
- `0x18000eca4`
- `0x18000edf0`
- `0x18001014c`
- `0x18001022c`
- `0x180010310`
- `0x180010428`
- `0x180010ae0`
- `0x1800118f4`
- `0x18001d788`
- `0x180020818`
- `0x180028da0`
- `0x180028e74`
- `0x180038be4`
- `0x180038e80`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001aeaf`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001aeaf`

## pseudocode

```c
void __noreturn std::vector<std::unique_ptr<NASignal>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x18001aea4  sub     rsp, 28h
0x18001aea8  lea     rcx, aVectorTooLong; "vector too long"
0x18001aeaf  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
