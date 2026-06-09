# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Xlen(void)

- ea: `0x180008390`
- end: `0x1800083a1`
- name: `?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083c0`
- `0x1800084b8`

## callees

- `0x180001440`

## pseudocode

```c
void __noreturn std::string::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180008390  sub     rsp, 28h
0x180008394  lea     rcx, aStringTooLong
0x18000839b  call    ?_Xlength_error@std@@YAXPEBD@Z
```
