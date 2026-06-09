# __scrt_dllmain_crt_thread_detach

- ea: `0x180001788`
- end: `0x18000179d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800012f0`

## callees

- `0x1800022ac`

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
0x180001788  sub     rsp, 28h
0x18000178c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001791  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001796  mov     al, 1
0x180001798  add     rsp, 28h
0x18000179c  retn
```
