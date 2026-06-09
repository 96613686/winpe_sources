# std::_Xlen_string(void)

- ea: `0x18000b37c`
- end: `0x18000b38e`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180007850`
- `0x180007940`
- `0x180007b54`
- `0x180007c4c`
- `0x180007da0`
- `0x180007ea4`
- `0x180007fc0`
- `0x180008134`
- `0x18000826c`
- `0x1800083ac`
- `0x180008514`
- `0x180008c00`
- `0x18000b4e8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b387`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b387`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18000b37c  sub     rsp, 28h
0x18000b380  lea     rcx, aStringTooLong; "string too long"
0x18000b387  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
