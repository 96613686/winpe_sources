# __imp_load_AuthzAccessCheck

- ea: `0x18000a600`
- end: `0x18000a60c`
- name: `__imp_load_AuthzAccessCheck`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000a581`

## import_xrefs

- `AUTHZ!AuthzAccessCheck` at `0x18000a600`

## pseudocode

```c
__int64 load_AuthzAccessCheck()
{
  return _tailMerge_authz_dll();
}

```

## disassembly

```asm
0x18000a600  lea     rax, __imp_AuthzAccessCheck
0x18000a607  jmp     __tailMerge_authz_dll
```
