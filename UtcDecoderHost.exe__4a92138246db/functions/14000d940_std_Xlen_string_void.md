# std::_Xlen_string(void)

- ea: `0x14000d940`
- end: `0x14000d952`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x14000d698`
- `0x14000ebb4`
- `0x14000ef1c`
- `0x14000f014`
- `0x14000f194`
- `0x14000f43c`
- `0x14000f544`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000d94b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000d94b`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x14000d940  sub     rsp, 28h
0x14000d944  lea     rcx, aStringTooLong; "string too long"
0x14000d94b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
