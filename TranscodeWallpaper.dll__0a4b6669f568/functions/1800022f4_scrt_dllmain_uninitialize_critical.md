# __scrt_dllmain_uninitialize_critical

- ea: `0x1800022f4`
- end: `0x180002308`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001f58`

## callees

- `0x180002dfc`

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
0x1800022f4  sub     rsp, 28h
0x1800022f8  xor     ecx, ecx
0x1800022fa  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800022ff  add     rsp, 28h
0x180002303  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
