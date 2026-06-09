# __scrt_dllmain_crt_thread_detach

- ea: `0x1800022e0`
- end: `0x1800022f5`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001e90`

## callees

- `0x180002ff4`

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
0x1800022e0  sub     rsp, 28h
0x1800022e4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800022e9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800022ee  mov     al, 1
0x1800022f0  add     rsp, 28h
0x1800022f4  retn
```
