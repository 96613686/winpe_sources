# std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry,std::allocator<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::_Xlength(void)

- ea: `0x180013954`
- end: `0x180013966`
- name: `?_Xlength@?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000e22c`
- `0x180013574`
- `0x18001bd50`
- `0x18001bfc8`
- `0x18001c188`
- `0x18001c400`
- `0x180021c1c`
- `0x180022a6c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001395f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001395f`

## pseudocode

```c
void __noreturn std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180013954  sub     rsp, 28h
0x180013958  lea     rcx, aVectorTooLong; "vector too long"
0x18001395f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
