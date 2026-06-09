# __scrt_dllmain_uninitialize_critical

- ea: `0x18000ef64`
- end: `0x18000ef78`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f350`

## callees

- `0x180010cec`
- `0x180015314`

## pseudocode

```c
__vcrt_bool _scrt_dllmain_uninitialize_critical()
{
  _scrt_stub_for_acrt_uninitialize_critical(0);
  return _vcrt_uninitialize_critical();
}

```

## disassembly

```asm
0x18000ef64  sub     rsp, 28h
0x18000ef68  xor     ecx, ecx
0x18000ef6a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000ef6f  add     rsp, 28h
0x18000ef73  jmp     __vcrt_uninitialize_critical
```
