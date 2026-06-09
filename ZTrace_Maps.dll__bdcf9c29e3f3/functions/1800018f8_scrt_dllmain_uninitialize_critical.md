# __scrt_dllmain_uninitialize_critical

- ea: `0x1800018f8`
- end: `0x18000190c`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001508`

## callees

- `0x18000232c`

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
0x1800018f8  sub     rsp, 28h
0x1800018fc  xor     ecx, ecx
0x1800018fe  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001903  add     rsp, 28h
0x180001907  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
