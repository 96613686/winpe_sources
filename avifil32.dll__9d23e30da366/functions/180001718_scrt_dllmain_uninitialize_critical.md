# __scrt_dllmain_uninitialize_critical

- ea: `0x180001718`
- end: `0x18000172c`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001248`

## callees

- `0x180001d6c`

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
0x180001718  sub     rsp, 28h
0x18000171c  xor     ecx, ecx
0x18000171e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001723  add     rsp, 28h
0x180001727  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
