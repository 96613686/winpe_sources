# __scrt_dllmain_uninitialize_critical

- ea: `0x180001704`
- end: `0x180001718`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001228`

## callees

- `0x180001d24`

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
0x180001704  sub     rsp, 28h
0x180001708  xor     ecx, ecx
0x18000170a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000170f  add     rsp, 28h
0x180001713  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
