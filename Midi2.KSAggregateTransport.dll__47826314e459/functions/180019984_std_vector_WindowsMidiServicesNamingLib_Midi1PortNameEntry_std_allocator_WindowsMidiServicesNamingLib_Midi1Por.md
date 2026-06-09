# std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry,std::allocator<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::_Xlength(void)

- ea: `0x180019984`
- end: `0x180019996`
- name: `?_Xlength@?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `21`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x1800131cc`
- `0x180019110`
- `0x180020104`
- `0x18002037c`
- `0x180020604`
- `0x180020998`
- `0x180020b58`
- `0x1800210c0`
- `0x180021e68`
- `0x1800296a4`
- `0x18002980c`
- `0x18002aa10`
- `0x18002aba0`
- `0x18002ade0`
- `0x18002dc18`
- `0x18002fbd8`
- `0x18003b038`
- `0x1800461a8`
- `0x18004c710`
- `0x18004e660`
- `0x1800512c0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001998f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001998f`

## pseudocode

```c
void __noreturn std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180019984  sub     rsp, 28h
0x180019988  lea     rcx, aVectorTooLong; "vector too long"
0x18001998f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
