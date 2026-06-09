# __scrt_dllmain_crt_thread_detach

- ea: `0x180001750`
- end: `0x180001765`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800012b0`

## callees

- `0x180002160`

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
0x180001750  sub     rsp, 28h
0x180001754  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001759  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000175e  mov     al, 1
0x180001760  add     rsp, 28h
0x180001764  retn
```
