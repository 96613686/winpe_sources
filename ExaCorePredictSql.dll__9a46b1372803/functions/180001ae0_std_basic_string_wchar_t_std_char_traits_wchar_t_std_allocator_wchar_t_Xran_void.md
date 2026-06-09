# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Xran(void)

- ea: `0x180001ae0`
- end: `0x180001af2`
- name: `?_Xran@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAXXZ`
- size: `18`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001670`
- `0x1800019b0`
- `0x180003080`
- `0x180003470`

## import_xrefs

- `MSVCP140!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180001aeb`
- `MSVCP140!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180001aeb`

## pseudocode

```c
void __noreturn std::wstring::_Xran()
{
  std::_Xout_of_range("invalid string position");
  JUMPOUT(0x180001AF1LL);
}

```

## disassembly

```asm
0x180001ae0  sub     rsp, 28h
0x180001ae4  lea     rcx, aInvalidStringP; "invalid string position"
0x180001aeb  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
