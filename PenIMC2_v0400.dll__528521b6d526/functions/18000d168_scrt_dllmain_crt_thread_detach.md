# __scrt_dllmain_crt_thread_detach

- ea: `0x18000d168`
- end: `0x18000d17d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d730`

## callees

- `0x18000e318`

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
0x18000d168  sub     rsp, 28h
0x18000d16c  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000d171  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000d176  mov     al, 1
0x18000d178  add     rsp, 28h
0x18000d17c  retn
```
