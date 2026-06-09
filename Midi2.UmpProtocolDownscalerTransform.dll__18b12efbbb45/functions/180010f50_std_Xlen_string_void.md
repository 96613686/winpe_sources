# std::_Xlen_string(void)

- ea: `0x180010f50`
- end: `0x180010f62`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b238`
- `0x18000b5dc`
- `0x18000b770`
- `0x18000c62c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010f5b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010f5b`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180010f50  sub     rsp, 28h
0x180010f54  lea     rcx, aStringTooLong; "string too long"
0x180010f5b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
