# __imp_load_GetWindowThreadProcessId

- ea: `0x1800033ef`
- end: `0x1800033fb`
- name: `__imp_load_GetWindowThreadProcessId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000333a`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x1800033ef`

## pseudocode

```c
__int64 load_GetWindowThreadProcessId()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x1800033ef  lea     rax, __imp_GetWindowThreadProcessId
0x1800033f6  jmp     __tailMerge_user32_dll
```
