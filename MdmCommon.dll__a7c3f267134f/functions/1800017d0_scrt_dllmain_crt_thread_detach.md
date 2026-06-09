# __scrt_dllmain_crt_thread_detach

- ea: `0x1800017d0`
- end: `0x1800017e5`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011b0`

## callees

- `0x180002684`

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
0x1800017d0  sub     rsp, 28h
0x1800017d4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017d9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017de  mov     al, 1
0x1800017e0  add     rsp, 28h
0x1800017e4  retn
```
