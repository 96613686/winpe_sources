# __scrt_dllmain_crt_thread_detach

- ea: `0x18000ec50`
- end: `0x18000ec65`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e800`

## callees

- `0x18000f920`

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
0x18000ec50  sub     rsp, 28h
0x18000ec54  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000ec59  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000ec5e  mov     al, 1
0x18000ec60  add     rsp, 28h
0x18000ec64  retn
```
