# __scrt_dllmain_uninitialize_critical

- ea: `0x180009adc`
- end: `0x180009af0`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009638`

## callees

- `0x18000af24`

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
0x180009adc  sub     rsp, 28h
0x180009ae0  xor     ecx, ecx
0x180009ae2  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009ae7  add     rsp, 28h
0x180009aeb  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
