# __scrt_dllmain_uninitialize_critical

- ea: `0x180021cc8`
- end: `0x180021cdc`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180021818`

## callees

- `0x180022724`

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
0x180021cc8  sub     rsp, 28h
0x180021ccc  xor     ecx, ecx
0x180021cce  call    __scrt_stub_for_acrt_uninitialize_critical
0x180021cd3  add     rsp, 28h
0x180021cd7  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
