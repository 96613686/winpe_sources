# __imp_load_NdrDllCanUnloadNow

- ea: `0x180001eee`
- end: `0x180001efa`
- name: `__imp_load_NdrDllCanUnloadNow`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001dd6`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180001eee`

## pseudocode

```c
__int64 load_NdrDllCanUnloadNow()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180001eee  lea     rax, __imp_NdrDllCanUnloadNow
0x180001ef5  jmp     __tailMerge_rpcrt4_dll
```
