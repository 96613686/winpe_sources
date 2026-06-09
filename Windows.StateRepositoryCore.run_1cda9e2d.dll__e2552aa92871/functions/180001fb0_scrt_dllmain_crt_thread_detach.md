# __scrt_dllmain_crt_thread_detach

- ea: `0x180001fb0`
- end: `0x180001fc5`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001b60`

## callees

- `0x180002c08`

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
0x180001fb0  sub     rsp, 28h
0x180001fb4  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001fb9  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001fbe  mov     al, 1
0x180001fc0  add     rsp, 28h
0x180001fc4  retn
```
