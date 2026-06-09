# __scrt_dllmain_uninitialize_critical

- ea: `0x1800028a4`
- end: `0x1800028b8`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002438`

## callees

- `0x180003444`

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
0x1800028a4  sub     rsp, 28h
0x1800028a8  xor     ecx, ecx
0x1800028aa  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800028af  add     rsp, 28h
0x1800028b3  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
