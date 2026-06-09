# __scrt_dllmain_crt_thread_detach

- ea: `0x180002800`
- end: `0x180002815`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800022e0`

## callees

- `0x180003444`

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
0x180002800  sub     rsp, 28h
0x180002804  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002809  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000280e  mov     al, 1
0x180002810  add     rsp, 28h
0x180002814  retn
```
