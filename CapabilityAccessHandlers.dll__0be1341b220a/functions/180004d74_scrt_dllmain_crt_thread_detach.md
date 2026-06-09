# __scrt_dllmain_crt_thread_detach

- ea: `0x180004d74`
- end: `0x180004d89`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004900`

## callees

- `0x1800057f0`

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
0x180004d74  sub     rsp, 28h
0x180004d78  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004d7d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004d82  mov     al, 1
0x180004d84  add     rsp, 28h
0x180004d88  retn
```
