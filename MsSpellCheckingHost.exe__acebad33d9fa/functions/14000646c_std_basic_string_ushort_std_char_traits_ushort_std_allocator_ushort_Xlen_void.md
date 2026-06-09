# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x14000646c`
- end: `0x14000647d`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000649c`
- `0x140006594`
- `0x14000ed4c`
- `0x14000eeb4`
- `0x14000ef9c`
- `0x14000f060`
- `0x140011ab0`

## callees

- `0x1400017a8`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x14000646c  sub     rsp, 28h
0x140006470  lea     rcx, aStringTooLong; "string too long"
0x140006477  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
