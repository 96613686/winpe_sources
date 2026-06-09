# std::vector<uchar,wil::secure_allocator<uchar>>::_Xlength(void)

- ea: `0x14000b204`
- end: `0x14000b216`
- name: `?_Xlength@?$vector@EU?$secure_allocator@E@wil@@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400069b0`
- `0x140006af4`
- `0x140007058`
- `0x140007d04`
- `0x140007dc0`
- `0x14000d5a8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000b20f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000b20f`

## pseudocode

```c
void __noreturn std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x14000b204  sub     rsp, 28h
0x14000b208  lea     rcx, aVectorTooLong; "vector too long"
0x14000b20f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
