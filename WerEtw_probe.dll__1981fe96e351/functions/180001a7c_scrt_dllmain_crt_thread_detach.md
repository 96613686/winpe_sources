# __scrt_dllmain_crt_thread_detach

- ea: `0x180001a7c`
- end: `0x180001a91`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800014f0`

## callees

- `0x1800028c0`

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
0x180001a7c  sub     rsp, 28h
0x180001a80  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a85  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a8a  mov     al, 1
0x180001a8c  add     rsp, 28h
0x180001a90  retn
```
