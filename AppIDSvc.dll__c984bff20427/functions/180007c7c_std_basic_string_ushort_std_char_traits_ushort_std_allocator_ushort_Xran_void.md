# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x180007c7c`
- end: `0x180007c8d`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c94`
- `0x180007e8c`
- `0x180008190`
- `0x18000822c`

## callees

- `0x18000135c`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x180007c7c  sub     rsp, 28h
0x180007c80  lea     rcx, aInvalidStringP
0x180007c87  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
