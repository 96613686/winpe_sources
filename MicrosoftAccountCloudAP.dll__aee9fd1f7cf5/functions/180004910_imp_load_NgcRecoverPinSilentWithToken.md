# __imp_load_NgcRecoverPinSilentWithToken

- ea: `0x180004910`
- end: `0x18000491c`
- name: `__imp_load_NgcRecoverPinSilentWithToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004891`

## import_xrefs

- `ngcrecovery!NgcRecoverPinSilentWithToken` at `0x180004910`

## pseudocode

```c
__int64 load_NgcRecoverPinSilentWithToken()
{
  return _tailMerge_ngcrecovery_dll();
}

```

## disassembly

```asm
0x180004910  lea     rax, __imp_NgcRecoverPinSilentWithToken
0x180004917  jmp     __tailMerge_ngcrecovery_dll
```
