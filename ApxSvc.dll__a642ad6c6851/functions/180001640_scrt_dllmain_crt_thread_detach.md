# __scrt_dllmain_crt_thread_detach

- ea: `0x180001640`
- end: `0x180001655`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011e0`

## callees

- `0x18000219c`

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
0x180001640  sub     rsp, 28h
0x180001644  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001649  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000164e  mov     al, 1
0x180001650  add     rsp, 28h
0x180001654  retn
```
