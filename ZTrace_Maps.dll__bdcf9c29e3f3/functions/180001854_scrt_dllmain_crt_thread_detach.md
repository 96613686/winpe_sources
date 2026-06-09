# __scrt_dllmain_crt_thread_detach

- ea: `0x180001854`
- end: `0x180001869`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800013b0`

## callees

- `0x18000232c`

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
0x180001854  sub     rsp, 28h
0x180001858  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000185d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001862  mov     al, 1
0x180001864  add     rsp, 28h
0x180001868  retn
```
