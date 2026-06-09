# __scrt_dllmain_crt_thread_detach

- ea: `0x180003c14`
- end: `0x180003c29`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003f80`

## callees

- `0x1800049bc`

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
0x180003c14  sub     rsp, 28h
0x180003c18  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003c1d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003c22  mov     al, 1
0x180003c24  add     rsp, 28h
0x180003c28  retn
```
