# __scrt_dllmain_crt_thread_detach

- ea: `0x1800015e8`
- end: `0x1800015fd`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x180001d1c`

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
0x1800015e8  sub     rsp, 28h
0x1800015ec  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015f1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015f6  mov     al, 1
0x1800015f8  add     rsp, 28h
0x1800015fc  retn
```
