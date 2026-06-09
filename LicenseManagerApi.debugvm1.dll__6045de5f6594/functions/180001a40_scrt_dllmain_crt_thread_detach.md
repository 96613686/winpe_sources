# __scrt_dllmain_crt_thread_detach

- ea: `0x180001a40`
- end: `0x180001a55`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800015f0`

## callees

- `0x1800029ec`

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
0x180001a40  sub     rsp, 28h
0x180001a44  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a49  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001a4e  mov     al, 1
0x180001a50  add     rsp, 28h
0x180001a54  retn
```
