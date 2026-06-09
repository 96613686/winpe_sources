# std::_Xlen_string(void)

- ea: `0x140002ea8`
- end: `0x140002eb9`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `17`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002408`
- `0x140002550`
- `0x14000c360`
- `0x14000c4a0`
- `0x14000d12c`

## callees

- `0x1400049cc`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x140002ea8  sub     rsp, 28h
0x140002eac  lea     rcx, aStringTooLong; "string too long"
0x140002eb3  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
