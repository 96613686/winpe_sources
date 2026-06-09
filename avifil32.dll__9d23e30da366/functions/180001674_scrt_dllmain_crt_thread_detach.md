# __scrt_dllmain_crt_thread_detach

- ea: `0x180001674`
- end: `0x180001689`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001d6c`

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
0x180001674  sub     rsp, 28h
0x180001678  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000167d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001682  mov     al, 1
0x180001684  add     rsp, 28h
0x180001688  retn
```
