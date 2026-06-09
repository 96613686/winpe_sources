# std::_Xlen_string(void)

- ea: `0x14000a2ac`
- end: `0x14000a2be`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `18`
- prototype: `void __noreturn(void)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x140007098`
- `0x140007188`
- `0x1400073c0`
- `0x1400074b8`
- `0x14000760c`
- `0x140007710`
- `0x14000782c`
- `0x1400079a0`
- `0x140007ad8`
- `0x140007c18`
- `0x140007d80`
- `0x1400084c4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000a2b7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000a2b7`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x14000a2ac  sub     rsp, 28h
0x14000a2b0  lea     rcx, aStringTooLong; "string too long"
0x14000a2b7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
