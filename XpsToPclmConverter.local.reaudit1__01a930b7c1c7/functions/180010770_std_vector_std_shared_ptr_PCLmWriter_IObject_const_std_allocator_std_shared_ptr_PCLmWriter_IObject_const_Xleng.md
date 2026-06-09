# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Xlength(void)

- ea: `0x180010770`
- end: `0x180010782`
- name: `?_Xlength@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ee94`
- `0x180010f34`
- `0x1800139a4`
- `0x180013aac`
- `0x180013be0`
- `0x180016a6c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001077b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001077b`

## pseudocode

```c
void __noreturn std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180010770  sub     rsp, 28h
0x180010774  lea     rcx, aVectorTooLong; "vector too long"
0x18001077b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
