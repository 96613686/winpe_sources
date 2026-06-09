# __scrt_dllmain_uninitialize_critical

- ea: `0x1800018bc`
- end: `0x1800018d0`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001418`

## callees

- `0x180002870`

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
0x1800018bc  sub     rsp, 28h
0x1800018c0  xor     ecx, ecx
0x1800018c2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018c7  add     rsp, 28h
0x1800018cb  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
