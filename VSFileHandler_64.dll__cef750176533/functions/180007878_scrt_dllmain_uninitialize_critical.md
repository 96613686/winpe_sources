# __scrt_dllmain_uninitialize_critical

- ea: `0x180007878`
- end: `0x18000788c`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__vcrt_bool()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800074f8`

## callees

- `0x1800092ec`
- `0x18000e72c`

## pseudocode

```c
__vcrt_bool _scrt_dllmain_uninitialize_critical()
{
  _acrt_uninitialize_critical(0);
  return _vcrt_uninitialize_critical();
}

```

## disassembly

```asm
0x180007878  sub     rsp, 28h
0x18000787c  xor     ecx, ecx; Terminating
0x18000787e  call    __acrt_uninitialize_critical
0x180007883  add     rsp, 28h
0x180007887  jmp     __vcrt_uninitialize_critical
```
