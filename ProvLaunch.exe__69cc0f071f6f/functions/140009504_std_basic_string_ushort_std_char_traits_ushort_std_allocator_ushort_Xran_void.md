# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x140009504`
- end: `0x140009516`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000951c`
- `0x14000961c`
- `0x140009838`

## import_xrefs

- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14000950f`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14000950f`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
  JUMPOUT(0x140009515LL);
}

```

## disassembly

```asm
0x140009504  sub     rsp, 28h
0x140009508  lea     rcx, aInvalidStringP; "invalid string position"
0x14000950f  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
