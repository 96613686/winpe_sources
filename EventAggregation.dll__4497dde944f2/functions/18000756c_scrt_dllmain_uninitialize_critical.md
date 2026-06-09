# __scrt_dllmain_uninitialize_critical

- ea: `0x18000756c`
- end: `0x180007580`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800070c8`

## callees

- `0x180007bf8`

## pseudocode

```c
__int64 _scrt_dllmain_uninitialize_critical()
{
  __int64 v0; // rcx

  _scrt_stub_for_acrt_uninitialize_critical(0);
  return _scrt_stub_for_acrt_uninitialize_critical(v0);
}

```

## disassembly

```asm
0x18000756c  sub     rsp, 28h
0x180007570  xor     ecx, ecx
0x180007572  call    __scrt_stub_for_acrt_uninitialize_critical
0x180007577  add     rsp, 28h
0x18000757b  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
