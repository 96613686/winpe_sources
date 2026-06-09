# __scrt_dllmain_crt_thread_detach

- ea: `0x180009a38`
- end: `0x180009a4d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800094e0`

## callees

- `0x18000af24`

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
0x180009a38  sub     rsp, 28h
0x180009a3c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009a41  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009a46  mov     al, 1
0x180009a48  add     rsp, 28h
0x180009a4c  retn
```
