# __scrt_dllmain_uninitialize_critical

- ea: `0x18000a268`
- end: `0x18000a27c`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009d98`

## callees

- `0x18000afd4`

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
0x18000a268  sub     rsp, 28h
0x18000a26c  xor     ecx, ecx
0x18000a26e  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000a273  add     rsp, 28h
0x18000a277  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
