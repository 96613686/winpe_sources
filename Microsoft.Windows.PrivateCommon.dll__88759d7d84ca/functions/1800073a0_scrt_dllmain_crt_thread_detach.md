# __scrt_dllmain_crt_thread_detach

- ea: `0x1800073a0`
- end: `0x1800073b5`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800076a0`

## callees

- `0x180008c00`
- `0x18000b834`

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
0x1800073a0  sub     rsp, 28h
0x1800073a4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800073a9  call    __vcrt_thread_detach
0x1800073ae  mov     al, 1
0x1800073b0  add     rsp, 28h
0x1800073b4  retn
```
