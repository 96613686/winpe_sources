# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x180005cc8`
- end: `0x180005ce0`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005b50`
- `0x180005d60`
- `0x180005e18`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180005cd3`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180005cd3`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180005cc8  sub     rsp, 28h
0x180005ccc  lea     rcx, aStringTooLong; "string too long"
0x180005cd3  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
