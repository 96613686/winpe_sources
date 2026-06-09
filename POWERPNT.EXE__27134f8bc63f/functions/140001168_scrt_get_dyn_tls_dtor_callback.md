# __scrt_get_dyn_tls_dtor_callback

- ea: `0x140001168`
- end: `0x140001170`
- name: `__scrt_get_dyn_tls_dtor_callback`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001ac0`

## pseudocode

```c
__int64 *_scrt_get_dyn_tls_dtor_callback()
{
  return &_dyn_tls_dtor_callback;
}

```

## disassembly

```asm
0x140001168  lea     rax, __dyn_tls_dtor_callback
0x14000116f  retn
```
