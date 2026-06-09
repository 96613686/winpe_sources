# __scrt_dllmain_uninitialize_critical

- ea: `0x1800016dc`
- end: `0x1800016f0`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011e8`

## callees

- `0x180001fcc`

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
0x1800016dc  sub     rsp, 28h
0x1800016e0  xor     ecx, ecx
0x1800016e2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016e7  add     rsp, 28h
0x1800016eb  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
