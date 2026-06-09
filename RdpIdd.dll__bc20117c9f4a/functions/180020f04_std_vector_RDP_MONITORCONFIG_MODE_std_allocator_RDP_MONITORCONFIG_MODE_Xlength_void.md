# std::vector<_RDP_MONITORCONFIG_MODE,std::allocator<_RDP_MONITORCONFIG_MODE>>::_Xlength(void)

- ea: `0x180020f04`
- end: `0x180020f1c`
- name: `?_Xlength@?$vector@U_RDP_MONITORCONFIG_MODE@@V?$allocator@U_RDP_MONITORCONFIG_MODE@@@std@@@std@@CAXXZ`
- size: `24`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180012de4`
- `0x180012f34`
- `0x180013c70`
- `0x180013d14`
- `0x180021b50`
- `0x180021c8c`
- `0x180022fe0`
- `0x180023174`
- `0x18002971c`
- `0x1800319e0`
- `0x180031e74`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180020f0f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180020f0f`

## pseudocode

```c
void __noreturn std::vector<_RDP_MONITORCONFIG_MODE>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180020f04  sub     rsp, 28h
0x180020f08  lea     rcx, aVectorTooLong; "vector too long"
0x180020f0f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
