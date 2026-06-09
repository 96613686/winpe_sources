# std::_Xlen_string(void)

- ea: `0x18000bbf8`
- end: `0x18000bc0a`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800030a0`
- `0x18000322c`
- `0x180003be4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bc03`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bc03`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18000bbf8  sub     rsp, 28h
0x18000bbfc  lea     rcx, aStringTooLong; "string too long"
0x18000bc03  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
