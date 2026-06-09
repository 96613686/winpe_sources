# __scrt_dllmain_crt_thread_detach

- ea: `0x180001e2c`
- end: `0x180001e41`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800019d0`

## callees

- `0x18000a120`

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
0x180001e2c  sub     rsp, 28h
0x180001e30  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e35  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e3a  mov     al, 1
0x180001e3c  add     rsp, 28h
0x180001e40  retn
```
