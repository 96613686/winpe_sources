# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x180002744`
- end: `0x180002755`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000275c`
- `0x18000297c`
- `0x180002b74`
- `0x180002dc0`

## callees

- `0x1800015fc`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x180002744  sub     rsp, 28h
0x180002748  lea     rcx, aInvalidStringP
0x18000274f  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
