# std::_Xlen_string(void)

- ea: `0x180007928`
- end: `0x180007932`
- name: `?_Xlen_string@std@@YAXXZ`
- size: `10`
- prototype: `void __noreturn(void)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180002198`
- `0x18000467c`
- `0x1800047dc`
- `0x1800048a8`
- `0x180004af8`
- `0x180004c38`
- `0x180004d90`
- `0x18000509c`
- `0x1800051d0`
- `0x1800053d4`
- `0x18000593c`
- `0x180007a94`

## callees

- `0x18000dc5c`

## pseudocode

```c
void __fastcall __noreturn std::_Xlen_string(const char *a1)
{
  std::_Xlength_error(a1);
}

```

## disassembly

```asm
0x180007928  sub     rsp, 28h
0x18000792c  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
