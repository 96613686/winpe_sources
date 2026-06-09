# __scrt_dllmain_crt_thread_detach

- ea: `0x180002250`
- end: `0x180002265`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001e00`

## callees

- `0x180002dfc`

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
0x180002250  sub     rsp, 28h
0x180002254  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002259  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000225e  mov     al, 1
0x180002260  add     rsp, 28h
0x180002264  retn
```
