# std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>>::_Xlen(void)

- ea: `0x140008ca8`
- end: `0x140008cba`
- name: `?_Xlen@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEBAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140003598`
- `0x140008a90`
- `0x140008b0c`
- `0x14000a780`
- `0x14000a99c`
- `0x14000aa3c`
- `0x14000b454`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140008cb3`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140008cb3`

## pseudocode

```c
void __noreturn std::vector<std::unique_ptr<ProvPackage>>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x140008ca8  sub     rsp, 28h
0x140008cac  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x140008cb3  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
