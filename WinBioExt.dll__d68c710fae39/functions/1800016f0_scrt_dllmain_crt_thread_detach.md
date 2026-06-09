# __scrt_dllmain_crt_thread_detach

- ea: `0x1800016f0`
- end: `0x180001705`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800012a0`

## callees

- `0x1800023bc`

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
0x1800016f0  sub     rsp, 28h
0x1800016f4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016f9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016fe  mov     al, 1
0x180001700  add     rsp, 28h
0x180001704  retn
```
