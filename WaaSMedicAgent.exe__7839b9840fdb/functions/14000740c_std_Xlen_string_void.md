# std::_Xlen_string(void)

- ea: `0x14000740c`
- end: `0x14000741d`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `17`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140004290`
- `0x14000b984`
- `0x14000f27c`
- `0x1400108c8`

## callees

- `0x14000b1ec`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x14000740c  sub     rsp, 28h
0x140007410  lea     rcx, aStringTooLong; "string too long"
0x140007417  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
