# std::_Xlen_string(void)

- ea: `0x180007900`
- end: `0x180007912`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180007398`
- `0x1800074d8`
- `0x180010634`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000790b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000790b`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180007900  sub     rsp, 28h
0x180007904  lea     rcx, aStringTooLong; "string too long"
0x18000790b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
