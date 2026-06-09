# __scrt_dllmain_uninitialize_critical

- ea: `0x1800020e4`
- end: `0x1800020f8`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001cc8`

## callees

- `0x1800029c4`

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
0x1800020e4  sub     rsp, 28h
0x1800020e8  xor     ecx, ecx
0x1800020ea  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800020ef  add     rsp, 28h
0x1800020f3  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
