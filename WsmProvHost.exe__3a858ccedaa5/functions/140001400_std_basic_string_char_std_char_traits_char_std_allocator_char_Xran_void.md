# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Xran(void)

- ea: `0x140001400`
- end: `0x140001411`
- name: `?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001418`
- `0x1400016f0`

## callees

- `0x1400013d4`

## pseudocode

```c
void __noreturn std::string::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x140001400  sub     rsp, 28h
0x140001404  lea     rcx, aInvalidStringP; "invalid string position"
0x14000140b  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
