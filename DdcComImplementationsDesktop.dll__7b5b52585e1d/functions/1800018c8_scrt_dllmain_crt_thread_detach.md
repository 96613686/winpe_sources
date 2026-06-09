# __scrt_dllmain_crt_thread_detach

- ea: `0x1800018c8`
- end: `0x1800018dd`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001330`

## callees

- `0x1800022b0`

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
0x1800018c8  sub     rsp, 28h
0x1800018cc  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018d1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018d6  mov     al, 1
0x1800018d8  add     rsp, 28h
0x1800018dc  retn
```
