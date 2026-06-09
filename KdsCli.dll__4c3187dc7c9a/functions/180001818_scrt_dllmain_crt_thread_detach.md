# __scrt_dllmain_crt_thread_detach

- ea: `0x180001818`
- end: `0x18000182d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800012c0`

## callees

- `0x180002870`

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
0x180001818  sub     rsp, 28h
0x18000181c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001821  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001826  mov     al, 1
0x180001828  add     rsp, 28h
0x18000182c  retn
```
