# __imp_load_D2D1CreateFactory

- ea: `0x180004564`
- end: `0x180004570`
- name: `__imp_load_D2D1CreateFactory`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800044e5`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x180004564`

## pseudocode

```c
__int64 load_D2D1CreateFactory()
{
  return _tailMerge_d2d1_dll();
}

```

## disassembly

```asm
0x180004564  lea     rax, __imp_D2D1CreateFactory
0x18000456b  jmp     __tailMerge_d2d1_dll
```
