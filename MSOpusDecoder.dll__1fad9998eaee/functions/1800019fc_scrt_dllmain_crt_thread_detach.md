# __scrt_dllmain_crt_thread_detach

- ea: `0x1800019fc`
- end: `0x180001a11`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001580`

## callees

- `0x18001b03c`

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
0x1800019fc  sub     rsp, 28h
0x180001a00  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a05  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a0a  mov     al, 1
0x180001a0c  add     rsp, 28h
0x180001a10  retn
```
