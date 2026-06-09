# __scrt_dllmain_crt_thread_detach

- ea: `0x180001654`
- end: `0x180001669`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001d8c`

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
0x180001654  sub     rsp, 28h
0x180001658  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000165d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001662  mov     al, 1
0x180001664  add     rsp, 28h
0x180001668  retn
```
