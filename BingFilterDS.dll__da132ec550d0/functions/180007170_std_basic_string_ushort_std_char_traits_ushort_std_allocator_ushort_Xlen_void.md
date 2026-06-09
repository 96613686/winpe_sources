# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x180007170`
- end: `0x180007181`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800071a0`
- `0x180007298`
- `0x180009b54`
- `0x18000ad28`
- `0x18000ae28`
- `0x18000afa0`

## callees

- `0x180001ff8`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x180007170  sub     rsp, 28h
0x180007174  lea     rcx, aStringTooLong
0x18000717b  call    ?_Xlength_error@std@@YAXPEBD@Z
```
