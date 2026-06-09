# __scrt_dllmain_uninitialize_critical

- ea: `0x18000d210`
- end: `0x18000d224`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d898`

## callees

- `0x18000e318`

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
0x18000d210  sub     rsp, 28h
0x18000d214  xor     ecx, ecx
0x18000d216  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000d21b  add     rsp, 28h
0x18000d21f  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
