# std::_Xlen_string(void)

- ea: `0x14000d9f0`
- end: `0x14000da01`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `17`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cc78`
- `0x14000ce04`
- `0x14000cf98`
- `0x14000de3c`

## callees

- `0x140011498`

## pseudocode

```c
void __noreturn std::_Xlen_string(void)
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x14000d9f0  sub     rsp, 28h
0x14000d9f4  lea     rcx, aStringTooLong; "string too long"
0x14000d9fb  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
