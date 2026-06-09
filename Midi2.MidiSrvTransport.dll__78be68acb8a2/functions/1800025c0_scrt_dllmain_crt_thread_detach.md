# __scrt_dllmain_crt_thread_detach

- ea: `0x1800025c0`
- end: `0x1800025d5`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800020f0`

## callees

- `0x180003088`

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
0x1800025c0  sub     rsp, 28h
0x1800025c4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800025c9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800025ce  mov     al, 1
0x1800025d0  add     rsp, 28h
0x1800025d4  retn
```
