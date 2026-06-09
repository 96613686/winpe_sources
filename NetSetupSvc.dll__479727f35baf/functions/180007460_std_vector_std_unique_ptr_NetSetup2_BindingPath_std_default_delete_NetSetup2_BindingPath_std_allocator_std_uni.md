# std::vector<std::unique_ptr<NetSetup2::BindingPath,std::default_delete<NetSetup2::BindingPath>>,std::allocator<std::unique_ptr<NetSetup2::BindingPath,std::default_delete<NetSetup2::BindingPath>>>>::_Xlength(void)

- ea: `0x180007460`
- end: `0x180007472`
- name: `?_Xlength@?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `21`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180006e90`
- `0x180008478`
- `0x18000e950`
- `0x18000ea48`
- `0x18000f8cc`
- `0x180011c44`
- `0x18001797c`
- `0x18001bd44`
- `0x18001be84`
- `0x18001c4b8`
- `0x1800253c0`
- `0x18002656c`
- `0x1800267a8`
- `0x180028b44`
- `0x18002a6c4`
- `0x18002a838`
- `0x18002a8d4`
- `0x18002aa2c`
- `0x18002ab78`
- `0x18002acc4`
- `0x18002b0cc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000746b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000746b`

## pseudocode

```c
void __noreturn std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180007460  sub     rsp, 28h
0x180007464  lea     rcx, aVectorTooLong; "vector too long"
0x18000746b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
