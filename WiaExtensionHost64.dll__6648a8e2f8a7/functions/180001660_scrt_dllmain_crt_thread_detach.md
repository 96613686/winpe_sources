# __scrt_dllmain_crt_thread_detach

- ea: `0x180001660`
- end: `0x180001675`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800010d0`

## callees

- `0x180001d24`

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
0x180001660  sub     rsp, 28h
0x180001664  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001669  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000166e  mov     al, 1
0x180001670  add     rsp, 28h
0x180001674  retn
```
