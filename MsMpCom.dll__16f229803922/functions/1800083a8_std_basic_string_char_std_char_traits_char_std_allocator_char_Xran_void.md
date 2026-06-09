# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Xran(void)

- ea: `0x1800083a8`
- end: `0x1800083b9`
- name: `?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083c0`
- `0x180008690`

## callees

- `0x18000146c`

## pseudocode

```c
void __noreturn std::string::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x1800083a8  sub     rsp, 28h
0x1800083ac  lea     rcx, aInvalidStringP
0x1800083b3  call    ?_Xout_of_range@std@@YAXPEBD@Z
```
