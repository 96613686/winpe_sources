# __scrt_dllmain_crt_thread_detach

- ea: `0x180002630`
- end: `0x180002645`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800021d0`

## callees

- `0x18000321c`

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
0x180002630  sub     rsp, 28h
0x180002634  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002639  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000263e  mov     al, 1
0x180002640  add     rsp, 28h
0x180002644  retn
```
