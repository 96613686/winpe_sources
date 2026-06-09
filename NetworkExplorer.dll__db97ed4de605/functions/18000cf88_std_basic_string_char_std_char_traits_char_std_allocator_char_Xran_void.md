# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Xran(void)

- ea: `0x18000cf88`
- end: `0x18000cf99`
- name: `?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cff4`
- `0x18000d2f0`
- `0x18000d38c`

## callees

- `0x18000741c`

## pseudocode

```c
void __noreturn std::string::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x18000cf88  sub     rsp, 28h
0x18000cf8c  lea     rcx, aInvalidStringP
0x18000cf93  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
