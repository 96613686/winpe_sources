# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Xran(void)

- ea: `0x1400059ec`
- end: `0x1400059fd`
- name: `?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005a5c`
- `0x140005d60`
- `0x140005dfc`

## callees

- `0x140001c0c`

## pseudocode

```c
void __noreturn std::string::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x1400059ec  sub     rsp, 28h
0x1400059f0  lea     rcx, aInvalidStringP; "invalid string position"
0x1400059f7  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
