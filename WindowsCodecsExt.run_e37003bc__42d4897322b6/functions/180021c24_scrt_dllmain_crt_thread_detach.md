# __scrt_dllmain_crt_thread_detach

- ea: `0x180021c24`
- end: `0x180021c39`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800216c0`

## callees

- `0x180022724`

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
0x180021c24  sub     rsp, 28h
0x180021c28  call    __scrt_stub_for_acrt_uninitialize_critical
0x180021c2d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180021c32  mov     al, 1
0x180021c34  add     rsp, 28h
0x180021c38  retn
```
