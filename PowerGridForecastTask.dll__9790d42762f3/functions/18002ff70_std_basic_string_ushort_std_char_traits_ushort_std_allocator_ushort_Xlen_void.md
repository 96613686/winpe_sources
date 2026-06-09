# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Xlen(void)

- ea: `0x18002ff70`
- end: `0x18002ff81`
- name: `?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x1800067e0`
- `0x180008360`
- `0x18001592c`
- `0x180015a28`
- `0x180015b10`
- `0x180015c0c`
- `0x180015cf4`
- `0x180015db0`
- `0x180015eb8`
- `0x180015fcc`
- `0x18001c6b4`
- `0x18001c7ec`
- `0x18002ffc4`
- `0x1800300bc`
- `0x180034034`
- `0x180034120`
- `0x1800341fc`
- `0x180034304`
- `0x180034d18`

## callees

- `0x1800022f0`

## pseudocode

```c
void __noreturn std::wstring::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x18002ff70  sub     rsp, 28h
0x18002ff74  lea     rcx, aStringTooLong
0x18002ff7b  call    ?_Xlength_error@std@@YAXPEBD@Z
```
