# std::vector<std::unique_ptr<_MIDI_PIN_INFO,std::default_delete<_MIDI_PIN_INFO>>,std::allocator<std::unique_ptr<_MIDI_PIN_INFO,std::default_delete<_MIDI_PIN_INFO>>>>::_Xlength(void)

- ea: `0x180014824`
- end: `0x180014836`
- name: `?_Xlength@?$vector@V?$unique_ptr@V_MIDI_PIN_INFO@@U?$default_delete@V_MIDI_PIN_INFO@@@std@@@std@@V?$allocator@V?$unique_ptr@V_MIDI_PIN_INFO@@U?$default_delete@V_MIDI_PIN_INFO@@@std@@@std@@@2@@std@@CAXXZ`
- size: `18`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f3b8`
- `0x180014664`
- `0x180016994`
- `0x180016b54`
- `0x180016de0`
- `0x180016fc4`
- `0x18001757c`
- `0x18001fc3c`
- `0x180024da8`
- `0x1800256d4`
- `0x18002a440`
- `0x18002db30`
- `0x180031f8c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001482f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001482f`

## pseudocode

```c
void __noreturn std::vector<std::unique_ptr<_MIDI_PIN_INFO>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180014824  sub     rsp, 28h
0x180014828  lea     rcx, aVectorTooLong; "vector too long"
0x18001482f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
