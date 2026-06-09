# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x180007188`
- end: `0x180007199`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800071a0`
- `0x180007540`
- `0x18000ad28`
- `0x18000ae28`

## callees

- `0x180002024`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x180007188  sub     rsp, 28h
0x18000718c  lea     rcx, aInvalidStringP
0x180007193  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
