# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Xlen(void)

- ea: `0x140001ea0`
- end: `0x140001eb1`
- name: `?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001f28`
- `0x140002020`

## callees

- `0x140001eb8`

## pseudocode

```c
void __noreturn std::string::_Xlen()
{
  std::_Xlength_error("string too long");
}

```

## disassembly

```asm
0x140001ea0  sub     rsp, 28h
0x140001ea4  lea     rcx, aStringTooLong; "string too long"
0x140001eab  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
