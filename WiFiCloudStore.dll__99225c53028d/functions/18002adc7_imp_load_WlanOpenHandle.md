# __imp_load_WlanOpenHandle

- ea: `0x18002adc7`
- end: `0x18002add3`
- name: `__imp_load_WlanOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002abfd`

## import_xrefs

- `wlanapi!WlanOpenHandle` at `0x18002adc7`

## pseudocode

```c
__int64 load_WlanOpenHandle()
{
  return _tailMerge_wlanapi_dll();
}

```

## disassembly

```asm
0x18002adc7  lea     rax, __imp_WlanOpenHandle
0x18002adce  jmp     __tailMerge_wlanapi_dll
```
