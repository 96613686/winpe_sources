# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x1800065dc`
- end: `0x1800065ee`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000310c`
- `0x18000a3c8`
- `0x18000a540`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800065e7`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800065e7`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x1800065dc  sub     rsp, 28h
0x1800065e0  lea     rcx, aStringTooLong; "string too long"
0x1800065e7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
