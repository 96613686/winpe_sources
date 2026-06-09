# __scrt_get_dyn_tls_init_callback

- ea: `0x1800018e4`
- end: `0x1800018ec`
- name: `__scrt_get_dyn_tls_init_callback`
- size: `8`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001148`

## pseudocode

```c
__int64 *_scrt_get_dyn_tls_init_callback()
{
  return &_dyn_tls_init_callback;
}

```

## disassembly

```asm
0x1800018e4  lea     rax, __dyn_tls_init_callback
0x1800018eb  retn
```
