# std::_Xlen_string(void)

- ea: `0x14000b1ec`
- end: `0x14000b1fe`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1400067e8`
- `0x140006f18`
- `0x1400074fc`
- `0x14000d858`
- `0x14000d974`
- `0x14000e870`
- `0x14000e9f8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000b1f7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000b1f7`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x14000b1ec  sub     rsp, 28h
0x14000b1f0  lea     rcx, aStringTooLong; "string too long"
0x14000b1f7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
