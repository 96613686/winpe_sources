# __scrt_dllmain_crt_thread_detach

- ea: `0x180003780`
- end: `0x180003795`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003330`

## callees

- `0x18000438c`

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
0x180003780  sub     rsp, 28h
0x180003784  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003789  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000378e  mov     al, 1
0x180003790  add     rsp, 28h
0x180003794  retn
```
