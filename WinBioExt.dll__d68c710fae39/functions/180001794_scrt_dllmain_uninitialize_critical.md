# __scrt_dllmain_uninitialize_critical

- ea: `0x180001794`
- end: `0x1800017a8`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800013f8`

## callees

- `0x1800023bc`

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
0x180001794  sub     rsp, 28h
0x180001798  xor     ecx, ecx
0x18000179a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000179f  add     rsp, 28h
0x1800017a3  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
