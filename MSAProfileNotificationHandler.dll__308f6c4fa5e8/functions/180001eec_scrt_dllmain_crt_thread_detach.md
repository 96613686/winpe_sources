# __scrt_dllmain_crt_thread_detach

- ea: `0x180001eec`
- end: `0x180001f01`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001940`

## callees

- `0x18000295c`

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
0x180001eec  sub     rsp, 28h
0x180001ef0  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001ef5  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001efa  mov     al, 1
0x180001efc  add     rsp, 28h
0x180001f00  retn
```
