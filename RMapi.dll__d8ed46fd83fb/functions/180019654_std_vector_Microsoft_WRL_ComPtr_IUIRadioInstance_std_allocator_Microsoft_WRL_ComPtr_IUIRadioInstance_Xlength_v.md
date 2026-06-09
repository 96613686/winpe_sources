# std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>,std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>>>::_Xlength(void)

- ea: `0x180019654`
- end: `0x180019666`
- name: `?_Xlength@?$vector@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800093c4`
- `0x18000b090`
- `0x180017d34`
- `0x18001a3c0`
- `0x18001a500`
- `0x18001a64c`
- `0x18001a7bc`
- `0x18001a914`
- `0x18001aa6c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001965f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001965f`

## pseudocode

```c
void __noreturn std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180019654  sub     rsp, 28h
0x180019658  lea     rcx, aVectorTooLong; "vector too long"
0x18001965f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
