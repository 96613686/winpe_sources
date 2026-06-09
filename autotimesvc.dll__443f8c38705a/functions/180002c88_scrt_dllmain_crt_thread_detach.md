# __scrt_dllmain_crt_thread_detach

- ea: `0x180002c88`
- end: `0x180002c9d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002700`

## callees

- `0x1800037e0`

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
0x180002c88  sub     rsp, 28h
0x180002c8c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002c91  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002c96  mov     al, 1
0x180002c98  add     rsp, 28h
0x180002c9c  retn
```
