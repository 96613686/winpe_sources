# __imp_load_SLOpen

- ea: `0x14000259f`
- end: `0x1400025ab`
- name: `__imp_load_SLOpen`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400024fc`

## import_xrefs

- `ext-ms-win-security-slc-l1-1-0!SLOpen` at `0x14000259f`

## pseudocode

```c
__int64 load_SLOpen()
{
  return _tailMerge_ext_ms_win_security_slc_l1_1_0_dll();
}

```

## disassembly

```asm
0x14000259f  lea     rax, __imp_SLOpen
0x1400025a6  jmp     __tailMerge_ext_ms_win_security_slc_l1_1_0_dll
```
