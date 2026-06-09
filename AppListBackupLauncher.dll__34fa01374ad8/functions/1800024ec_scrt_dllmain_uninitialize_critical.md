# __scrt_dllmain_uninitialize_critical

- ea: `0x1800024ec`
- end: `0x180002500`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800020e8`

## callees

- `0x180002ed0`

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
0x1800024ec  sub     rsp, 28h
0x1800024f0  xor     ecx, ecx
0x1800024f2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800024f7  add     rsp, 28h
0x1800024fb  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
