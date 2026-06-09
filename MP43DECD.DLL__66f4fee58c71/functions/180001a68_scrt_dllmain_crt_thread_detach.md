# __scrt_dllmain_crt_thread_detach

- ea: `0x180001a68`
- end: `0x180001a7d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001510`

## callees

- `0x1800022d8`

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
0x180001a68  sub     rsp, 28h
0x180001a6c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a71  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a76  mov     al, 1
0x180001a78  add     rsp, 28h
0x180001a7c  retn
```
