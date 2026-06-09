# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x140006484`
- end: `0x140006495`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000649c`
- `0x140006770`
- `0x14000f060`
- `0x14000f530`

## callees

- `0x1400017d4`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
}

```

## disassembly

```asm
0x140006484  sub     rsp, 28h
0x140006488  lea     rcx, aInvalidStringP; "invalid string position"
0x14000648f  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
