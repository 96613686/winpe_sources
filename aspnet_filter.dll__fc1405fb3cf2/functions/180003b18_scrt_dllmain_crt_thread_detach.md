# __scrt_dllmain_crt_thread_detach

- ea: `0x180003b18`
- end: `0x180003b2d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003290`

## callees

- `0x180004390`

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
0x180003b18  sub     rsp, 28h
0x180003b1c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003b21  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003b26  mov     al, 1
0x180003b28  add     rsp, 28h
0x180003b2c  retn
```
