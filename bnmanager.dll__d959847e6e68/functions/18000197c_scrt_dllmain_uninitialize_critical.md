# __scrt_dllmain_uninitialize_critical

- ea: `0x18000197c`
- end: `0x180001990`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800015a8`

## callees

- `0x180002344`

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
0x18000197c  sub     rsp, 28h
0x180001980  xor     ecx, ecx
0x180001982  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001987  add     rsp, 28h
0x18000198b  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
