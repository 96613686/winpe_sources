# __scrt_dllmain_crt_thread_detach

- ea: `0x180002ca0`
- end: `0x180002cb5`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002850`

## callees

- `0x1800037ec`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _scrt_stub_for_acrt_uninitialize_critical();
  _scrt_stub_for_acrt_uninitialize_critical();
  return 1;
}

```

## disassembly

```asm
0x180002ca0  sub     rsp, 28h
0x180002ca4  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002ca9  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002cae  mov     al, 1
0x180002cb0  add     rsp, 28h
0x180002cb4  retn
```
