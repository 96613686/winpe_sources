# std::vector<DWRITE_GLYPH_OFFSET,std::allocator<DWRITE_GLYPH_OFFSET>>::_Xlength(void)

- ea: `0x1800a9588`
- end: `0x1800a959a`
- name: `?_Xlength@?$vector@UDWRITE_GLYPH_OFFSET@@V?$allocator@UDWRITE_GLYPH_OFFSET@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x1800a7e2c`
- `0x1800ad8c0`
- `0x1800b5b64`
- `0x1800b5c70`
- `0x1800b6770`
- `0x1800b7070`
- `0x1800b716c`
- `0x1800b7268`
- `0x1800b7368`
- `0x1800b7434`
- `0x1800b74f0`
- `0x1800b88bc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a9593`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800a9593`

## pseudocode

```c
void __noreturn std::vector<DWRITE_GLYPH_OFFSET>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x1800a9588  sub     rsp, 28h
0x1800a958c  lea     rcx, aVectorTooLong; "vector too long"
0x1800a9593  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
