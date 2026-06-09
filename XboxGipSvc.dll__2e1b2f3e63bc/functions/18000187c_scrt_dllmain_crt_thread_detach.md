# __scrt_dllmain_crt_thread_detach

- ea: `0x18000187c`
- end: `0x180001891`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001350`

## callees

- `0x1800023ac`

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
0x18000187c  sub     rsp, 28h
0x180001880  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001885  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000188a  mov     al, 1
0x18000188c  add     rsp, 28h
0x180001890  retn
```
