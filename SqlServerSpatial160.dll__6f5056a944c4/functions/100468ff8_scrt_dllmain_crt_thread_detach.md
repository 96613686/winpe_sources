# __scrt_dllmain_crt_thread_detach

- ea: `0x100468ff8`
- end: `0x10046900d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100468bb4`

## callees

- `0x1004698f0`

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
0x100468ff8  sub     rsp, 28h
0x100468ffc  call    __scrt_stub_for_acrt_uninitialize_critical
0x100469001  call    __scrt_stub_for_acrt_uninitialize_critical
0x100469006  mov     al, 1
0x100469008  add     rsp, 28h
0x10046900c  retn
```
