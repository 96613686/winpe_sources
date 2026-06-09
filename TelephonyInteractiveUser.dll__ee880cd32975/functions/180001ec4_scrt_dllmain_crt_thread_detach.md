# __scrt_dllmain_crt_thread_detach

- ea: `0x180001ec4`
- end: `0x180001ed9`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001a50`

## callees

- `0x180011680`

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
0x180001ec4  sub     rsp, 28h
0x180001ec8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001ecd  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001ed2  mov     al, 1
0x180001ed4  add     rsp, 28h
0x180001ed8  retn
```
