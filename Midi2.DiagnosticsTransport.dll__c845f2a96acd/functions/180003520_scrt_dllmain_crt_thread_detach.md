# __scrt_dllmain_crt_thread_detach

- ea: `0x180003520`
- end: `0x180003535`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003050`

## callees

- `0x1800041e8`

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
0x180003520  sub     rsp, 28h
0x180003524  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003529  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000352e  mov     al, 1
0x180003530  add     rsp, 28h
0x180003534  retn
```
