# __scrt_dllmain_crt_thread_detach

- ea: `0x180001714`
- end: `0x180001729`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011b0`

## callees

- `0x18000209c`

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
0x180001714  sub     rsp, 28h
0x180001718  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000171d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001722  mov     al, 1
0x180001724  add     rsp, 28h
0x180001728  retn
```
