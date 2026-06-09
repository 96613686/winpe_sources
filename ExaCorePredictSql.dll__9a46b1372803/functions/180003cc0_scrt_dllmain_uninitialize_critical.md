# __scrt_dllmain_uninitialize_critical

- ea: `0x180003cc0`
- end: `0x180003cd4`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800040fc`

## callees

- `0x1800049bc`

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
0x180003cc0  sub     rsp, 28h
0x180003cc4  xor     ecx, ecx
0x180003cc6  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003ccb  add     rsp, 28h
0x180003ccf  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
