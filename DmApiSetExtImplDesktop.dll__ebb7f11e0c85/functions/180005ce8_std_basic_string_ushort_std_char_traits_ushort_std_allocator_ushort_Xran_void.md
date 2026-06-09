# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xran(void)

- ea: `0x180005ce8`
- end: `0x180005d00`
- name: `?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005d60`
- `0x180005ee0`
- `0x1800060cc`

## import_xrefs

- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180005cf3`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180005cf3`

## pseudocode

```c
void std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
  __debugbreak();
  JUMPOUT(0x180005D00LL);
}

```

## disassembly

```asm
0x180005ce8  sub     rsp, 28h
0x180005cec  lea     rcx, aInvalidStringP; "invalid string position"
0x180005cf3  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180005cfa  nop     dword ptr [rax+rax+00h]
0x180005cff  int     3; Trap to Debugger
```
