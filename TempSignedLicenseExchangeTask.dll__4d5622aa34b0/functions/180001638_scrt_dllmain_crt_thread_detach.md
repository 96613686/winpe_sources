# __scrt_dllmain_crt_thread_detach

- ea: `0x180001638`
- end: `0x18000164d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x180001fcc`

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
0x180001638  sub     rsp, 28h
0x18000163c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001641  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001646  mov     al, 1
0x180001648  add     rsp, 28h
0x18000164c  retn
```
