# __imp_load_SLGetInstalledProductKeyIds

- ea: `0x180001d3d`
- end: `0x180001d49`
- name: `__imp_load_SLGetInstalledProductKeyIds`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180001c76`

## import_xrefs

- `sppc!SLGetInstalledProductKeyIds` at `0x180001d3d`

## pseudocode

```c
__int64 load_SLGetInstalledProductKeyIds()
{
  return _tailMerge_sppc_dll();
}

```

## disassembly

```asm
0x180001d3d  lea     rax, __imp_SLGetInstalledProductKeyIds
0x180001d44  jmp     __tailMerge_sppc_dll
```
