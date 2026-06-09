# __scrt_dllmain_uninitialize_critical

- ea: `0x180007448`
- end: `0x18000745c`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__vcrt_bool()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007808`

## callees

- `0x180008c2c`
- `0x18000b834`

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
0x180007448  sub     rsp, 28h
0x18000744c  xor     ecx, ecx
0x18000744e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180007453  add     rsp, 28h
0x180007457  jmp     __vcrt_uninitialize_critical
```
