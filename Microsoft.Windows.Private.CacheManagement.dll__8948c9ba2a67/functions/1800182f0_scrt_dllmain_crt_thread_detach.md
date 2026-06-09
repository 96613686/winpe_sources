# __scrt_dllmain_crt_thread_detach

- ea: `0x1800182f0`
- end: `0x180018305`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800185d0`

## callees

- `0x180019cfc`
- `0x18001c79c`

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
0x1800182f0  sub     rsp, 28h
0x1800182f4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800182f9  call    __vcrt_thread_detach
0x1800182fe  mov     al, 1
0x180018300  add     rsp, 28h
0x180018304  retn
```
