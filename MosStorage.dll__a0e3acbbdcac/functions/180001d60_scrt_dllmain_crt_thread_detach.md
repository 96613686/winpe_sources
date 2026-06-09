# __scrt_dllmain_crt_thread_detach

- ea: `0x180001d60`
- end: `0x180001d75`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001900`

## callees

- `0x180002eac`

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
0x180001d60  sub     rsp, 28h
0x180001d64  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d69  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d6e  mov     al, 1
0x180001d70  add     rsp, 28h
0x180001d74  retn
```
