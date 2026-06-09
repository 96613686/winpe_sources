# __scrt_dllmain_uninitialize_critical

- ea: `0x180001b3c`
- end: `0x180001b50`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001698`

## callees

- `0x180002394`

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
0x180001b3c  sub     rsp, 28h
0x180001b40  xor     ecx, ecx
0x180001b42  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001b47  add     rsp, 28h
0x180001b4b  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
