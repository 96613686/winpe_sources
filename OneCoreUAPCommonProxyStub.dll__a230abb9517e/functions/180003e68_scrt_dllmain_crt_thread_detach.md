# __scrt_dllmain_crt_thread_detach

- ea: `0x180003e68`
- end: `0x180003e7d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003910`

## callees

- `0x1800058e0`

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
0x180003e68  sub     rsp, 28h
0x180003e6c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003e71  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003e76  mov     al, 1
0x180003e78  add     rsp, 28h
0x180003e7c  retn
```
