# __scrt_dllmain_crt_thread_detach

- ea: `0x18000165c`
- end: `0x180001671`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x180001f80`

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
0x18000165c  sub     rsp, 28h
0x180001660  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001665  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000166a  mov     al, 1
0x18000166c  add     rsp, 28h
0x180001670  retn
```
