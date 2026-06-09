# __imp_load_CreateWindowStationW

- ea: `0x1800095d4`
- end: `0x1800095e0`
- name: `__imp_load_CreateWindowStationW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009555`

## import_xrefs

- `ext-ms-win-ntuser-windowstation-l1-1-0!CreateWindowStationW` at `0x1800095d4`

## pseudocode

```c
__int64 load_CreateWindowStationW()
{
  return _tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800095d4  lea     rax, __imp_CreateWindowStationW
0x1800095db  jmp     __tailMerge_ext_ms_win_ntuser_windowstation_l1_1_0_dll
```
