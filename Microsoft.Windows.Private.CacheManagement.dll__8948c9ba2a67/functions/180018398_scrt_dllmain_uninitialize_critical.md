# __scrt_dllmain_uninitialize_critical

- ea: `0x180018398`
- end: `0x1800183ac`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__vcrt_bool()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180018738`

## callees

- `0x180019d28`
- `0x18001c79c`

## pseudocode

```c
__vcrt_bool _scrt_dllmain_uninitialize_critical()
{
  _scrt_stub_for_acrt_uninitialize_critical(0);
  return _vcrt_uninitialize_critical();
}

```

## disassembly

```asm
0x180018398  sub     rsp, 28h
0x18001839c  xor     ecx, ecx
0x18001839e  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800183a3  add     rsp, 28h
0x1800183a7  jmp     __vcrt_uninitialize_critical
```
