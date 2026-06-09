# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x180007c4c`
- end: `0x180007c5d`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c94`
- `0x180007d8c`
- `0x180007e8c`
- `0x180007f9c`

## callees

- `0x180001330`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180007c4c  sub     rsp, 28h
0x180007c50  lea     rcx, aStringTooLong
0x180007c57  call    ?_Xlength_error@std@@YAXPEBD@Z
```
