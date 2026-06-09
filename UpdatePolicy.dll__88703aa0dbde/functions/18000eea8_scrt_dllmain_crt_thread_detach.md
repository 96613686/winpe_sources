# __scrt_dllmain_crt_thread_detach

- ea: `0x18000eea8`
- end: `0x18000eebd`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f1e0`

## callees

- `0x180010cb4`
- `0x180015314`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _scrt_stub_for_acrt_uninitialize_critical();
  _vcrt_thread_detach();
  return 1;
}

```

## disassembly

```asm
0x18000eea8  sub     rsp, 28h
0x18000eeac  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000eeb1  call    __vcrt_thread_detach
0x18000eeb6  mov     al, 1
0x18000eeb8  add     rsp, 28h
0x18000eebc  retn
```
