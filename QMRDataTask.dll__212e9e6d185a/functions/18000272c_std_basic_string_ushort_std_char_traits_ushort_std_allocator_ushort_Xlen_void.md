# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x18000272c`
- end: `0x18000273d`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000275c`
- `0x18000285c`
- `0x18000297c`
- `0x180002a74`
- `0x180002b74`
- `0x180003000`

## callees

- `0x1800015d0`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18000272c  sub     rsp, 28h
0x180002730  lea     rcx, aStringTooLong
0x180002737  call    ?_Xlength_error@std@@YAXPEBD@Z
```
