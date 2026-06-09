# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Xran(void)

- ea: `0x18002ff88`
- end: `0x18002ff99`
- name: `?_Xran@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180008360`
- `0x18001592c`
- `0x180015b10`
- `0x180015db0`
- `0x18001c6b4`
- `0x18001c7ec`
- `0x18002ffc4`
- `0x180030430`
- `0x180034034`
- `0x1800341fc`
- `0x180034b24`

## callees

- `0x18000231c`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x18002ff88  sub     rsp, 28h
0x18002ff8c  lea     rcx, aInvalidStringP
0x18002ff93  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
