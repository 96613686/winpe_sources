# std::_Xlen_string(void)

- ea: `0x18000b430`
- end: `0x18000b442`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180009a08`
- `0x18000e2c4`
- `0x18000e414`
- `0x18000e7f0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b43b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b43b`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18000b430  sub     rsp, 28h
0x18000b434  lea     rcx, aStringTooLong; "string too long"
0x18000b43b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
