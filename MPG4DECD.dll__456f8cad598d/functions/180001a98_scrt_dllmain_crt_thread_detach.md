# __scrt_dllmain_crt_thread_detach

- ea: `0x180001a98`
- end: `0x180001aad`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001540`

## callees

- `0x180002394`

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
0x180001a98  sub     rsp, 28h
0x180001a9c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001aa1  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001aa6  mov     al, 1
0x180001aa8  add     rsp, 28h
0x180001aac  retn
```
