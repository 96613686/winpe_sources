# __scrt_dllmain_uninitialize_critical

- ea: `0x180009954`
- end: `0x180009968`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800095b8`

## callees

- `0x18000b030`

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
0x180009954  sub     rsp, 28h
0x180009958  xor     ecx, ecx
0x18000995a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000995f  add     rsp, 28h
0x180009963  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
