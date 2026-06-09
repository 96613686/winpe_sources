# std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry,std::allocator<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::_Xlength(void)

- ea: `0x180011a64`
- end: `0x180011a76`
- name: `?_Xlength@?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000cbfc`
- `0x180012a44`
- `0x180018c74`
- `0x18001e5dc`
- `0x18001ef14`
- `0x18001f170`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011a6f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011a6f`

## pseudocode

```c
void __noreturn std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180011a64  sub     rsp, 28h
0x180011a68  lea     rcx, aVectorTooLong; "vector too long"
0x180011a6f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
