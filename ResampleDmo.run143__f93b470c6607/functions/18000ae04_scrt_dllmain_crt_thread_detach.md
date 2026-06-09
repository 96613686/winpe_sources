# __scrt_dllmain_crt_thread_detach

- ea: `0x18000ae04`
- end: `0x18000ae19`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a820`

## callees

- `0x18006ade4`

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
0x18000ae04  sub     rsp, 28h
0x18000ae08  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000ae0d  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000ae12  mov     al, 1
0x18000ae14  add     rsp, 28h
0x18000ae18  retn
```
