# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Xlen(void)

- ea: `0x1800017a0`
- end: `0x1800017b2`
- name: `?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ`
- size: `18`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001520`
- `0x180001670`
- `0x180002c80`
- `0x180002f10`
- `0x180003080`
- `0x180003470`
- `0x1800038a0`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800017ab`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800017ab`

## pseudocode

```c
void __noreturn std::string::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x1800017a0  sub     rsp, 28h
0x1800017a4  lea     rcx, aStringTooLong; "string too long"
0x1800017ab  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
