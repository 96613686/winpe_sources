# __scrt_dllmain_crt_thread_detach

- ea: `0x180001758`
- end: `0x18000176d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001f68`

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
0x180001758  sub     rsp, 28h
0x18000175c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001761  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001766  mov     al, 1
0x180001768  add     rsp, 28h
0x18000176c  retn
```
